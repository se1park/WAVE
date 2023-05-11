JAVA Boostcourse
=============
2023-05-01 1일차 스터디
-------------

<pre>
<code>
public class HelloWorldApp {
	public static void main(String[] args) {
		System.out.println("Hello World!!");
	}
}
</pre>
</code>

- 데스크톱 애플리케이션 만들기

	- 기본 코드

<pre>
<code>
import javax.swing.*;   
import java.awt.Dimension;
import java.awt.Toolkit;
public class HelloWorldGUIApp{
    public static void main(String[] args){
        javax.swing.SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                JFrame frame = new JFrame("HelloWorld GUI");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setPreferredSize(new Dimension(400, 300));
                JLabel label = new JLabel("Hello World!!", SwingConstants.CENTER);
                frame.getContentPane().add(label);
                Dimension dim = Toolkit.getDefaultToolkit().getScreenSize();
                frame.setLocation(dim.width/2-400/2, dim.height/2-300/2);

                frame.pack();
                frame.setVisible(true);
            }
        });
    }
}
</pre>
</code>

- 수정해본 코드

<pre>
<code>
JLabel label = new JLabel("Hello World!!", SwingConstants.CENTER);
</pre>
</code>

***

2023-05-02 2일차 스터디
-------------

- Datatype.java

<pre><code>
public class Datatype{
	public static void main(String[] args) {
		System.out.println(6); // number
		System.out.println("six"); // String

		System.out.println("6"); // String

		System.out.println(6+6);
		System.out.println("6+6");
		System.out.println("6"+"6");
		// 양 옆에 문자열이 있을 경우는 더하기가 아닌 결합연산자라는 문자열을 위한 연산이 사용된다
		// 문자열은 곱하기 연산자를 사용할 수 없다

		System.out.println(6*6);

		System.out.println("111".length()); // 문자열의 길이를 알려준다
		System.out.println();
	}
}
</code></pre>

- Number.java

<pre><code>
public class Number {

	public static void main(String[] args) {
		// Operator
		System.out.println(6 + 2);
		System.out.println(6 - 2);
		System.out.println(6 * 2);
		System.out.println(6 / 2);

		// method
		// 메소드는 수학과 관련된 자주 사용되는 것들을 그룹핑해 놓은 캐비냇 같은 것
		System.out.println(Math.PI); // 적당한 정밀도로 보여준다
		System.out.println(Math.floor(Math.PI)); // floor는 수학적으로 내림, 뒤에있는 소수점을 자른다
		System.out.println(Math.ceil(Math.PI)); // ceil은 올림, 3.14에서 그 뒤에 값 1을 올림
		System.out.println(Math.ceil(6.77)); // 7.0

	}

}
</code></pre>

- StringApp.java

<pre><code>
public class StringApp {

	public static void main(String[] args) {

		// Character VS String
		System.out.println("Hello World"); // String, 문자열 = character들이 모여있는 것
		System.out.println('A'); // Character, 문자 = 한 글자만 표현할 때
		System.out.println("A"); // String

		// new line
		System.out.println("Hello "
				+ "World"); // 문자열과 문자열을 더한 것
		System.out.println("Hello \nWorld"); // 줄바꿈

		// escape
		// 역슬래쉬를 통해서 그 뒤에 따라오는 어떤 임무가 있는 문자의 임무를 일시적으로 해방시키는 것
		System.out.println("Hello \"World\""); // \"  \"은 Hello "World"

	}

}
</code></pre>

- Variable.java

<pre><code>
public class Variable {

	public static void main(String[] args) {

		/* 변할 수 있는 문자가 변수
		   변수는 데이터 타입을 지정해줘야 한다
		   변수를 만들 때는 그 변수가 어떤 데이터 타입을 담을 수 있는지 명확하게 표현해줘야 한다 */

		// Number -> interger
		int a = 1; // 정수 1
		System.out.println(a);

		// real number -> double
		double b = 1.1; // 실수 1.1
		System.out.println(b);

		// String
		String c = "Hello World!"; // 문자열
		System.out.println(c);

	}

}
</code></pre>

