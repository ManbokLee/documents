[to Root](./report.md)

# Prosthesis Case B


## Sample Data Case

```JSON
{
  "report_version": "RV1",
  "type": "prosthesis",
  "provider": "rayteams",
  "report": {
    "data": [
      {
        "key": 14,
        "type": "AnatomicCrown",
        "material": "ZI",
        "shade": "V3DM:1M2",
        "implantType": "CustomAbutment",
        "materialAbutment": "GCER"
      },
      {
        "key": 23,
        "type": "AnatomicInlay",
        "material": "AU"
      },
      {
        "key": 24,
        "type": "AnatomicInlay",
        "material": "AU"
      },
      {
        "key": 25,
        "type": "AnatomicInlay",
        "material": "AU"
      }
    ],
    "connects": {
      "c2324": {
        "code": "c2324",
        "keys": [
          24,
          23
        ],
        "state": "",
        "visible": true
      },
      "c2425": {
        "code": "c2425",
        "keys": [
          25,
          24
        ],
        "state": "",
        "visible": true
      }
    },
    "toothNumberingSystem": "FDI",
    "memo": "This is test case."
  },
  "revision": 1,
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
  },
  "created": 1682990271926
}
```
[Report Data Structure](./prosthesis-report-data-structure-x.md)   
[Report connects Structure](./prosthesis-report-connects-structure.md)   
[Report Memo Structure](./default-report-memo-structure.md)   
[Photos Structure](./rayface-photos-structure.md)   

### Sample
 - 14 번 치아는 Anatomic Crown으로 Zirconium dioxide소재로 Vita 3D Master 쉐이드 시스템의 1M2 쉐이드를 사용함
 - 23, 24, 25 번 치아는 Anatomic Inlay로 gold 소재를 사용함
 - photos는 RAYFace에서 생성된 정보이며 각각 해당하는 이미지 파일의 경로를 의미함