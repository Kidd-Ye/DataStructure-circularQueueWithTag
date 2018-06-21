# DataStructure-circularQueueWithTag
设置tag的循环队列

<pre><code>

/**
队空条件： Q.front == Q.rear 且 Q.tag == 0
队满条件： Q.front == Q.rear 且 Q.tag == 1
进队操作： Q.data[Q.rear]=x; Q.rear=(Q.rear + 1) % maxsize; Q.tag = 1
出队操作： x=Q.data[Q.front]; Q.front=(Q.front + 1) % maxsize; Q.tag = 0
**/

#include <iostream>
using namespace std;
#define maxsize 5

typedef struct queue{
    int tag = 0;
    int data[maxsize];
    int front = 0, rear = 0;
}Queue;

void EnQueue(Queue &q, int element){
    if (q.front == q.rear && q.tag == 1) {
        cout << "此时队满" << endl;
    }else{
        q.data[q.rear] = element;
        q.rear = (q.rear + 1) % maxsize;
        q.tag = 1;
    }
}

void DeQueue(Queue &q){
    if (q.front == q.rear && q.tag == 0) {
        cout << "此时队空" << endl;
    }else{
        cout << q.data[q.front] << "出队" << endl;
        q.front = (q.front + 1) % maxsize;
        q.tag = 0;
    }
}

</code></pre>
