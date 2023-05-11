> 2023-05-03
> Chapter 8
>> Chapter 8-1 변수의 정의
<pre><code>
public class Variable {
    public static void main(Static[] args) {
        int a = 1; // a는 정수 1이다.
        System.out.println(a);
        
        int b = 1.1; // 1.1은 정수(x) ERROR.
        double c = 1.1; // 1.1은 실수(o) -> c는 실수 1.1이다.
        System.out.println(c);
        String d = "Hello World"; 
        // "Hello World"는 문자열 d에 저장됨.
        System.out.println(d);
    }
}
</code></pre>
# 결과 : 1, 1.1, Hello World
>> Chapter 8-2 변수의 효용
<pre><code>
public class Letter {
    public static void main(String[] args) {
        String name = "leezche"; 
        // "leezche"는 문자열 name에 저장됨
        System.out.println("Hello, "+name+" ... "+name+" ... egoing ... bye");
        double VAT = 10.0;
        System.out.println(VAT);
    }
}
</code></pre>
# 결과 : Hello, leezche ... leezche ... egoing ... bye
>> Chapter 8-3 데이터 타입의 변환 - casting
<pre><code>
public class Casting {
    public static void main(String[] args) {
        double a = 1.1;
        double b = 1; 
        // 정수 1을 실수 1로 바꾸고 b에 담아서 출력 시 1.0이 나옴, 손실이 일어나지 않음
        double b2 = (double) 1; 
        // 강제로 1을 실수로 변환하여 1.0 출력.
        System.out.println(b);
        int c = 1.1; 
        // ERROR. 
        double d = 1.1;
        int e = (int)1.1; 
        // 강제로 1.1을 정수로 변환하여 1 출력, 손실이 일어남
        
        System.out.println(e);
        String f = Integer.toString(1); 
        // 1이 출력 되지만 실제로 1은 문자열이다.
        System.out.println(f.getClass()); 
        // .getClass()를 이용하여 출력 시 값의 데이터타입을 함께 출력.
    }
}
</code></pre>
# 결과 : 1.0, 1, 1, class java.lang.String
> Chapter 9
>> Chapter 9-1 프로그래밍이란 무엇인가
<pre><code>
public class Program {
    public static void main(String[] args) {
         
        System.out.println(1); // 1 출력
        System.out.println(2); // 2 출력
        System.out.println(3); // 3 출력
    }
}
</code></pre>
# 결과 : 1, 2, 3
> 프로그래밍을 하는 이유는 자동화 하기 위함.
> 컴퓨터 프로그래밍을 이용하여 사람이 잘 못하는 일을 기계에게 위임하여 자동화할 수 있음. (이런 작업을 하는 언어중 가장 유명한 언어가 JAVA.)
>> Chapter 9-2 프로그램 만들기 - IoT 라이브러리 설치하기
<pre><code>
public class programming {   
}
</code></pre>
> 방법 : iot 사물을 제어할 수 있는 프로그램을 작성하기 위해서 외부 패키지를 다운받아 org 폴더를 programming 프로젝트에 드래그 앤 드랍 시킨다.
>> Chapter 9-3 IoT 프로그램 만들기
<pre><code>
import org.opentutorials.iot.Elevator; 
// org폴더 > opentutorials > iot > Elevator를 import 함. 
import org.opentutorials.iot.Lighting;
// org폴더 > opentutorials > iot > Lighting를 import 함.
import org.opentutorials.iot.Security;
// org폴더 > opentutorials > iot > Security를 import 함.
public class programming {
    public static void main(String[] args) {
        String id = "JAVA APT 507"; 
        // 동작은 같지만 중복이 제거됨.
         
        // Elevator call 
        Elevator myElevator = new Elevator(id);
        // Elevator는 데이터 타입, myElevator는 변수
        myElevator.callForUp(1); 
        // 1층으로 엘레베이터를 보내라는 명령문
         
        // Security off 
        Security mySecurity = new Security(id);
        mySecurity.off();
         
        // Light on
        Lighting hallLamp = new Lighting(id+" / Hall Lamp");
        hallLamp.on();
        //hallLamp 의 불을 킨다.
         
        Lighting floorLamp = new Lighting(id+" / floor Lamp");
        floorLamp.on();
        //floorLamp 의 불을 킨다.
    }
}
</code></pre>
# 결과 : JAVA APT 507 -> Elevator callForUp stopFloor : 1
# JAVA APT 507 -> Security off
# JAVA APT 507 / Hall Lamp -> Lighting on
# JAVA APT 507 / floorLamp -> Lighting on
> Chapter 10 - 디버거
>> 이클립스에서 디버그 하는 방법은 우측상단 Run java 버튼 옆 아래 화살표를 눌러 Debug java를 클릭하면 된다.
>> 이클립스에서 브레이크 포인트를 지정하는 방법은 코드 편집창에서 줄 번호 왼편을 더블클릭하여 브레이크 포인트를 지정할 수 있다.
>> 브레이크 포인트를 지정하고 디버거를 실행하면 브레이크 포인트까지 코드가 실행되며 그 이후로 실행이 정지된다.
>> 브레이크 포인트를 해제 하는 방법은 지정했던 브레이크 포인트를 다시 클릭하면 해제할 수 있다.
>> 이클립스에서 우측의 Variable 탭에서 변수들을 확인할 수 있다.
>> Step Into 버튼을 클릭하면 코드의 자세한 실행과정(메소드)를 볼 수 있다.
>> 다시 원래의 코드로 돌아가고자 할 경우에는 Step Return 버튼을 클릭하여 돌아갈 수 있다.

