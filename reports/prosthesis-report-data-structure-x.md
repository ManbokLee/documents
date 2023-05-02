[to Root](./report.md)

### Prosthesis Report Data Structure

```JSON
{
  "report": {
    "data": [
      {
        "key": 11,
        "type": "AnatomicCrown",
        "material": "GCER",
        "shade": "VCL:A1"
      }
    ]
  }
}
```

| Props | Description |
| -- | -- |
| report.data[n].key | 치아 번호  |
| report.data[n].type | 해당 치아의 진료 Type |
| report.data[n].material | 해당 치아의 소재 |
| report.data[n].shade | 해당 치아의 쉐이드 <br> ":"로 분리하여 앞에 문자는 Shade System의 값 뒤 문자는 실제 쉐이드 값 |