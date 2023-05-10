**helloworld출력**
0501
public class HelloworldApp
	public static void main(String[] args) {
		System.out.println("HelloWorld!!");
	}
**데스크톱 어플리케이션 만들기**
import javax.swing.*;   
import java.awt.Dimension;
import java.awt.Toolkit;
public class HelloWorldGUI{
    public static void main(String[] args){
        javax.swing.SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                JFrame frame = new JFrame("HelloWorld GUI");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setPreferredSize(new Dimension(800, 300));
                JLabel label = new JLabel("Hello World!!", SwingConstants.RIGHT);
                frame.getContentPane().add(label);
                Dimension dim = Toolkit.getDefaultToolkit().getScreenSize();
                frame.setLocation(dim.width/2-400/2, dim.height/2-300/2);

                frame.pack();
                frame.setVisible(true);
            }
        });
    }
}
**Dimension()괄호안의 숫자로 가로 세로의 길이 조정and right를 넣어서 문자를 우측으로 보냄
수장한 코드JLabel label = new JLabel("Hello World!!", SwingConstants.LEFT);**

**사물을 자라로 제어하기, java코드를 이용해 라즈베리파이의 특정된 부위에 전기를 통하도록 할수 있음**

0502
public class Datatype{
	public static void main(String[]args) {
		System.out.println(6);//Number
		System.out.println("six");//String
		System.out.println("6");//String 6
		System.out.println(6+6);//12
		System.out.println("6"+"6");//66"문자사이의+는 문자결합자로 사용됨
		
		System.out.println(6*6);//36
		//System.out.println("6"*"6");문자열은 *사용이 되지않음//
		System.out.println("1111".length());//문자열의 길이를 알려줌 length는 숫자의 길이를 알려주지는 않음
		
		
	}
}
public class StringApp {

	public static void main(String[] args) {
	
		System.out.println("Hello World");//String
		//System.out.println('Hello World');Charter 문자와 문자열은 차이가 있음//
		System.out.println("Hello "
				+ "World");
		System.out.println("Hello \nWorld");//\n을 이용하여 줄바꿈을 사용할수 있다.
		System.out.println("Hello \"World\""); //문자열 사이에 ""를 추가하기 위해서 \\사이에 ""문자열을 추가해준다Hello "World"
		
	}

}

public class StringOperation {

	public static void main(String[] args) {
		
		System.out.println("Hello World".length());//11
		System.out.println("Hello, leezche ...bye. ".replace("leezche", "egoing"));//replace는 앞에를 뒤에로 바꿔준다.
		

	}

}
0503
public class Variable {

	public static void main(String[] args) {
		
		int a = 1;//number => integer==정수 -값과 0 +값을 가짐
		System.out.println(a);
		double b = 1.1;//real number =>double 실수 음의값과 0과 양의값과 소수점의 값을 가짐
		System.out.println(b);
		String c = "Hello World";//문자열
		System.out.println(c);
	}

}
public class Letter {

	public static void main(String[] args) {
		String name = "leezche";//변수의 이름을 정해줌으로써 목적을 파악할 수있다.
		System.out.println("Hello. "+name+" ... "+name+" ... "+name+" ... bye");
		double VAT = 10.0;
		System.out.println(VAT);
	}

}
public class program {

	public static void main(String[] args) {
		
		System.out.println(1);
		System.out.println(2);
		System.out.println(3);
		//만약 위 코드의 개수가 10000개가 넘는다면 사람이 할 수 없는 일을 컴퓨터 언어인 자바에 위임이켜서 실해하는것
	}

}
**iot프로그램 만들기**
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
public class OKjavaGoinHome {

