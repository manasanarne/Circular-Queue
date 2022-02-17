# Circular-Queue
#include<stdio.h>
#define MAX 5
int cq[MAX],front=-1,rear=-1;
void enqueue(int k)
{
   
    if ((rear==MAX-1 && front==0)||front==rear+1)
    {
        printf("queue overflow");
    }
    else
    {
        if (front==-1)
        {
        front=0;
        rear=0;
        }
        else if (rear==MAX-1)
        {
            rear=0;
        }
        else
        {
            ++rear;
        }
    }
    cq[rear]=k;
}
int dequeue()
{
    int x;
    if (front==-1)
    {
        return -1;
    }
    else
    {
        x=cq[front];
        if (front==rear)
        {
            front=-1;
            rear=-1;
        }
        else if(front==MAX-1)
        {
            front=0;
        }
        else
        {
            ++front;
        }
       
    }
    return x;
}
void display()
{
    int i;
    if (front<=rear)
    {
        for (i=front;i<=rear;i++)
        {
            printf("%d",cq[i]);
        }
    }
    else
    {
        for(i=front;i<=MAX-1;i++)
        {
            printf("%d",cq[i]);
        }
        for (i=0;i<=rear;i++)
        {
            printf("%d",cq[i]);
        }
    }
}
void main()
{
    int c,k;
    while(1)
    {
        printf("enter c:");
        scanf("%d",&c);
        switch(c)
        {
            case 1:printf("enter k:");
                   scanf("%d",&k);
                   enqueue(k);
                   break;
            case 2:dequeue();
                   break;
            case 3:display();
                   break;
            case 4:exit(0);
           
        }
    }
}

OUTPUT:
enter c:1
enter k:2
enter c:1
enter k:8
enter c:1
enter k:4
enter c:3
284enter c:2
enter c:3
84enter c:4
