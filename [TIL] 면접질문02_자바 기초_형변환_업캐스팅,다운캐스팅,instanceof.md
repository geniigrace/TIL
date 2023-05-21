- [자바] 형변환(Casting)
    
    ## 형변환
    
    - 개발자가 프로그램 코드로 행하는 강제 타입 변환
    - 기본자료형은 동등한 타입캐스팅이기 때문에 서로 변환이 가능하다.
    - 클래스타입은 상속관계에 놓여있는 경우 타입 캐스팅이 가능하다.
    
    ### 업캐스팅
    
    - 부모클래스는 명시적인 타입 캐스팅 없이 자식과 연결할 수 있다.
    - 자식클래스가 부모클래스로 캐스팅 되는 것
    - 자식클래스에서만 있는 속성과 메서드는 실행하지 못한다.
    - 컴파일러에 의해 수행된다.
    - 업캐스팅 하는 이유
        - 공통적인 부분을 만들어 간단하게 다루기 위함
        - 상속관계에서 자식 클래스가 몇개든 하나의 인스턴스로 묶어서 관리할 수 있음 → 코드량 간략, 가독성, 유지보수성 향상
    
    ```java
    public class Vehicle{
    	String type;
    
    	public Vehicle(String type){ //Vehicle 생성자
    		this.type=type;
    	}
    
    	public void type(){ //함수
    	System.out.println("탈것의 종류는 "+type+" 입니다.");
    	}
    }
    
    public class Car extends Vehicle{
    	private String name;
    	
    	public Car(String type){//Car 생성자
    		super(type);//Vehicle의 생성자
    	}
    
    	public void setName(String name){
    		this.name=name;
    	}
    
    	public void type(){
    		System.out.println("탈것의 종류는 "+type+"입니다.");
    	}
    
    	public void select(){
    		System.out.println("현재 선택한 "+type+"은/는 "+name+"입니다.");
    	}
    }
    
    public class Main{
    
    	public static void main(String[] args){
    	
    //Car
    	Cart car = new Car("자동차");
    	car.setname("토레스");
    
    	System.out.println("Car Object : "+car);
    	car.type();
    	car.select();
    
    //업캐스팅
    	Vehicle vehicle = car; 
    	//Vehicle vehicle = new Car("자동차");
    	
    	System.out.println("Car -> Vehicle Upcasting : "+vehicle);
    	vehicle.type();
    	//vehicle.select(); //error
    	//부모형태로 업캐스팅 되었기 때문에 업캐스팅 된 객체 vehicle에서는
    	//자식클래스의 car 의 select() 메소드를 사용할 수 없다.
    ```
    
    ### 다운캐스팅
    
    - 자식 클래스는 명시적인 타입 캐스팅이 있다면 부모와 연결할 수 있다.
    - 사용할 수 있는 객체 멤버를 증가시키는게 불안전하기 때문에 명시적인 형변환이 필수이다.
    - 다운캐스팅 하는 이유
        - 업캐스팅 한 객체를 다시 자식 클래스타입의 객체로 되돌려 자식클래스에서 가진 필드와 기능을 회복하기 위함이다.
    
    ```java
    //다운캐스팅
    (Car)vehicle.select();
    //부모클래스로 업캐스팅 된 vehicle 객체를 Car 클래스로 다운캐스팅
    ```
    
    ### 형변환 가능여부 instanceof
    
    - A instanceof B
        - A 객체 레퍼런스가 B 클래스타입으로 형변환이 가능한지 확인
        - A : 자식, B : 자신/부모 인 경우 true
        - B 클래스 타입으로 A가 참조하는 객체를 가리킬 수 있는지 확인
        
        ```java
        class Person{}
        class Student extends Person{}
        class Researcher extends Person{}
        class Professor extends Researcher{}
        
        //Person <- Student
        //Person <- Researcher <- Professor
        
        Person p;
        Student s;
        Researcher r;
        Professor pro;
        
        //Person는 자기자신, 모두가 Person의 자식클래스
        System.out.println(p instanceof Person); //true
        System.out.println(s instanceof Person); //true
        System.out.println(r instanceof Person); //true
        System.out.println(pro instanceof Person); //true
        
        //Student는 자기자신, Person을 부모로 하는 자식클래스
        System.out.println(s instanceof Person); //true
        System.out.println(s instanceof Student); //true
        System.out.println(s instanceof Researcher); //false
        System.out.println(s instanceof Professor); //false
        
        //Researcher는 자기자신, Person을 부모로 하는 자식클래스
        System.out.println(r instanceof Person); //true
        System.out.println(r instanceof Student); //false
        System.out.println(r instanceof Researcher); //true
        System.out.println(r instanceof Professor); //false
        
        //Professor는 자기자신, Person과 Researcher를 부모로 하는 자식클래스
        System.out.println(pro instanceof Person); //true
        System.out.println(pro instanceof Student); //false
        System.out.println(pro instanceof Researcher); //true
        System.out.println(pro instanceof Professor); //true
        ```