## JAVA 객체 지향 프로그래밍 - 7. 생성자와 this
[JAVA 객체 지향 프로그래밍 - 7. 생성자와 this](https://www.youtube.com/watch?v=_GIXzqq3Cp4&t=3s)
 - 수정하고자 하는 파일이 반드시 지정이 돼 있어야 하는데, 이 인스턴스를 생성하는 시점에 파일을 지정할 수
 - 있다면 아주 안전하게, 인스턴스가 생성될 때 필요한 초기값 
```Java
package others;

public class This {
	public static void main(String[] args) {
/* 구분자인 delimiter 값을 반드시 세팅해야 한다고 할 때, instance를 생성할 때 delimiter
 * 값을 지정하지 않으면, 우리가 만든 class가 instance화 되지 못한다면, 사용자 실수를 원천차단할 수 있지 
 * 않나.. 딜리미터값을 인스턴스 값을 생성할 때 지정하는 것
 * 생성자 constructor 
 */
		Print p1 = new Print("----");
//		new(생성자)가 없다면 인스턴스를 호출하는 것과 같은 행위. 생성자를 구현할 수 있는
//		기능을 제공하고 주요한 작업은 초기화. class print와 똑같은 public print{}를 만들면 걔가 바로
//		생성자. 클래스와 동일한 이름의 메소드가 있아면 그 메소드를 호출하도록 약속되있기 때문에, construct method
//		내에 생성함으로써 초기화 목적 달성. 프린트 메쏘드에 매개변수로 delimiter를 받으면 되겠다.
		
		p1.A();
		p1.A();
		p1.B();
		p1.B();

		Print p2 = new Print("****");

		p2.A();
		p2.A();
		p2.B();
		p2.B();

		p1.A();
		p2.A();
		p1.A();
		p2.A();


	}

}

```java
package others;

class Print {
	public  String delimiter= "";	
//		_delimiter 변수는 ---- 딜리미터 값에 주면 delimiter는 ----
//		가 된다	
	public Print(String delimiter) {
			this.delimiter = delimiter;
//**디스는 생성한 인스턴스를 가리키는 이름=> delimiter="";
			
//		생성자 - delimiter = _delimiter;
		
//	생성자로 _delimiter 인스턴스 생성, 딜리미터 값 을 ""로 지정
//	Print p1 = new Print("----")로 세팅 => 출력

	}


	public void A() {
		System.out.println(this.delimiter);
		System.out.println("A");
		System.out.println("A");
	}
	public void B() {
		System.out.println(this.delimiter);
		System.out.println("B");
		System.out.println("B");
	}

}
```


## JAVA 객체 지향 프로그래밍 - 8 .1. 활용 - 클래스화
[JAVA 객체 지향 프로그래밍 - 8 .1. 활용 - 클래스화](https://www.youtube.com/watch?v=siUcCqySsng&list=PLuHgQVnccGMAb-e41kXPSIpmoz1RvHyN4&index=9)

```java
package others;
//2억개 있을 때서로 비슷한 것끼리 모아 정리하자
class Accounting{
	public static double valueOfSupply;
    public static double vatRate = 0.1;
    public static double getVAT() {
        return valueOfSupply * vatRate;
    }
    public static double getTotal() {
        return valueOfSupply + getVAT();
    }
}
public class AccountingApp{
    public static void main(String[] args) {
        Accounting.valueOfSupply = 10000.0;
        System.out.println("Value of supply : " + Accounting.valueOfSupply);
        System.out.println("VAT : " + Accounting.getVAT());
        System.out.println("Total : " + Accounting.getTotal());
// 클래스를 이용해서 서로 모아서 연결해서 정리정돈하여 단정해 지게 만든다. 

//        클래스의 상태가 계속 바뀌어야 하는 상황이라면?
    }
}
```

## JAVA 객체 지향 프로그래밍 - 8.2. 활용 - 인스턴스화
[JAVA 객체 지향 프로그래밍 - 8.2. 활용 - 인스턴스화](https://www.youtube.com/watch?v=1KWFFwtM4Kg&list=PLuHgQVnccGMAb-e41kXPSIpmoz1RvHyN4&index=10)

```java
package others;

class Accounting2{
    public double valueOfSupply;
    public static double vatRate = 0.1;
    public Accounting2(double valueOfSupply) {
    	this.valueOfSupply = valueOfSupply;
//  this가 없는 valueOfSupply는 매개변수 this있는건 위에 파랑 인스턴스를 받음
    }
    //부가가치세율은 어떤 인스턴스율이건간에 동일하기 때문에, 인스턴스 소속보다는 클래스 소속의 
    //static으로 내버려 두는 것이 더 좋을 수 있다. 유지 보수의 편의성 
    public double getVAT() {
        return valueOfSupply * vatRate;
    }
    public double getTotal() {
        return valueOfSupply + getVAT();
    }
}
public class AccountingApp2 {
    public static void main(String[] args) {
        Accounting a1 = new Accounting();
        a1.valueOfSupply = 10000.0; 
        Accounting a2 = new Accounting();
        a2.valueOfSupply = 20000.0; 
        System.out.println("Value of supply : " + a1.valueOfSupply);
        System.out.println("Value of supply : " + a2.valueOfSupply);
         
        System.out.println("VAT : " + a1.getVAT());
        System.out.println("VAT : " + a2.getVAT());
         
        System.out.println("Total : " + a1.getTotal());
        System.out.println("Total : " + a2.getTotal());
//      여러상태가 하나의 클래스를 돌려사용할 경우 버그날 가능성이 높다 => 별도의 인스턴스 a1, a2를 만들어서 사용한다.
//  	인스턴스가 생성될 때, 꼭 가져야할 값, 
    }
}
```
