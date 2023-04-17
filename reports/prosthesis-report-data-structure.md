[to Root](./report.md)

### Prosthesis Report Data Structure

```JSON
{
  "report": {
    "data": [
      {
        "key": 13,
        "type": "crown",
        "child": [
          "crown"
        ],
        "type_crown": {
          "method": "anatomic",
          "material": "zirconia",
          "shade_system": "vita_classic",
          "shade": "A4"
        }
      }
    ]
  }
}
```

| Props | Description |
| -- | -- |
| report.data[n].key | 치아 번호 <br>FDI 표기  |
| report.data[n].type | 해당 치아의 진료 Type <br>Root Type으로 실제 Type은 child 배열안에 존재함 |
| report.data[n].child | 실제 진료 Type의 배열 1개인 경우 rootType과 동일 <br> 이 값들에 대응되도록 type_{child}가 생성되며 해당 객체에 실제 정보가 담김 <br>child가 여러개인 경우 type_{child}객체 역시 대응하여 생성됨 |
| report.data[n].type_{child} | 실제 진료정보가 담긴 객체 <br> 작성된 내용만 하위 prop으로 존재함 |
| report.data[n].type_{child}.method | child Type의 치료 방법 |
| report.data[n].type_{child}.material | child Type의 치료 소재 |
| report.data[n].type_{child}.shade_system | child Type에 사용된 shade의 system 이름 |
| report.data[n].type_{child}.shade | child Type의 shade 값 |