# fourth_task

counting
#include <bits/stdc++.h>
using namespace std;
 
void countSort(vector<int>& arr) {
	int max = *max_element(arr.begin(), arr.end());
	int min = *min_element(arr.begin(), arr.end());
	int range = max - min + 1;
 
	vector<int> count(range), output(arr.size());
	for (int i = 0; i < arr.size(); i++)
		count[arr[i] - min]++;
 
	for (int i = 1; i < count.size(); i++)
		count[i] += count[i - 1];
 
	for (int i = arr.size() - 1; i >= 0; i--) {
		output[count[arr[i] - min] - 1] = arr[i];
		count[arr[i] - min]--;
	}
 
	for (int i = 0; i < arr.size(); i++)
		arr[i] = output[i];
}
 
void printArray(vector<int>& arr) {
	for (int i = 0; i < arr.size(); i++)
		cout << arr[i] << " ";
	cout << "\n";
}
 
int main() {
	vector<int> arr = { -5, -10, 0, -3, 8, 5, -1, 10 };
	countSort(arr);
	printArray(arr);
	return 0;
}
 

selection
#include <bits/stdc++.h>
using namespace std;
 
void swap(int *xp, int *yp) {
	int temp = *xp;
	*xp = *yp;
	*yp = temp;
}
 
void selectionSort(int arr[], int n) {
	int i, j, min_idx;
	for (i = 0; i < n-1; i++) {
		min_idx = i;
		for (j = i+1; j < n; j++)
		if (arr[j] < arr[min_idx])
			min_idx = j;
		swap(&arr[min_idx], &arr[i]);
	}
}
 
void printArray(int arr[], int size) {
	int i;
	for (i=0; i < size; i++)
		cout << arr[i] << " ";
	cout << endl;
}
 
int main() {
	int arr[] = {64, 25, 12, 22, 11};
	int n = sizeof(arr)/sizeof(arr[0]);
	selectionSort(arr, n);
	cout << "Sorted array: \n";
	printArray(arr, n);
	return 0;
}
bubble 
#include <iostream>
using namespace std;
 
void swap(int *xp, int *yp) {
	int temp = *xp;
	*xp = *yp;
	*yp = temp;
}
 
void bubbleSort(int arr[], int n) {
	bool swapped;
	for (int i = 0; i < n-1; i++) {
		swapped = false;
		for (int j = 0; j < n-i-1; j++) {
			if (arr[j] > arr[j+1]) {
			swap(&arr[j], &arr[j+1]);
			swapped = true;
			}
		}
		if (!swapped)
			break;
	}
}
 
void printArray(int arr[], int size) {
	int i;
	for (i=0; i < size; i++)
		cout << arr[i] << " ";
	cout << endl;
}
 
int main() {
	int arr[] = {64, 34, 25, 12, 22, 11, 90};
	int n = sizeof(arr)/sizeof(arr[0]);
	bubbleSort(arr, n);
	printArray(arr, n);
	return 0;
}
 
