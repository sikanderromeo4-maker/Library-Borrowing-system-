#include "DoublyLinkedList.h"
#include "LibraryMenu.h"

int main() {
    DoublyLinkedList session;

    session.InsertRight(new BookNode(101, "Data Structures"));
    session.InsertRight(new BookNode(102, "Database Systems"));
    session.InsertRight(new BookNode(103, "Operating Systems"));

    RunLibraryMenu(session);

    return 0;
}