#ifndef BOOKNODE_H
#define BOOKNODE_H
#include <string>
using namespace std;

struct BookNode {
    int bookID;
    string title;
    BookNode* left;
    BookNode* right;

    BookNode(int id, string name);
};
#endif