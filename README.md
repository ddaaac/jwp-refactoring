# 키친포스

## 요구 사항

### 주문
- 주문을 할 수 있다.
    - 주문 테이블 id, 주문 항목(메뉴 id, 메뉴 수량)의 list를 필요로 한다.
    - 주문 시 기본 주문상태는 '조리'이다.
    - 주문과 주문 항목이 모두 저장된다.
    - 예외처리
        - 주문 항목이 비어있을 경우
        - 주문 항목의 메뉴 id에 해당하는 메뉴가 없을 경우
- 전체 주문을 주회할 수 있다.
- 주문의 상태를 수정할 수 있다.
    - 주문 id와 변경할 주문 상태를 필요로 한다.
    - 주문 상태에 따라 수정이 가능하다.
    - 예외처리
        - 주문 id에 해당하는 주문이 없을 경우
        - 주문 상태가 '계산 완료'일 경우

### 주문 테이블
- 주문 테이블을 생성할 수 있다.
    - 손님의 수와 empty 여부를 필요로 한다.
- 주문 테이블을 조회할 수 있다.
- 주문 테이블의 비어있음 여부를 수정할 수 있다.
    - 주문 테이블 id, 비어있음 여부를 필요로 한다.
    - 예외 처리
        - 주문 테이블 id에 해당하는 주문 테이블이 없을 경우
        - 주문 테이블의 단체 id가 없을 경우
        - 주문 테이블의 주문의 상태가 '조리' 또는 '식사'일 경우
- 주문 테이블의 손님 수를 수정할 수 있다.
    - 주문 테이블 id, 손님 수를 필요로 한다.
    - 예외 처리
        - 손님 수가 음수일 경우
        - 주문 테이블 id에 해당하는 주문 테이블이 없을 경우
        - 주문 테이블이 비어있을 경우

### 단체 주문
- 단체 주문을 생성할 수 있다.
    - 주문 테이블의 (id)리스트를 필요로 한다.
    - 예외 처리
        - 주문 테이블의 id에 해당하는 주문 테이블이 없는 경우
        - 주문 테이블 중에 하나라도 비어있지 않은 경우
        - 주문 테이블의 단체 그룹 id가 없는 경우
- 단체 주문을 삭제할 수 있다.
    - 단체의 id를 필요로 한다.
    - 예외처리
        - 단체에 해당하는 주문 테이블의 상태가 '조리' 또는 '식사'일 경우

### 상품
- 상품을 생성할 수 있다.
    - 상품 이름, 상품 가격을 필요로 한다.
    - 예외 처리
        - 상품 이름이 없는 경우
        - 상품의 가격이 음수인 경우
- 전체 상품을 조회할 수 있다.

### 메뉴
- 메뉴를 생성할 수 있다.
    - 메뉴 이름, 메뉴 가격, 메뉴 그룹 id, 메뉴 상품(상품 id, 상품 수량)의 리스트를 필요로 한다.
    - 예외 처리
        - 메뉴 가격이 없는 경우
        - 메뉴 가격이 음수인 경우
        - 메뉴 그룹 id에 해당하는 메뉴 그룹이 존재하지 않는 경우
        - 상품 id에 해당하는 상품이 없는 경우
        - 메뉴 가격이 메뉴 상품에 해당하는 가격 합보다 많을 경우
- 전체 메뉴를 조회할 수 있다.

### 메뉴 그룹
- 메뉴 그룹을 생성할 수 있다.
    - 메뉴 그룹 이름을 필요로 한다.
- 전체 메뉴 그룹을 조회할 수 있다.
        


## 용어 사전

| 한글명 | 영문명 | 설명 |
| --- | --- | --- |
| 상품 | product | 메뉴를 관리하는 기준이 되는 데이터 |
| 메뉴 그룹 | menu group | 메뉴 묶음, 분류 |
| 메뉴 | menu | 메뉴 그룹에 속하는 실제 주문 가능 단위 |
| 메뉴 상품 | menu product | 메뉴에 속하는 수량이 있는 상품 |
| 금액 | amount | 가격 * 수량 |
| 주문 테이블 | order table | 매장에서 주문이 발생하는 영역 |
| 빈 테이블 | empty table | 주문을 등록할 수 없는 주문 테이블 |
| 주문 | order | 매장에서 발생하는 주문 |
| 주문 상태 | order status | 주문은 조리 ➜ 식사 ➜ 계산 완료 순서로 진행된다. |
| 방문한 손님 수 | number of guests | 필수 사항은 아니며 주문은 0명으로 등록할 수 있다. |
| 단체 지정 | table group | 통합 계산을 위해 개별 주문 테이블을 그룹화하는 기능 |
| 주문 항목 | order line item | 주문에 속하는 수량이 있는 메뉴 |
| 매장 식사 | eat in | 포장하지 않고 매장에서 식사하는 것 |
