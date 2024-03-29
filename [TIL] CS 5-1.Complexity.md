# 5-1. 복잡도

Chapter: https://www.notion.so/5-d64a722aeb92475aa5afda0e0fd8bc2e
Done!: No
Projects: https://www.notion.so/CS-06b39c96b09f435fa450f29bac78a0f8

---

# 5.1 복잡도

## 5.1.1 시간복잡도

`시간복잡도` : 문제를 해결하는데 걸리는 시간과 입력의 함수 관계

- 어떠한 알고리즘의 로직이 얼마나 오랜 시간 걸리는지 나타내는데 쓰임
- `빅오표기법`으로 나타냄
- `빅오표기법`
    
    입력범위 n을 기준으로 해서 로직이 몇 번 반복되는지 나타내는 것
    
    가장 영향을 많이 끼치는 항의 상수 인자를 빼고 나머지 항을 없앰
    
    입력의 크기가 커질수록 연산량이 가장 많아지는 항은 n의 제곱항이므로 이것만 신경 쓰면 되된다는 이론
    
    - O(n의 제곱) > O(n) > O(log n) > O(1)  : O(1)을 지향해야함

### 시간복잡도는 왜 필요한가?

효율적인 코드로 개선하는 데 쓰이는 척도가 됨

## 5.1.2 공간복잡도

`공간복잡도` : 프로그램을 실행시켰을 때 필요로 하는 자원 공간의 양

- 정적 변수로 선언된 것 말고도 동적으로 재귀적인 함수로 인해 공간을 계속해서 필요로 할 경우도 포함됨

```cpp
int a[1004];

//a의 배열은 1004 * 4바이트의 크기를 가짐
```

## 5.1.3 자료구조에서의 시간 복잡도

보통 시간복잡도를 생각 할 때 평균과 최악의 시간 복잡도를 고려하며 사용함