#include <iostream>
#include <string.h>
#include <conio.h>
#include <stdio.h>
#include <stdlib.h>
int max(int a, int b);
int result( char *X, char *Y, int m, int n )
{
   int L[250][250];
      int i , j ;
   for (i=0; i<=m; i++)
   {
     for (j=0; j<=n; j++)
     {
       if (i == 0 || j == 0)
         L[i][j] = 0;

       else if(X[i-1] == Y[j-1])
         L[i][j] = L[i-1][j-1] + 1;

       else
         L[i][j] = max(L[i-1][j], L[i][j-1]);
     }
   }

   return L[m][n];
}
void print_lcs(char b[][20],char x[],int i,int j)
{
     if(i==0 || j==0)
      return;
     if(b[i][j]=='c')
      {
       print_lcs(b,x,i-1,j-1);
       cout<<x[i-1];
       }
      else if(b[i][j]=='u')
       print_lcs(b,x,i-1,j);
      else
       print_lcs(b,x,i,j-1);
}
void lcs_length(char x[],char y[])
{
     int m,n,i,j,c[20][20];
     char b[20][20];
     m=strlen(x);
     n=strlen(y);
     for(i=0;i<=m;i++)
      c[i][0]=0;
     for(i=0;i<=n;i++)
      c[0][i]=0;
     for(i=1;i<=m;i++)
      for(j=1;j<=n;j++)
      {
	if(x[i-1]==y[j-1])
	 {
	   c[i][j]=c[i-1][j-1]+1;
	   b[i][j]='c';         	   }
	 else if(c[i-1][j]>=c[i][j-1])
	 {
	      c[i][j]=c[i-1][j];
	      b[i][j]='u';
	      }
	 else
	 {
	     c[i][j]=c[i][j-1];
	     b[i][j]='l';
	     }
	}
    print_lcs(b,x,m,n);
 }
void lcs()
{
     int i,j;

     char x[20],y[20];
     cout<<"first : ";
     gets(x);
     cout<<"second : ";
     gets(y);
     int s=strlen(x);
     int v=strlen(y);
     cout<<endl<<"lenght of string for answer is : "<<result( x, y, s, v ) <<endl;
     cout<<"result is : "<<endl ;
     lcs_length(x,y);
     cout<<endl ;
     lcs_length(y,x);

 }
int main()
{
     lcs();
     getch() ;
}
int max(int a, int b)
{
    return (a > b)? a : b;
}
