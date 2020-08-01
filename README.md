# linked-list-operations-in-detail-in-java
not using Collections



class Node
{
    int data; 
    Node next;
}
public class Runnner
{
    public static void main(String[] args)
    {
        LinkedList li=new LinkedList();
        
        li.add(3);
        li.add(4);
        li.add(5);
        li.addAtStart(1);
        li.addAt(0,2);
        li.deleteAt(1);
        li.show();
    }
}
class LinkedList
{
    Node head;
    public void add(int data)
    {
        Node node=new Node();
        node.data=data;
        node.next=null;
        
        if(head==null)
        {
            head=node;
        }
        else
        {
            Node n=head;
            while(n.next!=null)
            {
                n=n.next;
            }
            n.next=node;
        }
    }
    void addAtStart(int data)
    {
        Node node=new Node();
        node.data=data;
        node.next=null;
        
        node.next=head;
        head=node;
    }
    void addAt(int index,int data)
    {
        Node node=new Node();
        node.data=data;
        node.next=null;
        Node n=head;
        if(index==0)
        {
            addAtStart(data);
        }
        else
        {
            for(int i=0;i<index-1;i++)
            {
                n=n.next; 
            }
            node.next=n.next;
            n.next=node;
        }
    }
    void deleteAt(int index)
    {
        if(index==0)
        {
            head=head.next;
        }
        else
        {
            Node n=head;
            Node n1=null;
            for(int i=0;i<index-1;i++)
            {
                n=n.next;
            }
            n1=n.next;
            n.next=n1.next;
            n1=null;
        }
        
    }
    void show()
    {
        Node n=head;
        while(n.next!=null)
        {
            System.out.println(n.data);
            n=n.next;
        }
        System.out.println(n.data);
    }
}
