#include <stdio.h>
#include <limits.h>

int minJumps(int arr[], int n)
{
    int dp[n];
    int i, j;


    dp[0] = 0;


    for (i = 1; i < n; i++)
    {
        dp[i] = INT_MAX;


        for (j = 0; j < i; j++)
        {
            if (i <= j + arr[j] && dp[j] != INT_MAX)
            {
                dp[i] = dp[j] + 1;
                break;
            }
        }
    }


    if (dp[n-1] == INT_MAX)
        return -1;
    else
        return dp[n-1];
}

int main()
{
    int arr[] = {2, 3, 1, 1, 4};
    int n = sizeof(arr)/sizeof(arr[0]);

    int min_jumps = minJumps(arr, n);

    if (min_jumps == -1)
        printf("End is not reachable");
    else
        printf("Minimum number of jumps required to reach the end: %d", min_jumps);

    return 0;
}


#include <stdio.h>
int main() 
{
    int arr[100], size, i, max1, max2;

    printf("Enter the size of the array: ");
    scanf("%d", &size);

    printf("Enter %d elements in the array: ", size);
    for (i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }

    max1 = arr[0];
    max2 = arr[1];

    if (max1 < max2) {
        int temp = max1;
        max1 = max2;
        max2 = temp;
    }

    for (i = 2; i < size; i++) {
        if (arr[i] > max1) {
            max2 = max1;
            max1 = arr[i];
        } else if (arr[i] > max2) {
            max2 = arr[i];
        }
    }

    printf("The largest two elements in the array are: %d and %d\n", max1, max2);

}


