#include <stdio.h>
#include<string.h>
#define MAXLINE 1000
int prv(char mass[], int begin, int end);
main()
{
	char str[MAXLINE];
	int l,F,i,pos,k,N;
	printf("write a string:\n");
	memset(str,'\0',MAXLINE);
	gets(str);
	printf("write N:\n");
	scanf("%d",&N);
	for (i=0,l=0;i<MAXLINE;++i,l++)
	{
		if(str[i]=='\0')
			break;
	}
	F=0;
		for(i = 0; i <= l; i++)
	{
		if(str[i]==' '|| str[i]=='.' || str[i]==',' || str[i]=='\t' || i==l)
		{
				k = (prv(str,pos,i)==0 && ((i-pos) > N) && F==1 ) ? ++k : k;
			F = 0;
		}
		else if (F==0)
		{
			F = 1;
			pos=i;
		}
	}
	 printf("quantity is:%d\n",k);
	return 0;
}
int prv(char str[], int begin, int end)
{
	int F,i;
	F=0;
	for (i=begin; i < end; i++)
	{
		if ((str[i]<'A' || str[i]>'Z') && (str[i]<'a' || str[i]>'z'))
			F=1;
	}
	return F;
}

