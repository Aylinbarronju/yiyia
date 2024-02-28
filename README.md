#include <iostream>
#include <algorithm>

using namespace std;

void insertionSort(int arr[], int n, bool ascendente) {
    if (ascendente) {
        for (int i = 1; i < n; i++) {
            int key = arr[i];
            int j = i - 1;
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j = j - 1;
            }
            arr[j + 1] = key;
        }
    } else {
        for (int i = 1; i < n; i++) {
            int key = arr[i];
            int j = i - 1;
            while (j >= 0 && arr[j] < key) {
                arr[j + 1] = arr[j];
                j = j - 1;
            }
            arr[j + 1] = key;
        }
    }
}

void printArray(int arr[], int n) {
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;
}

int main() {
    int arr[10];
    cout << "Ingrese 10 valores enteros separados por espacios: ";
    for (int i = 0; i < 10; i++) {
        cin >> arr[i];
    }

    char orden;
    cout << "Desea ordenar de manera ascendente (a) o descendente (d)? ";
    cin >> orden;

    bool ascendente;
    if (orden == 'a')
        ascendente = true;
    else if (orden == 'd')
        ascendente = false;
    else {
        cout << "Opción inválida. Se ordenará de manera ascendente por defecto." << endl;
        ascendente = true;
    }

    insertionSort(arr, 10, ascendente);

    cout << "Arreglo ordenado: ";
    printArray(arr, 10);

    return 0;
}
