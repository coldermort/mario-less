#include<stdio.h>
#include<stdlib.h>
#include<ctype.h>
#include<string.h>
int main(){
    int i,j ;
    int levels;
    char ch = '#';
    char input[50];
    do {
        printf("how many levels? ");
        fgets(input, sizeof(input), stdin);
        input[strcspn(input, "\n")] = '\0';

        if (strlen(input) == 0) {
            printf("You just pressed Enter! Please enter a number.\n");
            levels = 0; 
            continue;
             }
             int valid = 1;
        for (int i = 0; i < strlen(input); i++) {
            if (!isdigit((unsigned char)input[i])) {
                valid = 0;
                break;
            }
        }


        if (valid) {
            levels = atoi(input); 
        } else {
            levels = 0;}
        

        if (levels <= 0) {
            printf("Please enter a positive number!\n");
        }

    } while (levels <= 0);

    
    
    
    for(int i=1; i<=levels; i++){
        for(int j=levels-i; j; j--){
        printf("   ");}
        
    

        for(int j=1; j<=i; j++){
        printf(" %c ", ch);}
        printf("\n");
    }

    return 0;
}
