- [자바] Auto Boxing/Unboxing
    - Wrapper Class
        - 8가지에 해당하는 기본타입 데이터를 객체화 할 수 있도록 하는 클래스
        
        | Primitive Data Type | Wrapper Class |
        | --- | --- |
        | boolean | Boolean |
        | byte | Byte |
        | char | Charcter |
        | short | Short |
        | int | Integer |
        | long | Long |
        | float | Float |
        | double | Double |
    - Boxing / UnBoxing
        - Boxing : 기본 타입을 래퍼클래스의 객체로 객체화 하는 것
            - `.valueOf()`
        - Unboxing : 래퍼클래스 타입의 객체를 기본타입으로 변경하는 것
            - `intValue()` `doubleValue()` (PrimitiveDataType)Value()
        
        ```java
        int intValue = 20;
        
        //Boxing
        Integer boxingNum1 = Integer.valueOf(intValue);
        //Integer 클래스가 가지고있는 valueOf라는 Static 메소드를 이용해
        //20이라는 기본자료형을 전달하면 Integer 타입의 객체가 됨
        
        //Unboxing
        int unBoxingNum1 = boxingNum1.intValue();
        //박싱된 객체를 intValue()를 사용해 int 타입으로 바꿈
        ```
        
    - Auto Boxing / Auto Unboxing
        - JDK1.5부터는 박싱과 언박싱을 자바 컴파일러가 이를 자동처리 해준다.
        
        ```java
        int intValue = 20;
        
        //Auto Boxing
        Integer boxingNum2 = intValue;
        
        //Auto Unboxing
        int unBoxingNum2 = boxingNum2; 
        ```
        
    
    - Wrapper Class 값 비교
        - 기본타입과 래퍼클래스타입은 == 연산으로 비교가 가능하다.
        - 생성자를 이용해 생성한 객체의 경우, 주소값으로 비교하기 때문에 ==로 비교하지 못하고 equals를 사용해 비교한다.
        - 오토방식을 이요해서 생성한 값은 ==로 비교 가능하다.
        
        ```java
        int intNum = 20;
        Integer integerNum1 = new Integer(20);
        Integer integerNum2 = 20;
        Integer integerNum3 = 20;
        
        //기본타입과 래퍼클러스 타입 비교
        System.out.println(intNum == integerNum2); //true
        System.out.println(integerNum2 == integerNum3); //true
        System.out.println(integerNum1.equals(integerNum3)); //true
        System.out.println(integerNum1==integerNum2); //false
        ```
        
    - parsing
        - 문자열(String) 값을 기본 자료형 값으로 변경하는 것
            - `.parseByte()` `.parseInt()` parse(PrimitiveDataType)()
        - Character는 parsing 을 제공하지 않는다.
        
        ```java
        byte b = Byte.parseByte("1");
        short s = Short.parseShort("2");
        int i = Integer.parseInt("4");
        long l = Long.parseLong("8");
        float f = Float.parseFloat("4.0");
        double d = Double.parseDouble("8.0");
        boolean bl = Boolean.parseBoolean("true");
        
        char c = "abc".charAt(0);
        ```
        
    - toString()
        - 필드값을 문자열로 반환하는 메소드