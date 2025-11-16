#include <stdio.h>
#include <string.h>
#include <stdlib.h>

void lihatAlat() {
    FILE *f = fopen("items.txt", "r");
    char line[200];

    if (!f) {
        printf("File items.txt tidak ada.\n");
        return;
    }

    printf("\n== DAFTAR ALAT LAB ==\n");
    while (fgets(line, sizeof(line), f)) {
        printf("%s", line);
    }
    fclose(f);
}
