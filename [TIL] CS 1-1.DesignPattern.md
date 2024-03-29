# 1. 디자인 패턴과 프로그래밍 패러다임

Done!: No
Projects: https://www.notion.so/CS-06b39c96b09f435fa450f29bac78a0f8
기간: 2023년 3월 6일 → 2023년 3월 8일

---

# 1. 디자인 패턴과 프로그래밍 패러다임

## 1. 디자인 패턴

<aside>
💡 라이브러리 vs 프레임워크 : 공통으로 사용할 수 있는 특정 기능들을 모듈화 한 것

라이브러리 : 폴더명, 파일명에 규칙이 없다.
프레임워크 : 폴더명, 파일명에 규칙이 있다.

</aside>

### 0. 디자인패턴

- 프로그램 설계시 발생했던 문제점들을 객체간 상호관계등을 이용해 해결할 수 있도록 하나의 규약 형태로 만들어 놓은 것

### 1. 싱글톤패턴 Singleton Pattern

- 1 class ↔ 1 instance
- 보통 DB연결 모듈에 사용함
- 하나의 인스턴스를 다른 모듈들이 공유하여 사용함
    
    → 인스턴스 생성비용이 줄어듦
    
    → 의존성이 높아짐
    

장점 :

- 사용이 쉽고 실용적

단점 : 

- TDD(Test Driven Development) 시 걸림돌이 됨
    
    → 싱글톤은 미리 생성된 하나의 인스턴스를 기반으로 구현하므로 각 테스트마다 독립적인 인스턴스를 만들기가 어려움
    
- `TDD (Test Driven Development)`
    
    - TDD는 단위테스트를 주로 하는데, 단위테스트는 테스트가 서로 독립적이어야 하며 어떤 순서로든 실행할 수 있어야 함
    

- 모듈간의 결합을 강하게 만듦
    
    → 이를 해결하기 위해 의존성 주입(DI, Dependency Injection)으로 결합을 느슨하게 할 수 있음
    
- `의존성 주입(DI, Dependency Injection)`
    
    - 의존성(혹은 존속성)
    - A가 B에 의존성이 있다 : B의 변경사항에 대해 A도 변경해야함
    - 의존성 주입자를 통해 메인 모듈이 하위 모듈에 간접적으로 의존성을 주입하는 형태
      의존성 주입자에 의해 의존성이 낮아지며 이를 `디커플링` 이라 표현함
    
    의존성 주입의 장점
    
    1. 모듈을 쉽게 교체할 수 있는 구조 → 테스팅이 쉽고 마이그레이션이 쉬움
    2. 구현시 추상화레이어 → 구현체으로 구현됨 
        
        → 애플리케이션 의존성 방향성 일관됨, 애플리케이션을 쉽게 추론할 수 있음, 모듈간 관계가 명확해짐 
        
    
    의존성 주입의 단점
    
    1. 모듈의 분리 → 클래스가 증가하여 복잡성이 높아짐, 약간의 런타임 패널티가 발생함
    
    의존성 주입 원칙
    
    1. 상위 모듈은 하위모듈에서 어떤한 것도 가져오지 않아야 한다.
    2. 상위/하위 모듈 모두 추상화에 의존해야하며 추상화는 세부사항에 의존하면 안된다.
    

### 2. 팩토리패턴 Factory Pattern

- 객체를 사용하는 코드에서 객체 생성 부분을 떼어내 추상화 한 패턴
- 상속관계에 있는 클래스에서 상위클래스는 뼈대를, 하위클래스는 객체 생성에 관한 구체적인 내용을 담당

장점 

1. 상/하위 클래스의 분리로 유연성이 높아짐
2. 객체 생성 로직의 분리로 유지보수성 높아짐

### 3. 전략패턴 Stratege Pattern / Policy Pattern

- 객체의 행위를 바꾸고 싶은 경우, 전략이라고 부르는 캡슐화 알고리즘을 컨텍스트 안에서 바꿔주면서 상호교체가 가능한 패턴
    - `컨텍스트`
        - 상황, 맥랙, 문맥
        - 개발자가 어떤 작업을 완료하는데 필요한 모든 관련 정보
    
- 전략패턴을 활용한 라이브러리 `passport`
    - passport는 Node.js 에서 인증 모듈 구현시 사용되는 미들웨어 라이브러리

### 4. 옵저버패턴 Observer Pattern

- 주체(객체의 관찰자) 가 객체(Subject) 의 상태변화를 관찰하다가 변화가 있을 시 메서드 등을 통해 옵저버 목록에 있는 옵저버들에게 변화를 알려주는 패턴
- 옵저버 패턴의 예 : 트위터
- 이벤트 기반 시스템에 사용됨
- MVC 패턴에도 사용됨
    - `extends & implement`
        
        extends
        
        자식 클래스가 부모 클래스의 메서드를 상속받아 사용하며 자식클래스에서 추가/확장이 가능
        
        재사용성, 중복성의 최소화
        
        implement
        
        자식클래스가 부모 인터페이스를 재정의하여 구현하는 것
        
        반드시 부모의 메서드를 재정의하여 구현해야함
        