	public static void main(String[] args) {
		
		String id = "java apt 507";
		
		//Elevator call
		Elevator myElevator = new Elevator(id);//Elevator 는 데이터 타입, myElevator는 변수.
		myElevator.callForUp(1);
		
		//Security off
		Security mySecurity = new Security(id);
		mySecurity.off();
		
		//Light on
		Lighting hallLamp = new Lighting("id+ /  hall lamp");
		hallLamp.on();
		
		Lighting floorLamp = new Lighting("id+ / hall lamp");
		floorLamp.on();
		
		

	}

}
//디버거 코드를 분석 step over 명령어 하나만 실행 디버거를 통해 잘못된 코드를 찾을 수 있다.\

0507

import javax.swing.JOptionPane;

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
public class OKjavaGoinHome {

	public static void main(String[] args) {
		
		String id = JOptionPane.showInputDialog("Enter a ID");//showInputDialog는 상자에 값을입력할때까지 대기함		
		//Elevator call
		String bright = JOptionPane.showInputDialog("Enter a Bright Level");
		Elevator myElevator = new Elevator(id);//Elevator 는 데이터 타입, myElevator는 변수.
		myElevator.callForUp(1);
		
		//Security off
		Security mySecurity = new Security(id);
		mySecurity.off();
		
		//Light on
		Lighting hallLamp = new Lighting("id+ /  hall lamp");
		hallLamp.on();
		
		Lighting floorLamp = new Lighting("id+ / hall lamp");
		floorLamp.on();
		
		DimmingLights moodLamp = new DimmingLights(id+"moodLamp");
		moodLamp.setBright(Double.parseDouble(bright));
		moodLamp.on();
	}

}
//디버거 코드를 분석 step over 명령어 하나만 실행
//showInputDialog를 통해 값을 입력해야만 작동한는 장치를 만들어 보았다.

String id = args[0];
String bright = args[1];

//argument는 사용자 입력을 의미하는 문자열배열이다.

//parameter는 함수에서 전달되어 사용되어지는 변수이다. argument는 main()함수의 매개변수로 작용한다.

//배열은 메모리에 순서대로 차곡차곡 저장된 데이터 묶음이다.배열은 미리 데이터의 크기와 각 데이터의 종류가 지정되어야 메모리를얼마나 차지할지 정할수 있다.
javac를 이용해 자바의 각종 명령어를 알 수 있음.

컴파일 : 'javac 파일이름.java' 명령어를 사용하면 해당 파일이 컴퓨터가 이해할 수 있는 확장자가 .class인 파일이 생성된다. 

실행 : 'java 파일이름' 명령어를 사용해 프로그램을 실행시킨다. java가 해당 파일에서 파일이름과 동일한 클래스를 찾고 main 함수를 찾은 뒤 main 안의 코드를 순차적으로 실행하고 종료한다.

다른 사람이 만들어 여러 유용한 기능을 모아둔 클래스 집합, 개발 시 공동으로 사용될 수 있는 특정한 기능들을 모듈화 한 것으로, 완전한 프로그램이 아닌 특정한 부분만을 수행할 수 있도록 만들어 놓은 것. 
패키지는 비슷한 기능을 모아둔 것, 라이브러리는 패키지들이나 파일들이 모아져 있는것이 라이브러리이다 

이클립스나 비주얼 스튜디오가 설치가 안되어있거나 실행이 안될때 간략하게 터미널로 실행해 볼 수 있다


많은 클릭 과정을 생략하고 단 한줄로 컴파일 후 실행할 수 있다. 

0508
프로그램에게 사용되는 것이 API,
사용자가 자바 프로그램을 이용할 수 있도록 만들어 놓은것이 UI 

패키지 : 클래스들을 모아둔 것 패키지를 통해 라이브러리와 구별이 가능하다. 


패키지를 사용하는 것은 클래스명을 보장하기 위함이다
서로 다른 용도의 라이브러리를 사용할 때 이름이 충돌하는 클래스가 있을 수 있는데 
이럴 때 패키지 기능을 이용하여 클래스 이름이 충돌하는 것을 방지한다.

클래스 : 객체를 정의할 수 있는 틀 또는 설계도이다. 클래스는 객체의 변수들과 객체 생성을 나타내는 메소드들로 나타낸다. 

변수 : 데이터를 저장하기 위한 메모리 공간

