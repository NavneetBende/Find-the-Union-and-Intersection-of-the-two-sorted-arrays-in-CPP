Union and Interaction of the two sorted arrays in C++
Here, in this page we will discuss the program to find the union and interaction of two sorted arrays in C++ . We are given with two sorted arrays and we have to find the union and interaction of the given two arrays.

Union and Interaction of the two sorted arrays in C++
Algorithm to find Union :
Use two index variables i and j, initial values i = 0, j = 0
If arr1[i] is smaller than arr2[j] then print arr1[i] and increment i.
If arr1[i] is greater than arr2[j] then print arr2[j] and increment j. 
If both are same then print any of them and increment both i and j.
Print remaining elements of the larger array.
Algorithm to find Interaction :
Use two index variables i and j, initial values i = 0, j = 0.
If arr1[i] is smaller than arr2[j] then increment i.
If arr1[i] is greater than arr2[j] then increment j.
If both are same then print any of them and increment both i and j.
Union and Intersection in C++
Code to find Union and Interaction of the two sorted arrays in C++
#include <bits/stdc++.h>
using namespace std;

/* Function prints union of arr1[] and arr2[]
m is the number of elements in arr1[]
n is the number of elements in arr2[] */
void printUnion(int arr1[], int arr2[], int m, int n)
{
   int i = 0, j = 0;
   while (i < m && j < n) {
     if (arr1[i] < arr2[j])
      cout << arr1[i++] << " ";

     else if (arr2[j] < arr1[i])
       cout << arr2[j++] << " ";

     else {
       cout << arr2[j++] << " ";
       i++;
     }
  }

  /* Print remaining elements of the larger array */
  while (i < m)
   cout << arr1[i++] << " ";

  while (j < n)
   cout << arr2[j++] << " ";
}

void printIntersection(int arr1[], int arr2[], int m, int n)
{
   int i = 0, j = 0;
   while (i < m && j < n) {
    if (arr1[i] < arr2[j])
      i++;
    else if (arr2[j] < arr1[i])
      j++;
    else /* if arr1[i] == arr2[j] */
    {
       cout << arr2[j] << " "; 
       i++; 
       j++; 
     } 
 } 
} 
/* Driver program to test above function */ 
   int main()
 { 
    int m, n; 
    cin>>m;

   int arr1[m];

   for(int i=0; i<m; i++) 
    cin>>arr1[i];

   cin>>n;

   int arr2[n];

   for(int i=0; i<n; i++) cin>>arr2[i];

   // Function calling
   cout<<"Union : ";
   printUnion(arr1, arr2, m, n);


   cout<<"\nInteraction ";
   printIntersection(arr1, arr2, m, n);

   return 0;
}
Output
5

1 2 3 4 5

4

1 2 3 4

Union : 1 2 3 4 5

Intersection : 1 2 3 4