>8, 9, 10 ENDS

> 2023-05-04
>> 11강, 12강 스터디 내용

> Chapter 11-1 입력과 출력
<pre><code>
import javax.swing.JOptionPane; 
// javax.swing에 속해있는 JOptionPane이 로드되었다.
 
import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHomeInput {
    public static void main(String[] args) {
         
        String id = JOptionPane.showInputDialog("Enter a ID");
        // 이름 입력 (showInputDialog)
        String bright = JOptionPane.showInputDialog("Enter a Bright level");
        // 밝기 입력 (showInputDialog)

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
        //Double.parseDouble()시 double형으로 변환 됨.
        moodLamp.on();
    }
}
</code></pre>

# 입력 : JAVA APT 1004, 10
# 결과 : JAVA APT 1004 -> Elevator callForUp stopFloor : 1
# JAVA APT 1004 -> Security off
# JAVA APT 1004 / Hall Lamp -> Lighting on
# JAVA APT 1004 / floorLamp -> Lighting on
# JAVA APT 1004 moodLamp -> DimmingLights bright : 10.0
# JAVA APT 1004 moodLamp -> Lighting on
> Chapter 11-2 입력과 출력 - arguments & parameter
<pre><code>
import javax.swing.JOptionPane; 
// javax.swing에 속해있는 JOptionPane이 로드되었다.
 
import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHomeInput {
 
    public static void main(String[] args) {
        //args()는 매개변수이다.(patameter)
        String id = args[0];
        String bright = args[1];

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
        //Double.parseDouble()시 double형으로 변환 됨.
        moodLamp.on();
    }
}
</code></pre>

>> argument는 사용자 입력을 의미하는 문자열 배열이다.

>> parameter는 함수에서 전달되어서 사용되는 변수이다.

>> argument는 main()함수의 매개변수로 작용한다.

>> 196줄에 브레이크를 걸고 디버그 시키면 vscode 기준 왼편에 VARIABLES.Local 창이 뜨고 그 속에 args, id, bright에 할당한 값이 보인다.

<pre><code>
first(a,b);
return;

a,b("parameter","argument")
</code></pre>
>> 위 코드에서 a,b는 parameter이다.

>> 위 코드에서 "parameter","argument"는 argument이다.

> Chapter 12-1 직접 컴파일 - 실행 - 소개
>> 이클립스,vscode 없이 혼자 컴파일하기

>> 1. 자바 확장자가 붙은 소스코드를 Class확장자가 붙은 실행파일로 바꾼다 (Compile)

>> 2. 클래스 확장자가 붙은 파일을 실행한다(Run)

>> 3. 실행할 때 입력값을 준다 (Input)

> Chapter 12-2 직접 컴파일 - 실행 - 실행환경 살펴보기
>> 직접 컴파일을 하기 위해 자바의 설치경로를 알고 있어야 한다.

>> 터미널 열기 Window - 윈도우키 + R키로 실행창을 키고, cmd를 입력하여 명령프롬프트를 실행한다.

>> 컴파일, 실행을 하기 위해선 명령 프롬프트에 javac을 입력하여 컴파일 할 수 있다.

>> 자바의 설치경로(C:\Program Files\Java\jdk-17\bin\javac.exe)

>> 환경 변수는 윈도우 탐색기에서 내 PC 항목을 오른쪽 버튼으로 클릭하여 나오는 팝업창에 속성을 클릭한다. 이후 고급시스템 설정을 클릭하고 환경 변수를 클릭하면 환경 변수 목록을 확인할 수 있다. 목록 중 Path를 더블클릭하면 수정 할 수있다.

>> Path는 디렉터리 경로의 목록. 사용자가 전체 경로를 지정하지 않고 명령을 입력하면 목록을 확인하여 해당 명령어가 경로에 속하는지를 살펴본다. 이 과정을 통하여 어떠한 경로든 해당 명령어로 실행 파일을 실행할 수 있다.

> Chapter 12-3 직접 컴파일 - 실행 - 컴파일과 실행하기

>> 명령 프롬프트에서 소스 코드가 위치한 경로를 붙여넣기 한다. (ex)cd C:\Users\egoing\Desktop\java1\Programming

>> dir 명령어로 프로젝트 디렉토리 내부 구조를 확인할 수 있다.

>> 터미널에 javac를 입력하면 javac 명령어의 사용 방법을 보여준다.

>> javac Program.java 를 입력하여 Program.java를 컴파일한다. 에러가 날 시 javac -cp "." Program.java를 입력한다.

>> 컴파일된 클래스 파일을 실행하는 방법은 java Program을 입력한다. 에러가 날 시 java -cp "." Program 을 입력한다.

