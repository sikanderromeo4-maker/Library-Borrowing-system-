#include <iostream>
#include <limits>
#include "LibraryMenu.h"
using namespace std;

void RunLibraryMenu(DoublyLinkedList& session) {
    int choice, id;
    string title;

    do {
        cout << "\n===== LIBRARY BORROWING SESSION =====\n";
        cout << "1. Display Current Book\n";
        cout << "2. Move to Next Book\n";
        cout << "3. Move to Previous Book\n";
        cout << "4. Insert Book at the End\n";
        cout << "5. Insert Book After Current Book\n";
        cout << "6. Remove Current Book\n";
        cout << "7. Display First to Last\n";
        cout << "8. Display Last to First\n";
        cout << "9. Exit\n";
        cout << "Enter choice: ";
        cin >> choice;

        if (cin.fail()) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(), '\n');
            cout << "Enter a valid number.\n";
            continue;
        }

        switch (choice) {
        case 1:
            session.PrintCurrent();
            break;

        case 2:
            session.Next();
            session.PrintCurrent();
            break;

        case 3:
            session.Previous();
            session.PrintCurrent();
            break;

        case 4:
            cout << "Enter Book ID: ";
            cin >> id;
            cin.ignore(numeric_limits<streamsize>::max(), '\n');
            cout << "Enter Book Title: ";
            getline(cin, title);
            session.InsertRight(new BookNode(id, title));
            break;

        case 5:
            cout << "Enter Book ID: ";
            cin >> id;
            cin.ignore(numeric_limits<streamsize>::max(), '\n');
            cout << "Enter Book Title: ";
            getline(cin, title);
            session.InsertAfterCurrent(new BookNode(id, title));
            break;

        case 6: {
            BookNode* removed = session.RemoveCurrent();

            if (removed != nullptr) {
                cout << "Removed: " << removed->title << endl;
                delete removed;
            } else {
                cout << "No book to remove.\n";
            }
            break;
        }

        case 7:
            session.PrintForward();
            break;

        case 8:
            session.PrintBackward();
            break;

        case 9:
            cout << "Exiting Library System.\n";
            break;

        default:
            cout << "Invalid choice.\n";
        }

    } while (choice != 9);
}