# C-programming4

## Write a program to read a string and count the number of vowels using a separate function.

```
#include <stdio.h>
#include <string.h>

// Function to count vowels
int countVowels(char str[]) {
    int i, count = 0;

    for(i = 0; str[i] != '\0'; i++) {
        char ch = str[i];

        if(ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u' ||
           ch=='A' || ch=='E' || ch=='I' || ch=='O' || ch=='U') {
            count++;
        }
    }

    return count;
}

int main() {
    char str[100];
    int vowels;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    vowels = countVowels(str);

    printf("Number of vowels = %d\n", vowels);

    return 0;
}
```

## Output
<img width="448" height="279" alt="image" src="https://github.com/user-attachments/assets/6e036449-bece-4cd5-ba3d-5a87e2597184" />

## Write a function to reverse a string without using library functions like strrev().

```
#include <stdio.h>
#include <string.h>

// Function to reverse the string
void reverseString(char str[]) {
    int start = 0;
    int end = strlen(str) - 1;
    char temp;

    while(start < end) {
        temp = str[start];
        str[start] = str[end];
        str[end] = temp;

        start++;
        end--;
    }
}

int main() {
    char str[100];

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    // Remove newline character if present
    str[strcspn(str, "\n")] = '\0';

    reverseString(str);

    printf("Reversed string: %s\n", str);

    return 0;
}
```
## Output
<img width="407" height="181" alt="image" src="https://github.com/user-attachments/assets/a340fb3a-500c-4934-aced-0e3520c68e89" />

## Write a program to check whether a given string is palindrome or not using functions.

```
#include <stdio.h>
#include <string.h>

// Function to check palindrome
int isPalindrome(char str[]) {
    int start = 0;
    int end = strlen(str) - 1;

    while(start < end) {
        if(str[start] != str[end]) {
            return 0;   // Not palindrome
        }
        start++;
        end--;
    }

    return 1;   // Palindrome
}

int main() {
    char str[100];

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    // Remove newline character
    str[strcspn(str, "\n")] = '\0';

    if(isPalindrome(str)) {
        printf("The string is a palindrome.\n");
    } else {
        printf("The string is not a palindrome.\n");
    }

    return 0;
}
```

## Output
<img width="442" height="246" alt="image" src="https://github.com/user-attachments/assets/41e69cac-cfab-42a6-a705-c22cc73f32ec" />

## Write a function to calculate the length of a string manually.

```
#include <stdio.h>

// Function to calculate string length manually
int stringLength(char str[]) {
    int count = 0;

    while(str[count] != '\0') {
        count++;
    }

    return count;
}

int main() {
    char str[100];
    int length;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    // Remove newline character if present
    int i = 0;
    while(str[i] != '\0') {
        if(str[i] == '\n') {
            str[i] = '\0';
            break;
        }
        i++;
    }

    length = stringLength(str);

    printf("Length of the string = %d\n", length);

    return 0;
}
```

## Output
<img width="443" height="252" alt="image" src="https://github.com/user-attachments/assets/efeaff97-6d6c-4c99-b965-3ccc6ea72d15" />

## Write a function to count the number of words in a sentence.

```
#include <stdio.h>

// Function to count words in a sentence
int countWords(char str[]) {
    int i = 0, words = 0;

    while(str[i] != '\0') {

        // Check for beginning of a word
        if((i == 0 || str[i - 1] == ' ') && str[i] != ' ' && str[i] != '\n') {
            words++;
        }

        i++;
    }

    return words;
}

int main() {
    char str[200];
    int totalWords;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    totalWords = countWords(str);

    printf("Number of words = %d\n", totalWords);

    return 0;
}
```

## Output
<img width="550" height="240" alt="image" src="https://github.com/user-attachments/assets/01c638ce-078e-4a27-ad3c-ef107a6c9917" />
