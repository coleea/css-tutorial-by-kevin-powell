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

- 레이아웃 밖으로 엘리먼트가 튀어나오는 원인
    - width나 height를 고정 px로 사용했기 때문
        예) 150px, 300px
        