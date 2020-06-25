#include<stdio.h>
int main(void) 
{
	char b[10];
	char w[10];
	int b1[10];
	int w1[10]; 
	int i,t,j,rb,rw;
	int m=0; 
	int n=0; 
    scanf("Black: `%c%c %c%c %c%c %c%c %c%c` White: `%c%c %c%c %c%c %c%c %c%c`",&b[0],&b[5],&b[1],&b[6],&b[2],&b[7],&b[3],&b[8],&b[4],&b[9],&w[0],&w[5],&w[1],&w[6],&w[2],&w[7],&w[3],&w[8],&w[4],&w[9]);
	for(i=0;i<5;i++)
    {
    	if(b[i]=='A')       b1[i]=14;
    	else if(b[i]=='J')  b1[i]=11;
    	else if(b[i]=='Q')  b1[i]=12;
    	else if(b[i]=='K')  b1[i]=13;
    	else if(b[i]=='T')  b1[i]=10;
    	else                b1[i]=b[i]-'0';
	}
		for(i=0;i<5;i++)
    {
    	if(w[i]=='A')       w1[i]=14;
    	else if(w[i]=='J')  w1[i]=11;
    	else if(w[i]=='Q')  w1[i]=12;
    	else if(w[i]=='K')  w1[i]=13;
    	else if(w[i]=='T')  w1[i]=10;
    	else                w1[i]=w[i]-'0';
	}
	for(i=0;i<5;i++)
	{
		for(j=i+1;j<5;j++)
		{
			if(b1[j]<b1[i])
			{
				t=b1[j];  b1[j]=b1[i]; b1[i]=t;
			}
			if(w1[j]<w1[i])
			{
				t=w1[j];  w1[j]=w1[i]; w1[i]=t;
			}
		}
	}
	t=0;
	for(i=5;i<9;i++)
	{
	    if(b[i]!=b[i+1])   t=1;
	}
	if(t==0) m=5;
	t=0;
	for(i=0;i<4;i++)
	{
		j=b1[i+1]-b1[i];
		if(j!=1) t=1;
	}
	if(t==0&&m==5) m=6;
	if(t!=0&&m==5) m=5;
	if(t==0&&m!=5) m=4;
	if(m==0)
	{
		t=1;
		for(i=0;i<3;i++)
		{
			if(b1[i]==b1[i+1]&&b1[i]==b1[i+2]) {t=0; rb=b1[i];}
		}
		if(t==0) m=3;
	}
	if(m==0)
	{
		t=1;
		if(b1[0]==b1[1])
		{
			if(b1[2]==b1[3]||b1[3]==b1[4]) {t=0;rb=b1[3];}
		}
		if(b1[1]==b1[2])
		{
			if(b1[3]=b1[4]) {t=0;rb=b1[3];}
		}
		if(t==0) m=2;
	}
	if(m==0)
	{
		t=1;
		for(i=0;i<4;i++)
		{
			if(b1[i]==b1[i+1])  {t=0; rb=b1[i];}
			if(t==0) m=1;
		}
	}
	t=0;
	for(i=5;i<9;i++)
	{
	    if(w[i]!=w[i+1])   t=1;
	}
	if(t==0) n=5;
	t=0;
	for(i=0;i<4;i++)
	{
		j=w1[i+1]-w1[i];
		if(j!=1) t=1;
	}
	if(t==0&&n==5) n=6;
	if(t!=0&&n==5) n=5;
	if(t==0&&n!=5) n=4;
	if(n==0)
	{
		t=1;
		for(i=0;i<3;i++)
		{
			if(w1[i]==w1[i+1]&&w1[i]==w1[i+2]) {t=0; rw=w1[i];}
		}
		if(t==0) n=3;
	}
	if(n==0)
	{
		t=1;
		if(w1[0]==w1[1])
		{
			if(w1[2]==w1[3]||w1[3]==w1[4]) {t=0;rw=w1[3];}
		}
		if(w1[1]==w1[2])
		{
			if(w1[3]=w1[4]) {t=0;rw=w1[3]; }
		}
		if(t==0) n=2;
	}
	if(n==0)
	{
		t=1;
		for(i=0;i<4;i++)
		{
			if(w1[i]==w1[i+1])  {t=0;rw=w1[i];}
			if(t==0) n=1;
		}
	}
	if(m>n) printf("Black wins");
	if(m<n) printf("White wins");
	if(m==n&&m==0)
	{
		t=0;
		for(i=4;i>0;i--)
		{
			if(b1[i]>w1[i])      {printf("Black wins");break;}
			else if(b1[i]<w1[i]) {printf("White wins");break;}
			else t++;
		}
		if(t==5) printf("Tie");
	}
	if(m==n&&m==1)
	{
	   	if(rb>rw) printf("Black wins");
		if(rb<rw) printf("White wins");
		if(rb=rw) printf("Tie");
	}
	if(m==n&&m==2)
	{
		if(rb>rw) printf("Black wins");
		if(rb<rw) printf("White wins");
		if(rb=rw) printf("Tie");
	}
	if(m==n&&m==3)
	{
		if(rb>rw) printf("Black wins");
		if(rb<rw) printf("White wins");
		if(rb=rw) printf("Tie");
	}
	if(m==n&&m==4)
	{
		if(b1[4]>w1[4]) printf("Black wins");
		if(b1[4]<w1[4]) printf("White wins");
		if(b1[4]==w1[4]) printf("Tie");
	}
	if(m==n&&m==5)
	{
		t=0;
		for(i=4;i>0;i--)
		{
			if(b1[i]>w1[i])      {printf("Black wins");break;}
			else if(b1[i]<w1[i]) {printf("White wins");break;}
			else t++;
		}
		if(t==5) printf("Tie");
	}
	if(m==n&&m==6)
	{
		if(b1[4]>w1[4]) printf("Black wins");
		if(b1[4]<w1[4]) printf("White wins");
		if(b1[4]==w1[4]) printf("Tie");
	}
    return 0; 
}