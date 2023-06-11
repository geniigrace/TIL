# Array.prototype.includes()

`includes()` 메서드는 배열이 특정 요소를 포함하고 있는지 판별한다.

```jsx
const array1 = [1,2,3];

console.log(array1.includes(2));
//output : true

const pets = ['cat','dog','bat'];
console.log(pets.includes('cat'));
//output : true

console.log(pets.includes('puppy'));
//output : false
```

## 구문

`array.includes(valueToFind, fromIndex)`

- 매개변수
    - valueToFind
        - 탐색할 요소
        - 문자나 문자열을 비교할 때 대소문자를 구분한다.
    - fromIndex
        - 이 배열에서 searchElement 검색을 시작할 위치이다.
        - 배열의 길이보다 같거나 크면 false를 반환한다.
        - 기본값은 0 이다.
        - 음의 값은 array.length + fromIndex의 인덱스를 asc로 검색한다.
        - 생략이 가능하다.

## 반환값

Boolean 값으로 반환된다.