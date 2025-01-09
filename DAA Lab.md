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