# include <stdio.h>
int main(void)
{
    int i, j;  //循环变量
    int MinIndex;  //保存最小的值的下标
    int buf;  //互换数据时的临时变量
    int a[] = {5, 5, 3, 7, 4, 2, 5, 4, 9, 1, 8, 6};
    int n = sizeof(a) / sizeof(a[0]);  //存放数组a中元素的个数
    for (i=0; i<n-1; ++i)  //n个数比较n-1轮
    {
        MinIndex = i;
        for (j=i+1; j<n; ++j)  //每轮比较n-1-i次, 找本轮最小数的下标
        {
            if (a[MinIndex] > a[j])
            {
                MinIndex = j;  //保存小的数的下标
            }
        }
        if (MinIndex != i)  /*找到最小数之后如果它的下标不是i则说明它不在最左边, 则互换位置*/
        {
            buf = a[MinIndex];
            a[MinIndex] = a[i];
            a[i] = buf;
        }
    }
    printf("最终排序结果为:\n");
    for (i=0; i<12; ++i)
    {
        printf("%d ", a[i]);
    }
    printf("\n");
    return 0;
}