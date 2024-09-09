#include <iostream>
#include <string>

using namespace std;


struct TamaRocket {
    string sabor;
    double precio;
    int cantidad;
    string tipo;
};

void leerTamales(TamaRocket &p) {
    cout << "Ingrese el sabor del producto: ";
    getline(cin, p.nombre);
    cout << "Ingrese el precio del producto: ";
    cin >> p.precio;
    cout << "Ingrese la cantidad del producto: ";
    cin >> p.cantidad;
    cin.ignore(); // Limpiar el buffer del cin
    cout << "Ingrese el tipo del producto (ej. oaxaqueños, torta de tamal, clasico): ";
    getline(cin, p.tipo);
}
void imprimirTamales (const TamaRocket &p) {
    cout << "Sabor: " << p.nombre << endl;
    cout << "Precio: " << p.precio << endl;
    cout << "Cantidad: " << p.cantidad << endl;
    cout << "Tipo: " << p.tipo << endl;
}

void buscarPorSabor(const TamaRocket tamales, int n, const string &nombre) {
    bool encontrado = false;
    for (int i = 0; i < n; ++i) {
        if (tamales[i].tipo == tipo) {
            imprimirTamaRocket(tamales[i]);
            encontrado = true;
        }
    }
    if (!encontrado) {
        cout << "Producto con sabor " << nombre << " no encontrado." << endl;
    }
}


void buscarPorTipo(const TamalesRocket tamales, int n, const string &tipo) {
    bool encontrado = false;
    for (int i = 0; i < n; ++i) {
        if (tamales[i].tipo == tipo) {
            imprimirTamaRocket(tamales[i]);
            encontrado = true;
        }
    }
    if (!encontrado) {
        cout << "No se encontraron productos del tipo " << tipo << "." << endl;
    }
}

int main() {
    int n;
    cout << "Ingrese el número de productos: ";
    cin >> n;
    cin.ignore(); 
    TamaRocket*tamales = new TamaRocket[n];


    for (int i = 0; i < n; ++i) {
        cout << "Ingrese los datos del Tamal " << i + 1 << endl;
        leerTamales (tamales[i]);
    }
cout << "\nLista de todos los Tamales:\n";
    for (int i = 0; i < n; ++i) {
        cout << "\nTamales" << i + 1 << ":\n";
      imprimirTamaRocket(tamales[i]);
    }
    string criterioBusqueda;
    cout << "\nIngrese el sabor del producto a buscar: ";
    getline(cin, criterioBusqueda);
    buscarPorSabor(productos, n, criterioBusqueda);

    cout << "\nIngrese el tipo de productos a buscar: ";
    getline(cin, criterioBusqueda);
    buscarPorTipo(productos, n, criterioBusqueda);
    delete[] productos;

    return 0;
}
