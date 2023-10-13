# Cash Register
Design a cash register drawer function `checkCashRegister()` that accepts purchase price as the first argument (`price`), 
payment as the second argument (`cash`), and cash-in-drawer (`cid`) as the third argument.

`cid` is a 2D array listing available currency.

The `checkCashRegister()` function should always return an object with a `status` key and a `change` key.

`Return {status: "INSUFFICIENT_FUNDS", change: []}` if cash-in-drawer is less than the change due, or if you cannot return the exact change.

`Return {status: "CLOSED", change: [...]}` with cash-in-drawer as the value for the key change if it is equal to the change due.

Otherwise, return `{status: "OPEN", change: [...]}`, with the change due in coins and bills, sorted in highest to lowest order, 
as the value of the `change` key.

<img width="375" alt="Screenshot 2023-10-12 at 4 39 06 PM" src="https://github.com/LenaKwon/CodeChallenge/assets/37726487/74bb7c0a-2c2d-4766-87b4-35f6097fa7ee">
</br>

```
[
  ["PENNY", 1.01],
  ["NICKEL", 2.05],
  ["DIME", 3.1],
  ["QUARTER", 4.25],
  ["ONE", 90],
  ["FIVE", 55],
  ["TEN", 20],
  ["TWENTY", 60],
  ["ONE HUNDRED", 100]
]
```

## Before
```javascript
function checkCashRegister(price, cash, cid) {
  let change;
  return change;
}

checkCashRegister(19.5, 20, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]]);
```
## Answers
```javascript

function checkCashRegister(price, cash, cid) {
    //소숫점 계산 피하기 위해 정수로 만들어 준 후 결과값에서 100을 다시 나누어줄 예정
    let change = cash * 100 - price * 100 ;

    // 먼저 거슬러줄 수 있는 돈이 되는지 아닌지를 가려내기 위해 거스름돈과, cid 총액을 비교하기
    // cid 총액 구하기
    let cidTotal = 0;
    for(let elem of cid){  // 배열에서 for of 사용해서 loop 돌 수 있음
      cidTotal += elem[1] * 100
    }
    //console.log(cidTotal)

    // 조건 비교 1 : cid에 있는 총액 (cidTotal) 이 거스름돈보다 적게 남아있다면
    if(change < cidTotal){
      return {status: "INSUFFICIENT_FUNDS", change: []};
    //조건 비교 2 : cid에 있는 총액 (cidTotal)과 거스름돈이 같다면
    }else if(change == cidTotal){  
      return {status: "CLOSED", change: cid};
    //조건 비교 3: 거스름 돈이 충분할 경우 연산
    }else{
      let result =[]; //결과값을 저장할 부분
      cid = cid.reverse(); // 문제조건중 결과값을 내림차순으로 정렬하라고 했기 때문에 뒤집음.

      //화폐단위 문자열을 찾기위한 lookup 세팅
      // 내림차순으로 정렬해야지만, 차례차례 잔돈을 빼나가기 좋음?
      let currencyUnit = {
      'ONE HUNDRED': 10000,
      'TWENTY': 2000,
      'TEN': 1000,
      'FIVE': 500,
      'ONE': 100,
      'QUARTER':25,
      'DIME':10,
      'NICKEL':5,
      'PENNY':1
      }
      // 입력값의 cid를 돌면서 거스름돈 계산 시작
      for(let elem of cid){
        //마지막 결과값의 change 부분의 조건을 만족시키기 위한 임시배열을 만듦
        // 기본 값은 0 이고 여기에 cid에서 뺀돈 만큼 더해줄 것임.
        let moneyholer = [elem[0],0];
        // 우선 입력값도 이전과 같이 100을 곱해서 소수점 떼고 계산.
        elem[1] = elem[1] * 100;
        //console.log(moneyholer)

        // lookup 찾아보고 change 가 화폐단위보다 클 때만 계산 함. && 거슬러준 돈이 남아 있을 경우만 loop을 돈다.
        while(change >= currencyUnit[elem[0]] && elem[1] > 0 ){
          //console.log(currencyUnit[elem[0]])
          //console.log(elem[1])
          //잔돈 거슬러준 만큼 빼기
          change -= currencyUnit[elem[0]]
          //console.log(change)
          //cid 에서 거슬러준 잔돈 빼기
          elem[1] -= currencyUnit[elem[0]]; //0될때까지 빼야지 while loop 끝남
          //console.log(elem[1])
          // 임시 배열에 거슬러 준 값을 더해주면서 결과값으로 거슬러준 각 지폐와 동전의 총 합계를 받음
          // 최종 값 출력 전 100 으로 나눠주기
          moneyholer[1] += currencyUnit[elem[0]]/100 
          //console.log(moneyholer)
        }
        //moneyholer에 한 기록 중에 기록된 내용만 걸러서 결과값으로 push
        if(moneyholer[1]>0){
          result.push(moneyholer)
          //console.log(result)
        }
      }
      //for loop 으로 거스름 돈 체크 후에도 아직 거스름돈이 0 이 아닐 경우, 맞는 지폐나 동전이 없는 경우 출력
      if (change > 0){
        return {status: "INSUFFICIENT_FUNDS", change: []};
      }
      return {status: "OPEN", change: result }
    }
  }
  
  console.log(checkCashRegister(19.5, 20, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]]));
```
