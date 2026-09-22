# Ex20 Sorting an Array using Merge Sort Algorithm
## DATE: 20.07.2026
## AIM:
To design a program that sorts a given array of integers in ascending order without using built-in sorting functions, achieving O(n log n) time complexity and minimal space usage.
## Algorithm
1. Import the libraries.
2. Intialize an array with the values give by user.
3. Define a method mergeSort() to split the given array until there is only one element in each.
4. Define another method merge() to sort the array while merging each divided part.
5. Display the result.

## Program:
```
/*
Program to sort a given array of integers in ascending order without using built-in sorting functions
Name: Ashqar Ahamed S T
RegisterNumber: 212224240018
*/

import java.util.*;

public class Main {


    static void merge(int[] arr, int left, int mid, int right) {

        int n1 = mid - left + 1;
        int n2 = right - mid;

        int[] L = new int[n1];
        int[] R = new int[n2];


        for (int i = 0; i < n1; i++) {
            L[i] = arr[left + i];
        }

        for (int j = 0; j < n2; j++) {
            R[j] = arr[mid + 1 + j];
        }

        int i = 0;
        int j = 0;
        int k = left;


        while (i < n1 && j < n2) {

            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }

            k++;
        }

        // Copy remaining elements from L
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }

        // Copy remaining elements from R
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }


    static void mergeSort(int[] arr, int left, int right) {

        
        if (left >= right) {
            return;
        }

        int mid = left + (right - left) / 2;

        
        mergeSort(arr, left, mid);

        
        mergeSort(arr, mid + 1, right);

        
        merge(arr, left, mid, right);
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();

        int[] arr = new int[n];

        System.out.println("Enter elements:");

        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        // Merge Sort
        mergeSort(arr, 0, n - 1);

        System.out.println("Sorted array:");

        for (int i = 0; i < n; i++) {
            System.out.print(arr[i] + " ");
        }

        sc.close();
    }
}
```

## Output:

<img width="743" height="270" alt="output Day5" src="https://github.com/user-attachments/assets/29ef3a37-ecee-4fd5-8714-a6115a795db2" />


## Result:
The program has been successfully implemented and executed.
It sorts the given array of integers in ascending order using the Merge Sort algorithm with a time complexity of O(n log n) and minimal extra space.
