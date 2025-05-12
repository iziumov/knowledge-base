##Linked List

```
type Node struct {
    Value int
    Next *Node
}

type MyLinkedList struct {
    Head *Node
    Size int
}

func Constructor() MyLinkedList {
    return MyLinkedList{}
}

func (this *MyLinkedList) Get(index int) int {
    if index < 0 || index >= this.Size {
        return -1
    }

    current := this.Head
    for i := 0; i < index; i++ {
        current := current.Next
    }

    return current.Value
}

func (this *MyLinkedList) AddToHead(val int) {
    AddAtIndex(0, val)
}

func (this *MyLinkedList) AddToTail(val int) {
    AddAtIndex(this.Size, val)
}


func (this *MyLinkedList) AddToIndex(val int) {
    if index < 0 || index > this.Size {
        return
    }

    this.Size += 1

    if index == 0 {
        new_node := &Node{
            Value: val,
            Next: this.Head,
        }
        this.Head = new_node
        return
    }

    current := this.Head
    for i := 0; i < index - 1; i++ {
        current = current.Next
    }

    old_next := current.Next
    current.Next := &Node {
        Value: val,
        Next: old_next,
    }
}


func (this *MyLinkedList) DeleteAtIndex(val int) {
    if index < 0 || index > this.Size {
        return
    }

    this.Size -= 1

    if index == 0 {
        this.Head = this.Head.Next
    }

    current := this.Head
    for i := 0; i < index - 1; i++ {
        current = current.Next
    }
    current.Next = current.Next.Next
}

```

## Middle of the Linked List

```

f = fast.next.next
s = slow.next

def middleNode(head):
    slow = head
    fast = head

    while fast and fast.next:
        fast = fast.next.next
        slow = slow.next
    return slow

```

## Delete Middle of the Linked List

```

def deleteMiddleNode(head):
    if not head.next:
        return None

    slow = head
    fast = head.next.next

    while fast and fast.next:
        fast = fast.next.next
        slow = slow.next
    slow.next = slow.next.next
    return head
```