- Letter.java

<pre><code>
public class Letter {

	public static void main(String[] args) {
		String name = "gyuli";
		System.out.println("Hello, "+name+"... "+name+ "... egoing ... bye..");

		double VAT = 10.0; // 부가가치세
		System.out.println(VAT); // 부가가치세율

		/* 코딩을 하는데 있어서 코드는 나도 보지만 내가 아닌 다른 사람도 보는 것이기 때문에
		   코드를 딱 봤을 때 그 의미를 빨리 파악할 수 있도록 작성하는 것이 중요하다
		   이때 사용하는 가장 중요한 수단 중 하나가 수단이고 변수는 값의 이름을 부여하는 것이다
		   그러므로 좋은 이름을 사용해야 한다 */

	}

}
</code></pre>

- Casting.java

<pre><code>
public class Casting {

	public static void main(String[] args) {

		// casting
		// 데이터 타입을 다른 데이터 타입으로 컨버팅하는 것
		double a = 1.1;
		// 자동으로 1이 double형으로 컨버팅 된 것
		// 손실이 일어나지 않기 때문에 가능하기 때문에 가능한 것
		double b = 1; 
		// 수동으로 한 것 (명시적으로 한 것)
		double b2 = (double) 1;
		System.out.println(b);

		// int c = 1.1; 이렇게 하면 0.1을 잃어버리게 된다

		// Change type of 'd' to 'double'
		double d = 1.1;
		// Add cast to 'int'
		// int 형태로 강제로 바꾸겠다
		// 소수점 밑에 있는 것들이 사라져 손실이 일어난다
		// 그래서 자바에서 자동으로 해주지 않는 것
		int e = (int) 1.1;
		System.out.println(e);

		// 1 to String
		String f = Integer.toString(1);
		System.out.println(f);

		// 변수가 갖고있는 값이 어떤 데이터 타입인지 알려준다
		System.out.println(f.getClass());

	}

}
</code></pre>

- StringOperation.java

<pre><code>
public class StringOperation {

	public static void main(String[] args) {

		// 텍스트가 몇 글자인지 세야되는 경우
		System.out.println("Hello World".length()); // 11 글자

		// name을 gyuli로 바꾸어준다
		System.out.println("Hello, name~ bye!".replace("name","gyuli"));
		System.out.println("Hello, [[[name]]]... bye..".replace("[[[name]]]", "gyuli"));

	}

}
</code></pre>

***

2023-05-03 스터디
-------------

- Program.java

<pre><code>
public class Program {

	public static void main(String[] args) {

		System.out.println(1);
		System.out.println(2);
		System.out.println(3);

		// 하나하나의 기능들을 우리가 하고자 하는 일의 취지에 맞게 배치하면 컴퓨터가 이 작업을
		// 순차적으로 진행해주는 것을 통해서 자동화를 할 수 있다
		// 우리는 프로그래밍이 순차적으로 실행되는 것을 이용해
		// 사람이 잘 못 하는 것들을 기계에게 위임해서 자동화 할 수 있다는 효과를 얻을 수 있다
	}

}
</code></pre>

- OkJavaGoInHome.java

<pre><code>
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OkJavaGoInHome {

	public static void main(String[] args) {

		String id = "JAVA APT 507";

		// Elevator call
		Elevator myElevator = new Elevator(id);
		myElevator.callForUp(1);
		// id는 나의 주소
		// 엘리베이터가 어디에 있는지를 알아야 거기 있는 엘리베이터를 제어할 수 있다
		// 자바 아파트에 있는 엘리베이터가 12번째 문장이다

		// Security off
		Security mySecurity = new Security(id);
		mySecurity.off();

		// Light on
		Lighting hallLamp = new Lighting(id+ " / Hall Lamp");
		hallLamp.on();

		Lighting floorLamp = new Lighting(id+ " / floor Lamp");
		floorLamp.on();

	}

} // 자동화의 열쇠가 프로그래밍이다

</code></pre>

