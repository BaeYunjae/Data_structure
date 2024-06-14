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

# stack의 함수

- push(x)
- size()
- empty() : stack이 비어있으면 true, 아니면 false 반환
- top()
- pop() : stack의 가장 위에 있는 데이터를 뺀다. 값을 반환하지는 않는다.