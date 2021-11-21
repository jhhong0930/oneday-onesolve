# Tree 말단노드까지의 가장 짧은 경로(DFS)

<img src="https://user-images.githubusercontent.com/44156173/142771048-10f24e16-fb5f-4fc6-8404-11f8e60d3412.png" width="60%">


```java
package study.dfs;
import study.Node;

public class ShortestPathTerminalNode1104{
    Node root;
    public int DFS(int L, Node root){
        if(root.lt==null && root.rt==null) return L;
        else return Math.min(DFS(L+1, root.lt), DFS(L+1, root.rt));
    }

    public static void main(String args[]) {
        ShortestPathTerminalNode1104 tree=new ShortestPathTerminalNode1104();
        tree.root=new Node(1);
        tree.root.lt=new Node(2);
        tree.root.rt=new Node(3);
        tree.root.lt.lt=new Node(4);
        tree.root.lt.rt=new Node(5);
        System.out.println(tree.DFS(0, tree.root));
    }
}

```
