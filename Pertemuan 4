#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Node {
    char nim[20], nama[50];
    int nilai;
    struct Node *next, *prev;
} *head = NULL, *tail = NULL, *baru, *bantu;

void tambah(int posisi, char nim[], char nama[], int nilai) {
    baru = (struct Node*)malloc(sizeof(struct Node));
    strcpy(baru->nim, nim); strcpy(baru->nama, nama);
    baru->nilai = nilai; baru->next = baru->prev = NULL;

    if (!head) { head = tail = baru; }
    else if (posisi == 1) {
        baru->next = head; head->prev = baru; head = baru;
    } else {
        tail->next = baru; baru->prev = tail; tail = baru;
    }
}

int main() {
    int pil, n; char ni[20], na[50];
    
    tambah(2, "2025071029", "Christhoper", 75);
    tambah(2, "1001", "Andi", 80); tambah(2, "1002", "Budi", 85);
    tambah(2, "1003", "Citra", 90); tambah(2, "1004", "Dedi", 95);

    while (1) {
        printf("\n1.Tambah Awal 2.Tambah Akhir 3.Hapus Awal 4.Tampil 5.Keluar\nPilih: ");
        scanf("%d", &pil);
        if (pil == 5) break;
        if (pil == 1 || pil == 2) {
            printf("NIM: "); scanf("%s", ni);
            printf("Nama: "); scanf(" %[^\n]s", na);
            printf("Nilai: "); scanf("%d", &n);
            tambah(pil, ni, na, n);
        } else if (pil == 3 && head) {
            baru = head; head = head->next;
            if (head) head->prev = NULL; else tail = NULL;
            free(baru);
            printf("Berhasil dihapus.\n");
        } else if (pil == 4) { 
            for (bantu = head; bantu; bantu = bantu->next)
                printf("[%s | %s | %d]\n", bantu->nim, bantu->nama, bantu->nilai);
        }
    }
    return 0;
}
