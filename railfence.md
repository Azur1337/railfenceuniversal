// railfence array.cpp : Diese Datei enthält die Funktion "main". Hier beginnt und endet die Ausführung des Programms.
//

#include <iostream>
using namespace std;
const 
int main()
{
    string word;
    int column = 0;
    int row = 0;
    int rail;
    bool direction;
    int array[3][10];

    cout << "Geben Sie ein zu verschlüsselnes Wort in großbuchstaben ein: ";
    cin >> word;
    cout << "Geben Sie an, wieviele rails sie benutzen wollen(2-5): ";
    cin >> rail;

    for (int i = 0; i < 3; i++) {
        for (int x = 0; x < 10; x++) {
            array[i][x] = '*';
        }
    }


    for (int i = 0; i < word.length(); i++) {
        array[row][column] = word[i];
        if (row == 0) {
            direction = true;
        }
        else if (row == 3) {
            direction = false;
        }

        if (direction == true) {
            row += 1;
            column += 1;
        }
        else if (direction == false) {
            row -= 1;
            column += 1;
        }
    }



    for (int i = 0; i < 3; i++) {
        for (int x = 0; x < 10; x++) {
            if (array[i][x] != '*') {
                cout << array[i][x];
            }
        }
    }
    
}

// Programm ausführen: STRG+F5 oder Menüeintrag "Debuggen" > "Starten ohne Debuggen starten"
// Programm debuggen: F5 oder "Debuggen" > Menü "Debuggen starten"

// Tipps für den Einstieg: 
//   1. Verwenden Sie das Projektmappen-Explorer-Fenster zum Hinzufügen/Verwalten von Dateien.
//   2. Verwenden Sie das Team Explorer-Fenster zum Herstellen einer Verbindung mit der Quellcodeverwaltung.
//   3. Verwenden Sie das Ausgabefenster, um die Buildausgabe und andere Nachrichten anzuzeigen.
//   4. Verwenden Sie das Fenster "Fehlerliste", um Fehler anzuzeigen.
//   5. Wechseln Sie zu "Projekt" > "Neues Element hinzufügen", um neue Codedateien zu erstellen, bzw. zu "Projekt" > "Vorhandenes Element hinzufügen", um dem Projekt vorhandene Codedateien hinzuzufügen.
//   6. Um dieses Projekt später erneut zu öffnen, wechseln Sie zu "Datei" > "Öffnen" > "Projekt", und wählen Sie die SLN-Datei aus.
