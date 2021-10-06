#include <iostream>
#include <math.h>
#include <conio.h>
#include <windows.h>
#define v1 10
#define v2 10
#define v3 10
using namespace std;

void gotoxy(int x, int y)
{
    COORD coord;
    coord.X = (SHORT)x - 1;
    coord.Y = (SHORT)y - 1;
    SetConsoleCursorPosition(
        GetStdHandle(STD_OUTPUT_HANDLE), coord);
}
void main() {
    int x, y, k, a[v1][v2], b[v1][v2], c[v1][v2];
    //Ingresar datos matriz A
    cout << "MATRIZ A." << endl;
    for (x = 0; x < v1; x++) {
        for (y = 0; y < v2; y++) {
            cout << "Introduzca el valor del elemento [" << x << "][" << y << "]: ";
            cin >> a[x][y];
        }
    }
    cout << endl;
    //Imprimir datos matriz A
    for (x = 0; x < v1; x++) { 
        for (y = 0; y < v2; y++) {
            cout << a[x][y] << " ";
            if (y==9)
                cout << endl;
        }
    }
    cout << endl;
    //Ingresar datos Matriz B
    cout << "MATRIZ B." << endl; 
    for (x = 0; x < v1; x++) {
        for (y = 0; y < v2; y++) {
            cout << "Introduzca el valor del elemento [" << x << "][" << y << "]: ";
            cin >> b[x][y];
        }
    }
    cout << endl;
    //Imprimir datos Matriz B
    for (x = 0; x < v1; x++) { 
        for (y = 0; y < v2; y++) {
            cout << b[x][y] << " ";
            if (y==9)
                cout << endl;
        }
    }
    //Operación
    for (x = 0; x < v1; x++)
    { 
        for (y = 0; y < v2; y++)
        {
            c[x][y] = 0;
            for (k = 0; k < v3; k++) {
                c[x][y] = c[x][y] + (a[x][k] * b[k][y]);
            }
        }
    }
    //Resultado
    cout << endl << "MATRIZ C (Matriz A*B)." << endl;
    cout << endl;
    for (x = 0; x < v1; x++) {

        for (y = 0; y < v2; y++) {
            cout << c[x][y] << " ";
            if (y==9)
                cout << endl;
        }
    }
    system("PAUSE");
}
