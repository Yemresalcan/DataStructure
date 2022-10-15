# [16,21,11,8,12,22]
Yukarıdaki dizinin sort türüne göre aşamalarını yazınız.

                 [16,21,11,8,12,22]

        [16,21,11]                     [8,12,22]   

      [16,21] [11]                  [8,12]   [22]

    [16]  [21]  [11]                [8]  [12]  [22]

      [16]  [11,21]                   [8,12]  [22]
    
        [11,16,21]                      [8,12,22]
         
                  [8,11,12,16,21,22]
<hr>
### Big-O gösterimini yazınız.

2^x = n eleman bazlı ilerleme olduğu için => logn=x Kadar bu işlemi gerçekleştiriyoruz her işlemde o(n) kere işlem yapılıyor toplarsak en sonunda Big-O şeklinde olmuş olur => O(nlogn)

<hr>

[Patika.dev](https://www.patika.dev/tr)


## Merge Sort C code

```C
#include <stdio.h>
#include <stdlib.h>
 
void merge(int arr[], int l, int m, int r)
{
    int i, j, k;
    int n1 = m - l + 1;
    int n2 = r - m;
 
    
    int L[n1], R[n2];
 

    for (i = 0; i < n1; i++)
        L[i] = arr[l + i];
    for (j = 0; j < n2; j++)
        R[j] = arr[m + 1 + j];
 
    i = 0; 
    j = 0; 
    k = l; 
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) {
            arr[k] = L[i];
            i++;
        }
        else {
            arr[k] = R[j];
            j++;
        }
        k++;
    }
 
    
    while (i < n1) {
        arr[k] = L[i];
        i++;
        k++;
    }
 
    
    while (j < n2) {
        arr[k] = R[j];
        j++;
        k++;
    }
}
 

void mergeSort(int arr[], int l, int r)
{
    if (l < r) {
       
        int m = l + (r - l) / 2;
 
        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);
 
        merge(arr, l, m, r);
    }
}
 

void printArray(int A[], int size)
{
    int i;
    for (i = 0; i < size; i++)
        printf("%d ", A[i]);
    printf("\n");
}
 

int main()
{
    int arr[] = {16,21,11,8,12,22 };
    int arr_size = sizeof(arr) / sizeof(arr[0]);
 
    printf("Given array is \n");
    printArray(arr, arr_size);
 
    mergeSort(arr, 0, arr_size - 1);
 
    printf("\nSorted array is \n");
    printArray(arr, arr_size);
    return 0;
}

```
output: [8,11,12,16,21,22]