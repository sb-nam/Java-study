# Java 공부 정리

# 목차
- [Java란 무엇인가](#Java란-무엇인가)
- [형변환](#형변환)
- [변수](#변수)
- [String 연결](#String-연결)
- [연산자](#연산자)
- [관계 연산자](#관계-연산자)
- [논리 연산자](#논리-연산자)
- [비트 연산자](#비트-연산자)
- [시프트 연산자](#시프트-연산자)
- [증감 연산자](#증감-연산자)
- [if문](#if문)
- [삼항 연산자](#삼항-연산자)
- [switch 와 break 문](#switch-와-break-문)
- [while 문](#while-문)
- [do while 문](#do-while-문)
- [for문](#for문)
- [배열](#배열)
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
- [연습문제](#연습문제)
- [예외처리](#예외처리)


## Java란 무엇인가

- 객체 지향 언어

[목차로](#목차)

## 형변환

```java

//형변환 작은 범위 + 큰범위 계산시 자동으로 큰쪽으로 변환됨.

public class TypeConversion {

	public static void main(String[] args) {
		
		byte b = 127; // 현재 int 형 127. byte형 으로 바꾸고 싶다면 byte 표시가 필요.
		int i = 100;
		
		System.out.println(b + i); // 227 
		System.out.println(10 / 4); // int 형으로 계산 되어 2
		System.out.println(10.0 / 4); // double형으로 계산 되어 2.5
		System.out.println((char)0x12340041); // char형 A
		System.out.println((byte)(b + i)); // 값이 짤려서 이상해짐 범위 벗어남.
		System.out.println((int)2.9 + 1.8); // int 2 + doubel 1.8
		System.out.println((int)(2.9 + 1.8)); // 2.9 + 1.8 = 4.7 - > int형으로 변환 4
		System.out.println((int)2.9 + (int)1.8); // int 2 + int 1 = 3
	
	}

}
```



## 변수
- **변수 : 프로그램 실행시 자료가 임시로 저장되는 공간
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

- `<` n1이 n2보다 작은가? 참이면 true, 거짓이면 false (n1 < n2)
- `>` n1이 n2보다 큰가? 참이면 true, 거짓이면 false (n1 > n2)
- `<=` n1이 n2보다 같거나 작은가? 참이면 true, 거짓이면 false (n1 <= n2)
- `>=` n1이 n2보다 같거나 큰가? 참이면 true, 거짓이면 false (n1 >= n2)
- `==` n1과 n2가 같은가? 참이면 true, 거짓이면 false (n1 == n2)
- `!=` n1과 n2가 다른가? 참이면 true, 거짓이면 false (n1 != n2)

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



## 시프트 연산자

-`a >> b` a의 각 비트를 오른쪽으로 b번 시프트한다. 취상위 비트는 시프트 전의 최상위 비트로 채운다.
-`a >>> b` a의 각 비트를 오른쪽으로 b번 시프트한다. 최상위 비트의 빈자리는 항상 0으로 채운다.
-`a << b` a의 각 비트를 왼쪽으로 b번 시프트한다. 최하위 비트의 빈자리는 항상 0으로 채운다.

```java



public class BitShiftOperator {

	public static void main(String[] args) {
		
		short a = (short)0x55ff;
		short b = 0x00ff;
		
		//비트 연산
		System.out.printf("%x\n", a & b);
		System.out.printf("%x\n", a | b);
		System.out.printf("%x\n", a ^ b);
		System.out.printf("%x\n", ~ a);
		
		byte c = 20; // 0x14
		byte d = -8; // 0xf8
		
		//시프트 연산
		System.out.println(c << 2); // c 를 왼쪽으로 2번 시프트
		System.out.println(c >> 2); // c 를 오른쪽으로 2번 시프트
		System.out.println(d >> 2); // d 를 오른쪽으로 2번 시프트
		System.out.printf("%x\n", d >>> 2); // d를 오른쪽으로 2번 시프트
	}

}


```

[목차로](#목차)



## 증감 연산자

`a++` a를 1증가 하고 증가 전의 값을 반환/ `++a` a를 1증가 하고 증가된 값 반환.
`a--` a를 1감소하고 감소 전의 값을 반환/ `--a` a를 1감소하고 감소된 값 반환.

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

public class MultipleOfThree {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println("수를 입력 하시오.");
		int num = sc.nextInt();
		
		if(num % 3 == 0) {
			
			System.out.println("3의 배수 입니다.");
			
		} else {
			
			System.out.println("3의 배수가 아닙니다.");
			
		}

	}

}
```


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

```java


public class GradeSwitch {

	public static void main(String[] args) {
		
		char grade = 'C';
		
		switch (grade) {
		
		case 'A':
		case 'B':
			System.out.println("참 잘하였습니다.");
		        break;
		
		case 'C' :
		case 'D' :	
			
			System.out.println("좀 더 노력하세요.");
			break;
		
		case 'F' :
			System.out.println("다음 학기에 다시 수강하세요.");
			break;
			
		default :
			System.out.println("잘못된 학점 입니다.");
				
		}

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

```java

class WhileEx {

	public static void main(String[] args) {

		int i = 1; // 초기 값
		int j = 1;

		while (i <= 5) { // 조건이 참일 때 반복

			while (j <= 3) {

				System.out.println("i : " + i + ", j : " + j);

				j++;

			}

			i++;
			j = 1;

		}

	}

}
```

```java


class WhileEx2 {

	public static void main(String[] args) {

		int i = 2;
		int j = 1;

		while (i <= 9) {

			System.out.println(i + " 단 ");
					
			while (j <= 9) {
				
				System.out.println(i + " * " + j + " = " + i * j);
				
				j++; // j 가 10이 되어 반복문 빠져나감.
				
			}
			
			i++;
			j = 1; // j = 10 을 1부터 다시 반복하기 위해 1로 초기화.
		}

	}

}

```

```java

import java.util.Scanner;

public class Grading {

	public static void main(String[] args) {
		
		char grade;
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println("점수를 입력 하시오.");
		
		while (sc.hasNext() ) {
			
			int score = sc.nextInt();
			
			if (score >= 90)  // score가 90 이상.
				
				grade = 'A';
			
			else if (score >= 80) // score가 80 이상.
				
				grade = 'B';
			
			else if (score >= 70) // score가 70 이상.
				
				grade = 'C';
			
			else if (score >= 60) // score가 60 이상.
				
				grade = 'D';
			
			else  // score가 60 미만.
				
				grade = 'F';
			
			System.out.println("학점은 : " + grade + "입니다.");
		}
		
		sc.close();

	}

}

```


[목차로](#목차)


## do while 문

```java


public class DoWhileSample {

	public static void main(String[] args) {
		
		char a = 'a';
		
		do {
			
			System.out.print(a); // 작업문 
			a = (char)(a + 1);   //
			
		} while (a <= 'z');  // 조건식

	}

}

```


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

```java


class DoWhileEx {

	public static void main(String[] args) {
		
		int i = 1; // 초기 값
		int j = 1;
		
		do {
			
			do {
				
				System.out.println("i : "+ i + ", j : "+j);
				
				j++;
				
			}while(j <= 3);
			
			j = 1;
			i++;
			
		}while(i <= 5); // 조건식

	}

}

```

```java


class DoWhileEx2 {

	public static void main(String[] args) {
		
		int i = 2;
		int j = 1;
		
		do {
			
			System.out.println(i + " 단 ");
			
			do {
				
				System.out.println(i + " * " + j + " = " + i * j );
				
				j++; // j 가 10이 되어 반복문 빠져나감.
				
			}while(j <= 9);
			
			i++;
			j = 1; // j = 10 을 1 로 초기화 하여 다시 반복 조건 충족.
			
		}while(i <= 9);

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
        int total = 0;

		for (int i = 1; i <= 100; i++) {
			
			if (i % 7 == 0) {
				
				System.out.println(i);
                
				count++;
				total += i;
			}
					
		}
		
		System.out.println(" 7의 배수의 총합 : " + total);
		System.out.println(" 7의 배수의 개수 : " + count);

	}

}
```

```java

import java.util.Scanner;

// Sanner를 이용하여 정수를 입력받고 * 을 역삼각 형으로 출력하라.

class InvertedTriangle {

	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);

		System.out.println("숫자를 입력하세요 : ");
		int num = sc.nextInt();

		for (int i = num; i >= 1; i--) {

			for ( int j = i; j >=1; j--) {
				
				System.out.print("*");
			}
			
			System.out.println();

		}
		
		sc.close();
				
	}

}

```

```java


public class StarPrint2 {

	public static void main(String[] args) {
		
		for(int i = 1; i <= 5; i++) {
					
			for(int j = 1; j <= i; j++) {
				
				System.out.print("*");
				
			}
			
			System.out.println();
		}

	}

}
```

```java


public class StarPrint2 {

	public static void main(String[] args) {
		
		for(int i = 1; i <= 5; i++) {
					
			for(int j = 5; j >= i; j-- ) {
				
				System.out.print("*");
				
			}
			
			System.out.println();
		}

	}

}

```

```java

import java.util.Scanner;

class SumOfMul {

	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);

		System.out.println("숫자 입력 하세요 : ");
		int fir = sc.nextInt();

		int sum = 1;

		if (fir <= 10 && fir > 0) {

			for (int i = 1; i <= fir; i++) {

				sum *= i;
				
			}
			
			System.out.println(fir + "!" + " 은 " + "'"+ sum + "'"  + " 입니다.");

		} else {

			System.out.println("오류 입니다.");
		}

	}

}

```
[목차로](#목차)

## 배열

- 인덱스와 인덱스에 대응하는 데이터들로 이루어진 자료 구조.
- 배열은 같은 타입의 데이터들이 순차적으로 저장되는 공간.


```java

class ArrayEx {

	public static void main(String[] args) {
		
		int arr [] = { 10, 20, 30, 40, 50, 60, 70, 80, 90};
		
		for(int i = 0; i < arr.length; i++) {
			
			System.out.println(arr [ i ]);
		}
	}

}

```

```java


public class ArrayEx2 {
	
	public static void main(String[] args) {
		
		int arr [] = new int [5]; 
		// arr 이라는 이름의 배열을 만들고
		// 변수의 개수를 5개 만들었다.
		// new 키워드는 참조형 자료형이기 때문에 사용 되었다.
		
		int arr2 [] = { 10,20,30,40 };
		// 10,20,30,40으로 이루어진 배열을 만들어라.
		// arr2 라는 이름으로 배열을 만들었다.
	}

}

```

```java

import java.util.Scanner;

class ArrayEx3 {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
									
		int arr [] = new int [5];
		
		int sum = 0;
						
		double aver = 0;
		
		for(int i = 0; i < arr.length; i++) {
			
			System.out.print(i + 1 + "번 째 수 입력 :");
			arr [i] = sc.nextInt();
			
			sum += arr [i];
							
		}
		
		aver = sum / arr.length;
		
		System.out.println("배열의 합 : " + sum);
		System.out.println("배열의 평균 :" + aver);
		
		int max = arr [0];
		int min = arr [0];
		
		for(int i = 0; i < arr.length; i++) {
			
			if(max < arr [i]) {
			
			   max = arr [i];
				
			} else if(min > arr [i]) {
				
				min = arr [i];
			}
							
		}
		
		System.out.println("최대 값 :" + max);
		System.out.println("최소 값 :" + min );
		
		sc.close();
	}

}
```


```java
public class MaxMinExample {

    public static void main(String[] args) {
        int[] arr = new int[]{1, 2, 3, 4, 5};
        int max = arr[0];
        int min = arr[0];

        for(int i=0; i<arr.length; i++) {
            max = Math.max(max, arr[i]);
            min = Math.min(min, arr[i]);
        }

        System.out.println("Max value :" + max); // print 5
        System.out.println("Min value :" + min ); // print 1
    }
}

```

```java

// 양의 정수 10개를 입력받아 배열에 저장하고, 배열에 있는 3의 배수만 출력하라.

import java.util.Scanner;

class ArrayExe {

	public static void main(String[] args) {

		int array[] = new int[10];

		Scanner sc = new Scanner(System.in);

		System.out.println("정수를 10개 입력 하세요 : ");

		for (int i = 0; i < array.length; i++) {

			array[i] = sc.nextInt();

		}
		for (int i = 0; i < array.length; i++) {
			
			if(array [i] %  3 == 0) {
			
				System.out.println(" 3의 배수는 : " + array [i]);
			}
		}
		
		sc.close();

	}

}
```

```java

//배열과 반복문을 이용하여 금액을 입력 받아 필요한 화폐 단위의 개수를 구하라.

import java.util.Scanner;

class ArrayExe2 {

	public static void main(String[] args) {

		int price;
		int money[] = { 50000, 10000, 1000, 500, 100, 50, 10, 1 };

		Scanner sc = new Scanner(System.in);

		System.out.println("금액을 입력하시오.");
		price = sc.nextInt();
		
		for(int i = 0; i < money.length; i ++) {
			
			if(price / money[i] != 0) {
				
				System.out.println(money [i] + "원 짜리 : " + (price / money [i]) + "개" );
				
				price = (price % money [i]);
			}
		}
		
		sc.close();

	}

}
```

`친구의 feedback`

*MAX와 MIN 값을 구하는 방법은 Math class에서 제공하는 함수를 사용할 수 있습니다.*
*Math class에서 제공하는 max와 min 함수의 내부를 살펴보면 다음과 같은 코드로 이루어져 있습니다.*
*코드를 작성하고, ctrl을 누른상태로 함수명을 클릭하면 내부 코드를 볼 수 있으니, 코드를 살펴보시기 바랍니다*
```java
class Math {

    ...
   
    public static int max(int a, int b) {
        return (a >= b) ? a : b;
    }
    
    public static int min(int a, int b) {
        return (a <= b) ? a : b;
    }
    
    ...
    
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

```java

import java.util.Scanner;

class SumOfInt {

	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);

		System.out.println(" 첫 번째 수를 입력 하세요 : ");
		int num1 = sc.nextInt();

		System.out.println(" 두 번째 수를 입력 하세요 : ");
		int num2 = sc.nextInt();

		int sum = 0;

//		if (num1 < num2) {
//
//			for (int i = num1; i <= num2; i++) {
//
//				sum += i;
//
//			}
//
//		} else if (num1 > num2) {
//
//			for (int j = num2; j <= num1; j++) {
//
//				sum += j;
//			}
//
//		} else {
//			
//			sum = num1 + num2;
//		}

//		int i = num1;
//		int j = num2;
//		if (num1 < num2) {
//		
//			while (i <= num2) {
//				
//				sum += i;
//				i++;	
//							
//			}
//		} else if(num1 > num2) {
//			
//			while ( j <= num1) {
//				
//				sum += j;
//				j++;
//				
//			}
//									
//		} else {
//			
//			sum = num1 + num2;
//		}
		
		int i = num1;
		int j = num2;
		
		if (num1 < num2) {
			
			do {
				
				sum += i;
				i++;
				
			}while (i <= num2);
		
		} else if (num1 > num2) {
			
			do {
				
				sum += j;
				j++;
				
			}while (j <= num1);
			
		} else {
			
			sum = num1 + num2;
		}
		
		System.out.println(" 두 숫자 사이의 합 : " + num1 + " + " + num2 + " = " + sum);
		
		sc.close();
	}

}

3가지 반복문을 사용 하여 두 숫자 사이의 합 을 구해 보았다.

```

[목차로](#목차)



## 반복문의 중첩
- 가장 많이 등장하는 중첩은 for문의 중첩!

```java


public class NestedLoop {

	public static void main(String[] args) {
		
				
		for(int i = 1; i < 10; i++) { // 1단에서 9단
			
			for(int j =1; j < 10; j++) { // 각 단의 구구셈
				
				System.out.print(i + " * " + j + " = " + i * j); // 구구셈 출력
				System.out.print('\t'); // 하나씩 탭으로 띄우기
			
			}
			System.out.println(); // 한 단이 끝나면 줄 바꿈
		}

	}

}


```


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

```java

import java.util.Scanner;

class StarPrint1 {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println("가로 길이를 입력 하세요 :");
		int  n = sc.nextInt();
		
		System.out.println("세로 길이를 입력 하세요 :");
		int  m = sc.nextInt();
						
		if( n <= 1000 && m <= 1000) {
			
			for(int i = 1; i <= m; i++ ) {
				
				for(int j = 1; j <= n; j++) {
					
					System.out.print("*");
				}
				
				System.out.println();
			}
		}
		
		sc.close();
	}

}

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

class MethodExe {

	public static void main(String[] args) {

		System.out.println("메소드 호출");

		hello();
		goodBye();

		System.out.println("프로그램 종료");
	}

	private static void hello() {

		System.out.println("hello 호출 영역");
		System.out.println("하이! 헬로! 안녕?!");
		System.out.println("hello 끝나는 부분");

	}

	private static void goodBye() {

		System.out.println("goodBye 호출");
		System.out.println("안녕히 가세요!");
		System.out.println("goodBye 끝나는 부분!");

	}

}

```

```java

import java.util.Scanner;

class MethodExe2 {

	public static void main(String[] args) {
		
		int num1, num2;
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println(" 첫 번째 수 입력 : ");
		num1 = sc.nextInt();
		
		System.out.println(" 두 번째 수 입력 : ");
		num2 = sc.nextInt();
		
		sum(num1, num2);
		sub(num1, num2);
		mul(num1, num2);
		div(num1, num2);

	}
		
	private static void sum(int num1,int num2) {
		
		int value;
		value = num1 + num2;
		
		System.out.println(" 두 수의 합은 : " + value );
		
	}
	
	private static void sub(int num1, int num2) {
		
		int value;
		value = num1 - num2;
		
		System.out.println(" 두 수의 차이는 : " + value );
		
	}
	
	private static void mul(int num1, int num2) {
		
		int value;
		value = num1 * num2;
		
		System.out.println(" 두 수의 곱은 : " + value);
		
	}
	
	private static void div(int num1, int num2) {
		
		int value;
		value = num1 / num2;
		
		System.out.println(" 두 수의 나눗셈은 : " + value);
		
	}

}

```


```java

import java.util.Scanner;

class Solution {

	public static void main(String[] args) {

		long num1, num2, solution;

		Scanner sc = new Scanner(System.in);

		System.out.println("첫 번째 숫자 입력 : ");
		num1 = sc.nextInt();

		System.out.println("두 번째 숫자 입력 : ");
		num2 = sc.nextInt();

		solution = sum(num1, num2);
		System.out.println("두 숫자 사이의 합은 : " + solution);

	}

	private static long sum(long num1, long num2) {

		long solution = 0;

		if (num1 < num2) {

			for (long i = num1; i <= num2; i++) {

				solution += i;

			}
		}

		if (num1 > num2) {

			for (long j = num2; j <= num1; j++) {

				solution += j;

			}

		} 

		return solution;
	}

}

```

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

 private static 리턴값의 타입  함수명(타입 변수명, 타입 변수명) {

    함수의 명령문
     
    return 값;


}

리턴값의 타입(void) - 리턴 값을 반환 하지 않는다.
int, double -- 각각 int, double 타입을 반환한다.


```java

import java.util.Scanner;

class MethodExe2 {

	public static void main(String[] args) {
		
		int num1, num2, result;
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println(" 첫 번째 수 입력 : ");
		num1 = sc.nextInt();
		
		System.out.println(" 두 번째 수 입력 : ");
		num2 = sc.nextInt();
		
		result = sum(num1, num2);
		System.out.println(" 두 수의 합 : " + result);
		
		result = sub(num1, num2);
	    System.out.println(" 두 수의 차 : " + result);
		
	    result = mul(num1, num2);
	    System.out.println(" 두 수의 곱 : " + result);
		
	    div(num1, num2);
	    System.out.println(" 두 수의 나눗셈 : " + result);

	}
		
	private static int sum(int num1,int num2) {
		
		int value;
		value = num1 + num2;
		
		return value;
		
	}
	
	private static int sub(int num1, int num2) {
		
		int value;
		value = num1 - num2;
		
		return value;
		
	}
	
	private static int mul(int num1, int num2) {
		
		int value;
		value = num1 * num2;
		
		return value;
		
	}
	
	private static int div(int num1, int num2) {
		
		int value;
		value = num1 / num2;
		
		return value;
		
	}

}


```
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
- 클래스는 (생성자, 필드, 메소드) 를 필수로 가져가야한다.

```java

package Prcatice;

public class Circle {

	public int radius; // 원의 반지름.
	public String name; // 원의 이름.
	
	public Circle() { // 원의 생성자 메소드.
		
		
	}
	public double getArea() { // 원의 면적 계산 메소드.
		
		return 3.14 * radius * radius;
	}

	
}
```

```java

package Prcatice;

public class CircleExe {

	public static void main(String[] args) {
		
		Circle pizza;         // Circle 객체에 대한 래퍼런스 변수.
		pizza = new Circle(); // Circle 객체 생성.
		
		pizza.radius = 10; // radius 필드에 10 저장.
		pizza.name = "자바피자"; // name 필드에 "자바피자" 저장.
		pizza.getArea(); // pizza 객체의 면적 알아내기.
		
		System.out.println("피자의 넓이는 " + pizza.getArea() );

	}

}

```

```java

class Student {
	
	String name;
	String bloodType;
	String gender;
	
	int height;
	int weight;
	
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public String getBloodType() {
		return bloodType;
	}
	public void setBloodType(String bloodType) {
		this.bloodType = bloodType;
	}
	public String getGender() {
		return gender;
	}
	public void setGender(String gender) {
		this.gender = gender;
	}
	public int getHeight() {
		return height;
	}
	public void setHeight(int height) {
		this.height = height;
	}
	public int getWeight() {
		return weight;
	}
	public void setWeight(int weight) {
		this.weight = weight;
	}
	
	
}

```

```java


class StudentObjectExe {

	public static void main(String[] args) {
		
		Student std = new Student();
		
		std.setName("홍길동");
		std.setGender("남자");
		std.setBloodType("O");
		std.setHeight(170);
		std.setWeight(75);
		
		String name = std.getName();
		String gender = std.getGender();
		String bloodType = std.getBloodType();
		
		int height = std.getHeight();
		int weight = std.getWeight();
		
		printAccount(std);
	}

	private static void printAccount(Student std) {
		
		System.out.println("이름 : "+ std.getName() );
		System.out.println("성별 : "+ std.getGender() );
		System.out.println("혈액형 : "+ std.getBloodType() );
		System.out.println("키 : "+ std.getHeight() );
		System.out.println("몸무게 : "+ std.getWeight() );
	}

}

```

```java


class Car {

	int price;
	int drive;
	double fuelEf;
		
	String gearType;
	String fuelType;
	String carType;
	
	public int getPrice() {
		return price;
	}
	public void setPrice(int price) {
		this.price = price;
	}
	public int getDrive() {
		return drive;
	}
	public void setDrive(int drive) {
		this.drive = drive;
	}
	public double getFuelEf() {
		return fuelEf;
	}
	public void setFuelEf(double fuelEf) {
		this.fuelEf = fuelEf;
	}
	public String getGearType() {
		return gearType;
	}
	public void setGearType(String gearType) {
		this.gearType = gearType;
	}
	public String getFuelType() {
		return fuelType;
	}
	public void setFuelType(String fuelType) {
		this.fuelType = fuelType;
	}
	public String getCarType() {
		return carType;
	}
	public void setCarType(String carType) {
		this.carType = carType;
	}
	
	
}

```

```java


public class CarObject {

	public static void main(String[] args) {
		
		Car car = new Car();
		
		car.setPrice(27000000);
		car.setDrive(100000);
		car.setFuelEf(14.0);
		car.setGearType("auto");
		car.setCarType("suv");
		car.setFuelType("가솔린");
		
		int price = car.getPrice();
		int drive = car.getDrive();
		double fuelEf = car.getFuelEf();
		
		String gearType = car.getGearType();
		String carType = car.getCarType();
		String fuelType = car.getFuelType();
		
		System.out.println("가격 : "+ price);
		System.out.println("주행거리 : "+ drive);
		System.out.println("연비 : "+ fuelEf);
		System.out.println("기어타입 : "+ gearType);
		System.out.println("차종 : "+ carType);
		System.out.println("연료방식 : "+ fuelType); 
	}

}

```


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

```java


class Song {

	String title;
	String artist;
	String country;
	
	int year;
			
	public Song() {
		
		
	}
	
	public Song(String title, String artist, String country, int year) {
		
		this.title = title;
		this.artist = artist;
		this.country = country;
		this.year = year;
	}
	
	public void show() {
		
		System.out.println(year + "년 " + country + "국적의 "+ artist + "가 부른 "+ title);
	}

}


```

```java


class SongObject {

	public static void main(String[] args) {
		
		Song sg = new Song("Dancing Queen", "ABBA", "스웨덴",1978);
				
		sg.show();
				
	}

}

```
[목차로](#목차)




## 생성자 
- **생성자는 인스턴스 하나당 1번만 호출된다.!
- 자바 인스턴스 생성시 반드시 생성자는 호출된다.
- 생성자의 조건 1.클래스의 이름과 동일한 매소드
- 반환형이 선언되어 있지 않으면서, 반환하지 않는 매소드
- 객체를 생성과 동시에 원하는 값으로 필드값을 설정하는 기능을 가진 함수.

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

```java


class StudentObjectExe {

	public static void main(String[] args) {
		
		Student std1 = new Student("홍길동", "남", "O", 170, 75);
                Student std2 = new Student("박길순", "여", "A", 165, 50); // Student객체 괄호안의 자료 타입을 맞춰 줘야한다.
		
		printAccount(std1);
		printAccount(std2);
	}

	private static void printAccount(Student std) {
		
		System.out.println("이름 : "+ std.getName() );
		System.out.println("성별 : "+ std.getGender() );
		System.out.println("혈액형 : "+ std.getBloodType() );
		System.out.println("키 : "+ std.getHeight() );
		System.out.println("몸무게 : "+ std.getWeight() );
	}

}

```

```java

class Student {
	
	private String name;
	private String bloodType;
	private String gender;
	
	private int height;
	private int weight;
	
	public Student(String name, String gender, String bloodType, int height, int weight) { // 이것과 자료 타입, 순서 일치 시켜야함.
		
		this.name = name;
		this.gender = gender;
		this.bloodType = bloodType;
		this.height = height;
		this.weight = weight;
	}
	
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public String getBloodType() {
		return bloodType;
	}
	public void setBloodType(String bloodType) {
		this.bloodType = bloodType;
	}
	public String getGender() {
		return gender;
	}
	public void setGender(String gender) {
		this.gender = gender;
	}
	public int getHeight() {
		return height;
	}
	public void setHeight(int height) {
		this.height = height;
	}
	public int getWeight() {
		return weight;
	}
	public void setWeight(int weight) {
		this.weight = weight;
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

`친구의 feedback`

*for문 예제에서 해보았던 starPrint 문제를 StringBuilder를 통해 풀어볼 수 있습니다.*    
```java
// 기존의 방법
class StarPrint {
    public static void main(String[] args) {
	for(int i=1; i<=5; i++) {
            for(int j=5; j>=i; j--) {
	        System.out.println("*");
            }

	    System.out.println();
        }
    }
}

// StringBuilder를 사용한 방법

class StarPrint {
    public static void main(String[] args) {
        StringBuilder stringBuilder = new StringBuilder();
        for(int i=1; i<=5; i++) {
            for(int j=5; j>=i; j--) {
                stringBuilder.append('*');
            }

            stringBuilder.append('\n');
        }

        System.out.println(stringBuilder.toString());
    }
}
```
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


## 연습문제

```java

//$1 = 1100, 원화를 입력받아 달러로 바꾸어 출력하라.

import java.util.Scanner;

public class DallorChange {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
					
		System.out.println("원화를 입력하세요.");
		int won = sc.nextInt();
		double dallor = won / 1100;
		
		System.out.println(won + "원은 " + "$" + dallor + "입니다.");
		
		sc.close();
	}

}
```

```java
// 정수 3개 입력 받아 중간 값 구하기.

import java.util.Scanner;

public class ScannerExe {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println(" 첫번째 정수를 입력하시오.");
		int a = sc.nextInt();
		
		System.out.println(" 두번째 정수를 입력하시오.");
		int b = sc.nextInt();
		
		System.out.println(" 세번째 정수를 입력하시오.");
		int c = sc.nextInt();
		
		int result = 0;
		if(a < b && b < c || c < b && b < a) {
			
			result = b;
		}
		if(b < a && a < c || c < a && a < b) {
			
			result = a;
			
		} 
		if(a < c && c < b || b < c && c < a) {
			
			result = c;
			
		}
		
		System.out.println("중간 값은 : " + result);
		

		sc.close();
	}

}

```

```java

// 2자리의 수 (10 ~ 99)를 입력 받고, 십의 자리와 1의 자리가 같은지 판별하라.

import java.util.Scanner;

public class ScannerExe2 {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println("10~99 사이의 숫자를 입력하시오.");
		int num = sc.nextInt();
		
		if(num % 11 == 0) {
			
			System.out.println(" 10의 자리와 1의 자리가 같습니다.");
		
		} else {
			
			System.out.println(" 10의 자리와 1의 자리가 다릅니다.");
		}

		sc.close();
	}

}
```
```java

//삼각형의 변의 길이를 나타내는 정수 3개를 입력받고 그 수로 삼각형을 만들수 있는지 판별하라.
//삼각형이 되려면 두 변의 합이 다른 한 변보다 커야한다.

import java.util.Scanner;

public class ScannerExe3 {

	public static void main(String[] args) {
		
		int temp;
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println("첫 번째 정수를 입력하시오.");
		int a = sc.nextInt();
		
		System.out.println("두 번째 정수를 입력하시오.");
		int b = sc.nextInt();
		
		System.out.println("세 번째 정수를 입력하시오.");
		int c = sc.nextInt();

		// a < b
		if(a > b) {
			
			temp = a;
			a = b;
			b = temp;
			
		}
		// a < c
		if (a > c) {
			
			temp = a;
			a = c;
			c = temp;
		
		}
		// b < c
		if (b > c) {
			
			temp = b;
			b = c;
			c = temp;
			
		}
		// 치환하여 c를 항상 제일크게 만듬. 삼각형의 가장 큰 변은 두수의 합보다 항상 커야 삼각형이 된다. 
		if( (a + b) <= c) {
			
			System.out.println("삼각형이 안됩니다.");
		
		} else {
			
			System.out.println("삼각형이 됩니다.");
		}
		
		sc.close();
	}

}

```

```java

import java.util.Scanner;

public class RockScissorsPaper {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println("철수의 가위, 바위, 보, 를 입력 하시오.");
		String str1 = sc.next();
		System.out.print("철수 >> " + str1 + " ,");
		
		System.out.println("영희의 가위, 바위, 보, 를 입력 하시오.");
		String str2 = sc.next();
		
		if (str1.equals("가위")) { 
				
			if (str2.equals("가위"))
				
				System.out.println("비겼습니다.");
			
			else if (str2.equals("바위"))
				
				System.out.println("졌습니다.");
			
			else
				
				System.out.println("이겼습니다.");
			 
		} else if (str1.equals("바위")) {
			
			if (str2.equals("바위"))
				
				System.out.println("비겼습니다.");
			
			else if (str2.equals("가위"))
				
				System.out.println("이겼습니다.");
			
			else 
				
				System.out.println("졌습니다.");
			
		} else if (str1.equals("보")) {
			
			if (str2.equals("보"))
				
				System.out.println("비겼습니다.");
			
			else if (str2.equals("바위"))
				
				System.out.println("이겼습니다.");
			
			else 
				
				System.out.println("졌습니다.");
		}
			

	}

}

```

`친구의 피드백`
*코드를 보면, 문자열을 비교할 때 `equals` 함수를 사용하고 있습니다.*
*왜 `equals`를 사용할까요? `==`을 사용하면 안될까요?*
*다음의 코드는 둘다 동일하게 `true`가 나옵니다.*
*`equals`를 사용해야 하는 이유에 대해 생각해보면 좋을 것 같습니다.*
```java
class Main {
    public static void main(String[] args) {
    	String text1 = "a";
	String text2 = "a";
	
	System.out.println(text1 == text2); // true
	System.out.println(text1.equals(text2)); // true
    }
}
```



```java

import java.util.Scanner;

public class Season {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		int month;
		
		System.out.println("달을 입력하세요.(1~12)");
		month = sc.nextInt();
		
		if (month >= 3 && month <= 5)
			
			System.out.println("봄");
			
		else if (month >= 6 && month <= 8)
			
			System.out.println("여름");
		
		else if (month >= 9 && month <= 11) 
			
			System.out.println("가을");
		
		else if (month == 12 || month <= 2)
			
			System.out.println("겨울");
		
		else
			
			System.out.println("잘못 입력");

	}

}
```

```java


import java.util.Scanner;

public class Game369 {

	public static void main(String[] args) {

		int num;
		int count = 0;

		Scanner sc = new Scanner(System.in);

		System.out.println("1~99 사이의 정수를 입력하시오.");
		num = sc.nextInt();
			
		if (num % 10 == 3 || num % 10 == 6 || num % 10 == 9) {

			count++;
		}
		if (num / 10 == 3 || num / 10 == 6 || num / 10 == 9) 

			count++;
        
		if (count == 2) 

			System.out.println("박수 짝짝");
		else

			System.out.println("박수 짝");
		
		sc.close();
	}

}

```

```java 

import java.util.Scanner;

public class Calculation {

	public static void main(String[] args) {

		double num1, num2;
		String sign;

		Scanner sc = new Scanner(System.in);

		System.out.println("숫자를 입력하세요.");
		num1 = sc.nextDouble();

		System.out.println("연산 식을 입력하시오.");
		sign = sc.next();

		System.out.println("숫자를 입력하세요.");
		num2 = sc.nextDouble();

		if (sign.equals("+"))

			System.out.println(num1 + num2);

		else if (sign.equals("-"))

			System.out.println(num1 - num2);

		else if (sign.equals("*"))

			System.out.println(num1 * num2);

		if (sign.equals("/")) {

			if (num2 == 0) {
				System.out.println("0으로 나눌수 없습니다.");
				System.exit(0);
			}
			System.out.println(num1 / num2);

		} else

			System.out.println("잘못된 연산 입니다.");
			
		sc.close();	

	}

}




```

```java

import java.util.Scanner;

public class Calculation2 {

	public static void main(String[] args) {

		double num1, num2;
		String sign;

		Scanner sc = new Scanner(System.in);

		System.out.println("연산 >> ");
		num1 = sc.nextDouble();
		sign = sc.next();
		num2 = sc.nextDouble();

		switch (sign) {

		case "+":

			System.out.println(num1 + num2);
			break;

		case "-":

			System.out.println(num1 - num2);
			break;

		case "*":

			System.out.println(num1 * num2);
			break;

		case "/":

			if (num2 == 0) {
						
				System.out.println("0으로 나눌수 없습니다.");
			    System.exit(0);
				
			}
			System.out.println(num1 / num2);
			break;
		
		default :
			
			System.out.println(" 잘못된 연산 입니다.");
		}
		
		sc.close();
	}

}

```

```java


public class ForSample {

	public static void main(String[] args) {
		
		int i, j;
		
		for (j = 0, i = 1; i <= 10; i++) {
			
			j = j + i;
			
			System.out.print(i);
			
			if (i == 10) {
				
				System.out.print(" = ");
				System.out.print(j);
			
			} else
				
				System.out.print(" + ");
		}

	}

}
```

```java

import java.util.Scanner;

public class WhileSample {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		int count = 0; // count는 입력된 정수의 개수
		double sum = 0; // sum은 합
		
		System.out.println("정수를 입력하고 마지막에 -1 을 입력하세요.");
		int n = sc.nextInt(); // 정수 입력
		
		while (n != -1) { // -1 이 되면 while문을 벗어남
			
			sum = sum + n;
			count++;
			n = sc.nextInt(); //정수 입력
		}
		if (count == 0) {
			
			System.out.println("입력된 정수가 없습니다.");
			
		} else {
			
			System.out.print("정수의 개수는 " + count + " 개 이며 ");
			System.out.println("평균은 " + (double)sum / count);
		}
		

	}

}
```

```java

import java.util.Scanner;

public class ContinueExe {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println("정수를 5개 입력하세요.");
		
		int sum = 0;
		
		for(int i = 0; i <= 5; i++) {
			
			int n = sc.nextInt(); // 키보드에서 정수 입력
			
			if(n <= 0)
				
				continue; // 양수가 아닌경우 다음 반복으로 진행
		
			else
				
				sum = sum + n; // 양수인 경우 덧셈
		}
		
		System.out.println("양수의 합은 : " + sum);

		sc.close();
	}

}
```

```java


import java.util.Scanner;

public class ArrayExe {

	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);
		
		int intArray[] = new int [5]; // 5개의 공간 생성
		int max = -1;
		
		System.out.println("0 보다 큰 숫자 입력");
		
		for(int i = 0; i < 5; i++) {
			
			intArray[i] = sc.nextInt();
			
			if(intArray[i] > max) { // 현재 max보다 intArray가 클때
				
				max = intArray[i]; // intArray갑 max로 넣어줌
			}
			System.out.print("입력된 수에서 가장 큰 수는 " + max + " 입니다.");
		}

		sc.close();
	}

}

```

```java


public class ScoreAverage {

	public static void main(String[] args) {

		double score[][] = { { 3.3, 3.4 }, 
				             { 3.5, 3.6 }, 
				             { 3.7, 4.0 }, 
				             { 4.1, 4.2 } };

		double sum = 0;

		for (int year = 0; year < score.length; year++) {

			for (int term = 0; term < score[year].length; term++) {

				sum = sum + score[year][term];

			}

		}

		int n = score.length;
		int m = score[0].length;

		System.out.println("4년 전체 평점 평균은 " + sum / (n * m));
	}
}
```

```java


public class SkewedArray {
	
	public static void main(String[] args) {
		
		int intArray[][] = new int[4][];
		intArray[0] = new int[3];
		intArray[1] = new int[2];
		intArray[2] = new int[3];
		intArray[3] = new int[2];
		
		for(int i = 0; i < intArray.length; i++) {
			
			for(int j = 0; j <intArray[i].length; j++) {
				
				intArray[i][j] = (i + 1) * 10 + j;
			}
		}
		for(int i = 0; i < intArray.length; i++) {
			
			for(int j = 0; j < intArray[i].length; j++) {
				
				System.out.print(intArray[i][j] + " ");
				
			}

			System.out.println();
		}
		
	}

}

```

```java


public class ReturnArray {
	
	static int[] makeArray() {
		
		int temp[] = new int[4];
		
		for(int i = 0; i < temp.length; i++) {
			
			temp[i] = i;
			
		}
		return temp;
	}
	public static void main(String[] args) {
		
		int intArray[];
		
		intArray = makeArray();
		
		for(int i = 0; i < intArray.length; i++) {
			
			System.out.println(intArray[i]);
		}
	}

}

```

```java


public class Array2d {

	public static void main(String[] args) {

		int n[][] = { { 1 }, { 1, 2, 3 }, { 1 }, { 1, 2, 3, 4 }, { 1, 2 } };

		for (int i = 0; i < n.length; i++) {

			for (int j = 0; j < n[i].length; j++) {

				System.out.print(n[i][j] + " " );
			}

			System.out.println();
		}

	}
}

```

```java

// abcde
// abcd
// abc           나오도록 출력하라.
// ab
// a

import java.util.Scanner;

public class ScannerChar {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
				
		System.out.println("소문자 알파벳을 입력하시오.");
		
		String str = sc.next();
		char ch = str.charAt(0);
		
		for(char i = ch; i >= 'a'; i--) { // ch를 1씩 낮추겠다
			
			for(char j = 'a'; j <= i; j++) { //j 값이 i를 따라가도록 낮춤.
				
				System.out.print(j);
			}
			
			System.out.println();
		}
		
		sc.close();
	}
}

```

```java

// 4 x 4 2차원 배열을 만들고 1~10까지 범위의 정수를
// 랜덤하게 생성하여 정수 16개를 배열에 저장하고
// 2차원 배열을 화면에 출력하라.
public class Array2dRandom {

	public static void main(String[] args) {
		
		int arr[][] = new int[4][4];
		
		for(int i = 0; i < arr.length; i++) {
			
			for(int j = 0; j < arr[i].length; j ++) {
				
				arr[i][j] = (int)(Math.random() * 10 + 1);
				System.out.print(arr[i][j] + " ");
			}
			
			System.out.println();
		}
	}
}

```
```java

// 반복문을 이용하여 369 게임에서 1 부터 99 까지의
// 박수 짝, 박수 짝짝을 출력하라
package Prcatice;

public class For369 {

	public static void main(String[] args) {

		int count = 0;

		for (int i = 1; i < 100; i++) {

			if (i % 10 == 3 || i % 10 == 6 || i % 10 == 9) {

				count++;

			}
			if (i / 10 == 3 || i / 10 == 6 || i / 10 == 9) {

				count++;

			}
			if (count == 1) {

				System.out.println(i + " 박수 짝");

			}

			else if (count == 2) {

				System.out.println(i + " 박수 짝짝");

			}
			count=0;
		}
	}

}
```

```java

//다음 코드와 같이 과목과 점수가 짝을 이루도록 2개의 배열을 작성하라.

package Prcatice;

import java.util.Scanner;

public class ArrayScore {

	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);

		String course[] = { "Java", "C++", "HTML5", "컴퓨터구조", "안드로이드" };

		int score[] = { 95, 88, 76, 62, 55 };

		System.out.println("과목을 입력하세요.");
		
		while (true) {
		
			String name = sc.next();
			
			if(name.equals("그만"))
				break;
						
			for(int i = 0; i < course.length; i ++) {
				
				if(course[i].equals(name)) {
					
					int n = score[i];
					
					System.out.println(course[i] + "의 점수는 " + score[i]);
				
				} else if (i == 4)
					
					System.out.println("과목이 없습니다.");
			}
			
			sc.close();
			
		}

	}

}

```

```java

//Goods 클래스를 만들고 String name;int price;
//int numberOfStock,int sold; 타입의 필드를 만들고 
//클래스 안에 메인 함수를 만든뒤 출력하라.
package Prcatice;

public class Goods {

	public String name;
	public int price;
	public int numberOfStock;
	public int sold;

	public static void main(String[] args) {
		
		Goods camera = new Goods();
		
		camera.name = "Samsung";
		camera.price = 400000;
		camera.numberOfStock = 30;
		camera.sold = 50;
		
		System.out.println("상품이름 : " + camera.name);
		System.out.println("가격 : " + camera.price);
		System.out.println("재고 : " + camera.numberOfStock);
		System.out.println("판매량 : " + camera.sold);
	}
	
}

```

```java

//클래스 MyExp를 작성하라 . 지수값을 표현하는 클래스로서 두개의 정수형 맴버 필드
//base와 exp를 가진다. base 와 exp는 양의 정수만을 가지는것으로 가정한다.
//정수값을 리턴 하는 getValue() 라는 메소드를 제공한다.

package Prcatice;

public class MyExp {

	public int base;
	public int exp;
	
	public MyExp(int base, int exp) {
		
		this.base = base;
		this.exp = exp;
		
	}
	public int getValue() {
		
		return (int) Math.pow(base, exp);
	}
	
}
```
```java

package Prcatice;

public class MyExp_Exe {

	public static void main(String[] args) {

		MyExp exp = new MyExp(2, 3);

		System.out.println(exp.base + "의 " + exp.exp + "승은 " + exp.getValue());

	}

}
```

```java

// 클래스 Triangle을 작성하라. Triangle은 밑변과 높이의 두 실수 필드를 가지며
// 각각 width,height 변수를 가진다. width와 height는 양수만읠 가지며 넓이를 
// 리턴하는 getArea() 메소드를 가진다. [ 삼각형의 넓이 : 밑변 x 높이 /2]
// 밑변 4.8 , 높이 3.4
package Prcatice;

public class Triangle {

	double width;
	double height;
	
	public Triangle(double width , double height) {
		
		this.width = width;
		this.height = height;
		
	}
	public double getArea() {
		
		return width * height / 2;
	}
}
```

```java

package Prcatice;

public class TriangleExe {

	public static void main(String[] args) {

		Triangle tri = new Triangle(4.8 , 3.4);
		
		System.out.println("삼각형의 넓이는 : " + tri.getArea() );
	}

}

```

```java

// Circle 클래스와 CircleManager 클래스를 완성하라.
// x, y, radius 값을 읽어 3개의 Circle 객체를 만들고 show() 이용하여 이들을 모두 출력하라.
package Prcatice;

import java.util.Scanner;

class Circle {

	private double x, y;
	private int radius;

	public Circle(double x, double y, int radius) {

		this.x = x;
		this.y = y;
		this.radius = radius;

	}

	public void show() {

		System.out.println("(" + x + ", " + y + ")" + radius);

	}

	public int radius() {

		return radius;

	}

}

public class CircleManager {

	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);

		Circle c[] = new Circle[3];

		int max = 0;

		for (int i = 0; i < c.length; i++) {

			System.out.print("x, y, radius >>");

			double x = sc.nextDouble();
			double y = sc.nextDouble();
			int radius = sc.nextInt();

			c[i] = new Circle(x, y, radius);
		}

		for (int i = 0; i < c.length; i++) {

			c[i].show();

		}
		for (int i = 0; i < c.length; i++) {

			if (max < c[i].radius()) {
				max = c[i].radius();

			}
		}
		for (int i = 0; i < c.length; i++) {

			if (max == c[i].radius()) {

				System.out.print("가장큰 면적의 원은 : ");
				c[i].show();

			}

		}

		sc.close();
	}

}
```


`친구의 Feedback`

*위의 코드를 보면, 코드가 한 곳에 밀집되어 있습니다.*
*코드들의 역할을 함수로 분리하는 것이 좋아보입니다.*

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        CircleManager circleManager = new CircleManager();
        circleManager.createCircle(3);
        circleManager.showHasCirclesInfo();
        circleManager.showInfoOfMaxRadiusCircle();
    }
}

class CircleManager {

    private Circle[] circles;

    public void createCircle(int needCircleCount) {
        // scanner를 사용하다가 에러가 발생될 것을 대비해 try catch 문을 사용할 수 있습니다.
        Scanner sc = null;
        try { 
            sc = new Scanner(System.in);

            circles = new Circle[needCircleCount];
            for(int i=0; i<needCircleCount; i++) {
                System.out.println("x, y, getRadius >>");
                double x = sc.nextDouble();
                double y = sc.nextDouble();
                int radius = sc.nextInt();
                circles[i] = new Circle(x, y, radius);
            }
        } catch (Exception e) {
            System.out.print("circle create fail : " + e.getMessage());
            circles = null;
        } finally {
            if(sc != null) {
                sc.close();
            }
        }
    }

    public void showHasCirclesInfo() {
        if(circles != null) {
            for(int i=0; i<circles.length; i++) {
                System.out.println(i + " index circle info : " + circles[i]);
            }
        } else {
            System.out.println("not has circles");
        }
    }

    public void showInfoOfMaxRadiusCircle() {
        Circle maxRadiusCircle = getMaxRadiusCircleInCircles();
        if(maxRadiusCircle != null) {
            System.out.println("max radius circle info : " + maxRadiusCircle);
        } else {
            System.out.println("not has circles");
        }
    }

    private Circle getMaxRadiusCircleInCircles() {
        if(circles != null) {
            int maxRadiusOfCircles = circles[0].getRadius();
            int maxRadiusCircleIndex = 0;
            for(int i=1; i<circles.length; i++) {
                int radiusOfCurrentCircle = circles[i].getRadius();
                if(maxRadiusOfCircles < radiusOfCurrentCircle) {
                    maxRadiusOfCircles = radiusOfCurrentCircle;
                    maxRadiusCircleIndex = i;
                }
            }

            return circles[maxRadiusCircleIndex];
        } else {
            return null;
        }
    }
}

class Circle {
    private double x, y;
    private int radius;

    public Circle(double x, double y, int radius) {
        this.x = x;
        this.y = y;
        this.radius = radius;
    }

    public int getRadius() {
        return radius;
    }

    @Override
    public String toString() {
        return"(" + x + ", " + y + ")" + radius;
    }
}

```
```java

//2개의 static을 가진 ArrayUtil 클래스를 만들어보자. concat() 와 print()
//를 작성하여 ArrayUtil 클래스를 완성하라.

package Prcatice;

class ArrayUtill {

	public static int [] concat(int[] a, int [] b) {
	
		int [] arr= new int [a.length + b.length];
		
		for(int i = 0; i < a.length; i ++) {
			
			arr[i] = a[i];
		}
		for(int j = a.length; j < a.length + b.length; j++) {
			
			arr[j] = b[j - a.length];
		}
	
		return arr;
	}
	
	public static void print(int [] a) {
		
		for(int i = 0; i < a.length; i ++) {
			
			System.out.print(a[i] + " ");
		}
		
	}
}

public class StaticEx {
	
	public static void main(String [] args) {
		
		int [] array1 = { 1, 5, 7, 9 };
		int [] array2 = { 3, 6, -1, 100, 77 }; 
		int [] array3 = ArrayUtill.concat(array1, array2);
		ArrayUtill.print(array3);
	}
}
```

```java

package Prcatice;

import java.util.Scanner;

class Dictionary {

	private static String[] kor = { "사랑", "아기", "돈", "미래", "희망" };
	private static String[] eng = { "love", "baby", "money", "future", "hope" };

	public static String kor2eng(String word) {

		Scanner sc = new Scanner(System.in);

		for (int i = 0; i < kor.length; i++) {

			if(word.equals(kor[i])) {
				
				return eng[i];
			}
			
			
		}
		return null;

	}
}

public class DicApp {

		Scanner sc = new Scanner(System.in);
		
		String word;
		
		public void run() {
			
			while(true) {
				
				System.out.print("한글단어?");
				word = sc.next();
				
				if(word.equals("그만"));
				
				String result = Dictionary.kor2eng(word);
				
				if(result == null) {
					
					System.out.println(word + " 은/는 제사전에 없습니다.");
				
				} else {
					
					System.out.println(word + " 은/는 " + result );
				}
			}
		}

		public static void main(String [] args) {
			
			DicApp da = new DicApp();
			
			System.out.println("한영 검색 프로그램 입니다.");
			
			da.run();
		}
		
	
}

```

```java

//다수의 클래스를 만들고 활용하는 연습하기.
//더하기 빼기 곱하기 나누기를 수행하는 각 클래스를 만들자.

package Prcatice;

import java.util.Scanner;

public class Calculation {

	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);

		int a, b;
		String s;

		System.out.print("두 정수와 연산자를 입력하시오 >> ");
		a = sc.nextInt();
		b = sc.nextInt();
		s = sc.next();

		switch(s) {
		
		case "+" :
			
			Add add = new Add();
			add.setValue(a, b);
			System.out.println(add.calculate());
			break;
		
		case "-" :
			
			Sub sub = new Sub();
			sub.setValue(a, b);
			System.out.println(sub.calculate());
			break;
			
		case "*" :
			
			Mul mul = new Mul();
			mul.setValue(a, b);
			System.out.println(mul.calculate());
			break;
		
		case "/" :
			
			Div div = new Div();
			div.setValue(a, b);
			System.out.println(div.calculate());
			break;
			
		default	: System.out.println("잘못 입력 하셨습니다.");
		}
	}

}

class Add {

	int a;
	int b;

	void setValue(int a, int b) {

		this.a = a;
		this.b = b;
	}

	public int calculate() {

		return a + b;

	}
}

class Sub {

	int a;
	int b;

	void setValue(int a, int b) {

		this.a = a;
		this.b = b;
	}

	public int calculate() {

		return a - b;

	}
}

class Mul {

	int a;
	int b;

	void setValue(int a, int b) {

		this.a = a;
		this.b = b;
	}

	public int calculate() {

		return a * b;

	}
}

class Div {

	int a;
	int b;

	void setValue(int a, int b) {

		this.a = a;
		this.b = b;
	}

	public int calculate() {

		return a / b;

	}
}

```

```java

// 숫자야구게임 선생님 풀이

package Game;

import java.util.Scanner;

class BaseballNumber {

   int[] random;

 

   public BaseballNumber() {

      random = new int[3];

      do {

         random[0] = (int) (Math.random() * 10);

         random[1] = (int) (Math.random() * 10);

         random[2] = (int) (Math.random() * 10);

      } while (random[0] == random[1] || random[0] == random[2] || random[1] == random[2]);

   }

 

   public void showNumber() {

      System.out.print("컴퓨터 발생 수 : ");

      System.out.print(random[0] + " " + random[1] + " " + random[2]);

   }

 

   public int resultStrike(int[] userNum) {

      int strike = 0;

      if (random[0] == userNum[0])

         strike++;

      if (random[1] == userNum[1])

         strike++;

      if (random[2] == userNum[2])

         strike++;

      return strike;

   }

 

   public int resultBall(int[] userNum) {

      int ball = 0;

      if (random[0] == userNum[1] || random[0] == userNum[2])

         ball++;

      if (random[1] == userNum[0] || random[1] == userNum[2])

         ball++;

      if (random[2] == userNum[0] || random[2] == userNum[1])

         ball++;

      return ball;

   }

}

 

public class BaseballGame {

 

   public static void main(String[] args) {

      Scanner sc = new Scanner(System.in);

      BaseballNumber number = new BaseballNumber();

      int userNum[] = new int[3];

      int count = 5, strike, ball; // 전체 기회. 5번 안에 못맞추면 종료한다.

      System.out.println("숫자야구게임 시작");

      number.showNumber();

      while (count >= 1) {

         System.out.print("\n새 개의 수 순서대로 입력 (중복숫자 입력 금지) >> ");

         for (int i = 0; i < userNum.length; i++)

            userNum[i] = sc.nextInt();

         if (userNum[0] == userNum[1] || userNum[0] == userNum[2] || userNum[1] == userNum[2]) {

            System.out.println("중복숫자 입력하였습니다. 다시 입력하세요. \n");

            continue;

         }

         strike = number.resultStrike(userNum);

         ball = number.resultBall(userNum);

         System.out.println(strike+" Strike "+ball+" Ball");

         if (strike == 3) {

            System.out.println("맞추셨습니다.(짝짝짝!) \n");

            break;

         }

         count--;

         System.out.println("기회는" + count + "번 남았습니다. \n");

      }

 

      System.out.println("게임종료!");

   }

 

}

```

```java

package Practice2;

class Tv {

	private int size;

	public Tv(int size) {

		this.size = size;
	}

	protected int getSize() {

		return size;
	}
}
//-------------------------------------------------------------------------------------

class ColorTv extends Tv {

	int color;

	public ColorTv(int i, int j) {
		super(i);
		this.color = j;
	}

	void printProperty() {

		System.out.println(getSize() + "인치 " + color + "컬러");

	}
}

public class Run {
	public static void main(String[] args) {

		ColorTv myTv = new ColorTv(32, 1024);

		myTv.printProperty();

	}

}

```

```java

package Practice2;

class Tv {

	private int size;

	public Tv(int size) {

		this.size = size;
	}

	protected int getSize() {

		return size;
	}
}
//-------------------------------------------------------------------------------------

class ColorTv extends Tv {

	int color;

	public ColorTv(int size, int color) {
		super(size);
		this.color = color;
	}

	void printProperty() {

		System.out.println(getSize() + "인치 " + color + "컬러");

	}
}
//-------------------------------------------------------------------------------------
class IPTV extends ColorTv {

	private String ip;
	
	public IPTV(String ip, int size, int color) {
		super(size,color);
		this.ip = ip;
	}
	public String getIp() {
		
		return ip;
	}
	void printProperty() {
		
		System.out.println("나의 IPTV는 " + getIp() + " 주소의 " + getSize() + "인치 " + color + "컬러");
	}
	
	
}
public class Run {
	public static void main(String[] args) {

		IPTV iptv = new IPTV("192.1.1.2" , 32, 1024);

	    iptv.printProperty();

	}

}

```

```java

package Practice2;

import java.util.Scanner;

abstract public class Converter {
	
	abstract protected double convert(double src); // 추상 메소드
	abstract protected String getSrcString();
	abstract protected String getDestString();
	
	protected double ratio; // 비율 변환

	public void run() {
		
		Scanner sc = new Scanner(System.in);
		
		System.out.println(getSrcString() + "을" + getDestString() + "로 바꿉니다.");
		System.out.print(getSrcString() + "을 입력하세요.");
		
		double val = sc.nextDouble();
		double res = convert(val);
		
		System.out.println("변환 결과 : " + res + getDestString() + "입니다.");
		
		sc.close();
	}
}

```

```java

package Practice2;

class Won2Dollar extends Converter {

	public Won2Dollar(double i) {
		
		this.ratio = i;
	}

	@Override
	protected double convert(double src) {
		
		return src/ratio;
	}

	@Override
	protected String getSrcString() {
		
		return "원";
	}

	@Override
	protected String getDestString() {
		
		return "달러";
	}
	
}
public class Won2DollarExe {

	public static void main(String[] args) {
		
		Won2Dollar toDollar = new Won2Dollar(1200);
		
		toDollar.run();
		
	}

}
```


[목차로](#목차)

## 예외처리


```java

package Exception;
import java.util.Scanner;

public class ExceptionExe {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		int divisor = 0;
		int dividend = 0;
		
		System.out.println("나뉨수를 입력하시오.");
		dividend = sc.nextInt();
		
		System.out.println("나눗수를 입력하시오");
		divisor = sc.nextInt();
		
		System.out.println(dividend + "을/를" + divisor + "로 나누면 몫은 " + dividend / divisor + "입니다.");
	}

}

```

```java

package Exception;

import java.util.Scanner;

public class ExceptionExe_1 {

	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);

		int divisor = 0;
		int dividend = 0;

		System.out.println("나뉨수를 입력하시오.");
		dividend = sc.nextInt();

		System.out.println("나눗수를 입력하시오");
		divisor = sc.nextInt();

		try {

			System.out.println(dividend + "을/를" + divisor + "로 나누면 몫은 " + dividend / divisor + "입니다.");
		
		} catch (java.lang.ArithmeticException e) {

			System.out.println("0으로 나눌 수 없습니다.");
		}
	}

}

```

```java


package Exception;

public class ArrayException {

	public static void main(String[] args) {
	
		int intArray[] = new int[5];
		
		intArray[0] = 0;
		
		try {
			for(int i = 0; i < 5; i ++) {
				
				intArray[i + 1] = i + 1 + intArray[i];
				
				System.out.println("intArray["+ i + "]" + "=" + intArray[i]);
			}
		} catch(ArrayIndexOutOfBoundsException e) {
			
			System.out.println("배열의 인덱스가 범위를 벗어낫습니다.");
		}

	}

}
```

[목차로](#목차)
