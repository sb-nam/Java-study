# Java 공부 정리

# 목차
- [Java란 무엇인가](#Java란-무엇인가)
- [변수](#변수)



## Java란 무엇인가

- 객체 지향 언어

[목차로](#목차)





## 변수
- **int : 정수를 담을 수 있는 변수**
  - 다음과 같은 예제를 작성해 보았다.
  
```java
class Tutorial {
    
    public static void main(String args[]) {
        int num1 = 10;    
        System.out.println(num1); // -> 정수 10이 화면에 
    }
    
}
  
```

[목차로](#목차)
  
## 연산자

- `=` 연산자 오른쪽에 있는 값을 연산자 왼쪽에 있는 변수에 대입한다. (a=20)
- `+` 두 피연산자의 값을 더한다. (a=4+3)
- `-` 왼쪽의 피연산자 값에서 오른쪽의 피연산자 값을 뺀다. (a=4-3)
- `*` 두 피연산자의 값을 곱한다.(a=4*3)
- `/` 왼쪽의 피연산자 값을 오른쪽의 값으로 나눈다.(a=7/3)
- `%` 왼쪽의 피연산자 값을 오른쪽의 피연산자 값으로 나눴을때 얻게 되는 나머지를 반환한다.(a=7%3)
 
## 관계 연산자

- `<` n1이 n2보다 작은가? (n1 < n2)
- `>` n1이 n2보다 큰가? (n1 > n2)
- `<=` n1이 n2보다 같거나 작은가? (n1 <= n2)
- `>=` n1이 n2보다 같거나 큰가? (n1 >= n2)
- `==` n1과 n2가 같은가? (n1 == n2)
- `!=` n1과 n2가 다른가? (n1 != n2)

## 논리 연산자

- `&&` A와 B 모두 ture이면 연산결과는 true (A && b)  ->
- `||` A와 B 둘 중 하나라도 true이면 연산결과는 true ( A || B) ->
- `! ` 연산결과는 A가 true이면 false, A가 false이면 true (!A) <-

## 비트 연산자

- `&` 비트 단위로 AND연산을 한다. (n1 & n2) ->
- `|` 비트 단위로 OR 연산을 한다. (n1 | n2) ->
- `^` 비트 단위로 XOR 연산을 한다. (n1 ^ n2) -> // * 두 비트의 값이 서로 다를 경우에만 1을 반환함.
- `~` 피연산자의 모든 비트를 반전시켜서 얻은 결과를 반환함. (~n) <-

## 조건 연산자 (삼항 연산자)

```java
class Tutorial {
    
    public static void main(String args[]) {
        
        
        int num1 = 50 ;
        int num2 = 100 ;
        int big , diff ;


        big = (num1 > num2) ? num1 : num2; // (num1 > num2) 가 거짓이면 : 오른쪽 num2
        System.out.println(big);

        diff = (num1 < num2) ? num1 - num2 : num2 - num1; // (num1 < num2)가 참이면 : 왼쪽 num1 - num2
        System.out.println(diff);
        
    }
    
}
  
```
## switch 와 break 문

```java
class Tutorial {
    
    public static void main(String args[]) {
       
        
        int n=1; // n1= case 1, n2= case 2, n3= case 3 , 그외= deault

        switch(n){
            case 1 :
                System.out.println("Simple Java");

            case 2 :
                System.out.println("Funny Java");
                
            case 3 :
                System.out.println("Fantastic Java");
                

            default :
                System.out.println("The best programming language");
        }

        System.out.println("Do you like coffee?");
    }
    
}
**switch = 순차적으로 모두 실행  
```

```java
class Tutorial {
    
    public static void main(String args[]) {
       
        
        int n=1; // n1= case 1, n2= case 2, n3= case 3 , 그외= deault

        switch(n){
            case 1 :
                System.out.println("Simple Java");
                break;
            case 2 :
                System.out.println("Funny Java");
                break;
            case 3 :
                System.out.println("Fantastic Java");
                break;

            default :
                System.out.println("The best programming language");
        }

        System.out.println("Do you like coffee?");
    }
    
}
  **break = 해당 영역만 실행
```
```java
class Tutorial {
    
    public static void main(String args[]) {
       
        
        int n=1;

        switch(n){
            case 1 : case 2 : case 3 :                // n 1,2,3 을 하나의 부류로 묶을수도 있다.
                System.out.println("Simple Java");
                break;
            case 4 :  case 5 :                        // n 4,5 를 하나의 부류로 묶을수 있다.
                System.out.println("Fantastic Java");
                break;

            default :
                System.out.println("The best programming language");
        }

        System.out.println("Do you like coffee?");
    }
    
}
 
```
