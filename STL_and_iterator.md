# 목차
1. [STL이란](#stl이란)
2. [iterator](#iterator)
3. STL의 종류
    - [vector STL](#vector-stl)
    - [list STL](#list-stl)
    - [stack STL](#stack-stl)
    - [queue STL](#queue-stl)
    - [deque STL](#deque-stl)
    - [unordered_map STL](#unordered_map-stl)

<br>

# STL이란

- C++에서는 vector, stack, queue 등의 자료구조를 사용할 수 있다.
    
    → 왜? 이미 만들어 놓은 STL(Standard Template Library, 표준 템블릿 라이브러리)가 있기 때문이다.
    
- **컨테이너** : STL로 정의되어 있는 자료구조들
    
    예) vector, stack 등
    
- 컨테이너 내에 있는 원소들을 순회하기 위해 iterator라는 이름의 반복자를 사용한다.

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

<br>

---

# STL의 종류

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

# deque STL

```cpp
#include <iostream>
#include <deque>
using namespace std;

int main(){
	deque<int> dq;
	return 0;
}
```

## deque의 함수

- push_front(x) : 맨 앞에 데이터 x 추가
- push_back(x) : 맨 뒤에 데이터 x 삭제
- pop_front() : 맨 앞에 있는 데이터 빼기, 삭제만 할 뿐 값을 반환하지 않는다.
- pop_back() : 맨 뒤에 있는 데이터를 빼기, 값을 반환하지 않는다.
- size()
- empty()
- front() : deque 맨 앞에 있는 데이터 반환
- back() : deque 맨 뒤에 있는 데이터 반환

<br>

# unordered_map STL

unordered_map은 HashMap 자료구조로 되어 있다.

> **HashMap** 
- 해싱을 기반으로 데이터들을 관리해주는 자료구조
- (key, value) 쌍 형태로 들어가 있어, key와 그 key에 따른 value 값을 동시에 저장하는 형태
- 삽입, 삭제, 탐색 등 모든 함수의 시간복잡도 : **O(1)**
> 

```cpp
#include <iostream>
#include <unordered_map>
using namespace std;

int main(){
	unordered_map<int, int> um;  // <key 타입, value 타입> 
	return 0;
}
```

## unordered_map의 함수

- `um.insert( { K, V } )` 또는 `um[K] = V` : hashmap에 쌍 (K, V) 추가
- `um.erase(K)` : 현재 hashmap에 들어있는 데이터 중 key가 K인 쌍을 찾아 제거
- `um.find(K)` 또는 `um[K]` : 현재 hashmap에 key가 K인 쌍이 있는지 확인
    - 만약 있다면 해당 iterator 반환, 없다면 `um.end()` 반환
        - 값이 있다면 `um.find(K) != um.end()` , 없다면 `um.find(K) == um.end()` 만족
    - pair 타입이므로 아래와 같이 접근 가능
        - key가 K인 원소의 key 조회
            
            ```cpp
            // 첫번째 방법
            cout << (um.find(K))->first; 
            // 두번째 방법
            cout << (*um.find(K)).first;
            ```
            
        - key가 K인 원소의 value 조회
            
            ```cpp
            // 첫번째 방법
            cout << (um.find(K))->second; 
            // 두번째 방법
            cout << (*um.find(K)).second;  
            ```
            
    - 값만 조회하고 싶다면 `um[K]` 형태로도 이용 가능
        
        ```cpp
        	cout << um[K]; // key가 K인 원소의 value 조회 후 출력
        ```
