#include <iostream>

void insertionSort(int arr[], int n, bool ascending) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;

        if (ascending) {
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j = j - 1;
            }
        } else {
            while (j >= 0 && arr[j] < key) {
                arr[j + 1] = arr[j];
                j = j - 1;
            }
        }
        arr[j + 1] = key;
    }
}

int main() {
    int arr[] = {12, 11, 13, 5, 6, 7, 9, 1, 2, 8};
    int n = sizeof(arr) / sizeof(arr[0]);

    // Ordenar en orden ascendente
    insertionSort(arr, n, true);
    std::cout << "Array ordenado en orden ascendente:" << std::endl;
    for (int i = 0; i < n; i++)
        std::cout << arr[i] << " ";
    std::cout << std::endl;

    // Ordenar en orden descendente
    insertionSort(arr, n, false);
    std::cout << "Array ordenado en orden descendente:" << std::endl;
    for (int i = 0; i < n; i++)
        std::cout << arr[i] << " ";
    std::cout << std::endl;

    return 0;
}
