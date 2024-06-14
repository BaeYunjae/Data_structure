# 목차
1. [STL이란](#stl이란)
- [vector STL](#vector-stl)
- [stack STL](#stack-stl)
2. [iterator](#iterator)

<br>

# STL이란

- C++에서는 vector, stack, queue 등의 자료구조를 사용할 수 있다.
    
    → 왜? 이미 만들어 놓은 STL(Standard Template Library, 표준 템블릿 라이브러리)가 있기 때문이다.
    
- **컨테이너** : STL로 정의되어 있는 자료구조들
    
    예) vector, stack 등
    
- 컨테이너 내에 있는 원소들을 순회하기 위해 iterator라는 이름의 반복자를 사용한다.

<br>

# vector STL

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main(){
	vector<int> v;
	return 0;
}
```

## vector의 함수

- push_back(x)
- pop_back()
- size()

<br>

# list STL

- 이중연결리스트

```cpp
#include <iostream>
#include <list>
using namespace std;

int main(){
	list<int> s;
	return 0;
}
```

## list의 함수

- push_front(x) : 맨 앞에 데이터 추가
- push_back(x) : 맨 뒤에 데이터 추가
- pop_front() : 맨 앞에 있는 데이터 빼기
    
    C++ 철학상 (하나의 함수는 하나의 역할 + 안전성) 값 반환은 하지 않는다. 
    
- pop_back() : 맨 뒤에 있는 데이터 빼기
- size() : 현재 list에 들어있는 데이터의 수 반환
- empty() : 현재 list 비어있다면 true, 아니면 false 반환
- front() : 맨 앞에 있는 데이터 반환
- back() : 맨 뒤에 있는 데이터 반환

<br>

# stack STL

```cpp
#include <iostream>
#include <stack>
using namespace std;

int main(){
	stack<int> s;
	return 0;
}
```

## stack의 함수

- push(x)
- size()
- empty() : stack이 비어있으면 true, 아니면 false 반환
- top()
- pop() : stack의 가장 위에 있는 데이터를 뺀다. 값을 반환하지는 않는다.

<br>

# queue STL

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main(){
	queue<int> q;
	return 0;
}
```

## queue의 함수

- push(x) : 맨 뒤에 데이터 추가
- size()
- empty()
- front() : 맨 앞의 데이터 반환
- pop() : 맨 앞에 있는 데이터를 뺀다. 값을 반환하지는 않는다. 
⇒ 하나의 함수는 하나의 역할만 한다 (C++의 철학)

<br>

---

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