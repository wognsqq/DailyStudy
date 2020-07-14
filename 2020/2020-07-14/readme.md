------

## Class, variable 클래스 변수 네이밍 방법
- 파스칼 표기법(PascalCase) : 모든 단어에서 첫 번째 문자는 대문자이며 나머지는 소문자이다.
- 카멜 표기법(camelCase) : 최초에사용된 단어를 제외한 첫 번째 문자가 대문자이며 나머지는 소문자이다. 반의어는 반드시 대응하는 개념으로 사용한다.

1. 패키지(Package) 명명 규칙	
 패키지명은 표준 패턴을 따라야 한다. 가급적 한 단어의 명사를 사용한다.
2. 클래스(Class)명명 규칙
```

public class Naming {
// 	클래스명에는 파스칼을 사용한다.
	public class HelloWorld{}
// 	인터페이스에는 특별한 접두사나 접미사를 사용하지 않고 파스칼을 사용한다.
	public interface Animal{}
// 인터페이스를 구현한 클래스에는 특별한 접두사나 접미사를 사용하지 않고 파스칼을 사용한다.
	public class Tiger implements animal{}
// 추상 클래스에는 특별한 접두사 접미사를 사용하지 않고 파스칼 사용한다.
	public abstract class Animal{}
	public static void main(String[] args) {
		

	}

}
```

## JAVA 객체 지향 프로그래밍 - 4.1. 클래스 - 존재 이유와 기본형식  
[JAVA 객체 지향 프로그래밍 - 4.1. 클래스 - 존재 이유와 기본형식](https://www.youtube.com/watch?v=m1Cx8vDDmYo&list=PLuHgQVnccGMAb-e41kXPSIpmoz1RvHyN4&index=4)  
## JAVA 객체 지향 프로그래밍 - 4.2. 클래스 - 형식  
[JAVA 객체 지향 프로그래밍 - 4.2. 클래스 - 형식](https://www.youtube.com/watch?v=jpcXlhgEzmQ&list=PLuHgQVnccGMAb-e41kXPSIpmoz1RvHyN4&index=5)  
```java
package codes;
// 클래스 키워드 + 이름 
//{ 클래스의 소속인 변수 또는 메소드담기 클래스의 멤버는 delimiter A,B}
//자바는 소스 파일의 이름과 똑같은 파일을 찾아서 그 클래스의 main method를 
//실행하도록 되어있다. 
//앞의 public은 접근 제어자.public은 한번만 등장한다. 
//하나의 파일 안에 클래스를 여러개 만들 경우 각각의 클래스가 파일로 존재하게 된다. 
//클래스 파일은 별도로 쪼갤 수 있다. 
//기능에 대한 정리정돈을 하는 효과 => 클래스 쪼개서 ㅈㅏ바 파일로 정리
// Refactor => Move type to new File은 이 버전에는 없는듯 => 기존의 내용은 ~~했는데, print.java에 옮겨담겠다
class Print{
	public static String delimiter = "";

	public static void A() {
		System.out.println(delimiter);
		System.out.println("A");
		System.out.println("A");
	}

	public static void B() {
		System.out.println(delimiter);
		System.out.println("B");
		System.out.println("B");
	}
}

public class myOOP {
	public static void main(String[] args) {

		Print.delimiter = "----";
//		Print라는 클래스에 소속된 A메쏘드
		Print.A();
		Print.A();
		Print.B();
		Print.B();

		Print.delimiter = "****";
		Print.A();
		Print.A();
		Print.B();
		Print.B();

	}

}
//서로 연관되어 있다 => Print.을 찍으면 클래스를 통해 editor가 추천하는 기능까지
//사용할 수 있다.
```
