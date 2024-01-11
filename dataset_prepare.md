# Dataset 준비
## 준비과정에서 데이터 저장소
- 수집된 데이터 집합(text, OCR 등): NAS에 저장
- Formatted text data --> GitHub Respository로 관리
- 

## Dataset 구성도 예

    my_dataset_repository/
    ├── README.md
    ├── my_dataset_repository.py    # loading dataset script
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
    