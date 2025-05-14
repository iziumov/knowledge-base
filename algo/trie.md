## TRIE

```

class Node:
    self.children = {}
    self.terminal = False

class Trie:
    def __init__:
        self.root = Node()

    def insert(self, word):
        node = self.root
        for ch in word:
            if ch not in node.children:
                node.children[ch] = Node()
            node = node.children[ch]
        node.terminal = True

    def insert(self, word):
        node = self.root
        for ch in word:
            if ch not in node.children:
                node.children[ch] = Node()
            node = node.children[ch]
        return node.terminal

    def startWith(self, prefix):
        node = self.root
        for ch in prefix:
            if ch not in node.children:
                node.children[ch] = Node()
            node = node.children[ch]
        return True
```

```


class Node:
    self.children = {}
    self.words = []

class Trie:
    def __init__:
        self.root = Node()

    def insert(self, word):
        node = self.root
        for ch in word:
            if ch not in node.children:
                node.children[ch] = Node()
            node = node.children[ch]
        node.words.append(word)

    def insert(self, word):
        node = self.root
        for ch in word:
            if ch not in node.children:
                node.children[ch] = Node()
            node = node.children[ch]
        return node.words

def suggestedProducts(products, searchWord):
    root = Trie()
    for word in products:
        root.insert(word)
    result = []

    for i in range(len(searchWord)):
        found = root.search(searchWord[:i+1])
        if found:
            result.append(sorted(found)[:3])
        else:
            result.append([])
```
