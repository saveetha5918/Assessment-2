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
