# ATM-simulator-C
 ATM Simulator is a simple mini project developed using C language. It simulates basic ATM operations like deposit, withdrawal, and balance enquiry through a menu-driven interface. This project helps in understanding core C concepts such as loops, switch-case, and conditional statements. The program can be executed easily using Cxxdroid on mobile.
#include <stdio.h>

int main() {
    int choice;
    float balance = 1000, deposit, withdraw;

    while(1) {
        printf("\n--- ATM Simulator ---\n");
        printf("1. Deposit\n");
        printf("2. Withdraw\n");
        printf("3. Balance Enquiry\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter amount to deposit: ");
                scanf("%f", &deposit);
                balance += deposit;
                printf("Amount deposited successfully.\n");
                break;

            case 2:
                printf("Enter amount to withdraw: ");
                scanf("%f", &withdraw);
                if(withdraw > balance)
                    printf("Insufficient balance.\n");
                else {
                    balance -= withdraw;
                    printf("Please collect your cash.\n");
                }
                break;

            case 3:
                printf("Your current balance is: %.2f\n", balance);
                break;

            case 4:
                printf("Thank you for using ATM.\n");
                return 0;

            default:
                printf("Invalid choice. Try again.\n");
        }
    }
}