- 디버거

  버그는 우리가 짠 코드의 의도하지 않은 문제를 말한다.

  그 버그를 잡는 행위를 디버깅이라 하고 디버깅을 할 때 사용하는 도구를 디버거라 부른다.

  현대적인 개발 도구들은 내부적으로 디버거를 가지고 있다.

- 프로그램이 실행되는 것을 멈추고 싶을 때:

  멈추고 싶은 곳에서 더블 클릭을 한다 그러면 점이 생기는데 이 점을 breakpoint라 한다.

  그리고 벌레버튼을 누른다.

  그럼 화면 구성이 바뀌고 중지된 상태로 화면이 멈춘다.

  디버거를 이용하면 프로그램을 한줄한줄 실행시킬 수 있고(Step Over) 실행되는 그 순간에 애플리케이션 내의 변수의 상태를 하나하나 체크할 수 있다.

  디버거를 끝내고 싶을 땐 빨간색 버튼의 터미네이터를 클릭하고 우측 상단에 J(java) 버튼을 클릭한다.

***

2023-05-04 4일차 스터디
-------------

- 프로그램은 들어오는 정보인 입력을 처리해서 출력을 만들어내는 기계이다.

- input(입력값):

  Argument(프로그램을 실행할 때 텍스트 정보를 주는 것), File, Network, Audio, Program

- output(결과): Monitor, File, Audio, Program

- OkJavaGoInHomeInput.java

<pre><code>
import javax.swing.JOptionPane;

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OkJavaGoInHomeInput {
	
	// parameter, 매개변수 = args에 사용자가 입력한 값이 들어올 것이다
	// 문자열 뒤에 대괄호를 붙이면 문자열로만 이루어져 있는 배열이라는 데이터
	public static void main(String[] args) {
		
		// String id = JOptionPane.showInputDialog("Enter a ID");
		String id = args[0];
		//String bright = JOptionPane.showInputDialog("Enter a Bright level");
		String bright = args[1];
		// 창을 만들어낸다

		// Elevator call
		Elevator myElevator = new Elevator(id);
		myElevator.callForUp(1);
		
		// Security off
		Security mySecurity = new Security(id);
		mySecurity.off();
		
		// Light on
		Lighting hallLamp = new Lighting(id+ " / Hall Lamp");
		hallLamp.on();
		
		Lighting floorLamp = new Lighting(id+ " / floor Lamp");
		floorLamp.on();
		
		DimmingLights moodLamp = new DimmingLights(id+ " moodLamp");
		moodLamp.setBright(Double.parseDouble(bright));
		// bright는 String이지만 입력값으로 들어온 문자가 double 형으로 바뀐다
		moodLamp.on();
	}

} 
</code></pre>

- Runconfiguration

  입력값을 줄 때 Arguments에 값을 입력하면 된다.

  여러개의 값을 줄 땐 “입력값1” “입력값2” ...

  Arguments를 입력하게 되면 main 메소드의 args parameter는 argument 값을 받아서 동작한다.

- args

  문자열 배열(array)로 여러 개의 String 데이터가 들어올 수 있다.

  인덱스 0번부터 시작한다. ( args[0] )

- cmd
	- 외부 라이브러리도 포함해서 컴파일하기

	<pre><code>
	javac -cp ";lib" OkJavaGoInHome.java
	</code></pre>

	- 외부 라이브러리도 포함해서 실행하기

	<pre><code>
	java -cp ";lib" OkJavaGoInHome
	</code></pre>

	- 직접 컴파일 실행

	<pre><code>
	javac OkJavaGoInHomeInput.java
	java OkJavaGoInHomeInput "JAVA APT 707" 15.0
	// 띄어쓰기로 파라미터를 구분한다
	</code></pre>
	
***

2023-05-08 5일차 스터디
-------------

- Application Programming Interface

  자바가 기본적으로 제공하는 부품들의 조작방법을 API라 한다.

  Program은 시간의 순서에 따라서 실행된다는 시간이 강조된 표현 (시간의 순서)을 말한다.

  Application은 자바가 제공하는 부품들을 응용해서 Application 해서 만든다는 응용이 강조된 표현을 말한다.

  즉 우리가 자바를 응용해서 프로그래밍적으로 실행되는 프로그램을 만들기 위해서 사용해야 되는 조작 방법을 말한다.