> Chapter 12-4 직접 컴파일 - 실행 - 라이브러리이용
<pre><code>
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHome {
 
    public static void main(String[] args) {
         
        ....
    }
}
</code></pre>
>> OkJavaGoInHome.java 파일을 컴파일 하기 위해서는 OkJavaGoInHome가 Import 구문을 통해 org.opentutorials.iot 클래스들을 불러들이고 있어서 컴파일을 실행할 때 자동적으로 org.opentutorials.iot의 Elevator, Lighting, Security 클래스들도 컴파일한다. 이때 lib 폴더를 새로 만들어서 org 폴더를 lib 폴더 내부로 이동시킨다.

>> org.opentutorials.iot 패키지는 lib 라이브러리의 일부가 되었다. 그렇기 때문에 OkJavaGoInHome.java 파일은 제대로 실행되지 않는다.

>> 외부 라이브러리도 포함해서 컴파일 하기 위해서는 명령 프롬프트에서 javac -cp ".;lib" OkJavaGoInHome.java 명령어를 입력한다.

>> 외부 라이브러리도 포함해서 실행하려면 java -cp ".;lib" OkJavaGoInHome 명령어를 입력한다.

>> 1. 라이브러리란 다른 사람들 만들어 놓은 여러 유용한 기능을 모아둔 클래스의 집합.
>> 2. 패키지는 특정한 기능들을 모아둔 더 작은 단위의 집합.

> Chapter 12-5 직접 컴파일 - 실행 - 입력과 출력

<pre><code>
import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHomeInput {
    public static void main(String[] args) {
         
        String id = args[0];
        String bright = args[1];
        
        ....
    }
}
</code></pre>
>> org.opentutorials.iot 패키지는 다시 iot 폴더 밖으로 꺼낸다.

>> 터미널에서 javac OkJavaGoInHomeInput.java 명령어를 입력하여 컴파일 한다.

>> 터미널에서 아규먼트를 주기 위해서 실행할 클래스 파일 이름다음에 연달아서 입력한다. -> java OkJavaGoInHomeInput "JAVA APT 507" 15.0 (2번째 입력값 15.0은 큰 따옴표 안에 넣어도 되고, 소수점은 생략할 수 있다.)

>> 커맨드 라인에서 우리가 임의값을 추가하여 프로그램을 작동시킨다면 이것만으로 충분히 많은 일을 가치있게 할 수 있다. 

>> * 2023-05-04 11,12 END 

> * 2023-05-08 [Chapter 13 ~ 14.4]-

> Chapter 13 - 1 자바 문서 보는 법 - API vs UI

>> 자바 프로그램 : 자바 도구 응용 + 시간적 순서에 따른 동작

>> 프로그램 : 작업들의 시간적 순서에 주목

>> 애플리케이션 : 도구의 응용에 주목

>> 자바 API : 자바의 도구들을 응용하여 사용하기 위해서 일정한 조작 장치를 구성 한 것.

>> *자바 프로그램은 다른 자바 프로그램에서 사용이 가능하며 다른 프로그램에서 사용할 수 있도록 만들어 둔 장치 또한 API이다.

>> UI : 사용자가 자바 프로그램을 사용할 수 있도록 만들어 둔 장치

> Chapter 13 - 2 자바 문서 보는 법 - 패키지, 클래스, 변수, 메소드

>> 자바 프로그램을 만들기 위해서는 자바의 도구들을 사용할 수 있게 만든 장치인 자바 API를 이용한다.

>> API Documentation 페이지 왼쪽의 위쪽 섹션에는 패키지들에 대한 정보를 담고 있고, 왼쪽의 아래 섹션에는 클래스에 대한 정보를 담고 있다.

>> 패키지는 비슷한 성격의 클래스들을 하나의 묶음으로 정리한 것.

>> 클래스는 변수와 메소드라는 것을 모아서 하나의 묶음으로 정리한 것.

> Chapter 13 - 3 자바 문서 보는 법 - 클래스
<pre><code>
public class ClassApp {
 
    public static void main(String[] args) {
         
        System.out.println(Math.PI);
        System.out.println(Math.floor(1.6));
        System.out.println(Math.ceil(1.6));
    }
}
</code></pre>
# 결과 : 3.141592653689793, 1.0, 2.0
>> 위 코드는 수학과 관련된 작업을 해야하며 파이의 크기를 출력하기 위하여 math라는 클래스를 불러들여 출력하는 코드이다.

>> 위와 같이 클래스를 불러들여 원하는 값을 출력하기 위해선 (Math.PI)처럼 클래스.값 을 넣어야 한다.

>> 클래스는 서로 연관된 변수와 메소드들을 모아서 이름을 붙이고 묶음으로 정리한 것.

> Chapter 13 - 4 자바 문서 보는 법 - 인스턴스

>> 클래스 안에는 변수와 메소드가 존재한다.

>> 인스턴스는 클래스에 있는 속성을 사용하는 복제품을 만드는 것이다. 단 인스턴스를 사용하려면 클래스안에 constructor가 있어야 한다.

>> 클래스중에 constructor가 없는 클래스(예:Math)는 인스턴스로 사용하지 못하는 클래스. 즉, 인스턴스를 사용하려면 해당 클래스에 constructor가 있어야 한다.

