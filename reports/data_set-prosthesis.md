[to Root](./report.md)

# Data Set - Prosthesis

> 아래 내용 중 label, value 외의 값은 입력 폼을 만들기 위해 RAYTeams에서 사용한 방식이 포함되어 있습니다. 구현에 필요한 상태에 따라서 다르게 적용해도 무방합니다.

> 입력 폼을 만들기 위한 값의 경우 추가/변경이 발생할 수 있습니다.

## Type

### Props of Types.
``` JSON
[
  {
    "value": "inlay",
    "label": "Inlay",
    "unLink": true
  },
  {
    "value": "onlay",
    "label": "Onlay",
    "unLink": true
  },
  {
    "value": "coping",
    "label": "Coping"
  },
  {
    "value": "denture_coping",
    "label": "Denture Coping"
  },
  {
    "value": "crown",
    "label": "Crown"
  },
  {
    "value": "pontic",
    "label": "Pontic"
  },
  {
    "value": "post_core",
    "label": "Post & Core",
    "innerFill": true
  },
  {
    "value": "veneer",
    "label": "Veneer"
  },
  {
    "value": "implant_crown",
    "label": "Implant Crown"
  },
  {
    "value": "custom_abutment",
    "label": "Custom Abutment",
    "autoLink": true,
    "innerFill": true
  },
  {
    "value": "surgical_guide",
    "label": "Surgical Guide"
  },
  {
    "value": "offset_substructure",
    "label": "Offset Substructure"
  },
  {
    "value": "custom_abutment_implant_crown",
    "label": "Custom Abutment + Implant Crown",
    "child": [
      "custom_abutment",
      "implant_crown"
    ]
  },
  {
    "value": "custom_abutment_coping",
    "label": "Custom Abutment + Coping",
    "child": [
      "custom_abutment",
      "coping"
    ]
  },
  {
    "value": "diagnostic_wax_up",
    "label": "Diagnostic Wax-Up"
  },
  {
    "value": "partial_denture",
    "label": "Partial Denture",
    "unLink": true
  },
  {
    "value": "post_core_crown",
    "label": "Post & Core + Crown",
    "child": [
      "post_core",
      "crown"
    ]
  },
  {
    "value": "post_core_coping",
    "label": "Post & Core + Coping",
    "subLabel": "Coping",
    "child": [
      "post_core",
      "post_core_coping"
    ]
  }
]
```

### Description
| Pros  | Description |
| -- | -- |
| value | Type에 대한 고유한 값 <br>이 값으로 report가 작성되어야함 |
| label | 표시되는 Type에 대한 값 <br>엔드유저에게 노출되는 정보|
| subLabel | 자신의 type이 child로 소속된 경우 해당 경우에 보이는 표시 문자 <br>post_core_coping의 경우 자신의 대표 label을 가지지만 child값에 다른 값이 존재함으로 method, material등의 선택 화면에서는 Coping이라는 label을 표시 |
| unLink | 선택된 치아간 연결 설정이 불가능한지 여부 <br>이 값이 없거나 거짓이라면 치아간 연결 설정이 계산되어서 표시됨 <br> - 연결상태 선택 가능은 인접한 치아간의 소재가 동일하면 가능상태가 됨 <br> - ex: 11번 치아와 21번 치아의 소재가 동일하게 지르코니아라면 두개 치아간 연결 설정이 가능함. <br> - ex: 11번 치아와 21번 치아의 소재가 동일해도 unLink가 true인 inlay라면 연결 설정이 불가능함. |
| innerFill | 진료가 내부를 채우는 용도로만 사용되는지 여부 <br>이 값이 참이라면 shade 선택지가 필요 없음 |
| child | 없다면 자기 자신의 value를 값으로 가짐 (ex: Type Inlay -> child: ["inlay"]) <br>여러개가 존재한다면 해당 type의 진료가 포함된 상태 <br>여러개인 경우 method, material, shade도 각각 child의 values에 맞게끔 설정되어야함
 |

## Method

