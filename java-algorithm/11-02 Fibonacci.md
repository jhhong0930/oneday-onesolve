```java
package study.recursive;

//일반적인 피보나치
public class Fibonacci1102_1 {
    public int DFS(int n) {
        if(n == 1) return 1;
        else if(n == 2) return 1;
        else return DFS(n-2) + DFS(n-1);
    }

    public static void main(String[] args) {
        Fibonacci1102_1 T = new Fibonacci1102_1();
        int n=5;
        System.out.println(T.DFS(n));
    }
}

```

---

```java
package study.recursive;

//개선1) 배열에 값을 미리 저장해두기: 속도 개선
public class Fibonacci1102_2 {
    public static int[] fibo;

    public int DFS(int n) {
        if(n == 1) return fibo[n] = 1;
        else if(n == 2) return fibo[n] = 1;
        else return fibo[n] = DFS(n-2) + DFS(n-1);
    }

    public static void main(String[] args) {
        Fibonacci1102_2 T = new Fibonacci1102_2();
        int n=10;
        fibo = new int[n+1];

        for(int i=1; i<=n; i++) {
            System.out.print(T.DFS(i) + " ");
        }
    }
}

```

---

```java
package study.recursive;

//인터뷰에서 많이 나옴
//개선2) 배열에 미리 저장해둔 값을 사용하기(메모리제이션 활용) : 속도 개선
//for문 성능이 재귀 성능보다 더 좋음
public class Fibonacci1102_3 {
    public static int[] fibo;

    public int DFS(int n) {
        if(fibo[n] > 0) return fibo[n];

        if(n == 1) return fibo[n] = 1;
        else if(n == 2) return fibo[n] = 1;
        else return fibo[n] = DFS(n-2) + DFS(n-1);
    }

    public static void main(String[] args) {
        Fibonacci1102_3 T = new Fibonacci1102_3();
        int n=10;
        fibo = new int[n+1];

        for(int i=1; i<=n; i++) {
            System.out.print(T.DFS(i) + " ");
        }
    }
}

```
