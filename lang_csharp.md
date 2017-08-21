# C# 문법

## 주석 (Comments)
- `//` : 한줄 주석
- `/* ~ */` : 범위 주석

## 변수
- datatype
  - int
  - float / double
  - char / string
  - bool
- var : 선언시 추론하여 바인딩 (선언시 값을 지정해야함)

## 상수
- 타입 앞에 `const` 키워드 사용
- 선언시 초기화 해야함

## 연산자 (Operater)
- 사칙 연산자 : + - * /
- 나머지 연산 : %
- 복합 연산자 : +=, -=, ...
- 증감 연산자 : ++, --
- 비교 연산자 : >, <, <=, >=, !=

## 조건문
### if ( 조건식 ) { 코드 }
  - if () {} else {}
### switch () case {}
  - case ?: break;

## 반복문
### for
### foreach

## 배열

## 접근 제어
### public
### private


## 비주얼 스튜디오 C# Console Application 프로젝트

### 기본 코드
```cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace HelloCSharp {
   class Program {
      static void Main(string[] args) {
        // 콘솔 프로그램은 Main 메소드에서 시작
      }
   }
}
```

### 표준 출력

- `Console.WriteLine`메소드 사용

```cs
static void Main(string[] args) {
  Console.WriteLine( [출력할내용] );
  /* 포멧 스트링 */
  Console.WriteLine( "x = {0}; y = {1}", x, y);
}
```

### 표준 입력

- `Console.ReadLine`메소드 사용

```cs
static void Main(string[] args) {
  string yourName;
   Console.WriteLine("What is your name?");
   yourName = Console.ReadLine();
   Console.WriteLine("Hello {0}", yourName);
}
```

- `Convert.to[타입]` 메소드로 변환

```cs
static void Main(string[] args) {
  int age = Convert.ToInt32(Console.ReadLine());
  Console.WriteLine("You are {0} years old", age);
}
```
- 변환 타입 (기본 String)
  - 정수형 : .ToInt16 , .ToInt32 , .ToInt64
  - 실수형 : .ToFloat , .ToDouble
  - 논리형 : .ToBoolean
