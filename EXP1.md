#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>

int main()
{
    pid_t pid;<img width="369" height="246" alt="Screenshot 2026-10-31 095955" src="https://github.com/user-attachments/assets/592a56b4-4db9-4e79-96cf-ef113e39865f" />


    pid = fork();

    if (pid < 0)
    {
        printf("Process creation failed\n");
    }
    else if (pid == 0)
    {
        printf("\nChild Process\n");
        printf("PID: %d\n", (int)getpid());
        printf("Parent PID: %d\n", (int)getppid());
    }
    else
    {
        printf("\nParent Process\n");
        printf("PID: %d\n", (int)getpid());
        printf("Parent PID: %d\n", (int)getppid());
    }

    return 0;
}
