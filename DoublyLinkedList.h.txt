#ifndef DOUBLYLINKEDLIST_H
#define DOUBLYLINKEDLIST_H

#include "BookNode.h"

class DoublyLinkedList {
private:
    BookNode* head;
    BookNode* tail;
    BookNode* current;

public:
    DoublyLinkedList();
    ~DoublyLinkedList();

    bool IsEmpty();

    void InsertRight(BookNode* node);
    void InsertAfterCurrent(BookNode* node);
    BookNode* RemoveCurrent();

    void Next();
    void Previous();

    void PrintCurrent();
    void PrintForward();
    void PrintBackward();
};

#endif