#include<stdio.h>
#include<stdlib.h>
#include<sys/io.h>
#include<unistd.h>

int main(int argc,int *argv[])
{
  unsigned char data;
  iopl(3); //linux 权限获取
  data=inb(0x61);//读取IO地址0x61
  printf("data=%#x\n",data);
  outb(0x03,0x61); //打开蜂鸣器
  printf("data=%#x\n",inb(0x61));
  printf();
  iopl(0);
  
  return 0;
}