#include<stdio.h>
int main()
{
    int arr[100], n, temp, i, j, second_largest, second_smallest, sum = 0;
    float avg;
    printf("Enter the number of elements: ");
    scanf("%d", &n);
    printf("Enter the elements: ");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    for (i = 0; i < n; i++) {
        for (j = i + 1; j < n; j++) {
            if (arr[i] < arr[j]) {
                temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
    }
    second_largest = arr[1];
    second_smallest = arr[n-2];
    sum = second_largest + second_smallest;
    avg = (float) sum / 2;
    for (i = 0; i < n; i++) {
        if (arr[i] == avg) {
            printf("The average number %f is present in the array.\n", avg);
            return 0;
        }
    }
    printf("The average number %f is not present in the array.\n", avg);
    return 0;
}



#include <stdio.h>

int main() 
{
    int arr[100], n, max_diff = 0, i, j;
    printf("Enter the number of elements: ");
    scanf("%d", &n);
    printf("Enter the elements: ");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    for (i = 0; i < n; i++) {
        for (j = i+1; j < n; j++) {
            if (arr[j] - arr[i] > max_diff) {
                max_diff = arr[j] - arr[i];
            }
        }
    }
    printf("The maximum difference between two elements is %d.\n", max_diff);
    return 0;
}


#include <stdio.h>

int main()
{
    int arr[100], n, i, j, k;
    printf("Enter the number of elements: ");
    scanf("%d", &n);
    printf("Enter the elements: ");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    for (i = 0; i < n; i++) {
        for (j = i+1; j < n; j++) {
            if (arr[j] == arr[i]) {
                for (k = j; k < n; k++) {
                    arr[k] = arr[k+1];
                }
                n--; 
                j--;
            }
        }
    }
    printf("Resultant Array after removing duplicates: ");
    for (i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
	return 0;
}


#include <stdio.h>

int main() 
{
   int array[10], even[10], odd[10], i, j = 0, k = 0, n;

   printf("Enter the size of array: ");
   scanf("%d", &n);

   printf("Enter the elements of the array: ");
   for (i = 0; i < n; i++) {
      scanf("%d", &array[i]);
   }

   for (i = 0; i < n; i++) {
      if (array[i] % 2 == 0) {
         even[j] = array[i];
         j++;
      } else {
         odd[k] = array[i];
         k++;
      }
   }

   printf("\nEven elements of array: ");
   for (i = 0; i < j; i++) {
      printf("%d ", even[i]);
   }

   printf("\nOdd elements of array: ");
   for (i = 0; i < k; i++) {
      printf("%d ", odd[i]);
   }

   return 0;
}





#include <stdio.h>

int main() {
    int arr[100], i, n, posCount = 0, negCount = 0;

    printf("Enter the size of the array: ");
    scanf("%d", &n);

    printf("Enter the elements of the array:\n");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        if (arr[i] > 0) {
            posCount++;
        } else if (arr[i] < 0) {
            negCount++;
        }
    }


#include <stdio.h>
#include <string.h>

int main() {
    char str[100];
    int i, j, len, isPalindrome = 1;

    printf("Enter a string: ");
    scanf("%s", str);

    len = strlen(str);

    for (i = 0, j = len - 1; i < len / 2; i++, j--) {
        if (str[i] != str[j]) {
            isPalindrome = 0;
            break;
        }
    }

    if (isPalindrome) {
        printf("%s is a palindrome\n", str);
    } else {
        printf("%s is not a palindrome\n", str);
    }

    return 0;
}


2) solution:
#include <stdio.h>

int main() {
    int arr[11];
    int i, j, temp;

    for(i = 0; i <= 10; i++) {
        arr[i] = i * 3;
    }

    // Sort in ascending order
    for(i = 0; i <= 10; i++) {
        for(j = i+1; j <= 10; j++) {
            if(arr[i] > arr[j]) {
                temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
    }

    printf("Array elements in ascending order:\n");
    for(i = 0; i <= 10; i++) {
        printf("%d ", arr[i]);
    }

    printf("\n");

    // Sort in descending order
    for(i = 0; i <= 10; i++) {
        for(j = i+1; j <= 10; j++) {
            if(arr[i] < arr[j]) {
                temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
    }

    printf("Array elements in descending order:\n");
    for(i = 0; i <= 10; i++) {
        printf("%d ", arr[i]);
    }

    printf("\n");

    return 0;
}


#include <stdio.h>
#include <string.h>

int main() {
    char str1[100], str2[100];
    int len1, len2, i, j;

    printf("Enter the first string: ");
    scanf("%s", str1);

    printf("Enter the second string: ");
    scanf("%s", str2);

    len1 = strlen(str1);
    len2 = strlen(str2);

    for(i = len1, j = 0; j <= len2; i++, j++) {
        str1[i] = str2[j];
    }

    printf("Concatenated string: %s\n", str1);

    return 0;
}

3) solution

#include <stdio.h>

int main() {
   int arr[] = {12, 45, 67, 89, 34, 23};
   int n = sizeof(arr) / sizeof(arr[0]);
   int search_element = 89; // element to search
   int i, position = -1;
   
   for (i = 0; i < n; i++) {
      if (arr[i] == search_element) {
         position = i + 1;
         break;
      }
   }

   if (position == -1) {
      printf("Element not found in the array\n");
   } else {
      printf("Element found at position %d\n", position);
   }

   return 0;
}


#include <stdio.h>
#include <string.h>

int main() {
   char s1[50], s2[50];
   printf("Enter first string: ");
   gets(s1);
   printf("Enter second string: ");
   gets(s2);
   
   strcat(s1, s2);
   printf("Concatenated string: %s\n", s1);

   return 0;
}


4) solution

#include <stdio.h>

int main() {
    int i, j, isComposite;
    int compositeNumbers[50];
    int index = 0;

    for (i = 4; i <= 50; i++) {
        isComposite = 0;
        for (j = 2; j <= i / 2; j++) {
            if (i % j == 0) {
                isComposite = 1;
                break;
            }
        }
        if (isComposite) {
            compositeNumbers[index] = i;
            index++;
        }
    }

    printf("Composite numbers between 1 to 50: ");
    for (i = 0; i < index; i++) {
        printf("%d ", compositeNumbers[i]);
    }
    printf("\n");

    return 0;
}



#include <stdio.h>
#include <string.h>

int main() {
    char firstString[100];
    char secondString[100];
    int i, j, k;

    printf("Enter the first string: ");
    gets(firstString);

    printf("Enter the second string: ");
    gets(secondString);

    for (i = 0; i < strlen(firstString); i++) {
        for (j = 0; j < strlen(secondString); j++) {
            if (firstString[i] == secondString[j]) {
                for (k = j; k < strlen(secondString); k++) {
                    secondString[k] = secondString[k + 1];
                }
                j--;
            }
        }
    }

    printf("After removing characters present in first string: %s\n", secondString);

    return 0;
}