- User Interface

  사용자가 우리가 만든 프로그램을 조작하기 위해 사용하는 조작 장치라는 뜻에서 UI라고 부른다.

  우리가 만든 프로그램을 사용자가 사용하지 않고 또 다른 부품으로 사용될 수도 있다.

- 상속

  java.lang.Object

   java.io.Writer

    java.io.PrintWriter

  PrintWriter(자식)은 Writer(부모)라는 클래스를 상속받았다.

  Wirter(자식)은 Object(부모)를 상속받았다.

  PrintWriter class를 우클릭해서 Open Type Hierarchy 클릭하면 상속관계를 볼 수 있다.

  Object 자바의 가장 기본적인 class이며 모든 class는 Object를 상속 받는다.

- Override

  Writer class에도 write method가 있고, PrintWriter class에도 write method가 있다면 이는 PrintWriter의 write가 Writer의 write를 덮어쓰기 했다고 한다.

  = 오버라이드 했다

- classApp

<pre><code>
public class ClassApp {

	public static void main(String[] args) {
		
		System.out.println(Math.PI);
		System.out.println(Math.floor(1.6)); // 소수점 없애기
		System.out.println(Math.ceil(1.6)); // 소수점 무조건 올리기
		// class는 서로 연관된 변수와 메소드를 모아서 이름을 붙인 것
		// 얘네들은 다 일회용

	}

}
</code></pre>

- InstanceApp

<pre><code>
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.PrintWriter;
public class InstanceApp {

	public static void main(String[] args) throws IOException {
		
		PrintWriter p1 = new PrintWriter("result1.txt");
		// 괄호 안에 내가 저장하고 싶은 파일의 이름을 적는다
		// 저 변수에 담겨있는 무언가를 PrintWriter라는 class의 instance라 한다
		// p1에 아무거나 들어가면 안 되기 때문에
		// PrintWriter라는 class의 instance만 들어간다는 뜻에서 데이터타입을 저것으로 지정
		p1.write("Hello 1");
		p1.close();
		
		PrintWriter p2 = new PrintWriter("result2.txt");
		p2.write("Hello 2");
		p2.close();
		p2.toString();
		
		// 동시에 여러개의 파일을 작업해야 할 땐 하나의 클래스를 사용하는 것보다 하나의 클래스 앞에 new를 붙여
		// 복제하여 각각의 다른 상태를 가지고 있는 인스턴스를 만들어 사용하는 것이 더 효율적이다
		
		// Constructor가 없으면 일회용
		// 이를 이용해 인스턴스를 만드는 것이 허용되어 있다는 것
		// new 뒤에 붙인 것
		// 인스턴스는 p1

	}

}
</code></pre>

- AccountingApp

<pre><code>
public class AccountingApp {

	public static void main(String[] args) {
		
		double vauleOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = vauleOfSupply*vatRate;
		double total = vauleOfSupply+vat;
		double expense = vauleOfSupply*expenseRate;
		double income = vauleOfSupply-expense;
		double dividend1 = income * 0.5;
		double dividend2 = income * 0.3;
		double dividend3 = income * 0.2;
		
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ vat );
		System.out.println("Total : "+ total );
		System.out.println("Expense : "+ expense );
		System.out.println("Income : "+ income );
		System.out.println("Dividend : "+ dividend1 );
		System.out.println("Dividend : "+ dividend2 );
		System.out.println("Dividend : "+ dividend3 );
		
		// Edit -> Find/Replace... 10000.0의 값 전체를 바꿔준다
		// 값 우클릭 -> Refactor -> Extract Local Variable...

	}

}
</code></pre>

- Package

  정리정돈의 도구

  서로 연관된 비슷한 성격의 class를 모아서 이름을 붙인 것

- class

  Package에 속해있는 것들 

  서로 연관된 변수(Variable)와 메소드(method)를 모아서 이름을 붙인 것

***

2023-05-09 6일차 스터디
-------------

