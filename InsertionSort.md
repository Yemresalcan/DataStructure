# [23,27,16,2,18,6] => Insertion Sort
Aşamaları:

### Yukarıda verilen dizinin sort türüne göre aşamalarını yazınız.
Başlangıç: [22,27,16,2,18,6]   
<hr>
1.aşama: [2,27,16,22,18,6]      En küçük eleman olan 2 ile ilk eleman olan 22 yi yer değiştiriyoruz 
<hr>
2.aşama: [2,6,16,22,18,27]      Sonra yine en küçük eleman olan 6 ile  2.sırada olan 27 yi yer değiştiriyoruz 
<hr>
3.aşama: [2,6,16,18,22,27]      Tekrardan en küçük eleman olana bakıyoruz 16 yerinde zaten 18 e geçiyoruz 18 ile 22 yi yer değiştiriyoruz böylece sıralama bitmiş oluyor 
<hr>

### Big-O gösterimini yazınız.
 her yer değiştirme n-1 şeklinde ileriliyor o yüzden toplam  n*(n+1)/2 bu da (n^2 + n) / 2 oluyor Big-O gösteriminde n^2 ifadesi tek alınıyor baskın olduğundan gösterimi de O(n^2) şeklindedir 

### Dizi sıralandıktan sonra 18 sayısı hangi case kapsamına girer? Yazınız.
Time Complexity: 
Average case: Aradığımız sayının ortada olması,
Worst case: Aradığımız sayının sonda olması, 
Best case: Aradığımız sayının dizinin en başında olması. 

18 sayısı sayı dizisinde tam ortada yer aldığından dolayı averge case kapsamına girer. 

### [7,3,5,8,2,9,4,15,6] dizisinin Insertion Sort'a göre ilk 4 adımını yazınız.
Başlangıç: [7,3,5,8,2,9,4,15,6]

1.aşama: [2,3,5,8,7,9,4,15,6]
<hr>
2.aşama: [2,3,4,8,7,9,5,15,6]
<hr>
3.aşama: [2,3,4,5,7,9,8,15,6]
<hr>
4.aşama: [2,3,4,5,6,9,8,15,7]

<hr>

## Insertion Sort C code

```C

#include <math.h>
#include <stdio.h>
  

void insertionSort(int arr[], int n)
{
    int i, key, j;
    for (i = 1; i < n; i++) {
        key = arr[i];
        j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;
    }
}
  

void printArray(int arr[], int n)
{
    int i;
    for (i = 0; i < n; i++)
        printf("%d ", arr[i]);
    printf("\n");
}

int main()
{
    int arr[] = {22,27,16,2,18,6};
    int n = sizeof(arr) / sizeof(arr[0]);
  
    insertionSort(arr, n);
    printArray(arr, n);
  
    return 0;
}
```


output: [2,6,16,18,22,27]

[Patika.dev](https://www.patika.dev/tr)