#include "BookNode.h"

BookNode::BookNode(int id, string name) {
    bookID = id;
    title = name;
    left = nullptr;
    right = nullptr;
}