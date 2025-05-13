##Hash Table

```

type Node {
    Key int
    Value int
    Next *Node
}

type LinkedList {
    Head *Node
}

func (l *LinkedList) Get(key int) int {
    current := l.Head
    for current != nil {
        if current.Key == key {
            return current.Val
        }

        current = current.Next
    }

    return -1
}

func (l *LinkedList) Put(key, val int) {
    current := l.Head

    for current != nil {
        if current.Key == key {
            current.Val = val
        }

        current = current.Next
    }

    newNode := &Node {
        Key: key,
        Value: value,
        Next: l.Head,
    }

    l.Head = newNode
}

func (l *LinkedList) Remove(key int) {
    if l.Head == nil {
        return
    }

    if l.Head.key == key {
        l.Head = l.Head.Next
        return
    }

    current := l.Head

    for current.Next != nil {
        if current.Key == key {
            current.Next = current.Next.Next
        }

        current = current.Next
    }
}

type HashMap struct {
    n int
    buckets []*LinkedList
}

func Constructor() HashMap {
    n := 991
    buckets := make([]*LinkedList, n)
    for i := range buckets {
        buckets[i] := &LinkedList{}
    }

    return HashMap{
        n: n,
        buckets: buckets,
    }
}

func (this *HashMap) hash(x int) int {
    return x % this.n
}

func (this *HashMap) Put(key int, value int) {
    n := this.hash(key)

    this.buckets[n].Put(key, value)
}

func (this *HashMap) Get(key int) int {
    n := this.hash(key)

    this.buckets[n].Get(key)
}

func (this *HashMap) Remove(key int) {
    n := this.hash(key)

    this.buckets[n].Get(key)
}

```
