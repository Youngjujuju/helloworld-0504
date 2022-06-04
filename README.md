# 리눅스 명령어와 vim 에디터

#### 목차
+ 리눅스 명령어
  + top
    + 사용방법
    + top 단축키 명령어
  + ps
    + 사용방법
  + jobs
    + 사용방법
  + kill
    + 사용방법
    
+ vim 에디터
  + 매크로 사용방법
    + 이동
    + 편집 (삽입, 삭제, 수정, 복사, 붙여넣기 등)
    + 선택
    + 검색
    
## top
### 사용방법

**top [옵션]**
> -b : 배치모드로 정보를 출력한다. 실시간 상화 대화형모드로 정보를 화면에 일렬로 출력한다.
>
> -d delay : 지정한 시간(delay 초)의 간격으로 정보를 업데이트하여 출력한다.
> 
> -i idle : 토글값이 off일 때, idle 프로세스나 좀비 프로세스 정보를 출력하지 않는다.
> 
> -n num : 지정한 시간(num)만큼 업데이트 정보를 출력한다.
> 
> -p pid : 지정한 프로세스 ID(pid)의 정보만을 출력한다.
>
> -q : 시간의 간격 없이 계속하여 업데이트 정보를 출력한다.
>
> -s : 몇 개의 대화식 명령을 비활성화한다(시큐어 모드).
>
> -S : 누적된 정보를 출력한다(cumulative 모드).

### top 단축키 명령어

|명령어|설명|
|:---:|:---|
|space|정보를 업데이트한다.|
|^L|스크린을 다시 초기화한다.|
|F or f|필드를 추가나 제거한다.
|O or o|출력하는 필드의 정렬 순서를 변경한다.|
|h or ?|사용 가능한 명령어를 출력한다.|
|k|프로세스를 종료시킨다.|
|n or #|출력할 프로세스의 수를 지정한다.|
|s|출력할 정보의 업데이트 시간을 지정한다.|
|W|~/.toprc에 설정된 내용을 저장한다.|
|q|top을 종료한다.|

## ps
### 사용방법

**ps [옵션]**

*전체 프로세스와 관련된 옵션*
> -A : 모든 프로세스를 출력한다.
> 
> -N : -A 옵션과 비슷하나 ps 프로세스를 제외하고 출력한다.
> 
> -a : 세션 리더 및 터미널에 속하지 않는 프로세스를 제외하고 출력한다.
> 
> -d : 세션 리더를 제외한 모든 프로세스를 출력한다.
> 
> -e : 커널 프로세스를 제외한 모든 프로세스를 출력한다.

> T : 현재 터미널에서의 모든 프로세스를 출력한다.
> 
> a : 현재 터미널의 사용자 고유 프로세스를 출력한다.
> 
> r : 현재 실행 중인 프로세스를 출력한다.
> 
> x : 터미널이 없는 프로세스를 출력한다.
> 
> --deselect : -N 옵션과 같다.

*특정 프로세스를 선택하여 보여주는 옵션*
> -C : 지정한 명령어의 이름에 관련된 정보를 출력한다.
> 
> -G : 그룹 ID에 관련된 정보를 출력한다(이름도 지원).
> 
> -U : 사용자 ID에 관련된 정보를 출력한다(이름도 지원).
> 
> -g : 지정한 세션 리더 혹은 그룹명에 관련한 정보를 출력한다.
> 
> -p : 프로세스 ID를 출력한다.

> -s : 세션에 속한 프로세스를 지정한다.
> 
> -t : tty를 지정한다.
> 
> -u : 사용자 ID를 지정한다(이름도 지원).
> 
> U : 지정한 사용자의 프로세스를 출력한다.
> 
> p : 프로세스 ID를 지정한다.
> 
> t : tty를 지정한다.

> --Group : 실제 그룹 이름이나 ID를 지정한다.
> 
> --User : 실제 사용자 이름이나 ID를 지정한다.
> 
> --group : 유효 사용자 이름이나 ID를 지정한다.
> 
> --pid : 프로세스 ID를 지정한다.
> 
> --sid : 세션 ID를 지정한다.

> --tty : 터미널을 지정한다.
> 
> --user : 유효 사용자 이름이나 ID를 지정한다.
> 
> -123 : --sid 123과 같은 의미이다.
> 
> 123 : --pid 123과 같은 의미이다.

