[to Root](./report.md)

### Prosthesis Report Connects Structure

```JSON
{
  "report": {
    "connects": {
      "c1112": {
        "code": "c1112",
        "keys": [
          12,
          11
        ],
        "state": "",
        "visible": true,
        "select": true
      }
    }
  }
}
```


- 객체로 구성되어 있으며 c{toothNumberA}{toothNumberB} 형태의 키 값을 가짐
- 각각의 키에 대한 정보는 아래와 같음 (키는 {cKey}로 표시함)

| Props | Description |
| -- | -- |
| report.connects.{cKey}.code | 키값의 문자열 <br>prefix로 "c"를 가짐<br>c{toothNumberA}{toothNumberB} 형태로 구성 <br>toothNumberA는 항상 toothNumberB보다 작은 값 |
| report.connects.{cKey}.keys | 구성된 치아 번호의 배열 <br>오름 차순을 무시함 <br>FDI 표기법의 번호 |
| report.connects.{cKey}.state | 추후 활용을 위한 빈 값 |
| report.connects.{cKey}.visible | 연결 가능 상태를 보일지 여부<br>select가 true 경우 반드시 true이어야함 |
| report.connects.{cKey}.select | 연결된 여부 <br>false인 경우 visible이 true인 경우 연결되지 않은 상태로 보여짐 |