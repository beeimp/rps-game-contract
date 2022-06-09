# 가위바위보 게임

## 함수

createRoom: 가위바위보 게임을 하기 위한 방을 만듭니다.

joinRoom: 만들어진 방에 참가합니다.

payout: 게임을 마칩니다. 게임의 결과에 따라 베팅 금액을 송금합니다.

## 수도코드

1. 방장(originator)가 createRoom을 호출합니다.
   - 방장은 인자로 자신이 낼 가위/바위/보 값과 베팅 금액을 넘겨줍니다.
   - createRoom은 새로운 방을 만들고, 방의 번호를 리턴합니다.
2. 참가자(taker)는 joinRoom을 호출합니다.
   - 참가자는 인자로 참여할 방 번호, 자신이 낼 가위/바위/보 값과 베팅 금액을 넘겨줍니다.
   - joinRoom은 참가자를 방에 참여시킵니다.
   - joinRoom은 방장과 참가자의 가위/바위/보 값을 확인하고 해당 방의 승자를 설정합니다.
3. 방장 또는 참가자가 payout 함수를 호출합니다.
   - 인자로 게임을 끝낼 방 번호를 넘겨줍니다.
   - 게임의 결과에 따라 베팅 금액을 송금합니다.

## 개선

- 게임방 생성자의 입력값(가위/바위/보) 숨기기
    1. 방장은 hash(주먹/가위/보, nonce)로 암호화한 값을 전달하면서 방 생성
    2. 도전자는 생성된 방에 참여(주먹/가위/보)
    3. 방장은 도전자가 참여를 확인
    4. 방장은 제시간 값(주먹/가위/보)과 nonce값을 전달하여 승패 결정