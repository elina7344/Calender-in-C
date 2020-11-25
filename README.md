#include <stdio.h>
#include <stdlib.h>

int get_1st_weekday(int year)
{
    int day;
    day = (((year - 1) * 365) + ((year - 1) / 4) - ((year - 1) / 100) + ((year) / 400) + 1) % 7;
    return day;
}
int main()
{
system("Color 03F");
int year,i,j,k,m=0,n;
printf("\nEnter the year YYYY:");
scanf("%d",&year);
char *month[]={"JANUARY","FEBRUARY","MARCH","APRIL","MAY","JUNE","JULY","AUGUST","SEPTEMBER","OCTOBER","NOVEMBER","DECEMBER"};
int day[]={31,28,31,30,31,30,31,31,30,31,30,31};

if((year%4==0 && year%100!=0) || year%400==0)
    day[1]=29;

    n=get_1st_weekday(year);

for(i=0;i<12;i++)
{
    k=day[i];
    printf("\n\n~~~~~~~~~~~~~~~~%s~~~~~~~~~~~~~~~~~\n",month[i]);
printf("\n  Sun  Mon  Tue  Wed  Thu  Fri  Sat\n");

for(n=0;n<m;n++)

printf("     ");

for(j=1;j<=k;j++)
{
    printf("%5d",j);

    if(++m>6)
    {
         printf("\n");
         m=0;
    }

}
n=m;
}
}
