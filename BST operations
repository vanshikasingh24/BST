#include<bits/stdc++.h>
#define ll long long
#define ld long double
using namespace std;
struct BST
{
    int value;
    struct BST *r;
    struct BST *l;
};
BST* search(BST* root, int x)
{
    if(root==NULL||root->value==x)
        return root;
    if(x<root->value)
        return search(root->l,x);
    return search(root->r,x);
}
void ino(BST*root)
{
    if(root)
    {
        ino(root->l);
        cout<<(root->value)<<" ";
        ino(root->r);
    }
}
BST* insert(BST* p,int x)
{
    if(p==NULL)
    {
        BST* node = new BST;
        node->value = x;
        node->l=nullptr;
        node->r=nullptr;
        return node;
    }
    if(x<p->value)
        p->l=insert(p->l,x);
    else
        p->r=insert(p->r,x);
    return p;
}
BST* findmin(BST* p)
{
    BST* c=p;
    while(c&&c->l)
        c=c->l;
    return c;
}
BST* todelete(BST* p,int x)
{
    if(p==NULL)
        return p;
    else if(x<p->value)
        p->l=todelete(p->l,x);
    else if(x>p->value)
        p->r=todelete(p->r,x);
    else
    {
        if(p->l==NULL)
        {
            BST *t=p->r;
            free(p);
            return t;
        }
        else if(p->r==NULL)
        {
            BST *t=p->l;
            free(p);
            return t;
        }
        BST* t=findmin(p->r);
        p->value=t->value;
        p->r=todelete(p->r,t->value);
    }
    return p;
}
int main()
{
    ios::sync_with_stdio(false);
    cin.tie(0);cout.tie(0);
    //freopen("input.txt", "r", stdin);
    //freopen("output.txt", "w", stdout);
    BST *root=NULL;
    root=insert(root,7);
    root=insert(root,3);
    root=insert(root,9);
    root=insert(root,5);
    root=insert(root,8);
    root=insert(root,10);
    root=insert(root,1);
    ino(root);
    cout<<endl;
    root=todelete(root,9);
    ino(root);
    cout<<endl;
}
