[to Root](./report.md)

# Orthodontics Case A


## Sample Data Case

```JSON
{
  "report_version": "RV1",
  "type": "orthodontics",
  "provider": "rayteams",
  "report": {
    "data": [
      {
        "key": 11,
        "type": "anchor",
        "ortho_status": "anchor"
      }
    ],
    "medicalReport": {
      "conditions": [
        "open_bite",
        "other",
        "spacing",
        "crowding"
      ]
    },
    "memo": "이것은 테스트 케이스 입니다."
  },
  "reversion": 1,
  "photos": {
    "front_face_aspect": ".teams_medias/FFA.jpg",
    "front_intra_oral": ".teams_medias/FIO.jpg",
    "front_smile": ".teams_medias/FSM.jpg",
    "left_intra_oral": ".teams_medias/LIO.jpg",
    "max_intra_oral": ".teams_medias/MAX.jpg",
    "maxillary_dentition_buccal": ".teams_medias/MDB.jpg",
    "right_face_aspect": ".teams_medias/RFA.jpg",
    "right_intra_oral": ".teams_medias/RIO.jpg",
    "right_smile": ".teams_medias/RSM.jpg"
  }
}
```
[Report Data Structure](./data_set-orthodoctics_tooth.md)   
[Report MedicalReport Structure](./data_set-orthodoctics_medicalRecords.md)   
[Report Memo Structure](./default-report-memo-structure.md)   
[Photos Structure](./rayface-photos-structure.md)   

### Sample
 - 11번 치아는 anchor 임
 - 치아의 컨디션은 open_bite, other, spacing, crowding 이 4개의 상태를 가짐