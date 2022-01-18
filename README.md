#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>

#define N 9
void main()
{
    int num[N], index, i, temp, max, R;
    int middlenums = N / 3;
    printf("please enter an amount of numbers that can be devided by 3\n");

    for (index = 0; index < N; index++)
    {
        scanf("%d", &num[index]);
    }

    printf("\n");

    for (i = 0; i < middlenums; i++)
    {
        temp = num[i];
        num[i] = num[i + (2 * middlenums)];
        num[i + (2 * middlenums)] = temp;
    }

    for (i = 0; i < N; i++)
    {
        printf("%d", num[i]);
    }

    printf("\n");

    //(R = middlenums;R < middlenums*2;R++) 3-6
    //(i = 0;i >= middlenums;i++) 0-3
    // (num[middlenums + i] >= num[R])

    for (R = middlenums;R < middlenums * 2;R++)
    {
        for (i = 0;i >= middlenums;i++)
        {
            if (num[middlenums + i] >= num[R])
            {
                max = num[middlenums + i];
                printf("max %d", &max);
            }
        }
    }

    printf("\n max number in the middle part is %d", &max);

    system("pause");
}
