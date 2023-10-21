#include <stdio.h>

// Функция для конвертации числа из big-endian в little-endian
unsigned int bigEndianToLittleEndian(unsigned int num) {
    return ((num >> 24) & 0xFF) |
           ((num >> 8) & 0xFF00) |
           ((num << 8) & 0xFF0000) |
           ((num << 24) & 0xFF000000);
}

int main() {
    int N;
    scanf("%d", &N);

    if (N <= 0 || N >= 100) {
        printf("Недопустимое значение N\n");
        return 1;
    }

    for (int i = 0; i < N; i++) {
        unsigned int input;
        scanf("%u", &input);
        
        unsigned int littleEndian = bigEndianToLittleEndian(input);
        printf("%u\n", littleEndian);
    }

    return 0;
}