> Chapter 13 - 5 자바 문서 보는 법 - 상속
<pre><code>
//Class PrintWriter

java.lang.Object
    java.io.Writer
        java.io.PrintWriter
</code></pre>
>> 1. 들여쓰기 되어 표현된 각각의 클래스 간의 관계는 상속 관계.

>> PrintWriter 클래스는 Writer 클래스에서 상속을 받음.

>> Writer클래스는 Object 클래스로부터 상속을 받음.

>> 2. 자식에 해당하는 클래스는 부모에 해당하는 클래스의 모든 변수와 메소드를 사용할 수 있다.

>> 3. 그래서 PrintWriter 클래스는 Writer의 write 메소드를 사용할 수 있고
, Object의 toString 메소드를 사용할 수 있다.

> Chapter 14 - 2 나의 앱 만들기 - 오리엔테이션
> Chapter 14 - 3 나의 앱 만들기 - 기본 기능 구현
<pre><code>
public class AccountingApp {

	public static void main(String[] args) {
		
		System.out.println("Value of supply : " + 10000.0);
        System.out.println("VAT : " + (10000.0 * 0.1));
        System.out.println("Total : " + (10000.0 + (10000.0 * 0.1)));
        System.out.println("Expense : " + (10000.0 * 0.3));
        System.out.println("Income : " + (10000.0 - (10000.0 * 0.3)));
        System.out.println("Dividend 1 : " + (10000.0 - (10000.0 * 0.3)) * 0.5);
        System.out.println("Dividend 2 : " + (10000.0 - (10000.0 * 0.3)) * 0.3);
        System.out.println("Dividend 3 : " + (10000.0 - (10000.0 * 0.3)) * 0.2);

	}

}
</code></pre>
>> * 오리엔테이션에서 궁리한 문제에 대한 해결책을 제시하는 코드. 

>> 공급가를 10000.0 으로 잡고 시작.

>> 부가 가치세는 10000.0에 0.1.을 곱한 10000.0 * 0.1.

>> 총 판매가는 공급가와 부가가치세를 합한 10000.0 + (10000.0 * 0.1).
비용은 판매가의 30%이므로 10000.0 * 0.3.

>> 수익은 판매가에 비용을 뺀 값이므로 10000.0 - (10000.0 * 0.3).

>> 첫 번째 배당자는 수익의 50%를 배당받으므로 (10000.0 - (10000.0 * 0.3)) * 0.5.

>> 두 번째 배당자는 수익의 30%를 배당받으므로 (10000.0 - (10000.0 * 0.3)) * 0.3.

>> 세 번째 배당자는 수익의 20%를 배당받으므로 (10000.0 - (10000.0 * 0.3)) * 0.2.

> Chapter 14 - 3 나의 앱 만들기 - 변수도입
<pre><code>
public class AccountingApp {
 
    public static void main(String[] args) {
 
        double valueOfSupply = 10000.0; // 공급가
        double vatRate = 0.1; // 부가가치세율
        double expenseRate = 0.3; 
        double vat = valueOfSupply * vatRate;
        double total = valueOfSupply + vat;
        double expense = valueOfSupply * expenseRate;
        double income = valueOfSupply - expense;
        double dividend1 = income * 0.5;
        double dividend2 = income * 0.3;
        double dividend3 = income * 0.2;
 
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + vat);
        System.out.println("Total : " + total);
        System.out.println("Expense : " + expense);
        System.out.println("Income : " + income);
        System.out.println("Dividend 1 : " + dividend1);
        System.out.println("Dividend 2 : " + dividend2);
        System.out.println("Dividend 3 : " + dividend3);
 
    }
 
}
</code></pre>
>> 변수를 도입하면 코드의 재사용성을 높이고 가독성을 높일 수 있다.

> Chapter 14 - 4 나의 앱 만들기 - 입력값 도입
<pre><code>
public class AccountingApp {
 
    public static void main(String[] args) {
 
        double double valueOfSupply = Double.parseDouble(args[0]);
        // 공급가
        double vatRate = 0.1; // 부가가치세율
        double expenseRate = 0.3; 
        double vat = valueOfSupply * vatRate;
        double total = valueOfSupply + vat;
        double expense = valueOfSupply * expenseRate;
        double income = valueOfSupply - expense;
        double dividend1 = income * 0.5;
        double dividend2 = income * 0.3;
        double dividend3 = income * 0.2;
 
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + vat);
        System.out.println("Total : " + total);
        System.out.println("Expense : " + expense);
        System.out.println("Income : " + income);
        System.out.println("Dividend 1 : " + dividend1);
        System.out.println("Dividend 2 : " + dividend2);
        System.out.println("Dividend 3 : " + dividend3);
 
    }
 
}
</code></pre>
>> valueOfSupply(공급가)에 입력값을 입력받아 공급가를 사용자가 지정할 수 있도록 코드를 수정했다.

