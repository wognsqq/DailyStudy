## JAVA 객체 지향 프로그래밍 - 5. 인스턴스
[JAVA 객체 지향 프로그래밍 - 5. 인스턴스](https://www.youtube.com/watch?v=Y370ydbIb7Y&list=PLuHgQVnccGMAb-e41kXPSIpmoz1RvHyN4&index=6)

### 객체지향의 가장 큰 고비 instance
 - 클래스를 복제한 복제본 1,2,3.... => instance
 - 복제할 때 사용하는 new 라는 키워드!
 - 남이 만든 클래스 FileWriter => 복제해서 f1에 담았었다. f1 에는 FileWriter를 복제한 FileWriter의 인스턴스가 생긴 것
 - 나의 인스턴스를 만들자.
 - 할때마다 짜잘짜잘하게 바꾸지 말고 인스턴스를 써보자

```Java
package others;

public class Instance {
	public static void main(String[] args) {
// Print class를 인스턴스로 생성하기 위해서는  
		Print p1 = new Print();
//		인스턴스의 딜리미터를 준다 => static 뒤에 따라오는건 클래스인데 print class의 static을 없앤다. 
		p1.delimiter = "----";
		p1.A();
		p1.A();
		p1.B();
		p1.B();
//		print 클래스의 A소속이니까 static을 없앤다.
		
		Print p2 = new Print();
//		인스턴스의 딜리미터를 준다 => static 뒤에 따라오는건 클래스인데 print class의 static을 없앤다. 
		p2.delimiter = "****";
		p2.A();
		p2.A();
		p2.B();
		p2.B();

		p1.A();
		p2.A();
		p1.A();
		p2.A();
//		밑에거와 같음. p1이라는 독립된 존재를 이용해서, 중복된 코드 작성 없이
//		Print라는 하나의 코드를 돌려막을 필요 없이, p1, p2를 대입해서 쉽게 코딩
//		스태틱이 없는 변수와 메소드를 정의하는 것을 통해, print라는 클래스를 복제해서
//		각 데이터는 내부적으로 다른 데이터를 유지하도록 해서 중복을 제거 하는 new를 통해서요.
//		Print.delimiter = "----";
//		Print.A();
//		Print.delimiter = "****";
//		Print.A();
//		Print.delimiter = "----";
//		Print.B();
//		Print.delimiter = "****";
//		Print.B();

	}

}

```
``` java
package others;

class Print {
	public  String delimiter= "";	
	public void A() {
		System.out.println(delimiter);
		System.out.println("A");
		System.out.println("A");
	}
	public void B() {
		System.out.println(delimiter);
		System.out.println("B");
		System.out.println("B");
	}

}
```



## JAVA 객체 지향 프로그래밍 - 6. static
[JAVA 객체 지향 프로그래밍 - 6. static](https://www.youtube.com/watch?v=hvTuZshZvIo&list=PLuHgQVnccGMAb-e41kXPSIpmoz1RvHyN4&index=7)
 
 ```java
 package others;

class Foo{
//	Foo에 두개의 변수 생성
	public static String classVar = "I class var";
	public String instanceVar = " I instance var";
	public static void classMethod() {
//		클래스 메소드 안에서는 클래스 변수에는 접근이 가능하나 인스턴스에는 접근이 안된다.
		System.out.println(classVar);//ok
//		System.out.println(instanceVar);//error
	}
	public void instanceMethod() {
		System.out.println(classVar);//ok
		System.out.println(instanceVar);//ok
	}
}
public class StaticApp {
	public static void main(String[] args) {
		System.out.println(Foo.classVar); //ok
//		System.out.println(Foo.instanceVar);//error
//		클래스바에는 접근이 되나, 인스턴스바에는 안됨
//		인스턴스는 인스턴스를 통해 사용해야 한다.
		Foo.classMethod();
//		Foo.instanceMethod();
//		클래스를 통해 인스턴스 변수에 접근하는 것은 금지되어 있다. 
//		인스턴스 메소드에 접근하는 것도 금지되어 있다.
		Foo f1 = new Foo(); //인스턴스 생성
		Foo f2 = new Foo();
		
		System.out.println(f1.classVar); // I class var
		System.out.println(f1.instanceVar);// I instance var
		
		f1.classVar = "changed by f1";
		System.out.println(Foo.classVar); // changed by f1
		System.out.println(f2.classVar);// changed by f1
		
		f1.instanceVar = "changed by f1";
		System.out.println(f1.instanceVar); // changed by f1
		System.out.println(f2.instanceVar); // I instance var
//		static String classVar 클래스의 소속, f1에는 실제 값이 존재하지 않고
//		foo라는 클래스를 가리키고 있을 뿐
//		String instanceVar = "I instance var" f1이 생성될때 instanceVar값을 복제해 온다.
//		값을 가지고 있고, instance 값 바꾼다고 class의 값이 바뀌지 않는다.
//		Static classMethod(){} 마찬가지로 참조하는 것
//		instanceMethod(){} 복제. 값을 실제로 가지고 있음
//		클래스의 변수를 바꾸면 모든 인스턴스 변수의 값이 바뀐다.
//		인스턴스에서 클래스의 변수를 바꾸면, 클래스의 변수가 바뀌고, 걔가 사용하는 모든 인스턴스가 바뀐다.
		
		
		
	}
}
```