- 자바스크립트에서 옵저버패턴은 프록시객체를 통해 구현이 가능함
    - `proxy 객체`
        
        어떠한 대상의 기본적인 동작의 작업을 가로챌 수 있는 객체
        
        자바스크립트에서는 두개의 매개변수를 가짐
        
        1. target : 프록시할 대상
        2. handler : 프록시객체의 타겟 동작을 가로채서 정의할 동작들이 정해져 있는 함수
- Vue.js에서 ref나 reactive로 정의하면 해당값이 변경되었을 때 자동으로 DOM에 있는 값이 변경됨
    - `DOM`
        
        DOM(Document Object Model)
        
        문서 객체모델
        
        웹브라우저 상 화면을 이루는 요소
        

### 5. 프록시패턴/프록시서버 Proxy Pattern/ProxyServer

- 프록시 패턴
    - 대상객체(Subject)에 접근하기 전 그 접근에 대한 흐름을 가로채 대상 객체 앞단의 인터페이스 역할을 하는 디자인 패턴
    - 프록시패턴을 통해 객체의 속성, 변환 등을 보완하며 보안/데이터 검증/캐싱/로깅에 사용함
    - 프록시 객체로도 쓰이지만 프록시 서버로도 활용됨

> 프록시 서버에서의 캐싱
캐시안에 정보를 담아두고 그 정보에 대한 요청처리는 캐시에 담긴 데이터를 활용하는 것
→ 불필요한 외부연결이 없어지므로 트래픽을 줄일 수 있음
> 

- 프록시 서버
    - 서버와 클라이언트 사이에서 클라이언트가 자신을 통해 다른 네트워크 서비스에 간접 접속할 수 있게 하는 컴퓨터 시스템이나 응용프로그램 임
    - 프록시 서버로 쓰이는 `nginx`, `cloud flare`
        - nginx
            - 비동기 이벤트 기반의 구조와 다수의 연결을 효과적으로 처리 가능한 웹서버
            - 주로 Node.js 서버 앞단의 프록시서버로 활용됨
            - overflow 취약점을 예방하기 위해 사용됨
                - `overflow`
                    
                    버퍼 : 데이터가 저장되는 메모리 공간
                    
                    버퍼 오버플로우 : 메모리 공간을 벗어나는 경우
                    
                    → 사용되지 않아야할 영역에 덮어 씌워져 주소, 값을 바꾸는 공격이 발생하기도 함
                    
            - 익명사용자의 직접적인 서버접근을 차단하며 보안성을 강화함
                
                → 실제 port를 숨길 수 있음
                
                정적자원을 gzip 압축 가능함
                
                메인서버 앞단에서 로깅
                
                - `gzip`
                    
                    LZ77과 Huffman 코딩 조합인 DEFLATE 알고리즘을 기반으로 한 압축기술
                    
                    - 데이터 전송량을 줄일 수 있음
                    - 압축해제시 서버에서의 CPU 오버해드도 고려하여 사용해야함
                    
        - cloud flare
            
            전 세계적으로 분산된 서버가 있고, 이를 통해 시스템의 컨텐츠를 빠르게 전달할 수 있는 CDN 서비스
            
            - CDN 서비스
                
                Content Delivery Network
                
                사용자가 인터넷에 접속하는 곳과 가까운 곳에서 컨텐츠를 캐싱/배포하는 서버 네트워크
                
                웹서버로부터 컨텐츠를 다운받는 시간 감소
                
            - D Dos 공격 방어
                - D Dos
                    
                    짧은 기간 동안 네트워크에 많은 요청을 보내 네트워크를 마비시켜 웹사이트 가용성을 방해하는 사이버 공격 유형
                    
                - Cloud Flare는 의심스러운 트래픽, 사용자 접속이 아닌 시스템을 통해 오는 트래픽을 자동으로 차단함
                    
                    → Cloud Flare의 거대한 네트워크 용량+캐싱전략으로 D Dos 공격을 방어
                    
                    → DDos 공격에 대한 방화벽 대시보드 제공
                    
            - HTTPS 구축
                - HTTPS 구축시 별도의 인증서 없이 Cloud Flare를 사용하여 구축 가능
                