*출력 결과 필드를 제어하는 옵션*
> -0 : PID, TTY, STAT, TIME, COMMAND 등의 필드 목록을 출력한다.
> 
> -c : PID, CLS, PRI, TTY, TIME. CMD 등의 필드 목록을 출력한다.
> 
> -f : UID, PID, PPID, C, STIME, TTY, TIME, CMD 등의 필드를 CMD 필드의 전체 명령어 형태로 출력한다.
> 
> -j : PID, PGID, SID, TTY, TIME, CMD 등의 필드 목록을 출력한다.
> 
> -l : F, S, UID, PID, PPID, C, PRI, NI, ADDR, SZ, WCHAN, TTY, TIME, CMD 필드의 상세 정보를 출력한다.

> -o : 사용자가 정의한 포맷을 지정한다.
> 
> -y : -l 이나 l 옵션과 함께 ADDR 필드를 RSS 필드로 출력한다.
> 
> 0 : PID, TTY, STAT, IME COMMAND 필드 정보를 출력한다.
> 
> X : PID, STACKP, ESP, EIP, TMOUT, ALARM, STAT, TTY, TIME, COMMAND 필드의 정보를 리눅스 i386 레지스터 형식으로 출력한다.

> j : PPID, PID, PGID, SID, TTY, TPGID, STAT, UID, TIME, COMMAND 필드의 정보를 작업 제어에 관련된 형식으로 출력한다.
> 
> l : F, S, UID, PID, PPID, C, PRI, NI, ADDR, SZ, PSS, WCHAN, TTY, TIME, CMD 필드의 정보를 출력하고 -l 옵션과 함께 PSS 필드를 추가하여 출력한다.

> o : 사용자 지정 형식으로 출력한다.
> 
> s : UID, PID, PENDING, BLOCKED, IGNORED, CAUGHT, STAT, TTY, TIME, COMMAND 필드의 정보를 출력한다.
> 
> u : USER, PID, %CPU, %MEM, VSZ, RSS, TTY, STAT, START, TIME, COMMAND 필드의 정보를 출력한다.
> 
> v : PID, TTY, STAT, TIME, MAJFL, TRS, DRS, RSS, %MEM, COMMAND 필드의 정보를 출력한다.
> 
> --format : 사용자 지정 형식으로 출력한다.

*출력 필드의 내용을 변경하는 옵션*
> -H : 프로세스를 계층형으로 출력한다.
> 
> -m : 스레드 정보를 출력한다.
> 
> -n namelist : 시스템 이름 리스트 파일(namelist)을 지정한다.
> 
> -w : 너비에 맞게 잘려진 내용을 제한이 없는 너비의 내용으로 상세하게 출력한다.

> --cols : 스크린의 너비를 설정한다.
> 
> --columns : 스크린의 너비를 설정한다.
> 
> --cumulative : 죽은 자식 프로세스 데이터를 포함하여 출력한다.
> 
> --forest : 아스키 문자의 프로세스 트리 형태로 출력한다.
> 
> --html : HTML 이스케이프로 출력한다.

