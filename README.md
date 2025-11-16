#include <stdio.h>
#include <string.h>

void lihatAlat() {
    FILE *f = fopen("items.txt", "r");
    char line[200];

    if (!f) {
        printf("File items.txt tidak ditemukan.\n");
        return;
    }

    printf("\n=== DAFTAR ALAT LAB ===\n");
    while (fgets(line, sizeof(line), f)) {
        printf("%s", line);
    }

    fclose(f);
}

void pinjamAlat(char user[]) {
    FILE *f = fopen("loans.txt", "a");
    char id[20];

    printf("Masukkan ID alat yang mau dipinjam: ");
    scanf("%s", id);

    fprintf(f, "%s %s\n", user, id);
    fclose(f);

    printf("Peminjaman berhasil!\n");
}