- CORS와 프론트엔드의 프록시 서버
    - CORS
        
        Cross-Origin Resourse Sharing
        
        서버가 웹브라우저에서 리소스를 로드할때, 다른 오리진을 통해 로드하지 못하게 하는 HTTP 헤더 기반 메커니즘
        
        - origin
            
            프로토콜과 호스트 이름, 포트의 조합
            
            [https://kundal.com:1201/test](https://kundal.com:1201/test) 
            
            : [https://kundal.com:1201](https://kundal.com:1201) 이 origin
            
    
    프록시서버를 만드는 이유
    
    프론트엔드 개발시
    
    프론트엔드 서버와 백엔드 서버가 통신할 때, CORS error를 마주침. 이를 해결하기 위해 프록시서버를 만듦
    
    예)
    
    프론트엔드 127.0.0.1:3000
    
    백엔드 127.0.0.1:1201
    
    이 때, CORS 에러
    
    이 때 프록시서버를 두고 프론트서버에서 요청되는 origindmf 127.0.0.1:1201 로 바꿈
    

### 6. 이터레이터 패턴 Iterator Pattern

Iterator를 사용하여 Collection의 요소들에 접근하는 디자인 패턴

Iterator를 통해 자료형의 구조와는 상관없이 iterator라는 하나의 인터페이스로 순회가 가능

- Iterator protocol
    
    이터러블한 객체들을 순회할 때 쓰이는 규칙
    
    - 이터러블 한 객체
        
        반복이 가능한 객체로 배열을 일반화한 객체
        

### 7. 노출 모듈 패턴 Revealing Module Pattern

즉시실행 함수를 통해 private, public 같은 접근 제어자를 만드는 패턴

→ 자바스크립트는 전역범위에서 스크립트가 실행됨 (이것을 기반으로 자바스크립트에는 CJS(Common JS)모듈이 있음)

- 즉시 실행 함수
    
    함수를 정의하자마자 바로 호출하는 함수
    
    초기화 코드, 라이브러리 내 전역변수의 충돌방지에 사용됨
    
- 접근제어자
    
    public : 클래스에 정의된 함수에서 접근 가능, 자식클래스/외부클래스에서도 접근 가능
    
    protected : 클래스에 정의된 함수에서 접근 가능, 자식클래스에서 접근 가능, 외부클래스에서 접근 불가능
    
    private : 클래스에서 정의된 함수에서 접근 가능, 자식클래스/외부클래스 접근 불가능
    

### 8. MVC 패턴 Model, View, Controller Pattern

모델, 뷰, 컨트롤러로 이루어진 디자인 패턴

- 장점과 단점
    - 장점
        
        application의 구성요소 세가지를 역할로 구분하여 각 구성요소에만 집중해서 개발 가능
        
        재사용성, 확장성이 용이함
        
    - 단점
        
        application이 복잡해질수록 모델과 뷰 간 관계가 복잡해짐
        
- Model
    
    application의 data인 DB, 상수, 변수등을 뜻함
    
    뷰에서 데이터를 생성하거나 수정하면 컨트롤러를 통해 모델을 생성하거나 갱신함
    
- View
    
    사용자 인터페이스 요소
    
    모델을 기반으로 사용자가 볼 수 있는 화면
    
    단순히 화면에 표시하는 정보만 가지며 변경이 일어나면 컨트롤러에 전달해야함
    
- Controller
    
    하나 이상의 모델과 하나 이상의 뷰를 잇는 다리 역할
    
    메인 로직을 담당함
    
    모델과 뷰의 생명주기를 관리함
    
    모델이나 뷰의 변경통지를 받으면 이를 해석하여 각 구성요소에 전달해야함
    

### 9. MVP 패턴 Model, View, Presenter Pattern

MVC 패턴에서 파생됨

Controller 가 Presenter로 교체된 형태

Model ↔ Presenter 1:1 관계

model 갱신/변경

View ↔ Presenter 1:1 관계

UI갱신, 유저 이벤트

1:1 관계이기 때문에 더 강한 결합을 지님

### 10. MVVM 패턴 Model, View, View Model Pattern

MVC 패턴에서 파생됨

Controller 가 ViewModel로 교체된 형태

ViewModel : View 를 더 추상화 함

View → (data binding) → View Model → (갱신) → Model

View ← (command,notify) ← View Model ← (notify) ← Model

- Data Binding, Command
    
    Data Binding : 화면에 보이는 데이터와 웹브라우저의 메모리 데이터를 일치시키는 기법으로 뷰모델을 변경하면 뷰가 변경됨
    
    Command : 여러 요소에 대한 처리를 하나의 액션으로 처리할 수 있게 하는 기법
    

> MVC와 MVVM의 차이
> 

Command와 Data Binding을 가짐

View 와 ViewModel 사이 양방향 Binding을 지원

UI를 별도의 코드 수정없이 재사용 가능함

단위 테스팅 용이

MVVM 패턴의 예 : Vue.js (반응형이 특징인 프론트엔드 프레임워크)