> --headers : 헤더 라인을 반복한다.
> 
> --no-headers : 헤더를 보이지 않는다.
> 
> --lines : 스크린의 높이를 설정한다.
> 
> --rows : 스크린의 높이를 설정한다.
> 
> --sort : 정렬 방식을 지정한다. --sort＝[+|-]key[,[+|-]key[,···] 형식으로 여기서 사용할 수 있는 키(key)는 예제에서 설명한다. 예를 들어 ps jax --sort＝uid,-ppid,+pid 형식으로 지정할 수 있다.

> C : CPU 시간을 이용한다.
> 
> N : 지정한 시스템 이름의 리스트 파일을 사용한다.
> 
> O : 정렬 순서 지정하기 위한 옵션으로 O[+|-]K[,[+|-]K[,···]]의 형식으로 지정한다. K는 예제로 설명한다. +는 오름차순 정렬, –는 내림차순 정렬이다.

> S : 죽은 자식 프로세스의 데이터를 포함한다.
> 
> c : 시스템 내부에 보관 중인 명령어 이름을 출력한다.
> 
> e : 명령어에 대한 매개 변수와 함께 환경 변수를 출력한다.
> 
> f : 아스키(*) 아트로 프로세스 트리를 출력한다.

> h : 헤더 라인은 출력하지 않는다.
> 
> m : 모든 스레드 정보를 출력한다.
> 
> n : WCHAN과 USER 필드를 숫자 값으로 출력한다.
> 
> w : 필드의 너비에 맞게 잘려진 내용을 너비보다 상세하게 출력한다.

> --cols : 스크린의 너비를 설정한다.
> 
> --columns : 스크린의 너비를 설정한다.
> 
> --cumulative : 죽은 자식 프로세스 데이터를 포함한다.
> 
> --forest : 아스키 아트의 프로세스 트리를 출력한다.
> 
> --html : HTML 이스케이프를 출력한다.
> 
> --headers : 헤더 라인을 반복한다.

> --no-headers : 헤더를 출력하지 않는다.
> 
> --lines : 스크린의 높이를 설정한다.
> 
> --rows : 스크린의 높이를 설정한다.
> 
> --sort : 지정한 정렬 방식으로 출력한다.
> 
> --sort＝[+|-]key[,[+|-]key[,···] 형식이다. 여기서 사용할 수 있는 키(key)는 설명 및 예제에서 설명한다. 예를 들어 ps jax --sort＝uid,-ppid,+pid 형식으로 할 수 있다.

*프로그램의 정보*
> -V : 버전 정보를 출력한다.
> 
> L : 모든 형태의 지시자를 출력한다.
> 
> V : 버전 정보를 출력한다.
> 
> --help : 사용법을 출력한다.
> 
> --info : 디버깅 정보를 출력한다.
> 
> --version : 버전 정보를 출력한다.

## jobs
### 사용방법

**jobs [옵션]**

**jobs -x command [args]**
> -l : 프로세스 그룹 ID를 state 필드 앞에 출력한다.
> 
> -n : 프로세스 그룹 중에 대표 프로세스 ID를 출력한다.
> 
> -p : 각 프로세스 ID에 대해 한 행씩 출력한다.
> 
> command : 지정한 명령어를 실행한다.

## kill
### 사용방법

**kill [-s시그널][-a]pid**

**kill-l [시그널]**

> pid ··· : 종료시킬 프로세스 ID나 프로세스 이름을 지정한다.
> 
> -s : 전달할 시그널의 종류를 지정한다. 여기에는 시그널 이름이나 번호를 써준다.
> 
> -l : 시그널로 사용할 수 있는 시그널 이름들을 보여준다. 이것은 /usr/include/linux/signal.h 파일에서도 알 수 있다.
> 
> -1, : -HUP 프로세스를 재활성화한다.
> 
> -9 : 프로세스를 강제로 종료시킨다.

## 매크로 사용방법

### q

> `q{레지스터}` 로 매크로 기록 시작
> 
> `q` 로 매크로 기록 종료

### @
### 이동

**기본 이동**

> h, j, k, l: 좌,하,상,우 커서 이동
> 
> -: 줄의 처음 위치로 커서 이동
> 
> gg: 맨 위로 커서 이동
> 
> [shift + g]: 맨 아래로 커서 이동

**단어 단위로 이동**

> w: 단어의 시작 위치로 커서 이동 (forward 방향)
>> Ex. 3w: 세 단어 앞으로 커서 이동
>
> e: 단어의 마지막 위치로 커서 이동 (forward 방향)
> 
> b: 단어의 시작 위치로 커서 이동 (backward 방향)
> 
> ge: 단어의 마지막 위치로 커서 이동 (backward 방향)

**한 문장 내에서의 이동**

> 0(숫자): 라인 맨 앞으로 커서 이동
> 
> ^: 문장 맨 앞으로 커서 이동
> 
> $: 문장 맨 뒤로 커서 이동

**대략적인 위치로 이동 (현재 보이는 페이지 기준)**

> [shift + h]: 현재 보이는 페이지를 기준으로 맨 위로 커서 이동
> 
> [shift + m]: 현재 보이는 페이지를 기준으로 중간 라인으로 커서 이동
> 
> [shift + l]: 현재 보이는 페이지를 기준으로 맨 아래로 커서 이동

**페이지 이동**

> [ctrl+ f]: 다음 페이지의 첫 줄로 커서 이동
> 
> [ctrl+ b]: 다음 페이지의 마지막 줄로 커서 이동
> 
> [ctrl+ d]: 페이지의 절반 크기만큼 아래로 커서 이동
> 
> [ctrl+ u]: 페이지의 절반 크기만큼 위로 커서 이동

**원하는 줄 번호로 한 번에 이동**

> 줄 번호 설정 및 해지
>> [: + set number]: 줄 번호 설정
>> 
>>[: + set nonumber]: 줄 번호 설정

> 방법1
>> 1) [esc] 를 눌러 표준 모드로 진입
>> 
>> 2) [:] 를 누른 후 원하는 [줄 번호] 입력

> 방법2
>> 1) [esc] 를 눌러 표준 모드로 진입
>> 
>> 2) 원하는 [줄 번호] 입력
>> 
>> 3) [shift + g] 입력

**{}(컬리 블레이스, Curly Brace)을 기준으로 이동**