- Method와 Class

  메소드는 서로 연관된 코드를 그룹핑해서 이름을 붙인 정리정돈의 상자다

	클래스는 서로 연관된 변수와 메소드를 그룹핑한 것이다 그리고 거기에 이름을 붙인 것이다 역시나 정리정돈의 상자이다

	메소드와 클래스가 중요한 이유는 우리가 소프트웨어를 만들어가는 데 있어서 구조를 결정하기 때문이다

	마치 우리 신체에서 뼈대와 같은 역할을 하는 것이다 = 상당히 중요함!

- AccountingIFApp

<pre><code>
public class AccountingIFApp {

	public static void main(String[] args) {
		
		double vauleOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = vauleOfSupply*vatRate;
		double total = vauleOfSupply+vat;
		double expense = vauleOfSupply*expenseRate;
		double income = vauleOfSupply-expense;
		
		double dividend1;
		double dividend2;
		double dividend3;
		
		if(income>10000.0) {
		 dividend1 = income * 0.5;
		 dividend2 = income * 0.3;
		 dividend3 = income * 0.2;
		} else {
			dividend1 = income * 1;
			dividend2 = income * 0;
			dividend3 = income * 0;
		}
		
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ vat );
		System.out.println("Total : "+ total );
		System.out.println("Expense : "+ expense );
		System.out.println("Income : "+ income );
		System.out.println("Dividend : "+ dividend1 );
		System.out.println("Dividend : "+ dividend2 );
		System.out.println("Dividend : "+ dividend3 );
		

	}

}
</code></pre>

- AccountingArrayApp

<pre><code>
public class AccountingArrayApp {

	public static void main(String[] args) {
		// String[] -> 문자열로 이루어져 있는 배열이라는 뜻
		// 그 배열의 값을 가져올 때 args[0] 이렇게 해서 입력값을 가져왔다
		// = 배열의 값을 꺼내오는 것을 보여주는 것이다
		
		double vauleOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = vauleOfSupply*vatRate;
		double total = vauleOfSupply+vat;
		double expense = vauleOfSupply*expenseRate;
		double income = vauleOfSupply-expense;
		
		//double rate1 = 0.5;
		//double rate2 = 0.3;
		//double rate3 = 0.2;
		
		double[] dividendRates = new double[3];
		dividendRates[0] = 0.5;
		dividendRates[1] = 0.3;
		dividendRates[2] = 0.2;
		// 서로 연관된 데이터를 정리정돈 하는 수단이 배열이다
		// 배열과 반복문은 서로 같이 쓸 때 엄청난 시너지 효과를 가져온다
		
		double dividend1 = income * dividendRates[0];
		double dividend2 = income * dividendRates[1];
		double dividend3 = income * dividendRates[2];
		
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ vat );
		System.out.println("Total : "+ total );
		System.out.println("Expense : "+ expense );
		System.out.println("Income : "+ income );
		System.out.println("Dividend : "+ dividend1 );
		System.out.println("Dividend : "+ dividend2 );
		System.out.println("Dividend : "+ dividend3 );
		

	}

}
</code></pre>

- AccountingArrayLoopApp

<pre><code>
public class AccountingArrayLoopApp {

	public static void main(String[] args) {
		
		double vauleOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = vauleOfSupply*vatRate;
		double total = vauleOfSupply+vat;
		double expense = vauleOfSupply*expenseRate;
		double income = vauleOfSupply-expense;
		
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ vat );
		System.out.println("Total : "+ total );
		System.out.println("Expense : "+ expense );
		System.out.println("Income : "+ income );
		
		double[] dividendRates = new double[3];
		dividendRates[0] = 0.5;
		dividendRates[1] = 0.3;
		dividendRates[2] = 0.2;
		
		int i = 0; // 몇 번 반복됐는지
		while(i < dividendRates.length) {
			System.out.println("Dividend : "+ (income*dividendRates[i]) );
			i = i + 1; // 반복할 때마다 i의 값을 1씩 증가시킬 것이다
		}
		
