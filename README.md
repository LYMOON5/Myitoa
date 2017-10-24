#include<stdio.h>

//数字转化为字符串
char *Myitoa(char *str,int num)
{
	int a[100];
	int count=0; 

	while(num!=0)
	{
		a[count++]=num%10;   
		num/=10;
	}

	int i;
	int j;
	for(i=0;i<count/2;i++)  
	{
		int tmp;
		tmp=a[i];
		a[i]=a[count-i-1];
		a[count-i-1]=tmp;
	}

	char *p=str;
	for(j=0;j<count;j++)  
	{
		*str=a[j]+'0';
		str++;
	}
	return p;
}

int main()
{
  char ch[100]="";
	printf("%s\n",Myitoa(ch,1234));//数字转换成字符串测试用例
	printf("%s\n",Myitoa(ch,56789));//数字转换成字符串测试用例
  
  return 0;
}