### Props of Methods.
``` JSON
[
  {
    "value": "pfz",
    "label": "PFZ",
    "hasShade": true,
    "types": [
      "coping",
      "crown",
      "pontic",
      "custom_abutment_coping",
      "post_core_crown",
      "post_core_coping"
    ]
  },
  {
    "value": "pfg",
    "label": "PFG",
    "hasShade": true,
    "types": [
      "crown",
      "pontic",
      "custom_abutment_coping",
      "post_core_crown",
      "post_core_coping"
    ]
  },
  {
    "value": "pfm",
    "label": "PFM",
    "hasShade": true,
    "types": [
      "crown",
      "pontic",
      "custom_abutment_coping",
      "post_core_crown"
    ]
  },
  {
    "value": "pfm_post_core_coping",
    "label": "PFM",
    "hasShade": true,
    "types": [
      "post_core_coping"
    ]
  },
  {
    "value": "pfg_no_shade",
    "label": "PFG",
    "types": [
      "coping"
    ]
  },
  {
    "value": "pfm_no_shade",
    "label": "PFM",
    "types": [
      "coping"
    ]
  },
  {
    "value": "collarless",
    "label": "Collarless",
    "hasShade": true,
    "noneShades": [
      "wax"
    ],
    "types": [
      "coping",
      "custom_abutment_coping",
      "post_core_coping"
    ]
  },
  {
    "value": "e_max",
    "label": "e.max",
    "types": [
      "coping",
      "custom_abutment_coping",
      "post_core_coping"
    ]
  },
  {
    "value": "lisi",
    "label": "LiSi",
    "types": [
      "coping",
      "custom_abutment_coping",
      "post_core_coping"
    ]
  },
  {
    "value": "partial_denture_coping",
    "hasShade": true,
    "label": "Partial Denture Coping",
    "types": [
      "denture_coping"
    ]
  },
  {
    "value": "primary_telescopic_crown_pfg",
    "label": "Primary Telescopic Crown - PFG",
    "types": [
      "denture_coping"
    ]
  },
  {
    "value": "primary_telescopic_crown_pfm",
    "label": "Primary Telescopic Crown - PFM",
    "types": [
      "denture_coping"
    ]
  },
  {
    "value": "secondary_telescopic_crown_pfg",
    "label": "Secondary Telescopic Crown - PFG",
    "types": [
      "denture_coping"
    ]
  },
  {
    "value": "secondary_telescopic_crown_pfm",
    "label": "Secondary Telescopic Crown - PFM",
    "types": [
      "denture_coping"
    ]
  },
  {
    "value": "anatomic",
    "label": "Anatomic",
    "types": [
      "crown",
      "pontic"
    ]
  },
  {
    "value": "temporary",
    "label": "Temporary",
    "types": [
      "crown",
      "pontic",
      "implant_crown",
      "custom_abutment_implant_crown",
      "post_core_crown"
    ]
  },
  {
    "value": "temporary_no_method",
    "hasShade": true,
    "label": "Temporary",
    "types": [
      "partial_denture"
    ]
  },
  {
    "value": "layered",
    "label": "Layered",
    "types": [
      "crown",
      "post_core_crown"
    ]
  },
  {
    "value": "cut_back",
    "label": "Cut Back",
    "types": [
      "pontic"
    ]
  },
  {
    "value": "laminate",
    "label": "Laminate",
    "types": [
      "veneer"
    ]
  },
  {
    "value": "screw_type",
    "label": "Screw Type",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "cementation_type",
    "label": "Cementation Type",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "scrp",
    "label": "SCRP",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "screw_type_layered",
    "label": "Screw Type - Layered",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "screw_type_pfz",
    "hasShade": true,
    "label": "Screw Type - PFZ",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "screw_type_pfg",
    "hasShade": true,
    "label": "Screw Type - PFG",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "screw_type_pfm",
    "hasShade": true,
    "label": "Screw Type - PFM",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "cementation_type_layered",
    "label": "Cementation Type - Layered",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "cementation_type_pfz",
    "hasShade": true,
    "label": "Cementation Type - PFZ",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "cementation_type_pfg",
    "hasShade": true,
    "label": "Cementation Type - PFG",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "cementation_type_pfm",
    "hasShade": true,
    "label": "Cementation Type - PFM",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "scrp_layered",
    "label": "SCRP - Layered",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "scrp_pfz",
    "hasShade": true,
    "label": "SCRP - PFZ",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "scrp_pfg",
    "hasShade": true,
    "label": "SCRP - PFG",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "scrp_pfm",
    "hasShade": true,
    "label": "SCRP - PFM",
    "types": [
      "implant_crown",
      "custom_abutment_implant_crown"
    ]
  },
  {
    "value": "framework_partial_denture",
    "hasShade": true,
    "label": "Framework",
    "types": [
      "partial_denture"
    ]
  },
  {
    "value": "wax_rim",
    "hasShade": true,
    "label": "Wax Rim",
    "types": [
      "partial_denture"
    ]
  },
  {
    "value": "anatomic",
    "label": "Anatomic",
    "types": [
      "post_core_crown"
    ]
  }
]
```

