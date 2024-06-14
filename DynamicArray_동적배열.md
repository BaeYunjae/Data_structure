# 목차
1. [들어가기 전](#들어가기-전)
2. [동적 배열의 개념과 특징](#동적-배열)
3. [배열의 시간복잡도](#배열의-시간복잡도)
4. [동적 배열 선언 방법](#동적-배열-선언-방법)

5. [vector 순회 방법](#vector-순회-방법)

<br>

# 들어가기 전 
## 정적 배열

지금까지 내가 써오던 배열은 **정적 배열**이다.

```cpp
int arr[10];
```

### 정적 배열의 특징

- 정적 배열은 배열의 선언과 동시에 그 크기를 정해줘야 한다.
- 한 번 선언된 이후에는 크기를 바꿀 수 없다.

---

<br>

# 동적 배열
## 개념
: 길이를 자유롭게 줄이고 늘릴 수 있는 배열 


## 특징 

- 동적 배열은 그때그때 메모리를 필요한 만큼만 사용한다.
- 삽입, 삭제, 탐색하는 과정이 정적 배열과 동일하다. (시간복잡도 일치)

<br>

# 배열의 시간복잡도

- 배열의 시작과 끝에 데이터를 삽입하거나 삭제하는 경우 **O(1)**
- 배열 중간에 데이터를 삽입하거나 삭제하는 경우, 그 뒤에 있는 데이터들을 한 칸씩 밀거나 당겨와야 하기 때문에 **O(N)**

<br>

# 동적 배열 선언 방법

## vector 이용

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

# vector 순회 방법

1. **for문**

	```cpp
	vector<int> v;

	for (int i = 0; i < v.size(); i++){
		cout << v[i] << "\n";
	}
	```

2.  **iterator**

	```cpp
	vector<int> v;
	vector<int>::iterator it;

	for (it = v.begin(); it != v.end(); it++){
		cout << *it << "\n";
	}
	```