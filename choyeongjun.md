0501
4-1**HelloWorld**
public class HelloWorldApp {
	public static void main(String[] args) {
		System.out.println("Hello Word!!");
	}
}

4-3**Java 동작원리**
Java Source code.java

        |(compile)

Java Application.class

        |(Run)

Java Virtual Machine

        |(Run)

      computer          

5-1**Hello Java World**
import javax.swing.*;   
import java.awt.Dimension;
import java.awt.Toolkit;
public class HelloWorldGUIApp{
    public static void main(String[] args){
        javax.swing.SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                JFrame frame = new JFrame("HelloWorld GUI");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setPreferredSize(new Dimension(800, 300)); //800의 수치를 400으로 변경하면 결과 창의 가로길이가 줄어듬
                JLabel label = new JLabel("Hello World!!", SwingConstants.RIGHT); /* RIGHT를 CENTER로 변경하면 결과 창에 나타나는 HelloWorld!! 단어가 가운데에 오는 것을 볼 수 있음*/
                frame.getContentPane().add(label);
                Dimension dim = Toolkit.getDefaultToolkit().getScreenSize();
                frame.setLocation(dim.width/2-400/2, dim.height/2-300/2);

                frame.pack();
                frame.setVisible(true);
            }
        });
    }
}

5-2**사물을 자바로 제어하기**
import com.pi4j.io.gpio.GpioController;
import com.pi4j.io.gpio.GpioFactory;
import com.pi4j.io.gpio.GpioPinDigitalOutput;
import com.pi4j.io.gpio.PinState;
import com.pi4j.io.gpio.RaspiPin;

public class HelloWorldRaspberryPi {

	public static void main(String[] args) throws InterruptedException {

		final GpioController gpio = GpioFactory.getInstance();
		final GpioPinDigitalOutput pin = gpio.provisionDigitalOutputPin(RaspiPin.GPIO_01, "PinLED", PinState.LOW);
		final int SHORT_INTERVAL = 200; //0.2초를 의미함
		final int LONG_INTERVAL = SHORT_INTERVAL * 3;
		final int LETTER_INTERVAL = SHORT_INTERVAL * 7;

		while (true) {
			// H
			pin.high();//high는 불이 켜지는 동작
			Thread.sleep(SHORT_INTERVAL);
			pin.low();//low는 불이 꺼지는 동작
			Thread.sleep(SHORT_INTERVAL);
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(LETTER_INTERVAL);

			// e
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(LETTER_INTERVAL);

			// l
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);

			pin.high();
			Thread.sleep(LONG_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);

			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(LONG_INTERVAL);

			// l
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);

			pin.high();
			Thread.sleep(LONG_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);

			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(LONG_INTERVAL);
		}
	}
}

===============================================

0502
6-1
데이터의 여러가지 종류가 있고 그 종류에 따라 수행할 수 있는 연산이 달라진다.

6-2**데이터타입**
public class Datatype{
    public static void main(String[] args) {
        System.out.println(6); // Number
        System.out.println("six"); // String
         
        System.out.println("6"); // String 6
         
        System.out.println(6+6); // 12  단순 더하기 연산처리
        System.out.println("6"+"6"); // 66  각각 문자열로 묶여있으면 결합연산자로 사용됨
         
        System.out.println(6*6); // 36
//      System.out.println("6"*"6"); //문자열은 곱하기 연산을 할 수가 없다
         
        System.out.println("1111".length()); // 4
//      System.out.println(1111.length()); // error
    }
}

6-3**데이터연산**
public class Number {
 
    public static void main(String[] args) {
        // Operator
        System.out.println(6 + 2); // 8
        System.out.println(6 - 2); // 4
        System.out.println(6 * 2); // 12
        System.out.println(6 / 2); // 3
 
        System.out.println(Math.PI); // 3.141592653589793
        System.out.println(Math.floor(Math.PI)); // 3.0  floor은 내림표현으로 소수점을 잘라버림
        System.out.println(Math.ceil(Math.PI)); // 4.0  ceil은 올림표현으로 실수 +1을 하면 됨  ex) Math.ceil(5.1);
                                                                                                // 6
         
    }
 
}

6-4**문자열의 표현**
public class StringApp {
 
