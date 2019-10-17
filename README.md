# Java 공부 정리

# 목차
- [Java란 무엇인가](#Java란-무엇인가)
- [변수](#변수)
- [String 연결](#String-연결)
- [연산자](#연산자)
- [관계 연산자](#관계-연산자)
- [논리 연산자](#논리-연산자)
- [비트 연산자](#비트-연산자)
- [if문](#if문)
- [삼항 연산자](#삼항-연산자)
- [switch 와 break 문](#switch-와-break-문)
- [while 문](#while-문)
- [do while 문](#do-while-문)
- [for문](#for문)
- [continue와 break](#continue와-break)
- [반복문의 중첩](#반복문의-중첩)
- [break 레이블](#break-레이블)
- [메소드에 대한 이해와 메소드의 정의](#메소드에-대한-이해와-메소드의-정의)
- [키워드 return이 지니는 두가지 의미](#키워드-return이-지니는-두가지-의미)
- [변수의 스코프](#변수의-스코프)
- [static 변수](#static-변수)
- [메소드 오버로딩과 String 클래스](#메소드-오버로딩과-String-클래스)
- [클래스와 인스턴스](#클래스와-인스턴스)
- [생성자](#생성자)
- [자바 이름의 규칙](#자바-이름의-규칙)
- [클래스 패스와 패키지](#클래스-패스와-패키지)
- [접근제어 지시자](#접근제어-지시자)
- [메소드 오버로딩과 String 클래스](#메소드-오버로딩과-String-클래스)
- [String 클래스](#String-클래스)
- [StringBuilder와 StringBuffer 클래스](#StringBuilder와-StringBuffer-클래스)
- [콘솔 출력](#콘솔-출력)




## Java란 무엇인가

- 객체 지향 언어

[목차로](#목차)





## 변수
- **변수 : 프로그램 실행시 자료가 변환되는  공간
- **int : 정수를 담을 수 있는 변수**
- **자료형 변수명;
- **변수명=값;

- **실수 : double
- **문자열 : String(앞글자 대문자) 
  - 다음과 같은 예제를 작성해 보았다.
  
```java
class Tutorial {
    
    public static void main(String args[]) {
        int num1 = 10;    
        System.out.println(num1); // -> 정수 10이 화면에 
    }
    
}
  
```

```java

import java.util.Scanner;

class InputVariable {

	public static void main(String[] args) {

		Scanner scanner = new Scanner(System.in);
		
		int intNumber;
		double doubleNumber;
		String str;
		
		intNumber = scanner.nextInt();
		doubleNumber = scanner.nextDouble();
		str = scanner.next();
		
		System.out.println("입력한 정수 : " + intNumber);
		System.out.println("입력한 실수 : " + doubleNumber);
		System.out.println("입력한 문자열 : " + str);
	}

}
```

`친구의 Feedback`

*위의 코드를 살펴보면, scanner가 사용된 뒤 close되지 않고 있습니다.*    
*사용이 끝난 Scanner는 close() 해주어야 합니다.*     
*즉, 사용되지 않는 자원을 open하고 있는 상태로, 자원의 낭비가 발생되고 있습니다.*    

```java
// example
class InputVariable {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
	
	... // do something
	
	scanner.close();
    }
}
```


[목차로](#목차)




## String 연결

```java
public class Quiz {

	public static void main(String[] args) {
		
		String str = " 더휴먼 ";
		
		System.out.println(10 + 20 + str); // int + int + String 으로 계산 되어 = 30 더휴면
		System.out.println(str + 10 + 20); // String + 문자 10 + 문자 20 으로 형변환 되어 더휴면 1020

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

```java

import java.util.Scanner;

class Operator {

	public static void main(String[] args) {
		
		double number1, number2;
		double result = 0;
		
		Scanner scanner = new Scanner(System.in);
		
		System.out.println("첫 번째 수 입력 : ");
		number1 = scanner.nextDouble();
		
                System.out.println("두 번째 수 입력 : ");
		number2 = scanner.nextDouble();
		
		result = number1 + number2;
		System.out.println(result);
		
		result = number1 - number2;
		System.out.println(result);
		
		result = number1 * number2;
		System.out.println(result);
		
		result = number1 / number2;
		System.out.println(result);
		
                scanner.close();

	}

}

```

```java

import java.util.Scanner;

class GradeCard {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		int korean, english, math, result;
		
		System.out.println("korean score : " );
		korean = sc.nextInt();
		
		System.out.println("english score : " );
		english = sc.nextInt();
		
		System.out.println("math score : " );
		math = sc.nextInt();
		
		result = (korean + english + math) / 3;
		
		System.out.println("average : " + result );
		
		sc.close();
	
	}


}

```

[목차로](#목차)
 
 
 
 
## 관계 연산자

- `<` n1이 n2보다 작은가? (n1 < n2)
- `>` n1이 n2보다 큰가? (n1 > n2)
- `<=` n1이 n2보다 같거나 작은가? (n1 <= n2)
- `>=` n1이 n2보다 같거나 큰가? (n1 >= n2)
- `==` n1과 n2가 같은가? (n1 == n2)
- `!=` n1과 n2가 다른가? (n1 != n2)

[목차로](#목차)




## 논리 연산자

- `&&` A와 B 모두 ture이면 연산결과는 true (A && b)  ->
- `||` A와 B 둘 중 하나라도 true이면 연산결과는 true ( A || B) ->
- `! ` 연산결과는 A가 true이면 false, A가 false이면 true (!A) <-

[목차로](#목차)




## 비트 연산자

- `&` 비트 단위로 AND연산을 한다. (n1 & n2) ->
- `|` 비트 단위로 OR 연산을 한다. (n1 | n2) ->
- `^` 비트 단위로 XOR 연산을 한다. (n1 ^ n2) -> // * 두 비트의 값이 서로 다를 경우에만 1을 반환함.
- `~` 피연산자의 모든 비트를 반전시켜서 얻은 결과를 반환함. (~n) <-


[목차로](#목차)



## if문
{
조건식이 참일때 값 수행문
} 
else {
조건식이 거짓일때 값 수행문
}

조건식: 참, 거짓이 구분이 되는식( true,false)

```java

import java.util.Scanner;

public class GradeCard2 {

	public static void main(String[] args) {
		
		double kor,eng,math,average;
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println("국어 점수 : " );
		kor = sc.nextDouble();
		
		System.out.println("영어 점수 : " );
		eng = sc.nextDouble();
		
		System.out.println("수학 점수 :" );
		math = sc.nextDouble();
		
		average = (kor + eng + math) / 3;
		
		System.out.println("평균 점수 : " + average);
		
		if(average >= 80) {
			
			System.out.println("우수학생");
		}
		
		else {
			
			System.out.println("노력하세요");
		}
		
		sc.close();

	}

}
```
```java

import java.util.Scanner;

public class GradeCard3 {

	public static void main(String[] args) {
		
		double kor, eng, math, avr;
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println("국어 점수 : ");
		kor = sc.nextDouble();
		
		System.out.println("영어 점수 : ");
		eng = sc.nextDouble();
		
		System.out.println("수학 점수 : ");
		math = sc.nextDouble();
		
		avr = (kor + eng + math) / 3;
		System.out.println("평균 점수 : " + avr);
		
		if(avr >= 90) {
			
			System.out.println("A 학점");
		}
		
		else if(avr >= 80) {
			
			System.out.println("B 학점");
		}
		
		else if(avr >= 70){
			
			System.out.println("C 학점");
		}
		
		else {
			
			System.out.println("F 학점");
		}
			
		sc.close();		
		
	}

}
```

```java

import java.util.Scanner;

public class Population {

	public static void main(String[] args) {
		
		long pop;
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println("인구수 입력 :");
		pop = sc.nextLong();
		
		if(pop >= 10000000) {
			
			System.out.println("대도시");
		}
		
		else if(pop >= 500000) {
			
			System.out.println("중도시");
		}
		
		else {
			
			System.out.println("소도시");
		}
		
		sc.close();

	}

}

```

```java

import java.util.Scanner;

public class GradeCard4 {

	public static void main(String args[]) {
		
		double kor, eng, evr;
		
		Scanner sc = new Scanner(System.in);
							
		System.out.println("국어 점수 : " );
		kor = sc.nextDouble();
		
		System.out.println("영어 점수 : " );
		eng = sc.nextDouble();
		
/*	    if(kor >= 80 && eng >= 80 ) {
			
			System.out.println("우수");
		}
		
		else {
			
			System.out.println("보통");
		} 
*/		
		
		if(kor >= 80) {
			
			if(eng >= 80) {
			
			System.out.println("우수");
			}
		    else {
			
			System.out.println("보통");
		    }
		
		}
		
		else {
			
			System.out.println("보통");
		}
		
		sc.close();
	}

}
```


`친구의 Feedback`

*조건문을 사용할 때, 괄호를 작성하는 규칙이 존재합니다.*    
*if, else if, else를 작성할 때는 개행을 하는 것이 아니라 `}` 뒤에 이어서 작성합니다.*    
*자바 개발자들간의 coding convention(코드 작성 규칙)이므로, 이 규칙을 지킨다면 다른 개발자와의 협업에서 큰 도움이 됩니다.*    

```java
// bad case ㅡㅡ
class Example {
    public static void main(String[] args) {
        int grade = 80; // <- temporary variable
	
	if(90 <= grade) {
	    System.out.println("A grade");
	} 
	else if(80 <= grade) {
	    System.out.println("B grade");
	} 
	else {
	    System.out.println("C grade");
	}
    }
}

// good case ^^
class Example {
    public static void main(String[] args) {
        int grade = 80; // <- temporary variable
	
	if(90 <= grade) {
	    System.out.println("A grade");
	} else if(80 <= grade) {
	    System.out.println("B grade");
	} else {
	    System.out.println("C grade");
	}
    }
}
```

[목차로](#목차)



## 삼항 연산자

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

[목차로](#목차)



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
[목차로](#목차)



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
[목차로](#목차)


## do while 문

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
- **for(초기값,조건식,증가값)

```java

public class ForExe {

	public static void main(String[] args) {
		
		int even = 0;
		int odd = 0;
		
		for(int i = 1; i<=100; i++) {
			
			if(i % 2 == 0) {
			
				even = even + i;
			}
			else {
				
				odd = odd + i;
			}
		}
		
		System.out.println("1부터 100까지의 짝수 합 :" + even);
		System.out.println("1부터 100까지의 홀수 합 :" + odd);

	}

}
```



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

```java

import java.util.Scanner;

public class MultiplicationTable {

	public static void main(String[] args) {
						
		System.out.println("원하는 단 입력 :");
		
		Scanner sc = new Scanner(System.in);
		
		int n = sc.nextInt();
						
	    for(int i =1; i <= 9; i++) {
	    
	    	System.out.println(n +" * "+ i + " = " + (n*i) );
	    }
	    	    	  

	}

}
```

```java


class MultiplicationTable2 {

	public static void main(String[] args) {
		
		for (int i = 2; i <= 9; i++) {
			
			System.out.println(i + "단");

			for (int j = 1; j <= 9; j++) {
				
				System.out.println(i + " * " + j + " = " + i * j );

			}

		}
	}

}

```

```java



public class Sequence {

	public static void main(String[] args) {

		int count = 0;

		for (int i = 1; i <= 100; i++) {
			
			if (i % 7 == 0) {
				
				System.out.println(i);
                                count++;
				
			}
						
		}
		
		System.out.println(" 7의 배수의 개수" + count);

	}

}
```
[목차로](#목차)




## continue와 break

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
변수의 관한 scope 때문에 해당 반복문의 영역을 벗어 났기 때문에 (num); 이 당연히 출력이 안되네.
출력을 하려면 for문 밖에 num을 선언 해주거나, for문 안쪽으로 들여서 설정을 해야한다!
 
```
[목차로](#목차)



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
[목차로](#목차)




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
[목차로](#목차)



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

[목차로](#목차)




## 키워드 return이 지니는 두가지 의미
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
[목차로](#목차)



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
[목차로](#목차)



## 클래스와 인스턴스
- 클래스는 내가 만들고자 하는 틀 이고, 그 틀 안에 들어 있는 내용물을 객체 라고 볼수 있다.
- 객체란 내용물 즉 내가 구현할 대상이라고 볼수 있다.
- 인스턴스는 실체화 된 대상이라고 볼수 있다.

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

        Number nInst= new Number(); // 참조 변수 nInst가 class Number를 참조함.
        System.out.println("before call method :" + nInst.getNumber());
        //nInst가 getNumber를 호출함 -> 객체 내에 존재하는 변수 int num=0; 값이 반환됨.

        simpleMethod(nInst); 
        // 아래에 있는 simpleMethod를 호출하면서 class Number를 참조하는 nInst가 인자로 전달,
        // 호출된 매개변수 Number numb로 받으면서 numb를 이용하여 addNum 메소드를 호출함.
        System.out.println("after call method :"+ nInst.getNumber());
    }
    public static void simpleMethod(Number numb) {

        numb.addNum(12);
    }
}

```
```java
class FruitSeller { // 판매자 정보

    int numOfApple= 20;
    int myMoney= 0;
    final int APPLE_PRICE=1000;  // 변수의 상수화 final

    public int saleApple(int money) { // 과일 판매 기능
        int num= money/APPLE_PRICE; 
        numOfApple-=num;
        myMoney+=money;
        return num; // <- 2
    }
    
    public void showSaleResult() { //판매 현황
        System.out.println("The remainder Apple ="+ numOfApple);
        System.out.println("Sales revenue ="+ myMoney);
    }
}

class FruitBuyer { //구매자 정보

    int myMoney= 5000; // 소지금 5000
    int numOfApple= 0; // 소유 과일 0

    public void buyApple(FruitSeller seller, int money) {
        numOfApple+=seller.saleApple(money); 
        myMoney-=money;
    }
    
    public void showBuyResult() {

        System.out.println("Current Balance ="+ myMoney);
        System.out.println("Number of apples ="+ numOfApple);
    }
}

class FruitSalesMain1 {

    public static void main(String[] args) {

        FruitSeller seller= new FruitSeller(); // FruitSeller 참조하겠다.
        FruitBuyer buyer= new FruitBuyer();    // FruitBuyer 참조하겠다.
        buyer.buyApple(seller, 2000);   // seller에게 2000원 어치 구매

        System.out.println("Current situation of fruit seller ");
        seller.showSaleResult();

        System.out.println("Current situation of fruit buyers");
        buyer.showBuyResult();
    }
}

```
[목차로](#목차)




## 생성자 
- **생성자는 인스턴스 하나당 1번만 호출된다.!
- 자바 인스턴스 생성시 반드시 생성자는 호출된다.
- 생성자의 조건 1.클래스의 이름과 동일한 매소드
2.반환형이 선언되어 있지 않으면서, 반환하지 않는 매소드 
```java
class Number {
    
    int num;
    
    public Number() {
        
        num=10;
        System.out.println("생성자 호출!");
    }
    public int getNumber() {
        
        return num;
    }
}

class Constructor1 {
    
    public static void main(String[] args) {
        
        Number num1 = new Number(); // 생성과 동시에 호출됨.
        System.out.println(num1.getNumber());
        
        Number num2 = new Number();
        System.out.println(num2.getNumber());
    }
}
 
```
[목차로](#목차)




## 자바 이름의 규칙
- class의 이름은 대문자로 시작, 둘 이상의 단어가 묶일때 새로운 단어 첫글자는 대문자로 시작.
- 메소드와 변수의 이름 규칙 = 소문자 시작, 둘이상 단어 새로운 첫글자 대문자 시작.
- 상수의 이름 규칙 = 전부 대문자, 둘 이상 단어 묶일시 _ 표시.

[목차로](#목차)




## 클래스 패스와 패키지
- 클래스 패스 = 클래스를 찾는 경로.
- 패키지 = 디렉터리를 패키지 이름으로 감싸고, 패키지 이름을 항상 달아야지만 인스턴스 생성이
가능하도록 제한을 걸어둔것.

[목차로](#목차)




## 접근제어 지시자
- private = 클래스 내부에서만 접근 가능
- default = 동일 패키지, 동일 클래스에서 접근 가능
- protected = 동일 패키지, 동일 클래스, 상속받은 클래스에서 접근 가능
- public = 열려있음

[목차로](#목차)




## static 변수
- static 으로 선언된 변수는 메모리 공간에 하나만 존재, 어디서나 접근이 가능하나 public으로 선언되어야한다.
- 인스턴스 간에 데이터 공유가 필요한 상황에서 static 변수를 선언할 수 있다

[목차로](#목차)




## 메소드 오버로딩과 String 클래스
- 메소드 오버로딩 = 동일한 이름의 메소드를 둘 이상 동시에 정의하는것.
- 메소드의 매개변수 선언(개수 또는 자료형)이 다르면 메소드 오버로딩 성립.
- 오버로딩 된 메소드는 호출시 전달하는 인자를 통해서 구분된다.

[목차로](#목차)




## String 클래스
- String는 문자열 이다.
- String의 인스턴스에 저장된 문자열은 데이터 변경이 불가능하다.
- 동일한 문자열의 인스턴스를 하나만 생성해서 공유한다.

[목차로](#목차)




## StringBuilder와 StringBuffer 클래스
- StringBilder는 문자열의 저장 및 변경을 위한 메모리 공간을 지니는 클래스
- 문자열 데이터의 추가를 위한 append와 삽입을 위한 insert 메소드 제공
- 추가되는 데이터 크기에 따라서 버퍼의 크기가 자동으로 확장된다.
- 생성자를 통해서 초기 버퍼의 크기를 지정할 수 있다.
- 문자열의 복잡한 조합의 과정에서는 StringBuilder의 인스턴스가 활용된다.
- 때문에 추가로 생성되는 인스턴스의 수는 최대 두 개 이다.

[목차로](#목차)



## 콘솔 출력
- '%d' 10진수 정수 형태의 출력
- '%o' 8진수 정수 형태의 출력
- '%x' 16진수 정수 형태의 출력
- '%f' 실수의 출력
- '%e' e 표기법 기반의 실수 출력
- '%g' 출력의 대상에 따라서 %e 또는 %f 형태의 출력
- '%s' 문자열 출력
- %c' 문자 출력

[목차로](#목차)
