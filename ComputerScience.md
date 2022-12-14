# 미래컴퓨팅 기술

### 1. 클라우드 컴퓨팅

- 인터넷 서버를 통해 데이터 저장, 네트워크, 콘텐츠 사용 등 ICT 기술 관련 서비스를 동시에 사용할 수 잇는 컴퓨팅 환경
- 정보 : 인터넷 서버에 영구적으로 저장 / 정보기기와 같은 클라이언트에 일시적으로 보관

⇒ 하드웨어에 의존하지 않아도 되는 환경 조성

### 2. 사물인터넷

- 각종 사물에 컴퓨터칩과 통신 기능을 내장하여 인터넷과 연결하는 기술
- 핵심 기술
    - 센싱 기술 : 사물에서 데이터를 인식하고 추출해 인터넷으로 전송
    - 유무선통신 기술 : 분산된 컴퓨팅 자원을 서로 연결하여 고속 처리와 병렬 처리를 가능하게 함
    - 서비스 인터페이스 기술 : 각종 서비스 분야와 형태에 알맞게 정보를 가공•처리•융합
    - 보안 기술 : 해킹이나 정보 유출 방지

### 3. 인공지능

- 기계가 학습과 추리를 통해 사람과 동일한 작업을 수행할 수 있도록 하는 기술

### 4. 로봇

- 스스로 작업하는 능력을 갖춘 기계

### 5. 드론

- 로봇 기술을 응용한 무인 비행 물체

### 6. 자율주행 자동차

- 운전자가 조작하지 않아도 스스로 움직이는 자동차
- 인공지능•빅데이터•로봇 기술 등이 집약되어 있다.

<aside>
💡 하드웨어는 중앙처리장치, 기억장치, 입출력장치로 구성되어 있으며 각 장치는 시스템 버스로 연결되어 있다.

</aside>

### 시스템버스

- 컴퓨터에 있는 중앙처리장치, 주기억장치, 입출력장치 간 데이터를 주고받기 위해 사용하는 경로
- 선의 폭이 넓을수록 한번에 전송할 수 있는 데이터의 양도 많아진다.
- 버스의 크기나 데이터의 전송 속도가 시스템의 성능을 좌우한다.
- 데이터 버스
    - 중앙처리장치와 다른 장치(주기억장치, 입출력장치 등) 사이 또는 중앙처리장치 내부의 모듈들 사이에서 데이터가 이동하는 경로
- 주소 버스
    - 중앙처리장치가 사용하고자 하는 데이터의 주소가 이동하는 경로
    - 버스의 대역폭이 주기억장치의 용량을 결정한다.
- 제어 버스
    - 중앙처리장치가 기억장치나 입출력장치에 제어 신호를 전달하는 통로
    - 중앙처리장치에서 발생하는 제어 명령이나 상태 신호(입출력 동기화 신호, 중앙처리장치 상태 신호, 인터럽트 관련 신호, 클록 관련 신호 등)가 이 버스를 통해 이동한다.
<br><br>

# 중앙처리장치(CPU)

프로그램의 명령어와 데이터를 읽어 와서 명령어를 실행하고 입력된 데이터를 처리하는 일을 한다.

기계어로 된 명령어를 해독한 후 해당 명령어를 수행하기 위한 세부 작업을 실행하는 장치이다.

3개의 세부 모듈인 연산장치, 제어장치, 레지스터로 구성되어 있으며, 이들은 각각 내부 버스로 연결되어 있다.

### 연산장치

- 데이터의 계산 및 비교를 담당
- 중앙처리장치 내부에서 실제 연산을 담당한다.
- 산술연산
    - 덧셈, 뺄셈, 곱셈, 나눗셈 등 일상생활에서 자주 사용하는 사칙연산
    - 가산기를 만들어 다양한 사칙연산을 수행한다.
