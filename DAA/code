#include <stdio.h>
#define SIZE 10
int hashTable[SIZE];
int hashFunction(int key) {
    return key % SIZE;
}
void insert(int key) {
    int index = hashFunction(key);
    int i;
    for (i = 0; i < SIZE; i++) {
        int newIndex = (index + i) % SIZE;
        if (hashTable[newIndex] == -1 || hashTable[newIndex] == -2) {
            hashTable[newIndex] = key;
            return;
        }
    }
    printf("Hash Table is full. Cannot insert %d\n", key);
}
int search(int key) {
    int index = hashFunction(key);
    int i;
    for (i = 0; i < SIZE; i++) {
        int newIndex = (index + i) % SIZE;

        if (hashTable[newIndex] == key)
            return newIndex;

        if (hashTable[newIndex] == -1)
            return -1;
    }
    return -1;
}
void deleteKey(int key) {
    int pos = search(key);

    if (pos == -1) {
        printf("%d not found.\n", key);
    } else {
        hashTable[pos] = -2;
        printf("%d deleted.\n", key);
    }
}
void display() {
    int i;
    printf("\nHash Table:\n");
    for (i = 0; i < SIZE; i++) {
        printf("%d -> %d\n", i, hashTable[i]);
    }
}

int main() {
    int i;
    for (i = 0; i < SIZE; i++) {
        hashTable[i] = -1;
    }
    insert(5);
    insert(15);
    insert(25);
    insert(35);
    insert(95);
    display();
    printf("\nSearching 25 ? Position: %d\n", search(25));
    deleteKey(25);
    display();
    insert(55);
    display();
    printf("\n press Enter to exit.... ");
    getchar();
    return 0;
}