# 01-1. 자료구조에 대한 기본적인 이해

## 1. 자료구조

- 자료구조 : ‘데이터의 저장’을 담당하는 것

- 자료구조의 분류

    |선형구조|비선형구조|파일구조|단순구조|
    |:---:|:---:|:---:|:---:|
    |리스트|트리|순차파일|정수|
    |스택|그래프|직접파일|실수|
    |큐||색인파일|문자|
    ||||문자열|

# 01-2. 알고리즘의 성능분석 방법

## 1. 알고리즘

표현 및 저장된 데이터를 대상으로 하는 문제의 해결 방법

최적 : 적은 메모리 사용, 빠른 속도

## 2. 시간 복잡도와 공간 복잡도

알고리즘을 평가하는 요소

1. 시간복잡도
    
    속도에 해당하는 알고리즘의 수행시간 분석결과
    
    연산의 횟수를 통해서 알고리즘의 빠르기 판단
    
    알고리즘 별 연산 횟수를 함수의 형태로 구성하여 데이터 수의 증가에 따른 연산횟수의 변화 정도 파악 ⇒ 둘 이상의 알고리즘 비교에 용이
    
    <aside>
    데이터의 수가 많아짐에 따른 연산횟수의 증가 정도
    
    </aside>
    
2. 공간복잡도
    
    메모리 사용량에 대한 분석결과
    

## 3. 순차 탐색 알고리즘과 시간 복잡도

- 순차탐색 : 맨 앞에서부터 순서대로 탐색을 진행하는 알고리즘

```c
//주요 알고리즘
for(i=0; i<len; i++)
{
	if(ar[i] == target)
		return i;
}
```

- 핵심 : 동등비교를 하는 비교 연산
    
    값의 동등을 비교하는 == 연산을 적게 수행하는 탐색 알고리즘이 좋은 탐색 알고리즘
    
- 시간복잡도 계산
    1. 최악의 경우
        
        $$
        T(n)=n
        $$
        
    2. 평균적인 경우
        
        $$
        T(n)
            =\frac{3}{4}n
        $$
        
        최악의 경우에 비해서 상대적으로 시간 복잡도를 구하는 것이 쉽지 않다.
        
        시간 복잡도 함수는 신뢰도가 높지 않다.
        
    
    ⇒ ‘최악의 경우’를 시간 복잡도의 기준으로 삼는다.
    

## 4. 이진 탐색 알고리즘과 시간 복잡도

- 이진 탐색 알고리즘 : 탐색의 대상을 반복해서 반씩 떨구어 내는 알고리즘

```c
//주요 알고리즘
while(first <= last)
{
	mid = (first+last)/2;

	if(target == arr[mid]){
		return mid;
	}	else{
		if(target < arr[mid])
			last = mid-1;
		else
			first = mid+1;
	}
	return -1;
}
```

- 시간복잡도 계산
    1. 최악의 경우
        
        ==연산 : 연산횟수를 대표하는 연산
        
        $$
        T(n) = log_2n
        $$
        

## 5. 빅-오 표기법

- 데이터 수의 증가에 따른 연산횟수의 증가 형태를 표현한 것
    
    (=데이터 수의 증가에 따른 연산횟수의 증가율의 상한선을 표현한 것)
    

<aside>
💡 T(n)이 다항식으로 표현된 경우, 최고차항의 차수가 빅-오가 된다.

</aside>

- 대표적인 빅-오 표기들의 성능의 대소관계

$$
O(1)<O(logn)<O(n)<O(nlogn)<O(n^2)<O(n^3)<O(2^n)
$$

- 수학적 접근

> 두 개의 함수 f(n)과 g(n)이 주어졌을 때, 모든 n≥K에 대하여 f(n)≤Cg(n)을 만족하는 두 개의 상수 C와 K가 존재한다면, f(n)의 빅-오는 O(g(n))이다.
>

# 02-1. 함수의 재귀적 호출의 이해

### 재귀함수

- 함수 내에 자신을 다시 호출하는 함수

<aside>
❓ 완료되지 않은 함수를 다시 호출하는 것이 가능한가?
→ 함수가 호출되면 해당 함수의 복사본을 만들어 실행하는 구조이기 때문에 가능하다.

    (함수를 구성하는 명령문이 CPU로 복사되어 실행되며 얼마든지 복사 가능)

</aside>

- ‘재귀의 탈출조건’이 성립되어야 함수가 반환하기 시작한다.
- 재귀함수는 자료구조나 알고리즘의 어려운 문제를 단순화하는데 사용되는 중요한 무기이다.

### 팩토리얼

$$
f(n)={n*f(n-1),\quad n≥1\brace1,\quad\quad\quad\quad\quad\quad n=0}
$$

```c
//팩토리얼 함수
int Factorial(int n)
{
	if(n==0)   //탈출조건
		return 1;
	else
		return n*Factorial(n-1);	
}
```


# 02-2. 재귀의 활용

### 피보나치 수열(Fibonacci Sequence)

- 재귀적인 형태를 띄는 대표적인 수열
- 앞엣것 두 개를 더해서 현재의 수를 만들어가는 수열

