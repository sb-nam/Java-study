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
## while 문

```java
class Tutorial {
    
    public static void main(String args[]) {
       
        int num=0; 
        int num1=5

        while(num < 5) //<- 반복 조건 true 일시 반복 실행
        { System.out.println("I like Java"+num);
          num++; // <- 반복 조건을 무너뜨리는 조건. 반드시 들어가야됨. 아니면 무한정 반복됨.
        }
        while(num1 < 5) // 반복 조건 false 일시 실행 안됨
        { System.out.println("I like Java"+num1);
          num1++; 
        }
        
    }
    
}
 
```
## do~while 문

```java
class Tutorial {
    
    public static void main(String args[]) {
       
        int num=0;
        int num1=5;

        do    // <- 먼저 실행  
        { System.out.println("I like Java"+num);
          num++; 
        }while(num < 5); // <-true 일 경우 반복됨.
        
        do{     // 먼저 실행  
            System.out.println("I like Java"+num);
            num1++;
        }while(num1<5); // <- false 일 경우 실행 안됨.
        
    }
    
}
 
```
**while 문 -> 검사,실행 순서
**do~while 문 -> 실행,검사 

## for문

```java
class Tutorial {
    
    public static void main(String args[]) {
       
         //       1       2      3
       for(int num=0; num<3; num++){  // int num=0;    <-  1
                                      // while(num<3)   <- 2
           System.out.println(num);   // System.out.println(....)
                                      // num++;       <- 3
       }
       /*
       실행 순서
         //       1       2    4  
       for(int num=0; num<3; num++){        // int num=0;    <-  1
                                            // while(num<3)   <- 2
           System.out.println(num); <-3     // System.out.println(....) <- 3
                                            // num++;       <- 4
       }
       */
       
    }
}
for 문은 위와 같이 while문과 같은 형식을 취한다. 또한 실행 순서도 while문과 비슷한 순서로 진행함을 알아 두자!
 
```
## continue & break

```java
class Tutorial {
    
    public static void main(String args[]) {
       
        int num=0;
        int count=0;

        while(num++<100){

            if(num % 5 != 0 || num % 7 != 0){ // <- 5의 배수가 아니고, 7의 배수도 아닐때.if문 특성상 true일때 다음으로 진행됨.
                continue;         // <- 다음으로 진행 하지 않고 while 문을 다시 실행한다는 의미.
            }
            count++;              // <- 5의 배수이며 7의 배수 일 때만 count++ 하겠다.
            System.out.println(num);  // <- 35,70
        }
        System.out.println("count="+ count); // <- 2

        
    }
    
}
 
```
위의 while 문을 for 문으로 변경해 보앗다.
```java
class Tutorial {
    
    public static void main(String args[]) {
       
         int count=0;

        for(int num=0; num<100; num++){ // <-int num = 0 으로 햇을때 0,35,70 3가지가 왜나오지?
            // while(num++<100) <- 다음줄 부터 1 더하겠다는 의미네.. 그래서 for문에서는 int num=1이 맞다.
           
           if(num % 5 != 0 || num % 7 != 0){
                continue;
            }
            count++;
            System.out.println(num);
        }
        System.out.println("count="+ count);

        
    }
    
}
 
```
while 문을 for 문으로 변경2
```java
class Tutorial {
    
    public static void main(String args[]) {
         
         int num=1;

        while(true){

            if(num % 6 == 0 && num % 14 == 0){
                break;
            }
            num++;
        }
        System.out.println(num);

//       for(int num=1; true; num++){
//
//           if(num % 6 == 0 && num % 14 == 0){
//               break;
//           }
//           num++;
//       }
//        System.out.println(num);   <- 왜 출력이안되는 거지?

        
    }
    
}
while문은 정상 출력이 되는대 for문은 왜 출력이 안되는지 모르겠다. 좀 더 고민해 봐야지.
 
```
## 반복문의 중첩
- 가장 많이 등장하는 중첩은 for문의 중첩!

```java
class Tutorial {
    
    public static void main(String args[]) {
       
         for(int i=0; i<3; i++){    // <- 조건 1번 만족
                                        //     V
           System.out.println("i="+i);  //     V
                                        //     V
           for(int j=0; j<3; j++){  // <- 조건 모두 만족
              
              System.out.println("j="+j);
           }
       }

        
    }
    
}

 i가 0일때 j=0,1,2 . i가 1일때 j=0,1,2 . i가 2일때 j=0,1,2 로 진행된다.
```
## break 레이블
```java
class Tutorial {
    
    public static void main(String args[]) {
       
        outerLoop :    // <- 반복문의 조건을 설정 해놓고 반복문을 빠져나가고 싶을때 사용.
        for(int i=1; i<10; i ++){

            for(int j=1; j<10; j++){

                System.out.println("[" + i + "," + j + "]");
                if(i % 2 == 0 && j % 2 == 0){
                    break outerLoop; // 브레이크 레이블 범위 표시
                }
            }
        }

        
    }
    
}
**** break; 만 사용 하게 된다면 하나의 반복문만 나가게 됨.

```
## 메소드에 대한 이해와 메소드의 정의