>> 터미널에서 실행할 시 : javac 명령어로 AccountingApp.java를 컴파일하고 java 명령어로 AccountingApp을 실행하고 아규먼트로 원하는 공급가액을 입력하여 실행하면 valueOfSupply에 내가 직접 지정한 값으로 계산을 하여 값이 반환된다.


2023-05-08 13 ~ 14-4 END 
-------------

<hr/>

<2023-05-09 / 14-5 ~ 15>
-------------

* 조건문
<pre><code>
public class AccountingIFApp {
 
    public static void main(String[] args) {
 
        double valueOfSupply = Double.parseDouble(args[0]);
        double vatRate = 0.1;
        double expenseRate = 0.3;
        double vat = valueOfSupply * vatRate;
        double total = valueOfSupply + vat;
        double expense = valueOfSupply * expenseRate;
        double income = valueOfSupply - expense;
         
        double dividend1;
        double dividend2;
        double dividend3;
         
        if(income > 10000.0) { 
            // 만약 income이 10000.0원 보다 클 시 구문 실행
            dividend1 = income * 0.5;
            dividend2 = income * 0.3;
            dividend3 = income * 0.2;
        } else { 
            // 만약 income이 10000.0원 보다 작을 시 구문 실행
            dividend1 = income * 1.0;
            dividend2 = income * 0;
            dividend3 = income * 0;
        }
 
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + vat);
        System.out.println("Total : " + total);
        System.out.println("Expense : " + expense);
        System.out.println("Income : " + income);
        System.out.println("Dividend 1 : " + dividend1);
        System.out.println("Dividend 2 : " + dividend2);
        System.out.println("Dividend 3 : " + dividend3);
    }
}
</code></pre>
-제어문 : 프로그램의 실행 과정을 조건에 따라 바꾸는 것.   
-제어문의 종류 : 조건문, 반복문
* 배열
<pre><code>
public class AccountingArrayApp {
 
    public static void main(String[] args) {
 
        double valueOfSupply = Double.parseDouble(args[0]);
        double vatRate = 0.1;
        double expenseRate = 0.3;
        double vat = valueOfSupply * vatRate;
        double total = valueOfSupply + vat;
        double expense = valueOfSupply * expenseRate;
        double income = valueOfSupply - expense;
         
        double[] dividendRates = new double[3]; 
        //double 형 데이터로 이루어져 있는 배열, new double[3] = double형의 데이터를 3개를 담을 수 있는 수납공간이 만들어 짐.
        dividendRates[0] = 0.5;
        dividendRates[1] = 0.3;
        dividendRates[2] = 0.2;
         
        double dividend1 = income * dividendRates[0];
        double dividend2 = income * dividendRates[1];
        double dividend3 = income * dividendRates[2];
 
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + vat);
        System.out.println("Total : " + total);
        System.out.println("Expense : " + expense);
        System.out.println("Income : " + income);
        System.out.println("Dividend 1 : " + dividend1);
        System.out.println("Dividend 2 : " + dividend2);
        System.out.println("Dividend 3 : " + dividend3);
    }
}
</code></pre>
-배열 : 서로 연관된 데이터를 정리정돈하는 수단

* 반복문(while)
<pre><code>
public class AccountingArrayLoopApp {
 
    public static void main(String[] args) {
 
        double valueOfSupply = Double.parseDouble(args[0]);
        double vatRate = 0.1;
        double expenseRate = 0.3;
        double vat = valueOfSupply * vatRate;
        double total = valueOfSupply + vat;
        double expense = valueOfSupply * expenseRate;
        double income = valueOfSupply - expense;
         
         
 
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + vat);
        System.out.println("Total : " + total);
        System.out.println("Expense : " + expense);
        System.out.println("Income : " + income);
         
        double[] dividendRates = new double[3];
        dividendRates[0] = 0.5;
        dividendRates[1] = 0.3;
        dividendRates[2] = 0.2;
         
             
        int i = 0; // 반복하기전 i를 0으로 초기화시킴.
        while(i < dividendRates.length) {
            // 3보다 i의 값이 작을 동안 
            // 반복할 때 마다 i의 값을 1씩 증가시킨다.
            System.out.println("Dividend : " + (income*dividendRates[i]) );
            i = i + 1;
        }
    }
}
</code></pre>
-배열과 반복문을 함께 사용하면 프로그램을 훨씬 간결하게 만들 수 있다.   
-while 문은 괄호 안의 조건이 참인 한 블록내의 작업을 계속 반복한다.
-반복문은 배열과 단짝.

* 메소드
<pre><code>
public class AccountingMethodApp {
    //valueOFsupply, vatRate, expenseRate를 main 바깥에서 선언.
    //전역변수로 선언하면 main뿐만 아니라 어느곳에서든 사용될 수 있다.
    public static double valueOfSupply;
    public static double vatRate;
    public static double expenseRate;
    public static void main(String[] args) {
        valueOfSupply = 10000.0;
        vatRate = 0.1;
        expenseRate = 0.3;
        print();
    }
 