		// while은 반복문의 키워드이고 중괄호 안에 있는 코드가 계속해서 반복되게 하는 것이다
		// dividendRates.length의 값은 3
		// 배열과 단짝이다

	}

}
</code></pre>

- AccountingMethodApp

<pre><code>
public class AccountingMethodApp {
	
	public static double vauleOfSupply;
	public static double vatRate;
	public static double expenseRate;
	// 메인 메소드 밖에서 선언되었기 때문에 전역변수이다
	// 메인 안에서도 접근할 수 있고 getVAT도 접근할 수 있다
	// 즉 모든 메소드에서 접근할 수 있다
	// 우클릭 -> refactor -> Convert Local Variable to Field...

	public static void main(String[] args) {
		
		vauleOfSupply = 10000;
		vatRate = 0.1;
		expenseRate = 0.3;
		
		print();
		
		// vauleOfSupply는 main 메소드 중괄호 안에서 선언되었기 때문에 메인 메소드 안에서만 사용할 수 있는
		// 지역변수 (local variable) 이다

	}

	public static void print() {
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ getVAT() );
		System.out.println("Total : "+ getTotal() );
		System.out.println("Expense : "+ getExpense() );
		System.out.println("Income : "+ getIncome() );
		System.out.println("Dividend : "+ getDividend1() );
		System.out.println("Dividend : "+ getDividend2() );
		System.out.println("Dividend : "+ getDividend3() );
	}

	public static double getDividend1() {
		return getIncome() * 0.5;
	}
	
	public static double getDividend2() {
		return getIncome() * 0.3;
	}
	
	public static double getDividend3() {
		return getIncome() * 0.2;
	}

	public static double getIncome() {
		return vauleOfSupply-getExpense();
	}

	public static double getExpense() {
		return vauleOfSupply*expenseRate;
	}

	public static double getTotal() {
		return vauleOfSupply+getVAT();
	}

	private static double getVAT() {
		return vauleOfSupply*vatRate;
	} // 메소드를 만드는 코드

}

// 메소드는 서로 연관된 코드를 정리정돈 하는 상자다
</code></pre>

- AccountingClassApp

<pre><code>
class Accounting { // class 는 파일로 치면 디렉토리 역할과 비슷하다
	
	public double vauleOfSupply;
	public double vatRate;
	public double expenseRate;
	
	public void print() {
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ getVAT() );
		System.out.println("Total : "+ getTotal() );
		System.out.println("Expense : "+ getExpense() );
		System.out.println("Income : "+ getIncome() );
		System.out.println("Dividend : "+ getDividend1() );
		System.out.println("Dividend : "+ getDividend2() );
		System.out.println("Dividend : "+ getDividend3() );
	}

	public double getDividend1() {
		return getIncome() * 0.5;
	}
	
	public double getDividend2() {
		return getIncome() * 0.3;
	}
	
	public double getDividend3() {
		return getIncome() * 0.2;
	}

	public double getIncome() {
		return vauleOfSupply-getExpense();
	}

	public double getExpense() {
		return vauleOfSupply*expenseRate;
	}

	public double getTotal() {
		return vauleOfSupply+getVAT();
	}

	private double getVAT() {
		return vauleOfSupply*vatRate;
	} 
}

public class AccountingClassApp {

	public static void main(String[] args) {
		
		//Accounting.vauleOfSupply = 10000;
		//Accounting.vatRate = 0.1;
		//Accounting.expenseRate = 0.3;
		//Accounting.print();
		// 상태 = 변수의 값을 말한다
		// 이 과정이 빈번하게 발생한다면 클래스의 내부적인 상태를 바꾸는 행위가 버그를 유발할 가능성이 굉장히 높아진다
		
		// instance
		Accounting a1 = new Accounting();
		// new를 붙이면 Accounting class를 복제하는 명령이다
		// a1의 변수의 값으로는 Accounting의 복제본만 들어올 수 있다
		a1.vauleOfSupply = 10000.0;
		a1.vatRate = 0.1;
		a1.expenseRate = 0.3;
		a1.print();
		// class 이름 앞에 new를 붙여서 만들어진 그 무엇을 instance라 부른다
		// 이 코드가 동작하기 위해선 static 키워드를 사용하면 안 된다
		System.out.println("------------------------");
		
		Accounting a2 = new Accounting();
		a2.vauleOfSupply = 20000.0;
		a2.vatRate = 0.05;
		a2.expenseRate = 0.2;
		a2.print();

	}
	