> ]]: {로 커서 이동 (forward 방향)
>> 없으면 페이지의 맨 아래로 커서 이동
>> 
>> {은 가장 상위의 블록을 감싸고 있는 문자만 찾는다.

> [[: {로 커서 이동 (backward 방향)
> 
> ][: }로 커서 이동 (forward 방향)
>> 없으면 페이지의 맨 위로 커서 이동
>> 
>> }은 가장 상위의 블록을 감싸고 있는 문자만 찾는다.

> []: }로 커서 이동 (backward 방향)
> 
> %: {}나 ()에서 현재 괄호의 짝으로 커서 이동

### 편집 (삽입, 삭제, 수정, 복사, 붙여놓기 등)

**삽입 관련 단축키 (입력 가능한 상태로 변경)**

> i: 현재 커서가 위치한 문자의 앞에 Insert 하기
>
> I: 현재 커서가 위치한 줄 맨 앞에 Insert 하기
>
> a: 현재 커서가 위치한 문자의 뒤에 Insert 하기
>
> A: 현재 커서가 위치한 줄 맨 뒤에 Insert 하기
>
> O: 현재 커서가 위치한 줄 바로 윗줄에 Insert 하기
>
> o: 현재 커서가 위치한 줄 바로 아랫줄에 Insert 하기

**삭제/잘라내기 및 수정 관련 단축키**

> dd: 커서가 위치한 줄 잘라내기
> 
> dw: 커서가 위치한 곳부터 단어의 마지막까지 잘라내기
>> Ex. 숫자 + dd: 커서가 위치한 줄부터 숫자에 해당하는 수만큼의 줄 잘라내기

> [shift + d]: 현재 커서의 위치부터 줄의 끝까지 잘라내기
>
> x: 커서가 위치한 문자 잘라내기
> 
> [shift + x]: 커서가 위치한 문자 바로 앞에 있는 문자 잘라내기
>
> s: 커서가 위치한 문자 잘라내고 Insert 하기
> 
> cc 또는 [shift + s]: 커서가 위치한 줄 전체 잘라내고 Insert 하기
> 
> cw: 커서가 위치한 곳부터 단어의 마지막까지 잘라내고 Insert 하기
> 
> [shift + c]: 현재 커서의 위치부터 줄의 끝까지 잘라내고 Insert 하기
>
> [r + 변경할 문자]: 커서가 위치한 문자 하나 수정하기
>> Ex. 4rx: 현재 커서 이후 4개의 글자를 “x”로 수정한다.

**복사/붙여넣기 관련 단축키**

> yl: 현재 커서가 위치한 문자 하나만 복사하기
>> Ex. 3yl: 현재 커서 이후 3개의 문자를 복사한다.
>
> yy: 현재 커서가 위치한 줄 복사하기
> 
> yw: 현재 커서의 위치부터 단어가 끝나는 위치까지 복사하기
> 
> y: 블럭 단위로 체크한 내용(비주얼 모드 이용) 복사하기 - 한 문자만 복사 X
>> Ex. 숫자 + y: 커서가 위치한 줄부터 숫자에 해당하는 수만큼의 줄 복사하기
>>
>> Ex. y$: 커서가 위치한 곳부터 줄의 마지막까지 복사하기
>
> p:
>> 단어 복사: 현재 커서가 위치한 바로 다음 위치에 붙여넣기
>> 
>> 행 복사: 현재 커서가 위치한 줄 바로 아랫줄에 붙여넣기
>
> [shift + p]:
>> 단어 복사: 현재 커서가 위치한 바로 앞 위치에 붙여넣기
>
>> 행 복사: 현재 커서가 위치한 줄 바로 윗줄에 붙여넣기
>
> 숫자 + p: 해당 숫자 만큼 붙여넣기를 반복하기

### 선택

**한 줄 선택**

> [shift + v]: 라인 단위로 블럭지정이 가능하다.

**단어 단위로 여러 줄 선택**

> 1) [esc] 를 눌러 표준 모드로 진입
> 
> 2) v 를 눌러 여러 줄을 선택할 수 있는 상태를 만든다.
>> v: 단어 단위
>>
>> [shift + v]: 라인 단위

**멀티 포커스**

> [ctrl + v]: 블럭 단위로 여러 줄 선택. 즉, 사각형의 블럭지정이 가능하다.

### 검색

> / + 찾을 단어 + Enter: 문서에서 단어 찾기
>> n 또는 *: 다음 찾기 (forward 방향)
>> 
>> N 또는 #: 이전 찾기 (backward 방향)
