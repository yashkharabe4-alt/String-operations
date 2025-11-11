# String-operations
#include <stdio.h>

int compare(char x[30], char y[30]){
    int cmp = 1;  // assume equal
    
    for(int i=0; x[i] != '\0' || y[i] != '\0'; i++){
        if(x[i] != y[i]){
            cmp = 0;
            break;
        }
    }

    if (cmp == 0)
        return 0;  // not equal
    else
        return 1;  // equal
}

int length(char x[30]){
    int len = 0;
    for(int i=0; x[i] != '\0'; i++){
        len++;
    }
    return len;
}

int main() {
    char storedUser[30] = "aqert12";  // stored username
    char inputUser[40];

    printf("Enter a username: ");
    scanf("%s", inputUser);

    int same = compare(inputUser, storedUser);
    int len  = length(inputUser);

    if(len >= 6 && len <= 12 && same == 1){
        printf("The username is invalid ");
    }
    else{
        printf("valid username ");
    }

    return 0;
}
