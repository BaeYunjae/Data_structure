# 목차
1. [STL](#STL)
<br>
    1-1. [컨테이너](#컨테이너란)
2. [iterator](#iterator)
<br>
    2-1. [vector의 iterator](#vector의-iterator)

<br>

# STL

- C++에서는 vector, stack, queue 등의 자료구조를 사용할 수 있다.
    
    → 왜? 이미 만들어 놓은 STL(Standard Template Library, 표준 템블릿 라이브러리)가 있기 때문이다.
    
## **컨테이너**란?
: STL로 정의되어 있는 자료구조들
    
    예) vector, stack 등
    
- 컨테이너 내에 있는 원소들을 순회하기 위해 iterator라는 이름의 반복자를 사용한다.

<br>

# iterator

- 컨테이너를 조회하기 위해 사용하는 반복자

기본 형태 : `컨테이너 타입::iterator it;` 

```cpp
vector<int>::iterator it;
stack<int>::iterator it;
```

## vector의 iterator

- 시작 원소를 나타내는 위치는 `v.begin()` , 마지막 원소 그 다음 위치는 `v.end()` 로 설정해 vector를 순회할 수 있다.

    ```cpp
    vector<int>::iterator it;
    for(it = v.begin(); it != v.end(); it++){
        cout << *it << "\n";
    }
    ```

- `v.end()` 가 마지막 데이터 그 다음 위치이기 때문에 for문에서 it가 `v.end()` 가 되는 순간 종료!
- iterator는 pointer, 포인터처럼 각 원소의 주소를 가리키고, 해당 주소에 담겨있는 데이터를 참조하기 위해서 앞에 *를 붙여주어야 한다.
- 위 코드에서는  vector의 원소를 출력하기 위해 *it를 사용