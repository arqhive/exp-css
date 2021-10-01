# CSS Guideline (MDN)

1. shorthand 보다 longhand를 선호
2. attribute 주위에는 큰 따옴표를 사용
3. CSS function 파라미터는 컴마 공백으로
4. !important 사용 금지
5. border: none; 보다 border: 0;
6. 모바일 우선 미디어 쿼리 사용 (작은 것에서 큰 것으로)
7. ID Selector를 쓰지 말것 (덜 유연하고 클래스보다 특이성이 높이 때문에 재사용이 어려움)
8. , 여러 element를 선택시 줄을 바꿀것


# 좋은 습관
- semantic 하게 스타일을 작성하자
- 종속성을 최대한 제거하자
- 코드를 유연하게 (container가 width를 제어하고 contents가 height를 제어하도록)
- Grid를 사랑하자
- 셀렉터의 사용을 최소화 하자 (읽기가 어려워 진다.)
- 여러개의 클래스로 나누어 확장성을 도모하자

# 나쁜 습관
- 의존적 스타일을 피할것 .class p
- element selector를 사용하지 말것
- 높이를 고정 시킨 상태에서 정렬을 피할 것
- 중복을 발생시키지 말것

TODO: https://wit.nts-corp.com/2015/04/16/3538