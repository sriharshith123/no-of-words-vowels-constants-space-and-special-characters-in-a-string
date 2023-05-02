#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char str[100];
    int words = 0, vowels = 0, consonants = 0, space = 0, special = 0;
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strlen(str)-1] = '\0'; // remove newline character from input
    for (int i = 0; str[i] != '\0'; i++) {
        if (isspace(str[i])) {
            space++;
        }
        else if (isalpha(str[i])) {
            if (tolower(str[i]) == 'a' || tolower(str[i]) == 'e' || tolower(str[i]) == 'i' || tolower(str[i]) == 'o' || tolower(str[i]) == 'u') {
                vowels++;
            }
            else {
                consonants++;
            }
        }
        else if (isdigit(str[i])) {
            continue;
        }
        else {
            special++;
        }
    }
    words = space + 1;
    printf("Words = %d\n", words);
    printf("Vowels = %d\n", vowels);
    printf("Consonants = %d\n", consonants);
    printf("Space = %d\n", space);
    printf("Special Characters = %d\n", special);
    return 0;
}
