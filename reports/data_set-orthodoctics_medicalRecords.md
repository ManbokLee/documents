[to Root](./report.md)

# Data Set - Orthodontics: MedicalRecords
> 교정 진료 내용 중 치과에서 입력하는 필드에 대한 값과 라벨에 대한 구조 입니다.   
> 치아별로 정보가 기록되는 형태가 아닌 하나의 케이스에 대한 정보가 입력됩니다.   
> 치아별로 입력되는 데이터는 별도로 존재합니다.

## Clinical Conditions
```JSON
[
  { "value": "crowding", "label": "Crowding" },
  { "value": "deep_bite", "label": "Deep Bite" },
  { "value": "spacing", "label": "Spacing" },
  { "value": "class_ii_division_i", "label": "Class II Division I" },
  { "value": "class_ii_division_ii", "label": "Class II Division II" },
  { "value": "class_iii", "label": "Class III" },
  { "value": "uneven_smile", "label": "Uneven Smile" },
  { "value": "open_bite", "label": "Open Bite" },
  { "value": "overbite", "label": "Overbite" },
  { "value": "other", "label": "Other" }
]
```

|||
| -- | -- |
| 저장되는 key | medicalRecords.conditions |
| 저장되는 값 형태 | Array\<string\> |
| 저장되는 값 | 유저가 선택한 모든 value |

## Not To Moves
```JSON
[
  { "value": "na", "label": "N/A" },
  { "value": "upper", "label": "Upper" },
  { "value": "lower", "label": "Lower" },
  { "value": "anterior", "label": "Anterior" },
  { "value": "posterior", "label": "Posterior" }
]
```

|||
| -- | -- |
| 저장되는 key | medicalRecords.notMove |
| 저장되는 값 형태 | Array\<string\> |
| 저장되는 값 | 유저가 선택한 모든 value |

## Method of Gaining Space

#### Radio Case A
```JSON
[
  { "value": "primary", "label": "Primary" },
  { "value": "secondary", "label": "Secondary" },
  { "value": "none", "label": "None" }
]
```
- 사용처: Extraction (Which tooth to extract), Extraction

#### Radio Case B
```JSON
[
  { "value": "primary", "label": "Primary" },
  { "value": "secondary", "label": "Secondary" },
  { "value": "none", "label": "None" },
  { "value": "simulation", "label": "Refer to Clinical Simulation" }
]
```
- 사용처: Interproximal Reduction, Distalization, Proclination


### Extraction (Which tooth to extract)
|||
| -- | -- |
| 저장되는 key | medicalRecords.extractionExtract |
| 저장되는 값 형태 | string |
| 저장되는 값 | Radio Case A의 값 중 1 |

### Extraction
|||
| -- | -- |
| 저장되는 key | medicalRecords.extraction |
| 저장되는 값 형태 | string |
| 저장되는 값 | Radio Case A의 값 중 1 |

### Interproximal Reduction
|||
| -- | -- |
| 저장되는 key | medicalRecords.interproximal |
| 저장되는 값 형태 | string |
| 저장되는 값 | Radio Case B의 값 중 1 |

### Distalization
|||
| -- | -- |
| 저장되는 key | medicalRecords.distalization |
| 저장되는 값 형태 | string |
| 저장되는 값 | Radio Case B의 값 중 1 |

### Proclination
|||
| -- | -- |
| 저장되는 key | medicalRecords.proclination |
| 저장되는 값 형태 | string |
| 저장되는 값 | Radio Case B의 값 중 1 |

## Midline
#### Midline props
```JSON
[
  { "value": "simulation", "label": "Refer to Clinical Simulation" },
  { "value": "maintain", "label": "Maintain" },
  { "value": "correct_upper_by_1_5mm", "label": "Correct upper by 1-5 mm" },
  { "value": "correct_lower_by_1_5mm", "label": "Correct lower by 1-5 mm" }
]
```
|||
| -- | -- |
| 저장되는 key | medicalRecords.midline |
| 저장되는 값 형태 | string |
| 저장되는 값 | Midline props의 값 중 1 |

## Crossbite
#### Crossbite props
```JSON
[
  { "value": "maintain", "label": "Maintain" },
  { "value": "improve", "label": "Improve" },
  { "value": "none", "label": "None" },
  { "value": "simulation", "label": "Refer to Clinical Simulation" }
]
```
|||
| -- | -- |
| 저장되는 key | medicalRecords.crossbite |
| 저장되는 값 형태 | string |
| 저장되는 값 | Crossbite props의 값 중 1 |