    public static void print() {
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + getVAT());
        System.out.println("Total : " + getTotal());
        System.out.println("Expense : " + getExpense());
        System.out.println("Income : " + getIncome());
        System.out.println("Dividend 1 : " + getDiviend1());
        System.out.println("Dividend 2 : " + getDiviend2());
        System.out.println("Dividend 3 : " + getDiviend3());
    }
 
    public static double getDiviend1() {
        return getIncome() * 0.5;
    }
    public static double getDiviend2() {
        return getIncome() * 0.3;
    }
    public static double getDiviend3() {
        return getIncome() * 0.2;
    }
 
    public static double getIncome() {
        return valueOfSupply - getExpense();
    }
 
    public static double getExpense() {
        return valueOfSupply * expenseRate;
    }
 
    public static double getTotal() {
        return valueOfSupply + getVAT();
    } 
 
    public static double getVAT() {
        return valueOfSupply * vatRate;
    }
}
</code></pre>
-메소드 : 서로 연관된 코드를 그룹핑해서 이름을 붙인 정리정돈된 상자
ex) Math의 floor, ceil, PrintWriter의 write, close등.   
-메소드로 전역변수를 설정할 시 main함수 안에서 따로 지역변수를 지정하지 않아도 사용자가 많은 함수를 만들 시 미리 만들어놓은 Public 전역변수를 호출하여 코드를 단정하게 만들 수 있다.

* 클래스
<pre><code>
//ClassApp
class Accounting{
    //AccountingApp 소속의 변수들을 이사시킴.
    public static double valueOfSupply;
    public static double vatRate;
    public static double expenseRate;
    public static void print() {
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + getVAT());
        System.out.println("Total : " + getTotal());
        System.out.println("Expense : " + getExpense());
        System.out.println("Income : " + getIncome());
        System.out.println("Dividend 1 : " + getDiviend1());
        System.out.println("Dividend 2 : " + getDiviend2());
        System.out.println("Dividend 3 : " + getDiviend3());
    }
 
    public static double getDiviend1() {
        return getIncome() * 0.5;
    }
    public static double getDiviend2() {
        return getIncome() * 0.3;
    }
    public static double getDiviend3() {
        return getIncome() * 0.2;
    }
 
    public static double getIncome() {
        return valueOfSupply - getExpense();
    }
 
    public static double getExpense() {
        return valueOfSupply * expenseRate;
    }
 
    public static double getTotal() {
        return valueOfSupply + getVAT();
    } 
 
    public static double getVAT() {
        return valueOfSupply * vatRate;
    }
}
public class AccountingClassApp {
     
    public static void main(String[] args) {
        //기존 변수 앞에 Class로 선언한 Accounting.을 붙여 소속관계를 명확하게 할 수 있다.
        Accounting.valueOfSupply = 10000.0;
        Accounting.vatRate = 0.1;
        Accounting.expenseRate = 0.3;
        Accounting.print();
        // anotherVariable = ...;
        // anotherMethod = ...;
    }
}
</code></pre>
-클래스는 서로 연관된 변수와 메소드를 그룹핑한 것. (정리정돈의 상자)   
-메소드, 클래스 등이 중요한 이유는 소프트웨어를 만들어 감에 있어서 구조를 결정하기 때문.   
-클래스는 객체지향의 핵심이다.

* 인스턴스
<pre><code>
class Accounting{
    public double valueOfSupply;
    public double vatRate;
    public double expenseRate;
    public void print() {
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + getVAT());
        System.out.println("Total : " + getTotal());
        System.out.println("Expense : " + getExpense());
        System.out.println("Income : " + getIncome());
        System.out.println("Dividend 1 : " + getDiviend1());
        System.out.println("Dividend 2 : " + getDiviend2());
        System.out.println("Dividend 3 : " + getDiviend3());
    }
 
    public double getDiviend1() {
        return getIncome() * 0.5;
    }
    public double getDiviend2() {
        return getIncome() * 0.3;
    }
    public double getDiviend3() {
        return getIncome() * 0.2;
    }
 
    public double getIncome() {
        return valueOfSupply - getExpense();
    }
 
    public double getExpense() {
        return valueOfSupply * expenseRate;
    }
 
    public double getTotal() {
        return valueOfSupply + getVAT();
    } 
 
    public double getVAT() {
        return valueOfSupply * vatRate;
    }
}
public class AccountingClassApp {
     
    public static void main(String[] args) {
        // instance 
        Accounting a1 = new Accounting(); // Class를 복제함.
        a1.valueOfSupply = 10000.0;
        a1.vatRate = 0.1;
        a1.expenseRate = 0.3;
        a1.print(); 
        // Accounting1의 내부 상태는 모두 같아서 a2 이후에 print 문을 선언해도 상관없다.
         
        Accounting a2 = new Accounting(); // Class를 복제함
        a2.valueOfSupply = 20000.0;
        a2.vatRate = 0.05;
        a2.expenseRate = 0.2;
        a2.print();
    }
}
</code></pre>
-인스턴스는 하나의 클래스를 복제해서 서로 다른 데이터의 값과 서로 같은 메소드를 가진 복제본을 만드는 것.   
-위 코드에서 new Accounting()을 사용하여 Class를 복제함.  
-따라서 Class이름 앞에 new를 붙여서 만든 것을 인스턴스라고 함.   
-이 후 Public static에서 static을 빼도 코드에 오류가 없음.

