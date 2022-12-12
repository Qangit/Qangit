#include<stdio.h>
#include<string.h>
int main()
{
	char str[100];
	
	gets_s(str);
	int last = strlen(str);
	int frontindex = 0, backindex = last - 1;
	for (int i = 0; i < last; i++)
	{
		int panduan1 = str[i] >= 'a' && str[i] <= 'z';
		int panduan2 = str[i] >= 'A' && str[i] <= 'Z';
		if ((panduan1 || panduan2 == 1) || str[i] == '*')
		{
			;
		}
		else
		{
			printf("error\n");
			return -1;
		}

	}
	while (1)
	{
		int panduan1 = str[frontindex] >= 'a' && str[frontindex] <= 'z';
		int panduan2 = str[frontindex] >= 'A' && str[frontindex] <= 'Z';
		if (panduan1 || panduan2 == 1)
		{
			break;
		}
		else
		{
			frontindex++;
		}
	}
	while (1)
	{
		int panduan1 = str[backindex] >= 'a' && str[backindex] <= 'z';
		int panduan2 = str[backindex] >= 'A' && str[backindex] <= 'Z';
		if (panduan1 || panduan2 == 1)
		{
			break;
		}
		else
		{
			backindex--;
		}
		if (backindex == 0)
		{
			backindex = last - 1;
			break;
		}
	}
	for (int i = 0; i < frontindex; i++)
	{
		if (str[i] == '*')
	
			printf("%c",str[i]);

	}
	for (int i = frontindex; i <= backindex; i++)
	{
		int panduan1 = str[i] >= 'a' && str[i] <= 'z';
		int panduan2 = str[i] >= 'A' && str[i] <= 'Z';
		if (str[i] == '*')
		{
			;

		}
		else if (panduan1 || panduan2 == 1)
		{
			printf("%c", str[i]);
		}
	

	}
	for (int i = backindex+1; i < last; i++)
	{
		if (str[i] == '*')
		{
			printf("%c", str[i]);

		}
	
	}
	printf("\n");
	return 0;

}