메소드 : 특정 작업을 수행하는 일련의 과정을 묶은 것, 즉 클래스에 필요한 기능을 함수로 묶은 것 이 때, 클래스는 객체의 변수들로 이루어져있다고 되어있는데 이는 필드라고도 한다. 클래스에 포함되어 있는 변수가 필드인 것이다. 

클래스는 메소드와 변수들의 집합이다.
패키지는 그 클래스들을 담아놓은 집합
메소드는 값을 입력해야 하는 함수이고, 변수는 그 함수의 값이다.
클래스안에는 변수와 메소드가 있다.
인스턴스는 클래스에 있는 속성을 사용하는 복제품을 만드는 것이다.
단, 인스턴스를 사용하려면 클래스 안에 컨스트럭쳐가 있어야 된다.
그러나 클래스 중에 constructor가 없는 클래스(예:Math)는  인스턴스로 사용하지 못하는 클래스다. 즉, 인스턴스를 사용하려면 일단 해당 클래스에 constructor 있어야된다 

상속은 말 그대로 상속받는것.
하위클래스가 상위클래스의 변수와 메소드를 어느정도 이어받으면서 새로운 클래스를 만들어 내는 것
모든 메소드나 변수를 만들지 않아도되고, 상위클래스의 메소드/변수를 함께 사용 할 수 있어서 좋다.

public class Accounting {

	public static void main(String[] args) {
		
		System.out.println("Value of supply : "+10000.0);
		System.out.println("VAT : "+(10000.0*0.1));
		System.out.println("Total : "+ (10000.0*0.1));
		System.out.println("Expense : "+ (10000.0*0.1));
		System.out.println("Income : "+ (10000.0 - 10000.0*0.3));
		System.out.println("Dividend1 : "+ (10000.0 - 10000.0*0.3)*0.5);
		System.out.println("Dividend2 : "+ (10000.0 - 10000.0*0.3)*0.3);
		System.out.println("Dividend3 : "+ (10000.0 - 10000.0*0.3)*0.2);
		
		
		
	}

}
public class Accounting {

	public static void main(String[] args) {
		
		
		double valueOfSupply = 10000.0;
		double exepnseRate = 0.3;
		double vatRate = 0.1;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply*exepnseRate;
		double income = valueOfSupply - expense;
		double dividend1 = income*0.5;
		double dividend2 = income*0.3;
		double dividend3 = income*0.2;
		
		System.out.println("Value of supply : "+valueOfSupply);	
		
		System.out.println("VAT : "+vat);
		
		System.out.println("Total : "+ total);
		
		System.out.println("Expense : "+ expense);
		System.out.println("Income : "+ income);
		
		System.out.println("Dividend1 : "+ dividend1);
		
		System.out.println("Dividend2 : "+ dividend2);
		
		System.out.println("Dividend3 : "+ dividend3);
		
		
		
	}

}
double valueOfSupply = Double.parseDouble(args[0]);
//args라는 문자열을 더블형에 넣어줌
0509
if문을 사용한 조건문
public class Accountingif {

	public static void main(String[] args) {
			
		
		double valueOfSupply = Double.parseDouble(args[0]);
		double exepnseRate = 0.3;
		double vatRate = 0.1;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply*exepnseRate;
		double income = valueOfSupply - expense;
		double dividend1;
		double dividend2;
		double dividend3;
		if(income > 10000.0) {
			dividend1 = income*0.5;
			dividend2 = income*0.3;
			dividend3 = income*0.2;
		} else {
			dividend1 = income*1.0;
			dividend2 = income*0;
			dividend3 = income*0;
		}
		
		
		System.out.println("Value of supply : "+valueOfSupply);	
		System.out.println("VAT : "+vat);
		System.out.println("Total : "+ total);
		System.out.println("Expense : "+ expense);
		System.out.println("Income : "+ income);
		System.out.println("Dividend1 : "+ dividend1);
		System.out.println("Dividend2 : "+ dividend2);
		System.out.println("Dividend3 : "+ dividend3);
		
		
		
	}
	public class AccountingArray {

