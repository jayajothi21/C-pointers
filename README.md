# C-pointers
Pointers program 

1.Swap to number using pointers
#include <stdio.h>

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x, y;
    printf("Enter two integers: ");
    scanf("%d %d", &x, &y);

  printf("Before swapping: x = %d, y = %d\n", x, y);
    swap(&x, &y);
    printf("After swapping: x = %d, y = %d\n", x, y);
    return 0;
}
output:
Enter two integers: 10 20
Before swapping: x = 10, y = 20
After swapping: x = 20, y = 10
------------------------------------------------------------------
2.Reverse an array
#include <stdio.h>

int main() {
    int arr[100], n, i, temp;
    int *start, *end;

   printf("Enter number of elements: ");
   scanf("%d", &n);
    printf("Enter %d elements: ", n);
    for (i = 0; i < n; i++)
        scanf("%d", &arr[i]);

  start = arr;
    end = arr + n - 1;
    while (start < end) {
        temp = *start;
        *start = *end;
        *end = temp;
        start++;
        end--;
    }

  printf("Reversed array: ");
    for (i = 0; i < n; i++)
        printf("%d ", *(arr + i));
    printf("\n");
    return 0;
}

output:
Enter number of elements: 5
Enter 5 elements: 1 2 3 4 5
Reversed array: 5 4 3 2 1
--------------------------------------------------+-------------------------------
3.Maximum and minimum 

#include <stdio.h>

int main() {
    int arr[100], n, i;
    int *ptr, *max, *min;

   printf("Enter number of elements: ");
    scanf("%d", &n);
    printf("Enter %d elements: ", n);
    for (i = 0; i < n; i++)
        scanf("%d", arr + i);
    ptr = arr;
    max = min = arr;
    for (i = 1; i < n; i++) {
        if (*(ptr + i) > *max)
            max = ptr + i;
        if (*(ptr + i) < *min)
            min = ptr + i;
    }

  printf("Maximum element = %d\n", *max);
    printf("Minimum element = %d\n", *min);
    return 0;
}



output:
Enter number of elements: 5
Enter 5 elements: 12 45 7 89 23
Maximum element = 89
Minimum element = 7

