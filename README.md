# Computer_Structure
컴퓨터공학과 컴퓨터구조 정리입니다.

## 이진수 표기법(시험에쓰이는 단위)
```
시간 오름차순 Time Faster

10-3  밀리
10-6  마이크로
10-9  나노  
10-12 피코 

공간 오름차순 capacity,memory Space

10 3  킬로 
10 6  메가
10 9  기가  
10 12 테라
10 15 페타

외우기 밀마나피 KMGTPB
```

## High Level Language & Machine Language
```
High Level Language(사람이 이해하기 쉬운) C, JAVA
Low Level Language(기계가 이해하기 쉬운) Assembly

고급 언어는 있지만 저급 언어라는 단어가 없는 이유?

고급 언어 High Level Language는 High Quality가 아닌 Human Being을 뜻하고
Low Level Language는 Low Quality가 아닌 Machine Language를 뜻하기 때문입니다.
```

## 컴파일러와 어셈블러
```
C언어(High Level Language)로 작성된 프로그램을 swap.c라 하면

프로그램을 컴파일하는 과정(high level -> Machine language) 
cc -c swap.c (컴파일러가 컴파일) -> swap.o 목적프로그램이 생김(Machine) 사람이 이해할 수 없습니다.
이 swap.o 파일을 cc -o swap swap.o -> swap이라는 실행파일이 생깁니다.

프로그램을 어셈블하는 과정(high level -> Assembly language)
cc -S swap.c (어셈블러가 어셈블) -> swap.s (바로 목적프로그램이 생기지 않고 이진 기계어(어셈블리언어로 작성된 프로그램) -> as -o swap.o swap.s -> 목적프로그램 swap.o가 생김 -> cc -c swap swap.o 컴파일하면 최종적으로 실행파일이 생깁니다.

컴파일러와 비교하면 어셈블하는 과정은 어셈블리 프로그램을 작성하는 과정을 거친후에 목적프로그램을 생성하므로 과정이 추가된 것처럼 보입니다.
```
