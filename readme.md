# CSS Demystified: Start Writing CSS with Confidence (Module 1-3)

## Overlooked Fundamental 1: The box model

- A quick word on setting heights
    - height를 고정값으로 설정하는 건 대단히 위험한 일이다
        - width가 좁은 기기를 사용하면 overflow가 발생하기 때문
        - 항상 height가 늘어날 수 있다는 사실을 염두해 두어야 함
        - 그러므로 height 대신 min-height를 사용하는 것이 나음
        - height를 늘리고 싶으면 위아래로 패딩을 추가하는것이 나음
- 상속
    - 상속의 절대적인 규칙
        - typography와 관련된 것은 대부분 상속됨
            - 예) font-size, color
        - 모든 엘리먼트는 html엘리먼트의 스타일을 상속받음
        - 레이아웃에 관련된 `어떤것도` 상속되지 않음
            - 예) margin, padding, height
        - 주로 유저인풋, form과 관련된 엘리먼트의 요소는 상속되지 않음
            - textarea
            - input
            - optgroup
            - select
            - button

---

- html에서 1em의 기본크기
    - 대부분의 브라우저에서 16px로 설정되어 있음
    - 16 * 1.125 = 18px인데 16px보다 18px을 더 선호하는 경우가 있기 때문에 `html { font-size : 1.125rem}` 등을 설정하는 것

```
10px = 0.625rem
12px = 0.75rem
14px = 0.875rem
16px = 1rem (base)
18px = 1.125rem
20px = 1.25rem
24px = 1.5rem
30px = 1.875rem
32px = 2rem
```

- 접근성 이슈
    - 크롬의 settings에서 폰트 크기를 large로 설정한 경우
        - 폰트사이즈가 16px -> 20px로 증가함
    - 크롬의 settings에서 폰트 크기를 very large로 설정한 경우
        - 폰트사이즈가 16px -> 24px로 증가함
    - 크롬의 settings에서 폰트 크기를 small 로 설정한 경우
        - 폰트사이즈가 16px -> 12px로 감소함
    - 크롬의 settings에서 폰트 크기를 very small 로 설정한 경우
        - 폰트사이즈가 16px -> 10px로 감소함
    - 결론 : very small을 제외하면 4px단위로 rem값이 변경됨
- em
    - 가장 오해하기 쉬운 단위
    - font-size와 그 밖의 다른 요소에 따라서 참조하는 값이 달라짐
    - font-size에 em을 기입하면 부모 폰트사이즈를 기준으로 배율을 계산함
    - 그밖에 margin, padding, width 등에 em을 기입하면 현재 엘리먼트의 폰트 사이즈 기준으로 배율을 계산함
- em을 사용하는 이유
    - 가장 큰 이유는 접근성 때문
    - 모바일 기기 또는 브라우저의 설정에 따라서 rem값이 20px, 24px등으로 변경되는데 이 떄 div 요소를 고정 픽셀로 설정하면 전체적인 픽셀 크기의 배율이 rem에 따라 움직이지 않게됨
    - 즉 사용자가 대화면으로 보는것을 선호함에도 불구하고 그것이 화면에 반영되지 않게됨


- 레이아웃 밖으로 엘리먼트가 튀어나오는 원인
    - width나 height를 고정 px로 사용했기 때문
        - 예) 150px, 300px
        - width 또는 height를 고정픽셀로 사용하는 것은 위험함
        - 특히 height를 고정픽셀로 사용하면 위험한 이유는 모바일 기기의 width 폭이 좁기 때문에 십중팔구 레이아웃이 튀어나오기 때문
        - 또한 90vw같은 단위를 사용하는 것도 레이아웃 튀어나옴의 원인이 될 수 있음
        
