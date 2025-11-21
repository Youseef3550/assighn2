/*
=========================================================
        CSE233 – Assignment 2 (All in One File)
=========================================================
This file contains:
1. Process creation example (fork)
2. Linking simulation using functions
3. Loader example (simple print function)
=========================================================
*/

#include <stdio.h>
#include <unistd.h>

/* -------------------------------------------------------
   1. PROCESS CREATION (fork example)
------------------------------------------------------- */
void run_process_creation() {
    printf("\n--- Process Creation Example ---\n");

    pid_t pid = fork();

    if (pid == 0) {
        printf("Child process running | PID = %d\n", getpid());
    }
    else if (pid > 0) {
        printf("Parent process running | PID = %d\n", getpid());
    }
    else {
        printf("Error: fork() failed.\n");
    }
}

/* -------------------------------------------------------
   2. LINKER EXAMPLE (simulate file1.c + file2.c)
------------------------------------------------------- */
void hello() {
    printf("Message from simulated file1.c (hello function)\n");
}

void run_linker_example() {
    printf("\n--- Linker Example ---\n");
    hello();
}

/* -------------------------------------------------------
   3. LOADER EXAMPLE
------------------------------------------------------- */
void run_loader_example() {
    printf("\n--- Loader Example ---\n");
    printf("Testing dynamic loader simulation.\n");
}

/* -------------------------------------------------------
   MAIN MENU
------------------------------------------------------- */
int main() {
    int choice;

    while (1) {
        printf("\n====================================\n");
        printf("   CSE233 Assignment 2 - Main Menu\n");
        printf("====================================\n");
        printf("1. Run Process Creation Example\n");
        printf("2. Run Linker Example\n");
        printf("3. Run Loader Example\n");
        printf("4. Exit\n");
        printf("Choose option: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                run_process_creation();
                break;
            case 2:
                run_linker_example();
                break;
            case 3:
                run_loader_example();
                break;
            case 4:
                printf("Exiting...\n");
                return 0;
            default:
                printf("Invalid choice, try again.\n");
        }
    }
}
