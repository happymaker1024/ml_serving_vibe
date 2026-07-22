# ml_serving_vibe

전기차 에너지 소비량 예측 모델을 학습하고, Gradio 기반 웹 앱으로 서빙하는 프로젝트입니다.

## 프로젝트 개요
- 전기차 에너지 소비량을 예측하기 위한 회귀 모델 학습
- 학습된 모델을 파일로 저장하고 재사용 가능하도록 구성
- CSV 파일 업로드를 통해 예측 결과를 확인할 수 있는 웹 앱 제공

## 주요 기능
- 노트북에서 모델 학습 및 저장
- 학습된 LinearRegression 모델과 스케일러를 불러와 예측 수행
- CSV 파일 드래그 앤 드롭 업로드 지원
- Submit 버튼으로 예측 실행
- Clear 버튼으로 업로드 상태 초기화
- 예측 결과를 표 형태로 출력하고 CSV 파일로 다운로드 가능

## 프로젝트 구조
```text
ml_serving/
├── app/
│   └── app.py
├── data/
│   ├── ev_energy_consumption.csv
│   └── test_data.csv
├── model/
│   ├── linear_regression_model.pkl
│   └── scaler.pkl
├── practice_준비.ipynb
└── README.md
```

## 개발 환경
- Python 3.12
- 가상환경: .venv
- 주요 패키지:
  - gradio
  - pandas
  - scikit-learn
  - joblib
  - numpy
  - ipykernel

## 환경 설정
```bash
python -m venv .venv
.venv\Scripts\activate
pip install --upgrade pip
pip install gradio pandas scikit-learn joblib numpy ipykernel
```

## 노트북 환경 연결
```bash
python -m ipykernel install --user --name ml-serving --display-name "Python (ml-serving)"
```

## 실행 방법
1. 노트북에서 모델을 학습하고 아래 경로에 저장합니다.
   - model/linear_regression_model.pkl
   - model/scaler.pkl
2. Gradio 앱을 실행합니다.
```bash
python app/app.py
```
3. 브라우저에서 접속한 뒤 CSV 파일을 업로드하고 예측을 실행합니다.

## 참고 사항
- 예측에 사용할 CSV 파일의 컬럼 구조는 학습 시 사용한 입력 형식과 일치해야 합니다.
- 모델 파일과 스케일러 파일은 반드시 model/ 폴더에 저장해야 합니다.