<2023-05-09 / 14-5 ~ 15 END>
-------------

<hr/>

<2023-05-10 / JAVA 2 / 1 ~ 7.3>
-------------

* Boolean Datatype
<pre><code>
public class BooleanApp {
 
    public static void main(String[] args) {
         
        System.out.println("One");
        System.out.println(1);
         
        System.out.println(true); // 첫번째 데이터 타입
        System.out.println(false); // 두번째 데이터 타입
         
        String foo = "Hello world";
        // String true = "Hello world"; reserved word
         
        System.out.println(foo.contains("world"));
        System.out.println(foo.contains("egoing"));
    }
}
</code></pre>
-'.contains' 라는 메소드를 사용하면 return 값으로 그 문자열의 입력값으로 전달할 어떤 값이 들어있다면 True를 리턴하고 없다면 False를 리턴한다.   
-foo.contains() 안에 world 라는 문자열이 들어있으므로 true를 반환한다.   
-foo.contains() 안에 egoing 라는 문자열은 foo에서 입력되지 않았으므로 False를 반환한다.   

* 비교연산자
<pre><code>
public class ComparisonOperatorApp {
 
    public static void main(String[] args) {
         
        System.out.println(1 > 1); // false 반환
        System.out.println(1 == 1); // true 반환
        System.out.println(1 < 1); // false 반환
        System.out.println(1 >= 1); // true 반환
    }
}
</code></pre>
-a > b : a가 b보다 큼   
-a < b : a가 b보다 작음   
-a >= b : a가 b보다 크거나 같음    
-a <= b : a가 b보다 작거나 같음   
-a == b : a가 b와 같음   
-a != b : a가 b와 같지 않음   
-위 설명에 해당하는 진술이 참이라면 True, 아니라면 False를 반환.

* 조건문 형식 4-1
<pre><code>
public class IfApp {
 
    public static void main(String[] args) {
 
        System.out.println("a");
        if(false) { // 만약 조건식에 부합하지 않는다면
            System.out.println(1);
        } else if(true) { // 만약 조건식에 부합한다면
            System.out.println(2);
        } else { // else if 조건식이 아니라면
            System.out.println(3);
        }
        System.out.println("b");
    }
}
</code></pre>
-'IF'문의 구성요소 : 조건식 - 코드블럭(실행할 코드) - else if - else   
-'IF'와 '조건식'이 필수구성요소 이며, 나머지는 필수요소가 아니다.   
-'조건식'에는 'Boolean'타입만 기입할 수 있다.   
<pre><code>
 if (조건식) {
    // code
} else if (조건식) {
} else {
}
</code></pre>
-위와 같은 코드에서 IF의 조건식에 해당되면 IF속 코드가 실행되며, 아니라면 else IF의 조건을 확인하고 else IF의 코드를 실행하고, else IF 또한 아니라면 else의 코드를 실행한다.   

* 조건문 응용 1
<pre><code>
public class AuthApp {
    public static void main(String[] args) {
         
        String id = "egoing"; // 문자열 id 선언 후 "egoing" 값 기입
        String inputId = args[0]; // 들어갈 id는 args값의 0번째
         
        System.out.println("Hi."); // Hi.
         
        //if(inputId == id) { // 만약 inputId와 id값이 같다면 
        if(inputId.equals(id)) { // 위 주석처리 한 구문과 같은 의미
            System.out.println("Master!"); 
            // 같다면 Master! 출력
        } else { 
            System.out.println("Who are you?"); 
            // 아니라면 Who are you? 출력
        }
    }
}
</code></pre>

* 조건문 응용 2
<pre><code>
public class AuthApp {
 
    public static void main(String[] args) {
         
        String id = "egoing";
        String inputId = args[0];
         
        String pass = "1111"; // 비밀번호 1111 선언
        String inputPass = args[1];
         
        System.out.println("Hi.");
         
        if(inputId.equals(id) && inputPass.equals(pass)) {
            System.out.println("Master!");
        } else {
            System.out.println("Who are you?");
        }       
    }
}
</code></pre>
-위 코드에서 if(inputId.equals(id) && inputPass.equals(pass))를 해석하면 만약 아이디도 동일하고, 패스워드도 동일하다면 아래 구문을 동작시킨다. 하지만 그렇지 않으면 else 구문을 동작시킨다.   
-논리연산자 &&는 앞 구문이 참이고 뒤 구문이 참이면 전체 구문을 참으로 반환한다.   

* == vs equals   
-원시 데이터 타입 : boolean, byte, char, short, int, long, float, double   
-원시 데이터 타입의 변수는 선언되면 메모리에 공간이 할당 되며 실제값이 들어간다.   
-원시 데이터의 경우 == 연산자는 변수가 가리키는 값을 토대로 비교한다.   
-인스턴스 간 == 연산자를 이용할 경우 그 메모리의 주소를 비교하게 된다.
-원시 데이터는 equals를 가지고 있지 않다.
<pre><code>
int a = 1;
int b = 1;

String s1 = new String("JAVA");
String s2 = new String("JAVA");

