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

## 성능 
```
성능의 두 가지 관점 : 사용자 관점과 관리자(설계자) 관점

사용자 관점에서 성능은 응답시간(실행시간) 즉 컴퓨터가 작업을 완료하기까지 걸리는 시간을 포함하지만
관리자 관점에서의 성능은 처리량(대역폭) 즉 컴퓨터가 단위 시간당 완료하는 작업의 수가 더 중요합니다.

CPU를 더 빠른 버전으로 바꾸면 응답시간을 단축시켜서 처리량이 좋아진다.
하지만 CPU를 여러 개 설치한다 해서 응답시간이 단축되는 것은 아니고 처리량만이 개선된다.

가령 같은 작업을 하는데 A는 10초가 걸리고 B는 15초가 걸린다고 하고
A가 B보다 얼마나 빠르냐고 묻는다면 이 질문은 얼마나 성능이 좋은 지를 묻는 질문이며

1/10 / 1/15 가되어 1.5배 빠르다고 할 수 있다.(정량적인 답변)
시간은 10/15 초가 빠르다.
```

## 성능의 측정
```
시간은 컴퓨터 성능의 가장 기본적인 척도이다.
컴퓨터 성능의 시간이라 하면 사용자 CPU 시간(user CPU time)와 시스템 CPU 시간(system CPU time)으로 나눌 수 있다.
user cpu time은 cpu가 프로그램 실행에 소요된 시간이라 하면 system cpu time은 운영체제가 이 프로그램을 위한 작업을 하기 위해
소비한 시간으로 볼 수 있다.

가령 예를 들어 a+b를 계산하여 c에 저장하고 이 c를 출력하는 프로그램이 있다고 한다면 사용자 cpu 시간은 이 프로그램이 실행되어
c가 출력되는 데까지 걸리는 시간이라 한다면 시스템 cpu 시간은 c를 입출력 명령어를 해석하기 위해 운영체제에 올려져서 운영체제가 소비한 
시간이 되는 것이다. (운영체제 : cpu -> 운영체제 -> memory 창구와 같은 역할을 함)
```

## 클럭사이클
```
클럭의 시간 간격을 클럭 사이클(Clock cycle)이라고 하며 클럭 사이클, 클럭 주기, 클럭 틱, 틱 이라 한다.
클럭 사이클은 한 클럭 사이클에 걸리는 시간이(250ps)나 클럭 속도(4GHz)로 표시한다.
```

## CPU 성능과 성능 인자
```
CPU 성능에만 관심을 갖기로 했으므로 성능 척도는 CPU 실행시간이다.
프로그램 CPU 실행시간 = 프로그램의 cpu 클럭 사이클 수 * 클럭 사이클 시간 = 프로그램의 cpu 클럭 사이클 수 * 1/클럭 속도
```

## 명령어 성능
```
프로그램 수행에 필요한 명령어 수는 실행시간과 관련이 있다.

cpu 클럭 사이클 수 = 명령어 수(CI) * 명령어당 평균 클럭 사이클 수 (CPI)

CPU 실행시간 = 명령어 수(CI) * 명령어당 평균 클럭 사이클 수 (CPI) * 클럭 사이클 시간(1/클럭 속도)
```

## 명령어: 컴퓨터 언어 서론
```
컴퓨터 하드웨어가 알아들을 수 있는 언어에서 단어를 명령어(instruction)라고 하고 그 어휘를 명령어 집합(instruction set)이라고 한다.
MIPS는 1980년대 이후 설계된 명령어 집합들을 대표할 만한 것 중 하나이다.
ARMv7은 MIPS와 유사하다. ARM에서 MIPS로 이동하는 추세이다.
```

## 하드웨어 연산
```
네 변수의 합을 구하는 명령어이다.
add a, b, c <- b와 c의 합을 a에 저장한다.
add a, a, d <- 현재 a의 값과 d의 합을 a에 저장한다.
add a, a, e <- 현재 a의 값과 e의 합을 a에 저장한다.
```

## C 치환문 2개의 번역
```
a = b + c;
d = a - e;
위의 C명령어에서 mips 어셈블리 언어 명령어로의 변환은 컴파일러에 의해 이루어진다.

C컴파일러가 생성한 MIPS 코드를 보여라.

add a, b, c
sub d, a, e

위의 MIPS 명령어 2개로 컴파일된다.
```

## 복잡한 C 치환문의 번역
```
변수가 f, g, h, i, j인 조금 더 복잡한 다음 C문장에 대한 컴파일러 출력 결과를 보여라.

f = (g + h) - (i + j);

g + h 연산의 결과를 저장하기 위해서 컴파일러는 임시 변수 t0를 둔다.

add t0, g, h 

i + j 역시 연산의 결과를 저장하기 위해 임시 변수 t1을 둔다.

add t1, i, j

끝으로 f에 뺄셈 명령어로 결과를 처리한다.

sub f, t0, t1
```

