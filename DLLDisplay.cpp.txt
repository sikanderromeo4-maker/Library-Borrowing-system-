#include <iostream>
#include "DoublyLinkedList.h"
using namespace std;

void DoublyLinkedList::PrintCurrent() {
    if (current == nullptr) {
        cout << "Session is empty.\n";
        return;
    }

    cout << "Current Book: " << current->bookID
         << " - " << current->title << endl;
}

void DoublyLinkedList::PrintForward() {
    if (IsEmpty()) {
        cout << "No books available.\n";
        return;
    }

    BookNode* temp = head;
    cout << "\nBooks (First to Last):\n";

    while (temp != nullptr) {
        cout << temp->bookID << " - " << temp->title;

        if (temp == current)
            cout << " [CURRENT]";

        cout << endl;
        temp = temp->right;
    }
}

void DoublyLinkedList::PrintBackward() {
    if (IsEmpty()) {
        cout << "No books available.\n";
        return;
    }

    BookNode* temp = tail;
    cout << "\nBooks (Last to First):\n";

    while (temp != nullptr) {
        cout << temp->bookID << " - " << temp->title;

        if (temp == current)
            cout << " [CURRENT]";

        cout << endl;
        temp = temp->left;
    }
}