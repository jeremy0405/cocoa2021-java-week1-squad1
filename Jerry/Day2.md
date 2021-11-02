# Day2

### 코딩 스타일
가독성을 좋게 하기 위해 자바 사용자들은 코딩 스타일 규칙을 정해 쓰고 있다.
인텔리제이에 자바 스타일 가이드를 통해 코드 정렬(Ctrl+Alt+L) 하도록 설정하였다.
직접 코딩 한 후 코드 정렬 전 후의 차이가 적도록 코딩을 계속 진행해야 겠다.

### 객체지향 생활 체조 규칙
- [ ] 1. 한 메서드에 오직 한 단계의 들여 쓰기만 한다.
- [ ] 2. else 예약어를 쓰지 않는다
- [ ] 3. 모든 원시 값과 문자열을 포장한다.
- [ ] 4. 한 줄에 점을 하나만 찍는다.
- [ ] 5. 줄여 쓰지 않는다(축약 금지).
- [ ] 6. 모든 엔티티(entity)를 작게 유지한다.
- [ ] 7. 2개 이상의 인스턴스 변수를 가진 클래스를 쓰지 않는다.
- [ ] 8. 제일 클래스(first class) 컬렉션을 쓴다.
- [ ] 9. 게터getter/세터setter/프로퍼티property를 쓰지 않는다.

 아직은 무슨말인지 이해를 못하겠다.

else 안쓰는 법은 메소드로 만들어서 return 하는 방법.
 
 위의 규칙을 지키면 가독성이 좋아지고 궁극적으로 주석 없이 이해가능하게 코딩할 수 있다고 한다.


### 함수와 메소드
- 함수를 사용하는 이유?
코드를 분리하여 유지보수 시 편리하게 하기 위함.
코드의 재활용이 용이.

- 메소드와 함수의 차이는?
자바에서 메소드 = 함수로 혼용하여 사용
하지만 메소드와 함수는 엄연히 다름
함수는 독립적으로 존재 가능하지만 메소드는 클래스 내에서 존재함. 또한 함수는 멀티쓰레드 환경에서도 안전하지만 클래스는 안전함을 보장하지 않음. 클래스에서 멀티쓰레드 환경에서도 안전함을 보장하기 위해 다양한 디자인 패턴을 사용한다고 알고 있음.


### 콘솔에서 자바 실행하기
파일명.java 파일을 생성 후 코딩한 후에
javac (자바 컴파일러)를 통해 .class 파일을 만듬.
javac 파일명.java 를 통해 class 파일을 생성할 수 있고 이 파일은 바이트 코드로 작성됨.

java 파일명	을 통해 자바를 실행.


### 파일 읽기의 기초
- Scanner를 활용하는 간단 읽기
```java
import java.util.Scanner;

public class Main {

	public static void main (String[] args) {
		Scanner sc = new Scanner(System.in);
		int i = sc.nextInt(); // 정수 읽기
		double d = sc.nextDouble();// 실수 읽기
		String j = sc.next(); // 공백 이전까지 입력된 문자열 읽기
		String k = sc.nextLine(); //enter 이전까지 입력된 문자열 읽기(스페이스바 포함)
		Char c = sc.nextChar(); // 문자열 읽기		
		sc.close();	// Scanner 종료
	}
}
```

- BufferedReader() 를 활용하는 조금 어려운 읽기
	- 왜 BufferedReader를 사용하는가?
	BufferedReader 는 Scanner보다 속도가 훨씬 빠르다는 장점이 있다. 이는 입력된 데이터가 버퍼를 거쳐 전달되기 때문이다. 하지만 BufferedReader 는 Enter만 경계로 인식하고 받은 데이터가 String으로 고정되기 때문에 입력 데이터를 가공해야만 한다는 단점이 있다.
	```java
	import java.io.*;
	
	public class Main {
	
		public static void main (String[] args) throws IOException {
			BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
			
			int i = Integer.parseInt(br.readLine());
		}
	}
	```
	더 공부해야 할 키워드
	```java
	Stringtokenizer st = new Stringtokenizer(문자열);
	int a = Integer.parseInt(st.nextToken());
	
	
	StringBuilder sb = new StringBuilder();
	sb.append("*");
	System.out.print(sb);
	```
	

### Call by Value, Call by Reference
- 자바의 primitive의 경우 call by value, 객체의 경우는 call by reference
- 실제 자바는 Call by Value 뿐이다.

Call by value : 값에 의한 호출
Call by Reference : 주소에 의한 호출

C에서의 포인터와 그냥 일반적인 value 값 불러오는 것의 차이를 말하는 것 같다.

자세히 이해는 못함.

### 자바의 메모리 구조

>to do list
>- 자바 메모리 구조
>- 힙, 스택, 메소드 영역 역할
>- 자바 GC의 동작