<aside>
💡 수열의 n번째 값 = 수열의 n-1번째 값 + 수열의 n-2번째 값
⇒ 0, 1, 1, 2, 3, 5, 9, 13, 21, 34, 55 . . .

</aside>

$$
fib(n)\begin{cases} 0,\quad n=1 \\ 1, \quad n=2 \\ fib(n-1) + fib(n-2), \quad otherwise \end{cases}
$$

```c
//피보나치 함수
int Fibo(int n)
{
	if(n==1)
		return 0;
	else if(n==2)
		return 1;
	else
		return Fibo(n-1) * Fibo(n-2);
}
```

⇒ 수학적 재귀의 표현이 그대로 코드로 옮겨졌다.

- 중복된 재귀 호출을 반복한다.

⇒ 재귀함수는 매우 많은 수의 함수 호출을 동반하므로 성능상의 불리함이 존재한다.

### 이진 탐색 알고리즘

- 알고리즘 자체는 재귀적인 성격을 지니고 있다.
    
    > <반복패턴>
    1. 탐색 범위의 중앙에 목표 값이 저장되었는지 확인
    2. 저장되지 않았다면 탐색 범위를 반으로 줄여서 다시 탐색 시작
    > 

<aside>
* 재귀함수의 탈출조건<br>
⇒ 탐색 대상을 찾았거나 탐색 대상이 배열에 존재하지 않는 경우<br>
* 실패조건

⇒ 탐색 범위의 시작 위치(first)가 탐색 범위의 끝의 위치(last)보다 커지는 경우

</aside>

```c
//이진 탐색 함수
int BsearchRecur(int ar[], int first, int last, int target)
{
	int mid;
	if(first > last)    //탈출조건
		return -1;
	mid = (first+last)/2;

	if(ar[mid]==target)
		return mid;
	else if(target<ar[mid])
		return BsearchRecur(ar, first, mid-1, target);
	else
		return BsearchRecur(ar, mid+1, last, target);
}
```

-------
# 02-3. 하노이 타워(The Tower of Hanoi)
- 하나의 막대에 쌓여 있는 원반을 다른 하나의 원반에 그대로 옮기는 방법
    
    > <제약조건>
    >- 원반은 한 번에 하나씩만 옮길 수 있다.
    >- 옮기는 과정에서 작은 원반의 위에 큰 원반이 올려져서는 안된다.<br>
    ⇒ 막대 A에서 막대 C로 옮기기 위해서 막대 B의 도움이 필요하다.
- 재귀적으로 접근하지 않으면 해결이 쉽지 않은 문제이다.

<img src = "./img/Hanoi.png" width = 300>

<aside>
    #해결 과정<br>
    1. 작은 원반 n-1개를(맨 아래의 원반을 제외한 나머지 원반을) A에서 B로 이동<br>
    2. 큰 원반(맨 아래의 원반) 1개를 A에서 C로 이동<br>
    3. 작은 원반(위의 1단계에서 옮겨진 원반) n-1개를 B에서 C로 이동
</aside>

- 재귀의 탈출 조건 : 이동해야 할 원반의 수가 1개인 경우
```c
//하노이 타워 함수
void HanoiTowerMove(int num, char from, char by, char to)
{
	if(num==1)
		printf("원반1을 %c에서 %c로 이동\n", from, to);
	else
	{
		HanoiTowerMove(num-1,from,to,by);
		printf("원반%d을(를) %c에서 %c로 이동\n", num, from, to);
		HanoiTowerMove(num-1,by,from,to);
	}
}
```
### 하노이 타워 구현
```c
#include <stdio.h>

void hanoiMove(int num, char from, char by, char to)
{
	if (num == 1) {
		printf("원반1 : %c에서 %c로 이동\n",from,to);
	}
	else {
		hanoiMove(num - 1, from, to, by);
		printf("원반%d : %c에서 %c로 이동\n", num, from, to);
		hanoiMove(num - 1, by, from, to);
	}
}

int main(void)
{	
	int num;
	printf("원반의 수를 입력하세요. A에서 C로 이동합니다.\n");
	scanf_s("%d", &num);
	hanoiMove(num, 'A', 'B','C');
}
```

# 02-1. 함수의 재귀적 호출의 이해

### 재귀함수

- 함수 내에 자신을 다시 호출하는 함수

<aside>
❓ 완료되지 않은 함수를 다시 호출하는 것이 가능한가?
→ 함수가 호출되면 해당 함수의 복사본을 만들어 실행하는 구조이기 때문에 가능하다.

    (함수를 구성하는 명령문이 CPU로 복사되어 실행되며 얼마든지 복사 가능)

</aside>

- ‘재귀의 탈출조건’이 성립되어야 함수가 반환하기 시작한다.
- 재귀함수는 자료구조나 알고리즘의 어려운 문제를 단순화하는데 사용되는 중요한 무기이다.

### 팩토리얼

$$
f(n)={n*f(n-1),\quad n≥1\brace1,\quad\quad\quad\quad\quad\quad n=0}
$$

```c
//팩토리얼 함수
int Factorial(int n)
{
	if(n==0)   //탈출조건
		return 1;
	else
		return n*Factorial(n-1);	
}
```