### Description
| Pros  | Description |
| -- | -- |
| value | Method에 대한 고유 값 <br>이 값으로 report가 작성되어야함 |
| label | 표시되는 Method 대한 값 <br>엔드유저에게 노출되는 정보 |
| hasShade | default: false <br>이 값이 참이라면 기본적인 쉐이드 선택이 가능함 |
| noneShades | default: [] <br> hasShade가 참이더라도 쉐이드를 선택할 필요가 없는 material value <br> - ex: collarless method의 경우 hasShade 가 참이지만 wax 소재의경우 쉐이드 선택지를 제공하지 않음|
| types | 이 메소드를 선택할 수 있는 type 값의 배열 |

## Material

### Props of Materials
```JSON
[
  {
    "value": "multi_layered_zirconia",
    "label": "Multi-Layered Zirconia",
    "shade": true,
    "types": [
      "inlay",
      "onlay",
      "post_core",
      "veneer",
      "custom_abutment"
    ],
    "methods": [
      "pfz",
      "collarless",
      "anatomic",
      "layered",
      "cut_back",
      "screw_type",
      "cementation_type",
      "scrp",
      "screw_type_layered",
      "screw_type_pfz",
      "cementation_type_layered",
      "cementation_type_pfz",
      "scrp_layered",
      "scrp_pfz"
    ]
  },
  {
    "value": "zirconia",
    "label": "Zirconia",
    "shade": true,
    "types": [
      "inlay",
      "onlay",
      "post_core",
      "veneer",
      "custom_abutment"
    ],
    "methods": [
      "pfz",
      "anatomic",
      "layered",
      "cut_back",
      "screw_type",
      "cementation_type",
      "scrp",
      "screw_type_layered",
      "screw_type_pfz",
      "cementation_type_layered",
      "cementation_type_pfz",
      "scrp_layered",
      "scrp_pfz"
    ]
  },
  {
    "value": "pmma",
    "label": "PMMA",
    "shade": true,
    "types": [
      "veneer",
      "offset_substructure"
    ],
    "methods": [
      "anatomic",
      "temporary",
      "cut_back",
      "screw_type",
      "cementation_type",
      "scrp",
      "framework",
      "framework_partial_denture"
    ]
  },
  {
    "value": "gold",
    "label": "Gold",
    "shade": false,
    "types": [
      "inlay",
      "onlay"
    ],
    "methods": [
      "collarless",
      "anatomic",
      "pfg",
      "pfg_no_shade",
      "cut_back",
      "screw_type",
      "cementation_type",
      "scrp",
      "screw_type_pfg",
      "cementation_type_pfg",
      "scrp_pfg",
      "primary_telescopic_crown_pfg",
      "secondary_telescopic_crown_pfg"
    ]
  },
  {
    "value": "resin",
    "label": "Resin",
    "shade": true,
    "types": [
      "inlay",
      "onlay",
      "post_core"
    ],
    "methods": [
      ""
    ]
  },
  {
    "value": "lisi",
    "label": "LiSi",
    "shade": true,
    "types": [
      "inlay",
      "onlay",
      "veneer"
    ],
    "methods": [
      "collarless",
      "lisi",
      "anatomic",
      "layered",
      "cut_back",
      "screw_type",
      "cementation_type",
      "scrp",
      "screw_type_layered",
      "cementation_type_layered",
      "scrp_layered"
    ]
  },
  {
    "value": "e_max",
    "label": "e.max",
    "shade": true,
    "types": [
      "inlay",
      "onlay",
      "veneer"
    ],
    "methods": [
      "collarless",
      "anatomic",
      "layered",
      "cut_back",
      "screw_type",
      "cementation_type",
      "scrp",
      "screw_type_layered",
      "cementation_type_layered",
      "scrp_layered",
      "e_max"
    ]
  },
  {
    "value": "metal",
    "label": "Metal",
    "shade": false,
    "types": [
      "post_core",
      "offset_substructure"
    ],
    "methods": [
      "pfm",
      "pfm_no_shade",
      "collarless",
      "partial_denture_coping",
      "anatomic",
      "cut_back",
      "screw_type",
      "cementation_type",
      "scrp",
      "screw_type_pfm",
      "cementation_type_pfm",
      "scrp_pfm",
      "primary_telescopic_crown_pfm",
      "secondary_telescopic_crown_pfm",
      "framework",
      "framework_partial_denture",
      "pfm_post_core_coping"
    ]
  },
  {
    "value": "3d_print",
    "label": "3D Print",
    "shade": true,
    "types": [
      "inlay",
      "onlay",
      "veneer",
      "offset_substructure"
    ],
    "methods": [
      "collarless",
      "anatomic",
      "temporary",
      "layered",
      "cut_back",
      "screw_type",
      "cementation_type",
      "scrp",
      "screw_type_layered",
      "cementation_type_layered",
      "scrp_layered",
      "framework",
      "framework_partial_denture"
    ]
  },
  {
    "value": "glass_ceramic",
    "label": "Glass Ceramic",
    "shade": true,
    "types": [
      "inlay",
      "onlay",
      "veneer"
    ],
    "methods": [
      "anatomic",
      "cut_back"
    ]
  },
  {
    "value": "press_ceramic",
    "label": "Press Ceramic",
    "shade": true,
    "types": [
      "inlay",
      "onlay",
      "veneer"
    ],
    "methods": [
      "anatomic",
      "cut_back"
    ]
  },
  {
    "value": "hybrid_ceramic",
    "label": "Hybrid Ceramic",
    "shade": true,
    "types": [
      "inlay",
      "onlay",
      "veneer"
    ],
    "methods": [
      "anatomic",
      "cut_back"
    ]
  },
  {
    "value": "composite_resin",
    "label": "Composite Resin",
    "shade": true,
    "types": [
      "inlay",
      "onlay",
      "veneer"
    ],
    "methods": [
      "anatomic",
      "cut_back"
    ]
  },
  {
    "value": "wax",
    "label": "Wax",
    "shade": false,
    "types": [
      "inlay",
      "onlay",
      "veneer",
      "offset_substructure",
      "diagnostic_wax_up"
    ],
    "methods": [
      "collarless",
      "anatomic",
      "cut_back",
      "framework",
      "wax_rim",
      "framework_partial_denture"
    ]
  },
  {
    "value": "titanium",
    "label": "Titanium",
    "shade": false,
    "types": [
      "custom_abutment"
    ],
    "methods": [
      "pfm",
      "pfm_no_shade",
      "anatomic",
      "cut_back"
    ]
  },
  {
    "value": "peek",
    "label": "PEEK",
    "shade": true,
    "shadeType": [
      "material_shade"
    ],
    "types": [
      "offset_substructure"
    ],
    "methods": [
      "framework",
      "framework_partial_denture"
    ]
  },
  {
    "value": "cr_co",
    "label": "Cr-Co(Chromium-Cobalt)",
    "shade": false,
    "types": [],
    "methods": [
      "pfm_no_shade"
    ],
    "allowedTypes": [
      "coping"
    ]
  },
  {
    "value": "ni_cr",
    "label": "Ni-Cr(Nickel-Chromium)",
    "shade": false,
    "types": [],
    "methods": [
      "pfm_no_shade"
    ],
    "allowedTypes": [
      "coping"
    ]
  },
  {
    "value": "none",
    "label": "None",
    "shade": true,
    "types": [],
    "methods": [
      "collarless"
    ]
  },
  {
    "value": "stainless_steel",
    "shade": false,
    "label": "Stainless Steel",
    "types": [],
    "methods": [
      "anatomic",
      "cut_back"
    ]
  }
]
```

