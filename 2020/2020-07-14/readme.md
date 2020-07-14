------

## Class, variable 클래스  변수 네이밍 방법
- 파스칼 표기법(PascalCase) : 모든 단어에서 첫 번째 문자는 대문자이며 나머지는 소문자이다.
- 카멜 표기법(camelCase) : 최초에사용된 단어를 제외한 첫 번째 문자가 대문자이며 나머지는 소문자이다. 반의어는 반드시 대응하는 개념으로 사용한다.

1. 패키지(Package) 명명 규칙	
 패키지명은 표준 패턴을 따라야 한다. 가급적 한 단어의 명사를 사용한다.
2. 클래스(Class)명명 규칙
```

public class Naming {
public static void main(String[] args) {
}
}
// 	클래스명에는 파스칼을 사용한다.
	public class HelloWorld{}
// 	인터페이스에는 특별한 접두사나 접미사를 사용하지 않고 파스칼을 사용한다.
	public interface Animal{}
// 인터페이스를 구현한 클래스에는 특별한 접두사나 접미사를 사용하지 않고 파스칼을 사용한다.
	public class Tiger implements animal{}
// 추상 클래스에는 특별한 접두사 접미사를 사용하지 않고 파스칼 사용한다.
	public abstract class Animal{}
```
3. 메소드(Method)명명 규칙
```
public class MethodNaming {
public static void main(String[] args) {
import java.util.HashMap;

public class MethodNaming {
	public static void main(String[] args) {
		
	}

//	메소드 명에는 파스칼 표기법을 사용한다.
	public void SendMessage(String message) {
	
	}
//	속성에 접근하는 메소드명의 접두사는 'get','set'을 사용한다.
	public class SetDisplayName{}
	public class GetDisplayName{}
//	데이터를 조회하는 메소드명의 접두사는 find를 사용한다.
	public void FindData(String data) {}
//	데이터를 입력하는 메소드 명의 접두사는 input을 사용한다.
	public void InputData(HashMap data) {}
//	데이터를 변경하는 메소드명의 접두사는 modify를 사용한다.
	public void ModifyData(HashMap data) {}
//	데이터를 삭제하는 메소드명의 접두사는 delete를 사용한다.
	public void DeleteData(String data) {}
//	데이터를 초기화하는 메소드명의 접두사는 initialize를 사용한다.
	public void InitData(String data) {}
//	변환 값의 타입이 boolean인 메소드는 접두사로 is를 활용한다.
	public void isData(String Data) {}
//	데이터를 불러오는 메소드명의 접두사는 load를 사용한다.
	public void loadData(){}
//	데이터가 있는지 확인하는 메소드명의 접두사는 has를 사용한다.
	public void hasData(){}
//	보다 지능적인 set이 요구될때 사용하는 메소드명의 접두사는 register를 사용한다.
	public void registerAccount(){}
//	새로운 객체를 만든뒤 해당 객체를 리턴해주는 메소드명의 접두사는 create를 사용한다.
	public void createAccount(){}
//	해당 객체를 다른 형태의 객체로 변환해주는 메소드명의 접두사는 to를 사용한다.
	public void toStr() {}
//	해당 객체가 복수인지 단일인지 구분하는 메서드명의 접미사는 s를 사용한다.
	public void getMembers(){}
//	B를 기준으로 A를 하겠다는 메소드명의 전치사는 By를 사용한다.
	public void getUserByName(String name){}

}	
```	
4. 변수(Variable)명명 규칙

- 변수와 메소드의 파라미터에는 카멜표기법을 사용한다.
- 변수에 약어를 사용하지 않고 모든 의미를 충분히 담는다.
- 한 글자로 된 이름을 사용하지 않는다.
- 선언된 지점에서 초기화하며, 가능한 사용범위를 최소화 한다. 숫자 0 reference null
- 반복문에서 인덱스로 사용할 변수는 i,j,k등으로 사용한다.
- 지역변수와 멤버변수는 변수명 앞에 밑줄(_)을 사용하여 구별한다.
- boolean 타입의 변수는 접두사로 is를 사용한다 Ex) boolean isCheck


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
