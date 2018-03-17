#include<stdio.h>

int main()
{
    int n, i, j, k;
    scanf("%d", &n);
    float d=1, a[100][100], c;
    for(i=0;i<n;i++)
    {
        for(j=0;j<n;j++)
        {
            scanf("%f", &a[i][j]);
        }
    }
    for(i=1;i<n;i++)
    {
        for(j=0;j<i;j++)
        {
            for(k=0,c=a[i][j]/a[j][j];k<n;k++)
            {
                a[i][k]-=c*a[j][k];
            }
        }
    }
    for(i=0;i<n;i++)
    {
        d*=a[i][i];
    }
    printf("%.0f", d);
}
