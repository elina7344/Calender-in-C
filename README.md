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
system("Color 05F");
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
if(year % 400 == 0)
{

printf("\n\n%d is a Leap Year",year);
}
else if (year % 100 == 0)
{
    printf("\n\n%d is not a Leap Year.",year);
}
else if(year % 4 == 0)
{
    printf("\n\n%d is a Leap Year.",year);
}
else
{
 printf("\n\n%d is not a Leap Year.",year);
}
if(year % 400 == 0)
{

printf("\n\nThere are 366 days in the year %d",year);
}
else if (year % 100 == 0)
{
    printf("\n\nThere are 365 days in the year %d",year);
}
else if(year % 4 == 0)
{
    printf("\n\nThere are 366 days in the year %d",year);
}
else
{
 printf("\n\nThere are 365 days in the year %d",year);
}

//Zeller Algorithm//
//Zeller’s congruence is an algorithm devised by Christian Zeller//
//It is used to calculate the day of the week for any Gregorian calendar date//
 int h,q,s,t,u,D,M,Y;
  printf("\n\nTo find the particular day on the date please enter(dd/mm/yyyy)\n");
  scanf("%i/%i/%i",&D,&M,&Y);
  if(M == 1)
  {
    M = 13;
    Y--;
  }
  if (M == 2)
  {
    M = 14;
    Y--;
  }
  q = D;
  s = M;
  t = Y % 100;
  u = Y / 100;
  h = q + floor(13/5*(s+1)) + t + floor(t/4) +  floor(u/4) + 5 * u;
  h = h % 7;
  switch(h)
  {
    case 0 : printf("\nThe day is : Saturday \n");
break;
    case 1 : printf("\nThe day is : Sunday \n");
break;
    case 2 : printf("\nThe day is : Monday \n");
break;
    case 3 : printf("\nThe day is : Tuesday \n");
break;
    case 4 : printf("\nThe day is : Wednesday \n");
break;
    case 5 : printf("\nThe day is : Thursday \n");
break;
    case 6 : printf("\nThe day is : Friday \n");
break;
  }
return 0;
}

return 0;

}
