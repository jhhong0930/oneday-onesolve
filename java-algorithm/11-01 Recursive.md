## 재귀함수

```java
import java.util.*;
class Main {
	public void DFS(int n){
		if(n==0) return;
		else{
			DFS(n-1);
			System.out.print(n+" ");
		}
	}
	public void solution(int n){
		DFS(n);
	}
	public static void main(String[] args){
		Main T = new Main();
		T.solution(3);
		//System.out.println(T.solution(3));
	}	
}
```

<img src="https://user-images.githubusercontent.com/44156173/139704964-6cea5057-b9ad-4266-8d5c-74ceb7a97c05.png" width="60%">

<img src="https://user-images.githubusercontent.com/44156173/139705658-8880ed75-3a8e-48eb-b6a2-05e5ebe904a8.png" width="60%">

---


## 이진수 출력(재귀)

```java
import java.util.*;
class Main {
	public void DFS(int n){
		if(n==0) return;
		else{
			DFS(n/2);
			System.out.print(n%2);
		}
	}
	public void solution(int n){
		DFS(n);
	}
	public static void main(String[] args){
		Main T = new Main();
		T.solution(11);
		//System.out.println(T.solution(3));
	}	
}
```

<img src="https://user-images.githubusercontent.com/44156173/139705925-acd0ad75-40a6-4609-b742-e706e5dbe685.png" width="60%">

---

## 팩토리얼

```java
import java.util.*;
class Main {
	public int DFS(int n){
		if(n==1) return 1;
		else return n*DFS(n-1);
	}
	public static void main(String[] args){
		Main T = new Main();
		System.out.println(T.DFS(5));
	}	
}
```

<img src="https://user-images.githubusercontent.com/44156173/139706225-b59dcaf9-efd2-4e5c-bee7-894972ccc8a2.png" width="60%">
