# msys32 좋은듯?

gcc, openssl 등 패키지 관리해 준다  
gcc 구버전 -> vscode debugger에서 array의 주소만 보였음 -> msys32로 gcc 설치 & 해결

## gdb 11.2.0 Issue

vector 사용 시 에러가 있다...

- 2022.2.5) 에러 때문에 visual studio C++ toolset 으로 옮겼다.

$~$

# cout

```cpp
cout << 1; // unexpected result
```

ASCII(1) = SOH 이기 때문에 1을 출력하지 않는다.

```cpp
cout << (int)1; or cout << (string)1;
```

$~$

# Compile Environment

백준 cpp 컴파일 환경과 vscode 컴파일 환경이 다름 -> 다른 동작 가능성 있음  
ex) header 자동 추가 유무 등  
**확실하게 하려면 같은 컴파일 환경에서 체크하자!**

$~$

# out.exe 실행 디렉토리와 input.exe의 디렉토리

```
freopen("input.txt", "r", stdin);
```

- Expected = out.exe 파일 디렉토리 내의 input.txt를 가져온다
- Actual work = 현재 실행하는 디렉토리 내의 input.txt를 가져온다  
   -> ./input.txt 등으로 지정 해야할 듯?

  2022.02.06) 위의 설명은 틀림. vscode launch.json/task.json의 cwd 옵션 디렉토리를 참고하는 것이다

$~$

# 비트 연산자 & | ^

일련의 input에서, n 쌍의 input과 하나의 input이 있을 때 ex) 5 5 3 3 7  
 ^(XOR) 연산자를 이용하면 '7'을 쉽게 구할 수 있다

```C++
int x = 0;
while (~)
 x ^= input;
// x == 7
```

$~$

# VS Code GDB 디버깅

GDB로 디버그 -> output이 버퍼에 걸려서 안 보인다

```cpp
// fastio // fastio는 지운다
setvbuf(stdout, NULL, _IONBF, 0);
```

-> 보인다
