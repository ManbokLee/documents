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
        "key": 16,
        "type": "pontic",
        "child": [
          "pontic"
        ],
        "type_pontic": {
          "method": "anatomic",
          "material": "pmma",
          "shade_system": "vita_3d_master",
          "shade": "1M1"
        }
      },
      {
        "key": 15,
        "type": "pontic",
        "child": [
          "pontic"
        ],
        "type_pontic": {
          "method": "anatomic",
          "material": "pmma",
          "shade_system": "vita_3d_master",
          "shade": "1M1"
        }
      },
      {
        "key": 14,
        "type": "pontic",
        "child": [
          "pontic"
        ],
        "type_pontic": {
          "method": "anatomic",
          "material": "pmma",
          "shade_system": "vita_3d_master",
          "shade": "1M1"
        }
      },
      {
        "key": 13,
        "type": "pontic",
        "child": [
          "pontic"
        ],
        "type_pontic": {
          "method": "anatomic",
          "material": "pmma",
          "shade_system": "vita_3d_master",
          "shade": "1M1"
        }
      },
      {
        "key": 24,
        "type": "onlay",
        "child": [
          "onlay"
        ],
        "type_onlay": {
          "material": "zirconia",
          "shade_system": "vita_classic",
          "shade": "A1"
        }
      },
      {
        "key": 25,
        "type": "onlay",
        "child": [
          "onlay"
        ],
        "type_onlay": {
          "material": "zirconia",
          "shade_system": "vita_classic",
          "shade": "A1"
        }
      },
      {
        "key": 47,
        "type": "denture_coping",
        "child": [
          "denture_coping"
        ],
        "type_denture_coping": {
          "method": "primary_telescopic_crown_pfm",
          "material": "metal"
        }
      },
      {
        "key": 46,
        "type": "custom_abutment",
        "child": [
          "custom_abutment"
        ],
        "type_custom_abutment": {
          "material": "zirconia"
        }
      },
      {
        "key": 36,
        "type": "custom_abutment_implant_crown",
        "child": [
          "custom_abutment",
          "implant_crown"
        ],
        "type_custom_abutment": {
          "material": "zirconia"
        },
        "type_implant_crown": {
          "method": "screw_type_layered",
          "material": "zirconia",
          "shade_system": "vita_classic",
          "shade": "A1"
        }
      },
      {
        "key": 37,
        "type": "custom_abutment_implant_crown",
        "child": [
          "custom_abutment",
          "implant_crown"
        ],
        "type_custom_abutment": {
          "material": "zirconia"
        },
        "type_implant_crown": {
          "method": "screw_type_layered",
          "material": "zirconia",
          "shade_system": "vita_classic",
          "shade": "A1"
        }
      }
    ],
    "connects": {
      "c1314": {
        "code": "c1314",
        "keys": [
          14,
          13
        ],
        "state": "",
        "visible": true
      },
      "c1415": {
        "code": "c1415",
        "keys": [
          15,
          14
        ],
        "state": "",
        "visible": true,
        "select": true
      },
      "c1516": {
        "code": "c1516",
        "keys": [
          16,
          15
        ],
        "state": "",
        "visible": true
      },
      "c3637": {
        "code": "c3637",
        "keys": [
          37,
          36
        ],
        "state": "",
        "visible": true,
        "select": true
      },
      "c4647": {
        "code": "c4647",
        "keys": [
          47,
          46
        ],
        "state": "",
        "visible": true
      }
    },
    "memo": "This is test case B"
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
 - 13, 14, 15번 치아는 Pontic Type으로 Anatomic 방식으로 PMMA의 Vita 3D Master의 1M1 쉐이드로 진료
 - 14-15번 치아는 연결된 상태
 - 24, 25번 치아는 Onlay Zirconia Vita Classic의 A1 쉐이드로 진료
 - 37, 36번 치아는 Custom Abutment와 Implant Crown Type으로 Custom Abutment는 Screw Type 방법, Implant Crown은 Layered 방법을 적용 각각의 소재는 Zirconia로 동일하며 Shade는 Vita Classic의 A1 쉐이드로 진료, 이 두 치아는 연결된 상태
 - 47번 치아는 Denture Coping Type으로 Primary Telescopic Crown - PFM 방식 (이 방식의 소재는 Metal 만 존재)
 - 46번 치아는 Custom Abutment type으로 Zirconia 소재를 사용함