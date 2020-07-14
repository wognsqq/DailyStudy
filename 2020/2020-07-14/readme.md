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
