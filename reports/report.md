# Report

> 보철과 교정 유형의 데이터 구조 및 샘플 안내   


## Default Report Data Structure
 - 케이스의 진료정보가 최종적으로 저장되는 형태
 - 기본 저장 경로는 케이스의 root path
 - 기본 저장 파일 명은 "teams_report.json"
```JSON
{
  "report_version": "RV1",
  "type": "prosthesis",
  "provider": "rayteams",
  "report": {
    "toothNumberingSystem": "FDI",
    "data": [],
    "connects": {},
    "memo": ""
  },
  "revision": 1,
  "report_revisions": [],
  "photos": {},
  "created": 1682989474966
}
```

### Description

| Pros  | Description |
| -- | -- |
| report_version | string, required  <br>작성된 리포트 set의 버전 <br>이 버전에 따라서 RAYTeams에서 report안의 내용을 표시함   |
| type | string, required <br>available values: "prosthesis", "orthodontics" <br>report의 유형 |  
| provider | string, required <br>리포트가 작성된 프로그램 <br> - RAYTeams: rayteams<br> - D+Manager: dds_manager <br> - OrthoSimulator: ortho_simulator <br> RAYTeams외의 값은 임의 값으로 실제 사용할 값이 결정되면 변경예정|  
| revision | integer, optional <br>만약 리포트의 내용이 변경되었다면 변경된 최종 버전 숫자 |  
| report_revisions | array\<object\>, optional <br>object로는 기존 reversion의 모든 데이터가 저장 <br>만약 리포트의 reversion이 발생했다면 기존 리버전의 모든 내용을 포함하는 정보 <br>단 report_reversions 필드는 포함되지 않음 |  
| photos | object, optional <br> 별도로 표시할 사진, 동영상, 3D 모델등의 정보 <br> structure는 별도내용 확인|  
| report | object, requires <br> 작성된 리포트에 대한 내용 <br> orthodontics, prosthesis에 따라서 다른 data가 존재함 |  
| report.toothNumberingSystem | 치아번호 표시 방법 RAYTeams에서는 FDI 기준으로 표시함 |
| report.data | array\<object\>, required <br> 치아와 관련된 정보 <br>structure는 별도 내용 확인 |  
| report.connects | object, optional <br> 치아 선택 관련하여 연결관련된 정보 <br> structure는 별도 내용 확인|  
| report.medicalReport | object, optional <br> orthodontics 에서 기록되는 진료 내용 <br> structure는 별도 내용 확인 |  
| report.memo | string, optional <br> report에 별도로 기록된 메모가 있다면 해당 메모의 내용 <br> 개행은 "\n"으로 구별 |  
| created | report의 생성 timestamp (밀리 세컨트 까지) |

### Used Data Set [Version RV1]
[Prosthesis](./data_set-prosthesis.md)   
[Orthodontics:tooth](./data_set-orthodoctics_tooth.md)   
[Orthodontics:medical](./data_set-orthodoctics_medicalRecords.md)   

### Sample Reports
[Prosthesis Case A](./report-prosthesis-sample-x-A.md)   
[Prosthesis Case B](./report-prosthesis-sample-x-B.md)   
[Orthodontics Case A](./report-orthodontics-sample-A.md)   
[Orthodontics Case B](./report-orthodontics-sample-B.md)   