	// 소속관계를 명확하게 해야 다른 취지의 코드들과 뒤섞여도 상관없고, 흔한 이름의 메소드를 사용해도 같은 이름의 메소드들이
	// 공존할 수 있게 된다 ( class가 달라야 한다 )

}
</code></pre>

- instance

  인스턴스는 하나의 클래스를 복제해서 서로 다른 데이터의 값과 서로 같은 메소드를 가진 복제본을 만드는 것이다
	
- Outline

  class 안에 소속되어 있는 여러 가지 멤버들(변수, 메소드)의 리스트를 보여준다

  (Window -> showview)

***

2023-05-10 7일차 스터디
-------------

- BooleanApp

<pre><code>
package java_flow_control;

public class BooleanApp {

	public static void main(String[] args) {
		
		System.out.println("One");
		System.out.println(1);
		
		System.out.println(true);
		System.out.println(false);
		
		String foo = "Hello World";
		// String true = "Good";
		// true, false는 변수의 이름으로 사용할 수 없다
		// 이미 쓰이고 있는 컴퓨터 언어
		// = reserved word
		
		System.out.println(foo.contains("World")); // true
		// .contains는 그 문자열에 입력값으로 전달할 어떠한 값이 들어있다면 true를 return하고,
		// 없다면 false를 return 한다
		System.out.println(foo.contains("egoing")); // false

	}

}
</code></pre>

- ComparisonOperatorApp

<pre><code>
package java_flow_control;

public class ComparisonOperatorApp {

	public static void main(String[] args) {
		
		System.out.println(1 > 1); // false
		System.out.println(1 == 1); // true
		System.out.println(1 < 1);
		System.out.println(1 >= 1);
		System.out.println(1 <= 1);
		
		// 비교연산자는 왼쪽에 있는 값과 오른쪽에 있는 값을 비교해서 그 결과가 무엇이냐에 따라서
		// true or false 둘중 하나의 값을 만들어내는 연산자이다
	}

}
</code></pre>

- IfApp

<pre><code>
package java_flow_control;

public class IfApp {

	public static void main(String[] args) {
		
		System.out.println("a");
//		if(false) {
//			System.out.println(1);
//		} else {
//			if(true) {
//			System.out.println(0);
//			} else {
//				System.out.println(00);
//			}
//		}
		
		if(false) {
			System.out.println(1);
		} else if (true) {
			System.out.println(2);
		} else {
			System.out.println(3);
		}
		
		System.out.println("b");
		
		// if문 () 안에는 boolean만이 저 값이 될 수 있다
		// () 안의 값이 true일 때만 실행된다
		// 변화 가능하도록 바꾸어야 한다
	}

}
</code></pre>

- AuthApp

<pre><code>
package java_flow_control;

public class AuthApp {

	public static void main(String[] args) {
		
		System.out.println(args[0]);
		
		String id = "egoing";
		String inputId = args[0];
		
		String pass = "lk3374";
		String inputPass = args[1];
		
		
		System.out.println("Hi !");
		
		// if(inputId == id) {
//		if(inputId.equals(id)) {
//			if(inputPass.equals(pass)) {
//				System.out.println("Master !!");
//			} else {
//				System.out.println("Wrong pass..");
//			}
//		} else {
//			System.out.println("Who are you?");
//		}
		
		if(inputId.equals(id) && inputPass.equals(pass)) {
			System.out.println("Master !!");
		} else {
			System.out.println("Who are you??");
		}
		
	}

}
</code></pre>

- 산술 연산자

  1 + 1 = 2 여기서 +은 산술연산자

- 결합 연산자

  “1” + “1” = “11” 여기서 +은 결합연산자 (문자열을 만들어내는 연산자)

