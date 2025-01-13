### Linear Search
##### Algorithm:
```Algorithm
Input n
Enter the key element
Enter the whole array
Perform the array traversal to find the key element
for (i=1; i<n; i++)
	for (i=1; i<=n; i++)
		if (A(i) = key) {
			printf(“successful”);
			}
		else {
	printf(“unsuccessful);
```

##### Program
```C
#include <stdio.h>
int linearSearch(int arr[], int size, int target) {
	for (int i = 0; i < size; i++) {
		if (arr[i] == target) {
		return i;
		}
	}
	return -1;
}

int main() {
	int n, target;
	printf("Enter the number of elements in the array: ");
	scanf("%d", &n);
	int arr[n];
	printf("Enter %d elements:\n", n);
	for (int i = 0; i < n; i++) {
		scanf("%d", &arr[i]);
	}
	printf("Enter the element to search for: ");
	scanf("%d", &target);
	int result = linearSearch(arr, n, target);
	if (result != -1) {
		printf("Element found at index %d\n", result);
	} else {
	printf("Element not found in the array\n");
	}
return 0;
}
```


### Binary Search
```
mid = floor[(l+h)/2]
if (A[mid] = key) {
	printf("Successful");
}
elif (A[mid] > key) {
	h = mid - 1
	call binary search function}
}
else {
l = mid + 1
}
```

### Bubble Sort
create a bubble number (index 0) and compare with the adjacent number (index 1). depending on program, check whether the next number is larger or smaller than the bubble number. when bubble number < next number, the bubble passes to the next number, else when bubble number > next number, their places get swapped. This iteration continues until the whole array is sorted into descending or ascending order

```Pseudocode
for (i = 0; i < n; i++) {
	for (j = 0; j < n - 1 - i; j++) {
		if (a[j]) > a[j + 1]) {
			temp = a[j];
			a[j] = a[j + 1];
			a[j + 1] = temp;
			c++
			}
	}
	if (c = -0)
}
```

