[to Root](./report.md)

# Data Set - Orthodontics: Tooth
> 교정 진료 내용 중 치아별 상태를 기록하는 값입니다.   
> medicalRecords의 경우 별로로 존재합니다.

## Tooth Status
```JSON
[
  { "value": "missing", "label": "Missing" },
  { "value": "anchor", "label": "Anchor" },
  { "value": "extraction", "label": "Extraction" }
]
```

### 치아별 저장 방식 예시
```JSON
{
  "report": {
    "data": [
      {
        "key": 16,
        "type": "anchor",
        "ortho_status": "anchor"
      },
      {
        "key": 13,
        "type": "missing",
        "ortho_status": "missing"
      },
      {
        "key": 24,
        "type": "extraction",
        "ortho_status": "extraction"
      },
      {
        "key": 26,
        "type": "anchor",
        "ortho_status": "anchor"
      }
    ]
  }
}
```
- type과 ortho_status에 동일한 값 입력   