	public static void main(String[] args) {
			
		
		double valueOfSupply = Double.parseDouble(args[0]);
		double exepnseRate = 0.3;
		double vatRate = 0.1;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply*exepnseRate;
		double income = valueOfSupply - expense;
		
		double[] dividendRates = new double[3];
		dividendRates[0] = 0.5;
		dividendRates[1] = 0.3;
		dividendRates[2] = 0.2;
		
		double dividend1 = income*dividendRates[0];
		double dividend2 = income*dividendRates[1];
		double dividend3 = income*dividendRates[2];
		
		System.out.println("Value of supply : "+valueOfSupply);	
		
		System.out.println("VAT : "+vat);
		
		System.out.println("Total : "+ total);
		
		System.out.println("Expense : "+ expense);
		System.out.println("Income : "+ income);
		
		System.out.println("Dividend1 : "+ dividend1);
		
		System.out.println("Dividend2 : "+ dividend2);
		
		System.out.println("Dividend3 : "+ dividend3);
		
		
		
	}
	반복문을 사용함으로써 하나의 문장으로 여러개의 로직을 사용가능하게 한다.
	public class AccountingArrayLoop {

	public static void main(String[] args) {
			
		
		double valueOfSupply = Double.parseDouble(args[0]);
		double exepnseRate = 0.3;
		double vatRate = 0.1;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply*exepnseRate;
		double income = valueOfSupply - expense;
		
		double[] dividendRates = new double[3];
		dividendRates[0] = 0.5;
		dividendRates[1] = 0.3;
		dividendRates[2] = 0.2;
		
		
		System.out.println("Value of supply : "+valueOfSupply);	
		System.out.println("VAT : "+vat);
		System.out.println("Total : "+ total);
		System.out.println("Expense : "+ expense);
		System.out.println("Income : "+ income);
		
		double dividend1 = income*dividendRates[0];
		double dividend2 = income*dividendRates[1];
		double dividend3 = income*dividendRates[2];
		
		
		int i = 0;
		while(i < dividendRates.length) {
		System.out.println("Dividend : "+ (income * dividendRates[i]));
		i = i + 1;
		}
		
	}

}
public class AccountingMethod {
	public static double valueOfSupply;
	public static double vatRate;
	public static double exepnseRate;
	public static void main(String[] args) {
			
		valueOfSupply = 10000.0;
		vatRate = 0.1;
		
		double vat = getVAT();
		double total = getTotal();
		double expense = getExepnse();
		double income = getIncome();
		double dividend1 = getDividend1();
		double dividend2 = getDividend2();
		double dividend3 = getDividend3();
		
		print();
			
	}

	public static void print() {
		System.out.println("Value of supply : "+valueOfSupply);	
		System.out.println("VAT : "+getVAT());
		System.out.println("Total : "+ getTotal());
		System.out.println("Expense : "+ getExepnse());
		System.out.println("Income : "+ getIncome());
		System.out.println("Dividend1 : "+ getDividend1());
		System.out.println("Dividend2 : "+ getDividend2());
		System.out.println("Dividend3 : "+ getDividend3());
	}

	public static double getDividend1() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}
	public static double getDividend2() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public static double getDividend3() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public static double getIncome() {
		double income = valueOfSupply - getExepnse();
		return income;
	}

	public static double getExepnse() {
		double expense = valueOfSupply*exepnseRate;
		return expense;
	}

	public static double getTotal() {
		double total = valueOfSupply + getVAT();
		return total;
	}

	private static double getVAT() {
		return valueOfSupply*vatRate;//메소드를 만드는 코드
	}

}
//메소드를 사용해 수많히 많은 개수의 코드를 간략화 해서 만들수 있다.

//클래스
class Accounting{
	 {
		System.out.println("Value of supply : "+valueOfSupply);	
		System.out.println("VAT : "+getVAT());
		System.out.println("Total : "+ getTotal());
		System.out.println("Expense : "+ getExepnse());
		System.out.println("Income : "+ getIncome());
		System.out.println("Dividend1 : "+ getDividend1());
		System.out.println("Dividend2 : "+ getDividend2());
		System.out.println("Dividend3 : "+ getDividend3());
	}

