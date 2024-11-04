# java-lotto-precourse



# 로또 게임 애플리케이션

## 개요
이 애플리케이션은 로또 번호를 무작위로 생성하고, 당첨 번호와 보너스 번호를 입력받아 사용자가 구매한 로또의 당첨 여부와 수익률을 계산해 출력하는 콘솔 기반의 로또 게임입니다.

## 주요 기능
- [ ] 로또 구매 및 당첨 확인: 구입 금액을 입력하면 구입 가능한 수량만큼 로또 번호를 발행합니다.
- [ ] 당첨 번호 입력: 당첨 번호와 보너스 번호를 입력받아, 각 구매한 로또 번호와 비교하여 당첨 여부를 확인합니다.
- [ ] 수익률 계산: 사용자가 구매한 로또의 총 수익률을 계산하여 제공합니다.

## 사용법
- [ ] 최대 구매금액 long 타입으로하여 9,223,372,036,854,775,807 일때 모든 로또가 다 당첨되는경우가 구매 가능한 최대 개수=4,611,686,018
- [ ] 애플리케이션 실행 후, 구입 금액을 입력합니다. (금액은 1,000원 단위로 입력해야 하며, 예외 상황 발생 시 에러 메시지가 출력됩니다.)
- [ ] 당첨 번호와 보너스 번호를 입력합니다. (잘못된 값이 입력되면 예외 메시지가 출력되고, 올바른 값을 입력할 때까지 반복하여 입력받습니다.)
- [ ] 결과로 사용자가 구매한 로또 번호, 당첨 통계, 수익률을 콘솔에 출력합니다.

## 예외 처리
- [ ] 구입 금액 예외: 구입 금액이 1,000원 단위로 나누어 떨어지지 않으면 [ERROR] 메시지가 출력됩니다. 
- [ ] 숫자 파싱 오류: 입력된 값이 숫자가 아닐 경우 [ERROR] 메시지가 출력됩니다.
  -  로또번호입력 포멧은 구분자 , 를 기준으로 1 ~ 45 사이값을 입력해야하며 공백있어도 허용하게함.
- [ ] 번호 유효성: 
  - 로또 번호는 1~45 범위의 중복되지 않은 6개 숫자로 이루어져야 한다.
  - 범위 초과 하거나 번호 중복 시 [ERROR]  메시지가 출력됩니다.
  - 보너스번호는 로또번호 6개와 중복 안되어야함 

## 디자인 패턴
- [ ] 옵저버 패턴 : WinningLottoNumber과 PurchasedLotto는  1:n 구조를 활용하고 싶어 도입
- WinningLottoNumber 객체는 Subject 역할로, 당첨 번호와 보너스 번호가 설정되면 이를 구독 중인 PurchasedLotto(Observer) 객체들에  알림을 보냅니다.
- 각 PurchasedLotto는 Observer로서 알림을 받고 자신의 당첨 여부와 등수를 자동으로 계산합니다.
- 이를 통해 모든 로또가 자신의 당첨 여부와 등수를 자동으로 확인하게 됩니다.
## 문제 요구사항 Enum 사용
- [ ] LottoRank를 열거형 클래스로 로또 등수에 따른 상금을 정의하여  각 PurchasedLotto 및 당첨 결과에 이를 활용 할 수 있음.