- primitive (데이터 타입)

  원시라는 뜻으로, 더 이상 쪼갤 수 없는 데이터를 말한다

	primitive = boolean, int, double, short, long, float, char

	non primitive = String, Array, Date, File, Class ...

- LogicalOperatorApp

<pre><code>
package java_flow_control;

public class LogicalOperatorApp {

	public static void main(String[] args) {
		
		// AND
		System.out.println(1 == 1);
		System.out.println(true && true); // true
		// logical 연산자는 좌항과 우항 모두 boolean이 와야한다
		System.out.println(true && false); // false
		System.out.println(false && true); // false
		System.out.println(false && false); // false
		
		// OR
		System.out.println(true || true); // true
		System.out.println(true || false); // true
		System.out.println(false || true); // true
		System.out.println(false || false); // false
		
		// NOT
		System.out.println(!true); // false
		System.out.println(!false); // true

	}

}
</code></pre>

- AuthApp2

<pre><code>
package java_flow_control;

public class AuthApp2 {

	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args[0];
		
		String pass = "lk3374";
		String pass2 = "lk5332";
		String inputPass = args[1];
		
		
		
		System.out.println("Hi !");
		
		boolean isRight = (inputPass.equals(pass) || inputPass.equals(pass2));
		
		
		if(inputId.equals(id) && isRight) {
			System.out.println("Master !!");
		} else {
			System.out.println("Who are you??");
		}
		
	}

}
</code></pre>

- LoopApp

<pre><code>
package java_flow_control;

public class LoopApp {

	public static void main(String[] args) {
		
		System.out.println(1);
		
		int i = 0; // 어떤 변수 이름을 써도 되지만, 반복문에서 카운팅하기 위해 i를 쓴다
		while(i < 3) {
			System.out.println(2);
			System.out.println(3);
			// i = i + 1;
			i++;
		}
		
		System.out.println("----------------------------------");
		
		// 괄호 안에는 boolean
		// 디버거 F6번 사용 (다음줄 실행)
		
		// 몇번 반복해 ~ 라고 시킬 땐 for문이 더 좋다
		// 괄호 안에 초깃값 설정, boolean, 반복이 실행될 때마다 +
		for(int j = 0; j < 3; j++) {
			System.out.println(2);
			System.out.println(3);
		}
		// 무조건 한번은 실행된다
		
		System.out.println(4);

	}

}
</code></pre>

- ArrayApp

<pre><code>
package java_flow_control;

public class ArrayApp {

	public static void main(String[] args) {
		
		// egoing, jinhuck, youbin
		// String users = "egoing, jinhuck, youbin";
		String[] users = new String[3]; // 배열의 크기 3 (3칸짜리 캐비닛)
		users[0] = "egoing";
		users[1] = "jinhuck";
		users[2] = "youbin";
		// 문자열로 이루어져 있는 배열이라고 하는 데이터 타입을 값으로 하는 users라고 하는 변수를 만드는 것
		
		System.out.println(users[1]);
		System.out.println(users.length); // 배열에 담겨있는 값이 3개다
		// = 3칸짜리 배열이다
		
		// 배열을 생성할 때 값을 담아서 생성하는 방법
		int[] score = {10, 100, 100};
		System.out.println(score[0]);
		System.out.println(score.length);
		
		// 0,1,2 -> index
		// "egoing"... -> element, 원소

	}

}
</code></pre>

- LoopArray

<pre><code>
package java_flow_control;

public class LoopArray {

	public static void main(String[] args) {
		
		/*
		 * <li>egoing</li>
		 * <li>jinhuck</li>
		 * <li>younin</li>
		 */
		
		String[] users = new String[3]; 
		users[0] = "egoing";
		users[1] = "jinhuck";
		users[2] = "youbin";
		
		for(int i = 0; i < 3; i++) {
			System.out.println("<li> " + users[i] +" </li>");
		}
		
		for(int i = 0; i < users.length; i++) {
			System.out.println(users[i] +",");
			if(i==2) {
				System.out.println(users[i]);
			}
		}
	}
}
</code></pre>