- 단위를 적지 않으면 발생하는 일
    - line-height : 폰트 크기에 대해 상대적인 값으로 해석된다. 이것은 font-size의 em과 비슷하다
    - font-size : 단위를 적지 않으면 유효하지 않은 값이며 브라우저에서 무시한다
    - width : 유효하지 않은 값이며 브라우저에서 무시한다
    - margin : 유효하지 않은 값이며 브라우저에서 무시한다

- z-index
    - z인덱스의 값은 정수만 허용됨. 1.1은 유효하지 않은 값이므로 반영되지 않음
    - z인덱스가 적용되려면 position이 static외의 값으로 지정되어야 함. position이 지정되지 않으면 z인덱스 값이 무시됨
    - 대부분의 html요소의 포지션은 기본값이 static이므로 별도의 포지션을 지정하지 않는다면 z-index가 작동하지 않음    
    - z인덱스에서 -99999999999999는 유효한 값으로 해석됨

- position
    - dialog를 제외한 모든 html element의 기본 position은 static
    - dialog의 position은 크롬과 파이어폭스에서 absolute이며 display는 none
    - 이는 dialog가 모달을 구현하기 위한 요소이기 때문
    - static은 일반적인 flow에 따라 배치됨
    - 그 외의 포지션은 일반적인 플로우에서 벗어남

- width와 height
    - 음수 값을 허용하지 않음

- line-height
    - -1을 입력하면 유효하지 않은 값으로 인식하여 값을 무시함
    - 0은 유효한 값

- margin, padding, border-width
    - 음수 값을 허용하지 않음

- opacity값은 0~1사이의 실수가 유효한 값
    - 하지만 9999 또는 -9999도 유효한 값으로 인식됨
    - 이는 값이 clamp되기 때문
    - 9999를 입력하면 1로 클램프 됨

- 값이 auto인 경우
    - width와 height : 컨텐츠에 따라 너비와 높이가 자동으로 계산됨
    - margin: auto 값이 주어지면, 브라우저는 가능한 한 동일한 마진을 가지도록 요소를 수평 가운데 정렬하려고 합니다. 이는 블록 레벨 요소에 대해서만 작동하며, 요소가 display: flex나 display: grid 등의 값을 가진 컨테이너 내부에 있을 때에는 다르게 작동할 수 있습니다.
    - left, right, top, bottom: 이 속성들은 position이 absolute 또는 fixed인 요소에서 사용되며, auto 값이 주어지면 브라우저는 요소를 자동으로 위치시키려고 시도합니다. 이때 위치는 주로 부모 요소나 다른 관련된 요소에 의해 결정됩니다.
    - overflow: auto 값이 주어지면, 브라우저는 요소의 내용이 그 경계를 넘어갈 경우 스크롤바를 자동으로 보여줍니다.


- 기본값이 display : block인 엘리먼트 리스트
    - 기타등등
    - div : 일반적인 블록 요소
    - p>: 단락
    - h1 ~ h6: 제목
    - ol : 정렬된 목록
    - ul : 정렬되지 않은 목록
    - li : 목록 아이템 (그러나 이 요소는 보통 display: list-item이라는 고유한 값을 가집니다. 이 값은 display: block과 비슷하게 작동하지만, 추가로 목록 마커를 생성합니다)
    - dl : 정의 목록
    - dt : 정의 목록의 용어
    - dd : 정의 목록의 설명
    - pre : 미리 서식을 지정한 텍스트
    - address : 연락처 정보
    - blockquote : 긴 인용구
    - form : 입력 양식
    - hr : 수평 줄
    - table : 표
    - fieldset : 폼 필드 세트
    - noscript : 스크립트를 지원하지 않는 경우에 표시될 내용
    - section : 섹션 (HTML5)
    - article : 기사 (HTML5)
    - aside : 사이드바 (HTML5)
    - nav : 네비게이션 링크 (HTML5)
    - figure : 독립적인 콘텐츠 (HTML5)
    - figcaption : 그림 캡션 (HTML5)
    - header : 헤더 (HTML5)
    - footer : 푸터 (HTML5)