	public static double valueOfSupply;
	public static double vatRate;
	public static double exepnseRate;
	public static double getDividend1() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}
	public static double getDividend2() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public static double getDividend3() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public static double getIncome() {
		double income = valueOfSupply - getExepnse();
		return income;
	}

	public static double getExepnse() {
		double expense = valueOfSupply*exepnseRate;
		return expense;
	}

	public static double getTotal() {
		double total = valueOfSupply + getVAT();
		return total;
	}

	private static double getVAT() {
		return valueOfSupply*vatRate;//메소드를 만드는 코드
	}
	public static void print() {
		
		
	}

	
}
public class Accountingclass {
	
	public static void main(String[] args) {
			
		Accounting.valueOfSupply = 10000.0;
		Accounting.vatRate = 0.1;
		Accounting.exepnseRate = 0.3;
		Accounting.print();;
		//anotherVariable = ...;
		//anotherMethod = ...;
	
		
			
	}

	
	
}
//클래스는 객체지향의 핵심으로 서로 연관된 변수와 메소드를 그룹핑해 소속관계를 명확히 해서 이름을 붙여 놓은 것이다. 사용하는 이유는 소속관계를 명확학게 해 재사용성과 유지보수를 용이하게 하기 위해서 이다.//
//인스턴스는 하나의 클래스를 복제해서 서로다른 데이터의 값과 서로 같은 메소드를 가진 복제본을 만드는 것.

//클래스는 객체지향의 핵심으로 서로 연관된 변수와 메소드를 그룹핑해 소속관계를 명확히 해서 이름을 붙여 놓은 것이다. 사용하는 이유는 소속관계를 명확학게 해 재사용성과 유지보수를 용이하게 하기 위해서 이다.//
//인스턴스는 하나의 클래스를 복제해서 서로다른 데이터의 값과 서로 같은 메소드를 가진 복제본을 만드는 것.
//클래스의 상태를 변경하는 행위가 버그를 유발할 가능성이 있음
//클래스 앞에 new를 붙여 복제한 것을 인스턴스(instance)라고 함
//static이 사용되어서는 안됨
class Accounting{
	public double valueOfSupply;
	public double vatRate;
	public double exepnseRate;
	 {
		System.out.println("Value of supply : "+valueOfSupply);	
		System.out.println("VAT : "+getVAT());
		System.out.println("Total : "+ getTotal());
		System.out.println("Expense : "+ getExepnse());
		System.out.println("Income : "+ getIncome());
		System.out.println("Dividend1 : "+ getDividend1());
		System.out.println("Dividend2 : "+ getDividend2());
		System.out.println("Dividend3 : "+ getDividend3());
	}

	
	public double getDividend1() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}
	public double getDividend2() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public double getDividend3() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public double getIncome() {
		double income = valueOfSupply - getExepnse();
		return income;
	}

	public double getExepnse() {
		double expense = valueOfSupply*exepnseRate;
		return expense;
	}

	public double getTotal() {
		double total = valueOfSupply + getVAT();
		return total;
	}

	private  double getVAT() {
		return valueOfSupply*vatRate;//메소드를 만드는 코드
	}
	public void print() {
		
		
	}

	
}

public class Accountingclass {
	
	public static void main(String[] args) {
			
		
		//instance
		Accounting a1 = new Accounting();
		a1.valueOfSupply = 10000.0;
		a1.vatRate = 0.1;
		a1.exepnseRate = 0.3;
		a1.print();
		
		Accounting a2 = new Accounting();
		a2.valueOfSupply = 20000.0;
		a2.vatRate = 0.05;
		a2.exepnseRate = 0.2;
		a2.print();
			
	}

	
	
}