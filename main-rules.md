# Code Rules
개인 프로젝트 진행중 지켜야 할 규칙들

---

## 0. Philosophy
1. 가독성 / 명시성 : 언제 돌아와도 코딩 가능한 코드
2. OOP / 모던 스타일 : 현대에 걸맞는 스타일 가이드

---

## 1. Project set

### Directory

```
src/ : 소스코드
libs/ : 라이브러리
assets/ : 리소스
build/ : 빌드 파일들
docs/ : 문서들

그외 디렉토리 이름 kebab-case 사용
```

### File naming
* PascalCase 사용 - 클래스 이름 그대로

```
// e.g.
Controller.hpp
BackBuffer.cpp
```

---

## 2. Code style

### Naming rules
* PascalCase : 클래스 명, public 멤버, 전역 변수
* camelCase : 함수, public 외 멤버, 지역 변수
* UPPER_SNAKE_CASE : 상수
* 접두사, 접미사 사용 안함

```cpp
const int CONSTANT;
int GlobalVal;

class Class {
public:
    void GetPublic();
    int PublicVal;

protected:
    void getProtect();
    int protectVal;

private:
    void getPrivate();
    int privateVal;
};

int foo() {
    int retVal = 0;
    return retVal;
}
```

### Coding rules

#### Spaces
* O : 조건 / 반복문 괄호 앞
* X : 연산자 앞 뒤, 중괄호 앞

#### Indentation
* Size : 4 spaces (tab X)
* O : 중괄호 내부
* X : 접근 한정자, case 키워드

#### Comment
* 문서 자동화 주석 툴 지향
* 한가지의 주석 스타일 지향
* TODO: 주석 사용, 다른 특수 주석 태그 사용 X

#### ETC
* 중괄호 시작은 선언과 같은 줄에 위치
* 한 줄 조건 / 반복문 : 중괄호 사용 X -> 같은 줄에 위치
* 한 줄 함수 : 한 줄에 위치
* 최대 길이 : 120자

```cpp
/*
@class Class
@brief Counting number
*/ 
class Class {
public:
    int GetEvenCount(int val) {
        if(val < 0) return 0;

        int count = 0;

        while(val >= 0) {
            val /= 2;
            count += 1;
        }
        return count;
    }

    int GetOddCount(int val) {
        // TODO: Implement the odd counter.
    }
};
```
---

## 3. Paradigm
* 라이브러리에서 자료형 제공시, 그것 사용하기 (e.g. GLfloat, XMFLOAT3)
* 쓸데없는 NULL 체크 금지
* SOLID 원칙만큼은 확실히 지키기
