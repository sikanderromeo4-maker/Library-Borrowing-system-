#include "DoublyLinkedList.h"

DoublyLinkedList::DoublyLinkedList() {
    head = nullptr;
    tail = nullptr;
    current = nullptr;
}

bool DoublyLinkedList::IsEmpty() {
    return head == nullptr;
}

DoublyLinkedList::~DoublyLinkedList() {
    BookNode* temp = head;

    while (temp != nullptr) {
        BookNode* next = temp->right;
        delete temp;
        temp = next;
    }
}