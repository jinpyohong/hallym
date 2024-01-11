# Dataset 준비
## 구축 및 관리해야 할 Repository의 종류

- 수집된 데이터 집합(text, OCR 등): NAS에 저장
- Original text data repository (`name_org`)
  - 수집된 데이터를 가공하여 정리하여 formatted text data 파일들로 repository 구축
  - GitHub Respository로 데이터 추가/축적하고 version 관리
  - develop branch에서 수정, 정리하고 main branch에 release해야 함
  - LFS가 필요없게 파일 크기를 작게 유지한다 (< 50MB)
  - 한글 text를 포함하는 파일은 utf-8 encoding되어야 함 
- Huggingface Datasets API로 활용가능한 dataset repository (`name`)
  - Original text data repository에서 release되는 최신 버전을 Dataset화 --> Huggingface dataset repository 구조를 적절하게 정의하여 재편성
  - invalid한 raw들을 수정/삭제하고, data의 유효성을 검증해야 함 
  - 필요하다면, 하나의 Dataset을 여러 용도(or task)로 사용할 수 있게 configuation을 정의해야
  - GitHub or Huggingface Hub?
    - 1안) Huggingface Hub에 Respository를 직접 구축하고 버전 관리
    - 2안) GitHub에 repository를 구축하고 version 관리하고, 최신 release를 Huggingface Hub에 fork하여 사용
      - ?? Huggingface에서 fork가 가능한지 검토 필요


## Dataset Repository 구성도 예

    my_dataset_repository/
    ├── README.md
    ├── my_dataset_repository.py    # loading dataset script (optional)
    └── data/
        └── 살인/           # config name
            ├── train/
                ├── 판결문-00000.jsonl
                └── 판결문-10223.jsonl
            ├── valid/      # optional
                └── 판결문-*.jsonl
            └── test/
                └── 판결문-*.jsonl
        ...
        └── 사기/           # config name
            ...

하나의 data file에는 1 or more raws 를 담을 수 있다.
수정 및 추가는 이 단위 파일에서 이루어진다.

Filename에 sequence number를 메기고 `glob` 패턴으로 지칭 가능해야 한다.

