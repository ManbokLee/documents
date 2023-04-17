[to Root](./report.md)

### RAYFace Photos Structure

```JSON
{
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

- photos의 경우 RAYFace에서 생성한 값이며 사용자에게 입력받은 값이 아닌 RAYTeams가 생성 요청을해서 받은 값


| Props | Description |
| -- | -- |
| photos.front_face_aspect | 정면 사진 |
| photos.front_intra_oral | 정면 사진 + 구강 내 상악 하악 스캔 파일이 오버랩 된 사진 |
| photos.front_smile | 정면 스마일 사진 |
| photos.left_intra_oral | 상악 하악 스캔파일이 큰 사이즈로 오버랩 된 정면 기준 반 좌측 사진 |
| photos.max_intra_oral | 상악 하악 스캔파일이 큰 사이즈로 오버랩 된 정면 기준 사진 |
| photos.maxillary_dentition_buccal | 상악 사진 |
| photos.right_face_aspect | 우측 사진 |
| photos.right_intra_oral | 우측 사진 + 구강 내 상악 하악 스캔 파일이 오버랩 된 사진 |
| photos.right_smile | 우측 스마일 사진 |
