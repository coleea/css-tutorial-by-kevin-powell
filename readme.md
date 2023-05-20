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
        - typography와 관련된 것은 무조건 상속됨