## 피연산자
```
산술 명령어의 피연산자에는 제약이 있다. MIPS 구조에서 레지스터의 크기는 32비트이다.
MIPS에서는 32비트가 한 덩어리로 처리되는 일이 빈번하므로 이것을 워드(word)라고 부른다.

변수에 해당하는 레지스터들은 $s0, $s1 등으로 표기하고 
컴파일 과정에서 필요한 임시 레지스터들은 $t0, $t1 등으로 표기한다.
```

## 레지스터를 사용하여 C 치환문을 번역
```
f = (g + h) - (i + j);

위의 C 프로그램에서 컴파일러가 변수 f, g, h, i, j를 레지스터 $s0, $s1, $s2, $s3, $s4 에 할당했다고 하고
컴파일된 MIPS 코드를 보여라

앞의 예제와 유사하다. 변수 대신에 위에서 말한 레지스터 이름을 사용하고, 임시 변수 대신 임시 레지스터
$t0와 $t1을 사용한다. 달러를 앞에 붙이면 레지스터

add $t0, $s1, $s2
add $t1, $s3, $s4
sub $s0, $t0, $t1
```

## 메모리 피연산자를 사용하는 치환문의 번역
```
A는 100워드 짜리 배열이고 변수 g, h는 레지스터 $s1, $s2에 각각 할당되었다고 가정
배열 A의 시작주소가 $s3에 기억되어있다고 할 때 다음 C문장을 컴파일하라.

g = h + A[8];

피연산자 중에 A[8] 배열은 메모리에서 레지스터로 옮긴 후 연산을 시작해야 한다.

lw $t0, 8($s3) // lw (load word : 메모리에서 레지스터로 피연산자를 옮기는데 A배열의 시작주소 $s3에 인덱스 8을 더한값 여기서 인덱스는 잘못되었음)

add $s1, $s2, $t0
```

## 정렬 제약
```
MIPS에서 워드의 시작 주소는 항상 4의 배수가 되어야 한다. 따라서 앞의 코드에서
바이트 주소를 제대로 구하려면 베이스 레지스터 $s3에 변위 4*8 = 32를 더해야한다.

적재와 반대로 레지스터에서 메모리로 데이터를 보내는 명령을 저장(store)라고 한다.

적재와 저장을 사용한 번역

A[12] = h + A[8]

변수 h가 레지스터 $s2에 할당되어 있으며 배열 A의 시작 주소는 $s3에 들어있다고 가정한다.

먼저 A[8]의 정확한 베이슽스 레지스터는 4*8 32가 된다.

따라서 lw $t0, 32($s3), add $t0 $s2, $t0,

마지막 명령어는 48을 변위로 $s3을 베이스 레지스터로 사용하여 합을 A[12]에 저장한다.

sw $t0, 48($s3)
```

## 판단을 위한 명령어
```
beq register1, register2, L1 : register1와 register2가 같으면 L1에 해당하는 문장으로
bne register1, register2, L2 : register1와 register2가 같으면 L2에 해당하는 문장으로
```

## if then else를 조건부 분기로 번역
```
if(i == j) f = g + h; else f = g - h;

f, g, h, i, j는 변수이고 레지스터 $s0 ~ $s4에 해당한다.

bne $s3, $s4, Else
add $s0, $s1, $s2
j Exit
Else: sub $s0, $s1, $s2
Exit:
```

## while 순환문의 번역
```
while(save[i] == k)
  i += 1;

i와 k는 레지스터 $s3와 $s5에 할당 배열 save의 시작 주소가 $s6에 저장

Loop: sll $t1, $s3, 2
add $t1, $t1, $s6
lw $t0, 0($t1)
bne $t0, $s5, Exit
addi $s3, $s3, 1
j Loop
Exit:
```

## 다른 프로시저를 호출하지 않는 C 프로시저의 컴파일
```
스택에 푸쉬할때는 $sp 값을 감소시켜야하고 스택에 팝할때는 $sp 값을 증가시켜야함

int leaf_example (int g, int h, int i, int j)
{
  int f;
  
  f = (g + h) - (i + j);
  return f;
}

인수 g, h, i, j는 인수 레지스터 $a0, $a1, $a2, $a3에 해당하고 
f는 $s0에 해당한다.

leaf_example: addi $sp, $sp, -12 // 프로시저호출하면서 스택포인터에 3개의 공간을 만듬(푸쉬)
sw $t1, 8($sp) // $t1을 위한 공간 8번째 변위에 저장
sw $t0, 4($sp) // $t0를 위한 공간 4번째 변위에 저장
sw $s0, 0($sp) // 인수의 계산 결과값을 저장하는 $s0를 위한 공간 0번째 변위에 저장

add $t0, $a0, $a1 
add $t1, $a2, $a3
sub $s0, $t0, $t1

add $v0, $s0, $zero // 결과값 레지스터 v0에 결과값 f를 저장

스택에 저장한 값들을 빼내서 레지스터를 원상복구 (팝 -> sp값 증가)

lw $s0, 0($sp) // 나중에 들어간 것부터 빼내기
lw $t0, 4($sp) 
lw $t1, 8($sp)
addi $sp, $sp, 12 // 스택 포인터 증가

jr $ra // 복귀 주소를 사용하는 점프 명령으로 끝낸다.
```