    public static void main(String[] args) {
         
        // Character VS String 
        System.out.println("Hello World"); // String 문자열(Character들의 집합체)
        System.out.println('H'); // Character 한 글자를 표현하는 데이터 타입
        System.out.println("H"); // String
     
        System.out.println("Hello "
                + "World"); // 문자열과 문자열이 더해진 것(줄바꿈 안됨)
         
        // new line
        System.out.println("Hello \nWorld"); // 줄바꿈
         
        // escape
        System.out.println("Hello \"World\"");// Hello "World"      " 앞에 \를 넣어 줌으로써 "World"를 표현할 수 있게 됨
    }
 
}

6-5**문자열 다루기**
public class StringOperation {
 
    public static void main(String[] args) {
         
        System.out.println("Hello World".length()); // 11   length를 사용하면 문자열 내부의 글자 수를 파악할 수 있음
        System.out.println("Hello, [[[name]]] ... bye. ".replace("[[[name]]]", "duru")); /* replace - 특정 문자열을 다른 문자열로 교체하는 명령 내릴 수 있음*/
 
    }
 
}

===============================================

0503
8-1**변수의 정의(Variable)**
public class Variable {
 
    public static void main(String[] args) {
         
        int a = 1; // Number -> integer(정수) 
        System.out.println(a);
         
        double b = 1.1; // real number(실수) -> double 
        System.out.println(b);
         
        String c = "Hello World"; // 문자열
        System.out.println(c);
    }
 
}

8-2**변수의 효용**
public class Letter {
 
    public static void main(String[] args) {
        String name = "leezche";
        System.out.println("Hello, "+name+" ... "+name+" ... egoing ... bye");  // 개인적으로 C언어에서 scanf와 비슷한 원리라 생각함
         
        double VAT = 10.0;
        System.out.println(VAT); 

        //남들이봐도 쉽게 알아볼 수 있게 코딩을 이쁘게 해야함

    }
 
}

8-3**Casting**
public class Casting {
 
    public static void main(String[] args) {
         
        double a = 1.1;
        double b = 1;  // double을 사용했기 때문에 1.0 으로 출력            자동화
        double b2 = (double) 1; //                                        수동화 
         
        System.out.println(b);
         
        // int c = 1.1; 
        double d = 1.1; 
        int e = (int) 1.1; // (int)를 사용해 줌으로써 1.1 -> 1로 변경한 후 int e 에 적용. 즉, int e = 1; 과 동일한 의미
        System.out.println(e);
         
        // 1 to String 
        String f = Integer.toString(1);
        System.out.println(f.getClass());
 
 
    }
 
}

9-3**IoT 프로그램 만들기**
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHome {
 
    public static void main(String[] args) {
         
        String id = "JAVA APT 507";
         
        // Elevator call 
        Elevator myElevator = new Elevator(id);
        myElevator.callForUp(1);
         
        // Security off 
        Security mySecurity = new Security(id);
        mySecurity.off();
         
        // Light on
        Lighting hallLamp = new Lighting(id+" / Hall Lamp");
        hallLamp.on();
         
        Lighting floorLamp = new Lighting(id+" / floorLamp");
        floorLamp.on();
 
    }
 
}

===============================================

0504
11-1**입력과 출력**
import javax.swing.JOptionPane;
 
import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHomeInput {
 
    public static void main(String[] args) {
         
        String id = JOptionPane.showInputDialog("Enter a ID"); // JOptionPane의 showInputDialog를 이용하여 정보를 String 데이터로 받음
        String bright = JOptionPane.showInputDialog("Enter a Bright level"); // 밝기또한 마찬가지
         
        // Elevator call 
        Elevator myElevator = new Elevator(id);
        myElevator.callForUp(1);
         
        // Security off 
        Security mySecurity = new Security(id);
        mySecurity.off();
         
        // Light on
        Lighting hallLamp = new Lighting(id+" / Hall Lamp");
        hallLamp.on();
         
        Lighting floorLamp = new Lighting(id+" / floorLamp");
        floorLamp.on();
         
        DimmingLights moodLamp = new DimmingLights(id+" moodLamp");
        moodLamp.setBright(Double.parseDouble(bright));
        moodLamp.on();
 
    }
 
}

11-2**arguments&parameter**
main 메소드의 args 파라미터를 이용하여 코드내의 값을 편하게 설정할 수 있음
public static void main(String[] args){
        String id = args[0];
        String bright = args[1];
}
argument 값을 다양하게 사용하여 결과값을 알아볼 수 있음
args는 문자열 배열로 여러개의 String 데이터가 들어있을 수 있음
인덱스는 0부터 시작함

===============================================