- 논리연산
    - 논리곱(AND), 논리합(OR), 부정(NOT) 등을 수행하는 연산
    - 피연산자로 2진수인 0과 1을 사용
    - 논리회로를 이용하므로 산술연산보다 구현하기 쉽다.

### 제어장치

- 명령어를 해석하고 시스템 실행을 담당
- 명령어가 순서대로 실행되도록 제어하는 장치
- 수행할 명령어를 해독한 후 명령어 수행에 필요한 제어 신호를 생성한다.
- 연산장치, 중앙처리장치 내부의 다른 모듈, 외부 장치(메모리, 입출력장치 등) 의 제어를 담당하는 컨트롤 타워이기도 하다.

### 레지스터

- 중앙처리장치에서 명령어를 실행하는 동안 필요한 정보를 저장
- 중앙처리장치와 속도가 비슷한 고속의 기억장치
- 중앙처리장치 내부의 저장장치
- 중앙처리장치 내부 상태를 저장하는 목적으로 사용되기도 한다.

### 중앙처리장치의 동작

1. 인출 단계(Fetch)
    
    주기억장치에 저장된 명령어 하나를 읽어 온다.
    
2. 해독 단계(Decode)
    
    읽어 온 명령어를 제어 정보로 해독한다.
    
3. 실행 단계(Execute)
    
    해독된 명령어를 실행한다.
    

### 클록 펄스

- 클록
    - 컴퓨터에서 일정한 박자를 만들어 내는 장치
- 펄스
    - 클록이 일정한 간격으로 만드는 틱
- 클록 펄스
    - 컴퓨터 내에서 동작하는 각 구성 요소의 모든 동작을 동기화하기 위해 사용하는 전자적 펄스

### 인터럽트

중앙처리장치가 특정한 기능을 수행하던 중 급하게 다른 일을 처리하고 할 때 사용하는 기능

작업을 수행하던 중 인터럽트가 발생하면, 컴퓨터는 수행하던 일을 중지하고 현재 상태(CPU 내부의 레지스터 값 등)를 보관한다. 그리고 인터럽트가 처리되면 저장해던 이전 작업의 상태를 복구시켜 수행을 재개한다.

- 입출력 인터럽트
    - 입출력 종료 등의 이유로 중앙처리장치 수행을 요청하는 인터럽트
- 소프트웨어 인터럽트
    - 중앙처리장치가 명령을 수행하는 중간에 소프트웨어가 발생시키는 인터럽트
    - 기계어 레벨에서 제공되지 않는 명령이 운영체제의 시스템 콜 형태로 제공됨

# 기억장치

## 주기억장치(메인메모리)

외부에서 들여온 데이터를 보관하는 공간

작업에 필요한 프로그램과 데이터를 저장하는 장소

보조기억장치보다 속도가 빠르고 상대적으로 비싸다

### 램

- 휘발성 메모리
    - 전원이 끊기면 내용이 지워짐
- 개인용 컴퓨터의 메인메모리로 사용, GB 용량 사용
- 랜덤 접근 (← 램을 설명하는 단어)
    - 주소를 지정하면 메인메모리의 어느 곳이든 상관없이 동일한 접근 속도로 데이터를 사용할 수 있다는 의미
- DRAM(동적램)
    - 일정 시간이 지나면 저장된 데이터가 사라짐
    - 주기적으로 다시 재생시켜 주어야 한다
- SRAM
    - 전원이 연결되어 있는 동안에는 데이터를 계속 보관할 수 있어 따로 재생할 필요가 없다.
    - 속도는 빠르지만 가격이 비싸다
- 일반적으로 메인메모리에는 DRAM을, 고속메모리에는 SRAM을 사용한다.

### 롬

- 비휘발성 메모리
    - 전원이 제거되어도 저장된 내용은 지워지지 않는다.
