
#include <stdio.h>
#include <fcntl.h>
#include <unistd.h>
int main() {
    int s, d, n;
    char buffer[100];
    s = open("source.txt", O_RDONLY);
    if (s == -1) {
        printf("Source file not found\n");
        return 1;
    }
    d = open("dest.txt", O_WRONLY | O_CREAT | O_TRUNC, 0644);
    if (d == -1) {
        printf("Destination file error\n");
        close(s);
        return 1;
    }
    while ((n = read(s, buffer, sizeof(buffer))) > 0) {
        write(d, buffer, n);
    }
    close(s);
    close(d);
    printf("File copied successfully\n");
    return 0;
<img width="348" height="223" alt="Screenshot 2026-11-26 083138" src="https://github.com/user-attachments/assets/87f5288e-43c4-4c12-8d4a-eb43c33b0ff8" />
