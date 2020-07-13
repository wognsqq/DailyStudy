## JAVA 객체 지향 프로그래밍 -1. 수업소개
 - Object Oriented Programming 객체 지향 프로그래밍
 - method =  functuin, subroutine, procedural = 절차지향 프로그래밍 (procedural programming)
 - method programming
 - 메쏘드를 이용해서 작은 부품을 만들고 더큰 프로그램을 만드는 것
 - class(수납상자) 메쏘드 {변수 이름 붙어서 정리정돈} => 객체 지향 프로그래밍, 객체 지향 언어
 - 메쏘드와 변수를 그룹핑하고 이름을 붙인 것
 - 코드를 단정하게 정리정돈 하는 방법을 알게 될 것. 분신술 (instance) 부모 자식 상속, 클래스의 설계도 interface

## JAVA 객체 지향 프로그래밍 -2. 남의 클래스&남의 인스턴스
```JAVA
package others;

import java.io.FileWriter;
import java.io.IOException;

public class projectOOP {
	public static void main(String[] args) throws IOException {
//		class : System, Math, FileWriter
//		instance : f1, f2
		
		System.out.println(Math.PI);
//		내림.소수점에 있는 값을 0으로 해서 소수점 버림
		System.out.println(Math.floor(1.8));
//		올림. =2.0
		System.out.println(Math.ceil(1.8));
		
//		 수학과 관련된 껍데기가 메쓰 클래스
		
//		new에 따라 data.txt에 파일을 저장하겠다는 복제본f1이 생기는 것
//		복제본 타입 =FileWriter, import 처리
		FileWriter f1 = new FileWriter("data.txt");
		f1.write("Hello");
		f1.write("Java");
		f1.close();
//		메쓰의 경우, 그냥 메쓰 클래스를 바로 사용한 것, 밑의 FIleWriter는 앞에 new를 붙여 
//		f1에 담기는 내용을 가진 복제본
		
		FileWriter f2 = new FileWriter("data2.txt");
		f2.write("Hello");
		f2.write("Java");
		f2.close();
		
		f1.write("!!!");
		f1.close();
//		f2 data2.txt에 저장하겠다는 
//		Math.Pi 등은 내부적으로 어떤상태를 유지할 필요가 없는 1회용
//		FileWriter의 경우, 긴 작업을 해나갈 수도 있으므로, 클래스를 직접 사용하는 것이 아니라,
//		클래스를 복제해서 f1, f2로 제어한다.

	}
}
```

## JAVA 객체 지향 프로그래밍 -3. 변수와 메소드
```JAVA
package others;

public class myOOP {
	public static String delimiter = ""; // myoop소속인 변수

	public static void main(String[] args) {
		// syso에 4개=> 오른쪽 => refactor => extract method => printA타이핑
		delimiter = "----";
		printA();
		printA();
		printB();
		printB();

		delimiter = "****";
		printA();
		printA();
		printB();
		printB();
//		메쏘드 안에서 정의된 변수는 그 메쏘드 안에서만 쓸 수 있다. 
//		myoop 소속인 변수를 만들면 된다

	}

	private static void printA() {
// 	구분자를 *로 하고 싶을 때  parameter = ( 매개변수) 를 바꿔준다.
		System.out.println(delimiter);
		System.out.println("A");
		System.out.println("A");
	}

	private static void printB() {
		System.out.println(delimiter);
		System.out.println("B");
		System.out.println("B");
	}
	//.. 1억개의 또다른 메쏘드가 있다고 한다면? 다음시간에
}
```

[## JAVA 객체 지향 프로그래밍 -1. 수업소개](https://www.youtube.com/watch?v=uvYWAfZzb8k&list=PLuHgQVnccGMAb-e41kXPSIpmoz1RvHyN4&index=1)
[## JAVA 객체 지향 프로그래밍 -2. 남의 클래스&남의 인스턴스](https://www.youtube.com/watch?v=nMiS5ZRSgCw&list=PLuHgQVnccGMAb-e41kXPSIpmoz1RvHyN4&index=2)
[## JAVA 객체 지향 프로그래밍 -3. 변수와 메소드](https://www.youtube.com/watch?v=YcWaITX54k4&list=PLuHgQVnccGMAb-e41kXPSIpmoz1RvHyN4&index=3)
