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

**java코드를 이용해 라즈베리파이의 특정된 부위에 전기를 통하도록 할수 있음**

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
// argument는 사용자 입력을 의미하는 문자열배열이다.
//parameter는 함수에서 전달되어 사용되어지는 변수이다. argument는 main()함수의 매개변수로 작용한다.
//배열은 메모리에 순서대로 차곡차곡 저장된 데이터 묶음이다.배열은 미리 데이터의 크기와 각 데이터의 종류가 지정되어야 메모리를얼마나 차지할지 정할수 있다.
javac를 이용해 자바의 각종 명령어를 알 수 있음.
컴파일 : 'javac 파일이름.java' 명령어를 사용하면 해당 파일이 컴퓨터가 이해할 수 있는 확장자가 .class인 파일이 생성된다. 

실행 : 'java 파일이름' 명령어를 사용해 프로그램을 실행시킨다. java가 해당 파일에서 파일이름과 동일한 클래스를 찾고 main 함수를 찾은 뒤 main 안의 코드를 순차적으로 실행하고 종료한다.

다른 사람이 만들어 여러 유용한 기능을 모아둔 클래스 집합, 개발 시 공동으로 사용될 수 있는 특정한 기능들을 모듈화 한 것으로, 완전한 프로그램이 아닌 특정한 부분만을 수행할 수 있도록 만들어 놓은 것. 
패키지는 비슷한 기능을 모아둔 것, 라이브러리는 패키지들이나 파일들이 모아져 있는것이 라이브러리이다 

이클립스나 비주얼 스튜디오가 설치가 안되어있거나 실행이 안될때 간략하게 터미널로 실행해 볼 수 있다


많은 클릭 과정을 생략하고 단 한줄로 컴파일 후 실행할 수 있다. 