[to Root](./report.md)

# Prosthesis Case A


## Sample Data Case

```JSON
{
  "report_version": "RV1",
  "type": "prosthesis",
  "provider": "rayteams",
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
      },
      {
        "key": 12,
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
      },
      {
        "key": 11,
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
      },
      {
        "key": 21,
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
    ],
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
      },
      "c1213": {
        "code": "c1213",
        "keys": [
          13,
          12
        ],
        "state": "",
        "visible": true,
        "select": true
      },
      "c1121": {
        "code": "c1121",
        "keys": [
          11,
          21
        ],
        "state": "",
        "visible": true,
        "select": true
      }
    },
    "memo": "This is memo of case."
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
[Report Data Structure](./prosthesis-report-data-structure.md)   
[Report connects Structure](./prosthesis-report-connects-structure.md)   
[Report Memo Structure](./default-report-memo-structure.md)   
[Photos Structure](./rayface-photos-structure.md)   

### Sample
 - 21, 11, 12, 13번 치아는 Crown Type으로 모두 anatomic 방법으로 zirconia를 사용하여 vita classic의 A4 쉐이드로 진행함
 - 11-21, 11-12, 12-13 치아의 진료는 모두 연결되어 있음
 - photos는 RAYFace에서 생성된 정보이며 각각 해당하는 이미지 파일의 경로를 의미함