String s3 = "JAVA";
String s4 = "JAVA";
</code></pre>
-위 코드의 경우 s1,s2,s3(4)변수는 각각 10번지, 11번지, 12번지라는 주소값을 가리키고 있기 때문에 == 연산자를 이용하면 false라고 연산한다.   
-반면, equals 메소드는 변수가 최종적으로 가리키고 있는 값을 기준으로 판단하여 다른 번지에 저장되어 있는 s1,s2,s3(4)에 대해서도 서로 같다고 판단한다.

* 논리연산자
-조건연산자 : &&, ||
-논리연산자 || : L || R 중 하나라도 참이면 True를 반환.
-논리연산자 ! : NOT 연산 수행후 참, 거짓 값을 반전.   
<pre><code>
public class AuthApp2 {
 
    public static void main(String[] args) {
         
        String id = "egoing";
        String inputId = args[0];
         
        String pass = "1111";
        String pass2 = "2222";
        String inputPass = args[1];
         
        System.out.println("Hi.");
        boolean isRightPass = (inputPass.equals(pass) || inputPass.equals(pass2));
        // 둘중 하나라도 true면 true 반환
        if(inputId.equals(id) && isRightPass ) 
        {
            System.out.println("Master!");
        } else {
            System.out.println("Who are you?");
        }       
    }
}
</code></pre>
-boolean isRightPass = (inputPass.equals(pass) || inputPass.equals(pass2)); 에서 하나라도 참이면 true 값을 반환하는 변수를 선언.   
-if(inputId.equals(id) && isRightPass ) 에서 && 논리 연산자를 사용하여 두 개의 조건문이 모두 참인 경우에만 IF문의 코드를 실행하게 된다.
-논리연산자를 사용하면 조건식을 간결하게 만들어 코드에 대한 가독성이 좋아지고 유지, 보수가 원활해진다.

* 반복문
<pre><code>
public class LoopApp {
 
    public static void main(String[] args) {
         
        System.out.println(1);
        System.out.println("=== while ===");
        int i = 0;
        //..
        while(i < 3) {
            System.out.println(2);
            System.out.println(3);
            //i = i + 1;
            //..
            i++;
        }
        System.out.println("=== for ===");
        for(int j=0; j < 3; j++) {
            System.out.println(2);
            System.out.println(3);
        }
         
        System.out.println(4);
    }
}
</code></pre>
-'while'문에는 'iF'문처럼 'boolean' 타입의 조건식을 기입해야한다.   
-while 문을 해석하면 i < 3으로 i가 3보다 작으면 계속 반복시킨다.   
-'for'문은 사용자가 직접 반복횟수를 지정시킬 때 용이하다.   
-for(int j = 0; j < 3; j++) 구문을 해석하면 int j = 0; 으로 j 값을 초기화 시키고 j가 3이 되기 전까지 j에 1을 증가시킨다.   
-따라서 i++ 는 i = i + 1과 같다.
-'while'문은 자유도가 높고 'for'문은 사용자가 반복횟수를 지정할 수 있기에 자유도가 낮다.

* 배열
-배열은 반복문과 항상 함께한다.
<pre><code>
public class ArrayApp {
 
    public static void main(String[] args) {
         
        // egoing, jinhuck, youbin 
        //String users = "egoing, jinhuck, youbin";
        String[] users = new String[3];
        users[0] = "egoing";
        users[1] = "jinhuck";
        users[2] = "youbin";
         
        System.out.println(users[1]);
        System.out.println(users.length); // 배열의 크기 출력
         
        int[] scores = {10, 100, 100}; // 원소, element
        System.out.println(scores[1]);
        System.out.println(scores.length); // 배열의 크기 출력
    }
}
</code></pre>
-배열 선언 시 변수 타입명 뒤에 []를 입력하고 변수이름을 입력한다.   
-초기화를 할 경우 new 키워드를 이용하여 []안에 개수를 입력한다.   
-리터럴로 입력할 수 있는 데이터 타입은 {}안에 요소를 리터럴로 입력한다.   
-'배열'은 '인덱스'를 통해 접근하고 '인덱스'는 []안에 입력한다.   

* 반복문 + 배열
<pre><code>
public class LoopArray {
 
    public static void main(String[] args) {
        /*
         <li>egoing</li>
         <li>jinhuck</li>
         <li>youbin</li>
        */
         
        String[] users = new String[3];
        users[0] = "egoing";
        users[1] = "jinhuck";
        users[2] = "youbin";
         
        for(int i = 0; i < users.length; i++) {
            System.out.println(users[i]+",");
        }  
    }
}
</code></pre>
-위 코드중 for문을 해석하면 int i = 0;으로 초기화 시킨 뒤 i가 users.length. 즉, 배열의 요소 개수보다 작을때 반복하여 i값을 1씩 증가시킨다.   
-따라서 밑에 프린트문은 배열 값에 i 를 넣어 i가 1씩 증가할때마다 해당하는 배열의 문자열을 출력한다.
-조건식에서 length필드를 사용하게 되면 직접 배열의 요소 개수를 입력하지 않아도 되는 편리성을 가지게 된다.   

<2023-05-10 / JAVA 2 / 1 ~ 7.3 END>
-------------

<hr/>