- 랜덤 접근의 특징을 가지고 있다.
- 롬 내의 데이터는 읽을 수만 있고 일반적인 방법으로는 변경할 수 없다.
- 전원이 끊겨도 데이터가 남아 있는 특징을 활용해, 컴퓨터를 부팅할 때 수행되어야 하는 부트스트랩 로더를 저장한다.
- Mask ROM
    - 정보의 기록 횟수와 저장방식에 따라 데이터를 지우거나 쓸 수 없다.
- PROM
    - 데이터를 한번만 저장할 수 있다.
- EPROM
    - 여러 번 쓰고 지울 수 있는 있다.
- EEPROM
    - 여러 번 쓸 수 있으며 쓰기 전에 저장된 정보는 따로 지울 필요가 없다.

## 캐시메모리

CPU와 이보다 상대적으로 느린 메인메모리 사이에 위치한 장치로, 데이터 접근 효율성을 향상시킨다.

CPU가 메인메모리의 특정 주소에 접근할 때 그 주변까지 캐시메모리로 읽어 내, 향후 비슷한 곳으로 찾아가야 할 때 접근 속도를 높이는 것이 목적

지역성의 원칙을 활용한 메모리인데, 컴퓨터 프로그램은 일반적으로 시간적 지역성과 공간적 지역성의 특성을 가진다.

- 시간적 지역성 : 한 번 사용한 정보는 곧 다시 쓰일 가능성이 높다
- 공간적 지역성 : 한 번 사용된 적 있는 정보 영역의 주변부가 다시 사용될 가능성이 높다
- 캐시 적중
    - CPU에서 원하는 정보가 캐시메모리에 존재하는 상황
- 캐시 미스
    - CPU에서 원하는 정보가 캐시메모리에 존재하지 않는 상황
- 캐시 적중률
    - 원하는 정보가 캐시메모리에 존재할 확률
    - 캐시 적중률(H) = 캐시 적중 횟수 / 전체 기억장치 참조 횟수

메인메모리에 있는 데이터를 좀 더 빠르게 사용하기 위해서 사용한다.

### 캐시메모리의 동작 과정

1. CPU가 메인메모리에 있는 데이터를 읽어야 할 때는 먼저 캐시메모리를 조사한다.
2. 캐시메모리에 데이터가 있으면 바로 CPU로 전달된다
3. 만일 데이터가 없다면 메인메모리에서 보통 블록 단위로 가져온다.
4. CPU에는 워드 단위로 전송한다.

## 보조기억장치

CPU가 처리할 데이터나 프로그램을 저장하기 위한 기억장치

접근 속도가 느리지만 저렴하고 정보를 많이 저장할 수 있음

자기테이프, 자기디스크, 광디스크, 플래시메모리

# 병렬 컴퓨터

다수의 CPU를 병렬 처리해 초고속으로 작업을 수행하는 컴퓨터

## 병렬처리

동시에 동작하는 CPU를 여러 대 갖추고 있는 컴퓨터에서만 실행할 수 있는 처리 방식

프로그램 실행 속도를 높이기 위한 명령어 스트림과 데이터 스트림을 처리하는 방식에 따라 SIMD, MIMD, SISD로 나뉜다.

### SIMD

- 모든 CPU가 같은 프로그램(명령어)를 수행하지만 병렬적으로 다른 데이터를 처리하는 구조로, 가장 일반적인 병렬 연산 기법
- 배열이나 행렬 같은 벡터 데이터 연산에서 유용하게 쓰임
- Ex) 1차원 배열 요소 2개를 각각 더해야 하는 프로그램이라면 각 배열의 요소들이 동시에 다른 프로세서를 통해 더해지는 식이다.

### MIMD

- 각각의 CPU가 서로 다른 프로그램을 수행하면서 서로 다른 데이터를 처리하는 구조
- 모든 프로그램이 협력해 하나의 목적을 이룬다.


### SISD

- 하나의 프로그램을 수행할 때 하나의 데이터를 이용해 처리하는 구조
- 일반 개인용 컴퓨터 CPU 대부분이 SISD 구조이다.