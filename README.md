# pattern
#include <stdio.h>
void drawpat(char draw[])
{
    int j,line = 0,k = 0;
   printf("Draw the pattern\n");
    for(j = 0;j<=8;j++)
    {
      line ++;
      printf(" %c  ",draw[j]);
      if(line == 3)
      {
          printf("\n");
          //printf("(%d) (%d) (%d) \n",j-1,j,j+1);
          line = 0;
      }
    }
    //printf("Save:0\n");
}

void main()
{
  int pattern[3][3];
  int *p,sum = 0,choice = 1;
  p = &pattern[0][0];
  char draw[9]={"123456789"};
  while(choice!=0)
  {
    //system("clear");
    drawpat(draw);
    scanf("%d",&choice);
    draw[choice-1] = '$';
    if(choice!=0)
    sum += *(p+choice-1);
  }
  printf("Sum of patter is %d\n",sum);
}