- 자바 프로그램의 시작은 main이라는 이름의 메소드를 실행하는 데서부터 시작한다.
- 메소드는 한번 정의되면 여러 번 실행 가능하다.
- 메소드의 정의에서 메소드의 이름 오른편에 등장하는 변수를 '매개변수' 라고 한다.
- `매개변수` 는 메소드 호출 시 전달되는 값의 저장을 위한 용도로 사용 된다.
- 메소드 호출시 전달되는 값의 자료형과 '매개변수' 의 자료형은 항상 일치해야 한다.
- 메소드가 정의되는 위치는 프로그램에 영향을 미치지 않는다.
```java
class Tutorial {
    
    public static void main(String args[]) {
       
       System.out.println("program start");
       hiEveryone(12); // 메소드 호출 방법
       hiEveryone(13); // (12),(13) int age에 저장됨.
       System.out.println("program end");
    }

    public static void hiEveryone(int age){ // <- int age 매개 변수

        System.out.println("good morning");
        System.out.println("I am "+ age + "years old");
        

        
    }
    
}
 
```
- 메소드는 여러개의 값을 한번에 전달도 가능 하고, 값을 전달하지 않아도 된다.
```java
class Tutorial {
      
    public static void main(String args[]) {
       
        double myHeight=175.9;
        hiEveryone(12, 12.5); // <- 정수형 변수 int ,실수형 변수 double
        hiEveryone(13, myHeight); 
        byEveryone(); // <- 공란
    }

    public static void hiEveryone(int age, double height){ // <- 정수 12 가 먼저 나오기 때문에 
                                                           // int age , double height 순서. 자료형 일치 시킴. 
        System.out.println("i am "+ age + " yeard old");
        System.out.println("myHeight" + height + "cm");
    }

    public static void byEveryone(){ // <- 위에가 공란이기 때문에 공란.

        System.out.println("see you again");

        
    }
    
}
  
 
```
- 값을 반환하는 메소드
```java
class Tutorial {
   
   //   void = 값을 반환하지 않겠다.
   
   public static void main(String args[]) {
       
        int result = adder(4,5);
        System.out.println("4 + 5 ="+ result);
        System.out.println("3.5 * 3.5=" + square(3.5));
    }
     
     //   int adder -> int = int 형 데이터를 반환하겠다.
    
    public static int adder(int num1,int num2){
        int addResult= num1 + num2;
        return addResult;      // return = 반환 하겠다. 뭘? addResult 값을 반환하겠다.
    }
    
    //  double square -> double = double 형 데이터를 반환하겠다.
   
   public static double square(double num){
        return num * num;     // = return 반환 하겠다. 뭘? num * num 값을 반환 하겠다.

        
    }
    
}
  
 
```

## 키워드  return이 지니는 두가지 의미
- 값의 반환
- 메소드의 종료

```java
class Tutorial {
   
     public static void main(String args[]) {
       
        divide(4,2);
        divide(6,2);
        divide(9,0);
    }

    public static void divide(int num1, int num2 ){

        if(num2==0){

            System.out.println("0으로는 값을 나눌 수 없습니다.");
            return;  // <- 메소들르 종료 하겠다는 의미.
         // void 이기 때문에 값을 반환하면 안되고 num2가 0이라면 내용 출력후 메소드가 종료됨.
        }            

        System.out.println("나눗셈 결과 :" + (num1 / num2));
    
    
    }
    
}
  
 
```
## 변수의 스코프
- 스코프(scope)는 범위 또는 영역 이라는 뜻을 갖고 있다.
- 영역은 변수의 접근, 또는 변수가 존재할 수 있는 영역을 의미한다.
```java
class Tutorial {
   
     public static void main(String args[]) {
       
      boolean scope=true;                                  // ---
      if(scope) {                    // @@@@
          int num=1;
          num++;
          System.out.println(num);
      }                              // @@ num =1 의 유효범위
      else {                         // ##
          int num=2;
          System.out.println(num);
      }                              //## num =2 의 유효범위
      simple();
                                                          //---변수 scope의 유효범위
    }
    public static void simple() {    //%% 

        int num=3;
        System.out.println(num);

    
    
    }                                //%% num=3의 유효범위
    
}
  
   선언된 지역을 벗어나면 변수는 자동 소멸된다.
```   
## 클래스와 인스턴스
```java
 class Number {

    int num=0;

    public void addNum(int n) {

        num+=n;
    }
    public int getNumber() {
        return num;
    }
}

 class passInstance {

    public static void main(String [] args) {

        Number nInst= new Number();
        System.out.println("before call method :" + nInst.getNumber());

        simpleMethod(nInst);
        System.out.println("after call method :"+ nInst.getNumber());
    }
    public static void simpleMethod(Number numb) {

        numb.addNum(12);
    }
}

```
