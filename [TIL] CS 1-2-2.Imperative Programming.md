# 1-2. 프로그래밍 패러다임

Chapter: https://www.notion.so/1-21f5010abb9c412d81b5d33d0db2064f
Done!: No
Projects: https://www.notion.so/CS-06b39c96b09f435fa450f29bac78a0f8

---

# 2. 명령형 프로그래밍

## 2.1. 객체지향 프로그래밍

객체지향 프로그래밍 (OOP, Object-Oriented Programming) 

- 객체들의 집합으로 프로그램의 상호작용을 표현
- 데이터를 객체로 취급하여 객체 내부에 선언된 메서드를 활용하는 방식
- 설계에 많은 시간이 소요됨
- 처리속도가 다른 프로그래밍 패러다임에 비해 상대적으로 느림

### 객체지향 프로그래밍의 특징

1. 추상화(Abstraction)
    - 복잡한 시스템으로부터 핵심적인 개념 또는 기능을 간추려 내는 것
2. 캡슐화(Encapsulation)
    - 객체의 속성과 메서드를 하나로 묶고 일부를 외부에 감추어 은닉하는 것
3. 상속성(Inheritance)
    - 상위 클래스의 특성을 하위 클래스가 이어받아서 재사용하거나 추가, 확장하는 것
    - 코드의 재사용측면, 계층적인 관계 생성, 유지보수성 측면에서 중요함
4. 다형성(Polymorphism)
    - 하나의 메서드나 클래스가 다양한 방법으로 동작하는 것
    - 대표적 다형성 : `오버로딩`, `오버라이딩`

- 오버로딩 Overloading
    
    같은 이름을 가진 메서드를 여러 개 두는 것
    
    메서드의 타입, 매개변수의 유형, 개수 등으로 여러 개를 둘수 있음
    
    컴파일 중에 발생하는 정적 다형성
    
    ```java
    class Person {
    	public void eat(String a){
    		System.out.println("I eat "+a);
    	}
    
    	public void eat(String a, String b){
    		System.out.println("I eat "+a+" and "+b);
    	}
    }
    
    public class CalculateArea {
    
    	public static void main(String[] args){
    
    		Person p = new Person();
    		p.eat("apple");
    		p.eat("tomato","banana");
    	}
    }
    ```
    

- 오버라이딩 Overriding
    
    주로 메서드 오버라이딩을 말함
    
    상위 클래스로부터 상속받은 메서드를 하위 클래스가 재정의 하는 것
    
    런타임 중 발생하는 동적 다형성
    
    ```java
    class Animal{
    	public void bark(){
    		System.out.println("mumu!mumu!");
    	}
    }
    
    class Dog extends Animal{
    	@Override
    	public void bark(){
    		System.out.println("wal!!! wal!!!");
    	}
    
    public class Main{
    	public static void main(String[] args){
    		Dog d = new Dog();
    		d.bark();
    	}
    }
    
    ```
    

### 객체지향 프로그래밍 설계 원칙 (SOLID)

1. 단일 책임 원칙 SRP, Single Responsibility Principle
    
    모든 클래스는 각각 하나의 책임만 가져야하는 원칙
    
2. 개방-폐쇄 원칙 OCP, Open Closed Principle
    
    유지보수 사항이 생긴다면 코드를 쉽게 확장할 수 있도록 하고, 수정할 때는 닫혀 있어야 하는 원칙
    
    기존의 코드는 잘 변경하지 않으면서도 확장은 쉽게 할수 있어야 함
    
3. 리스코프 치환 원칙 LSP, Liskov Substitution Principle
    
    프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 하는 것
    
    클래스는 상속되기 마련이며 부모/자식이라는 계층관계가 만들어짐
    
    이 때, 부모 객체 자리에 자식 객체를 넣어도 시스템이 문제없이 돌아가게 만드는 것
    
4. 인터페이스 분리 원칙 ISP, Interface Segregation Principle
    
    하나의 일반적인 인터페이스보다 구체적인 여러개의 인터페이스를 만들어야 하는 원칙
    
5. 의존 역전 원칙 DIP, Dependency Inversion Principle
    
    자신보다 변하기 쉬운 것에 의존하던 것을 추상화된 인터페이스나 상위 클래스를 두어 변하기 쉬운 것의 변화에 영향받지 않게 하는 원칙
    
    상위 계층은 하위 계층의 변화에 대한 구현으로부터 독립해야 함
    

## 2.2. 절차형 프로그래밍

절차형 프로그래밍

로직이 수행되어야 할 연속적인 계산과정으로 이루어짐

일이 진행되는 방식으로 코드를 구현하기만 하면 되기 때문에 가독성이 좋으며 실행 속도가 빠름

계산이 많은 작업에 쓰임

모듈화하기가 어렵고 유지보수성이 떨어짐