### Description
| Pros  | Description |
| -- | -- |
| value | Material에 대한 고유 값 <br>이 값으로 report가 작성되어야함 |
| label | 표시되는 Material 대한 값 <br>엔드유저에게 노출되는 정보 |
| shade | default: false <br>이 소재가 기본 shade를 지원하는지 여부 <br>type의 innerFill이 존재한다면 이 값은 무시됨며 shade를 선택하지 않음|
| shadeType | default: [] <br>이 소재가 쉐이드를 지원하는 경우 이 값에 shade value가 존재한다면 해당 쉐이드를 선택지로 제공함 <br>정의되지 않은 경우 기본 쉐이드로 계산됨|
| types | 이 소재를 제공하는 type값  <br>methods와 함께 합집합으로 계산됨 |
| methods | 이 소재를 제공하는 methods값 <br>types와 함께 합집합으로 계산됨 |

## Shade

### Props of Shades
```JSON
[
  {
    "value": "material_shade",
    "label": "Material Shade",
    "items": [
      "None",
      "Natural",
      "White",
      "Pink",
      "Yellow"
    ]
  },
  {
    "value": "vita_classic",
    "label": "Vita Classic",
    "default": true,
    "items": [
      "None",
      "A1",
      "A2",
      "A3",
      "A3.5",
      "A4",
      "B1",
      "B2",
      "B3",
      "B4",
      "C1",
      "C2",
      "C3",
      "C4",
      "D2",
      "D3",
      "D4",
      "0M1",
      "0M2",
      "0M3"
    ]
  },
  {
    "value": "vita_3d_master",
    "label": "Vita 3D Master",
    "default": true,
    "items": [
      "None",
      "1M1",
      "1M2",
      "2L1.5",
      "2L2.5",
      "2M1",
      "2M2",
      "2M3",
      "2R1.5",
      "2R2.5",
      "3L1.5",
      "3L2.5",
      "3M1",
      "3M2",
      "3M3",
      "3R1.5",
      "3R2.5",
      "4L1.5",
      "4L2.5",
      "4M1",
      "5M1",
      "5M2",
      "5M3",
      "0M1",
      "0M2",
      "0M3",
      "0M1.5",
      "0M2.5",
      "0.5M1",
      "0.5M1.5",
      "0.5M2",
      "0.5M2.5",
      "1M1.5",
      "1.5M1",
      "1.5M1.5",
      "1.5M2",
      "1.5M2.5",
      "2M1.5",
      "2M2.5",
      "2.5M1",
      "2.5M1.5",
      "2.5M2",
      "2.5M2.5",
      "2.5M3",
      "3M1.5",
      "3M2.5",
      "3.5M1",
      "3.5M1.5",
      "3.5M2",
      "3.5M2.5",
      "3.5M3",
      "4M1.5",
      "4M2.5",
      "4.5M1",
      "4.5M1.5",
      "4.5M2",
      "4.5M2.5",
      "4.5M3",
      "5M1.5",
      "5M2.5",
      "2L2",
      "2.5L1.5",
      "2.5L2",
      "2.5L2.5",
      "3L2",
      "3.5L1.5",
      "3.5L2",
      "3.5L2.5",
      "4L2",
      "2R2",
      "2.5R1.5",
      "2.5R2",
      "2.5R2.5",
      "3R2",
      "3.5R1.5",
      "3.5R2",
      "3.5R2.5",
      "4R2"
    ]
  },
  {
    "value": "ivoclar",
    "label": "Ivoclar",
    "default": true,
    "items": [
      "None",
      "01",
      "1A",
      "2A",
      "1C",
      "2B",
      "1D",
      "1E",
      "2C",
      "3A",
      "5B",
      "2E",
      "3E",
      "4A",
      "6B",
      "4B",
      "6C",
      "6D",
      "4C",
      "3C",
      "4D",
      "BL1",
      "BL2",
      "BL3",
      "BL4"
    ]
  }
]
```

### Description
| Pros  | Description |
| -- | -- |
| value | Shade에 대한 고유 값 <br>이 값으로 report가 작성되어야함 |
| label | 표시되는 Shade 대한 값 <br>엔드유저에게 노출되는 정보 |
| default | default: false <br>이 쉐이드가 기본 제공되는 쉐이드 여부 |
| items | 이 쉐이드가 제공하는 색상 값 배열 |
