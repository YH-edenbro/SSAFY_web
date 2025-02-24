# CSS(Cascading Style Sheet)
- 웹 페이지의 디자인과 레이아웃을 구성하는 언어

## CSS 구문
```
h1 {
    color: red;
    font-size: 30px;
}
```
- h1 선택자(Selector)
- color: red; 선언(Declaration) 
- font-size 속성(Property)
- 30px 값(Value)

# CSS 적용 방법

1. 인라인(Inline) 스타일
2. 내부(Internal) 스타일 시트
3. 외부(External) 스타일 시트

### 1. 인라인(Inline) 스타일
- HTML 요소 안에 style 속성 값으로 작성

### 2. 내부(Internal) 스타일 시트
- head 태그 안에 style 태그에 작성
- 학습 과정에서 주로 사용

### 3. 외부(External) 스타일 시트
- 별도 CSS 파일 생성 후 HTML link 태그를 사용해 불러오기

## CSS 선택자

### CSS Selectors
- HYML 요소를 선택하여 스타일을 적용할 수 있도록 하는 선택자

### CSS Selectors 종류

- 기본 선택자
    - 전체(*) 선택자
    - 요소(tag) 선택자
    - 클래스(class) 선택자
    - 아이디(id) 선택자
    - 속성(attr) 선택자 등

- 결합자 (Combinators)
    - 자손 결합자 (" " (space) )
    - 자식 결합자 (">")

### CSS Selectors 특징

- 전체 선택자 (*)
    - HTML 모든 요소를 선택

- 요소 선택자
    - 지정한 모든 태그를 선택

- 클래스 선택자 ('.' (dot))
    - 주어진 클래스 속성을 가진 모든 요소를 선택

- 아이디 선택자 ('#')
    - 주어진 아이디 속성을 가진 요소 선택
    - 문서에는 주어진 아이디를 가진 요소가 하나만 있어야 함

### CSS 결합자 특징

- 자손 결합자 (" " (space))
    - 첫 번째 요소의 자손 요소들 선택
    - 예) p span은 < p > 안에 있는 모든 < span >를 선택 (하위 레벨 상관 없이)

- 자식 결합자 (">")
    - 첫 번째 요소의 직계 자식만 선택
    - 예) ul > li은 < ul > 안에 있는 모든 < li >를 선택 (한단계 아래 자식들만)

## 명시도

### 명시도(Specificity)
- CSS Selector에 가중치를 계산하여 어떤 스타일을 적용할지 결정
- 돌일한 요소를 가리키는 2개 이상의 CSS 규칙이 있는 경우 가장 높은 명시도를 가진 Selector가 승리하여 스타일이 적용됨

### Cascade(계단식)
- 한 요소에 동일한 가중치를 가진 선택자가 적용될 때 CSS에서 마지막에 나오는 선언이 사용됨

### 명시도가 높은 순
1. Importance
    - **!important**
2. Inline 스타일
3. 선택자 (더 좁은 범위의 선택이 명시도가 더 높다)
    - id 선택자 > class 선택자 > 요소 선택자
3. 소스 코드 선언 순서

---> class선택자를 99%를 사용하여 명시도를 명료하게
### !important
- 다른 우선순위 규칙보다 우선하여 적용하는 키워드
    - Cascade의 구조를 무시하고 강제로 스타일을 적용하는 방식이므로 사용을 권장하지 않음

### CSS 상속
- 기본적으로 CSS는 상속을 통해 부모 요소의 속성을 자식에게 상속해 재사용성을 높임

### CSS 속성 2가지 분류
- 상속 되는 속성
    - Text 관련 요소(font, color, text-align), opacity, visibility 등

- 상속 되지 않는 속성 (레이아웃-배치)
    - Box model 관련 요소(width, height, border, box-sizing ...)
    - position 관련 요소(position, top/right/bottom/left, z-index) 등

### CSS 상속 여부 확인
- MDN의 각 속성별 문서 하단에서 상속 여부를 확인할 수 있음

## CSS Box Model
- 웹 페이지의 모든 HTML 요소를 감싸는 사각형 상자 모델

### 원은 네모 박스를 깎은 것

### 박스 타입
1. Block box (아래)
2. Inline box (오른쪽)

-> 박스 타입에 따라 페이지에서의 배치 흐름 및 다른 박스와 관련하여 박스가 동작하는 방식이 달라짐

### 박스 표시(Display) 타입
1. Outer display type
    - 
    - Block & Inline
    - 박스가 문서 흐름에서 어떻게 동작할지를 결정
    - 속성
        - **block, inline**
- **block의 특징**
    - 항상 새로운 행으로 나뉨
    - width와 height 속성 사용 가능
    - padding, margin, border로 인해 다른 요소를 상자로부터 밀어냄
    - width 속성을 지정하지 않으면 박스는 inline 방향으로 사용 가능한 공간을 모두 차지함
        - 상위 컨테이너 너비 100%로 채우는 것
    - 대표적인 block 타입 태그
        - h1~6, p, div
- **inline의 특징**
    - 새로운 행으로 넘어가지 않음
    - width와 height 속성을 사용할 수 없음
    - 수직 방향
        - padding, margin, border가 적용되지만 다른 요소를 밀어낼 수는 없음
    - 수평 방향
        - padding, margins, borders가 적용되어 다른 요소를 밀어낼 수 있음
    - 대표적인 inline 타입 태그
        - a, img, span, strong, em
2. Inner display type
    -
    -

### Normal flow
- 일반적인 흐름 또는 레이아웃을 변경하지 않은 경우 웹 페이지 요소가 배치되는 방식