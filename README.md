# Data_Structure
자료구조
>- <a href="#array">배열</a> 
>- <a href="#list">리스트</a> 
>- <a href="#stack">스택</a>


<br>
<br>

# <div id="array">배열(Array)</div>
## 정의
> Array(배열) : 한 종류의 데이터 타입을 연속적으로 메모리에 저장한 집합이다.
```
int array[10] = {0,1,2,3,4,5,6,7,8,9};
```

예를 들어 int 타입 데이터 10개를 연속적인 메모리에 저장하게 해주는 것이 배열이다.
<br>  
<br>


## 특징  

### 인덱스[index]
>배열은 인덱스[index]를 통해 배열의 요소{0,1,2...}에 접근할 수 있다.
```
printf("%d",array[0]); // 0을 출력한다.
printf("%d",array[1]); // 1을 출력한다.
printf("%d",array[2]); // 2를 출력한다.
```

배열의 인덱스는 항상 0부터 시작 한다.  
따라서 array 변수의 경우, 10개의 int 타입 데이터를 가지고 있기 때문에 인덱스는 0부터 9까지이다.  
<br>
<br>
### 배열의 내부
>일반 변수와 달리 배열 변수 안에는 배열이 시작하는 지점의 메모리 주소를 가진다.
```
printf("%p", array); // 00B8FA70 메모리 위치 출력(16진수)
printf("%d", sizeof(int)); // int는 4 byte
```

따라서  
0의 메모리 위치는 00B8FA70  
1의 메모리 위치는 00B8FA74  
2의 메모리 위치는 00B8FA78  
...  

<br>  
<br>

## 생각
>다른 자료 구조들에 비해 배열의 유일한(?) 특징은 [연속적인 메모리 위치]라고 생각한다. 다른 자료 구조들의 경우 데이터가 나란히 이어져 있는 경우는 있지만, 물리적으로 메모리가 이어져 있는 경우는 (내가 알기론) 없기 때문이다.
___
<br>
<br>
<br>
<br>

# <div id="list">리스트(List)</div>
## 정의
>List(리스트) : n개의 데이터 타입이 서로 연결되어 순서가 있다.  

리스트의 각각의 요소들이 서로 연결되어져 있다.

## 특징
>리스트는 아래와 같이 2가지로 구현할 수 있다.
1. 배열  
2. 연결 리스트

<br>
<br>

> ### 배열(Array)
배열의 경우 구현이 간단하지만  
삽입,삭제시 때에 따라 리스트의 순서를 유지하기 위해 배열의 많은 요소들을 하나씩 옮겨야 하기 때문에 비효율적이다.  
또한 배열이 선언한 이후에, 배열의 크기를 늘리거나 줄일 수 없는 정적인(static) 형태를 가지고 있다.  
C언어의 경우 일반적인 지역변수나 배열은 Stack이라는 메모리에 저장이 된다.  

> 삽입  
<img height=200 src="List_array_insert.gif">      


> 삭제  
<img height=200 src="List_array_remove.gif">   

<br>
<br>

> ### 연결 리스트(LinkedList)
연결 리스트의 경우 구현이 복잡하지만
삽입,삭제가 효율적이고, 크기를 줄이고 늘릴 수 있는 동적인(dynamic) 형태를 가진다.
C언어의 경우 head이라는 메모리에 저장하여 사용한다.






```
typedef struct _Node{
    int data;
    struct _Node* next;
}Node;
```
___
<br>
<br>
<br>
<br>

# <div id="stack">스택(Stack)</div>
## 정의
>Stack(스택) : 탑(top)에 의해 삽입과 삭제가 이루어지는 정렬된 리스트  

<br>
<br>

## 특징
>스택은 쉽게 말해 상자 쌓기와 비슷하다.  
 
 창고에서 상자를 정리하기 위해서는 맨 처음에 상자를 바닥에 두고, 그 다음 상자를 위에 올린다.  

이와같이 데이터가 아래부터 위로 쌓아 올라가는 듯한 형태의 자료구조가 스택이다. 이 때 가장 최근에 삽입된 데이터를 탑(Top)이라고 부르며 데이터가 삽입(push) 및 삭제(pop)될 때 항상 탑을 기준으로 작동한다.  
 
비어있는 스택에 데이터 A0가 삽입되면 A0가 탑이 된다.  
이후에 데이터 A1이 삽입되면 탑(A0) 위에 A1이 쌓이면서 A1이 탑이된다.  
<img width = 150 src="Stack_push.gif">  
<br>
반대로 스택에 쌓인 데이터를 삭제한다면 맨 위에 쌓여있는 데이터 부터 즉, 가장 최근에 삽입된 데이터(A4) 먼저 삭제된다.   
<img width = 150 src="Stack_pop.gif">  

이러한 특징을 **LIFO(Last In First Out)** 라고 부른다.   
**가장 최근에 들어온 데이터가 먼저 나가는 특징을 가지고 있다.**  

<br>
<br>

## 생각
>스택은 대표적으로 미로찾기 알고리즘,후위식 및 전위식 계산에 쓰이는 자료구조 이다.