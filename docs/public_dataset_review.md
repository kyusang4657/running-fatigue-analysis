# 공개 러닝·웨어러블 데이터셋 검토

## 1. 목적

본 문서는 러닝 피로 변화 분석 연구에 활용 가능한 공개 러닝·웨어러블 데이터셋을 조사하기 위한 문서이다.

본 연구의 핵심 범위는 **러닝 피로 변화 분석**이다. 따라서 러닝, 웨어러블 센서, IMU, 심박수, 러닝 로그와 관련된 데이터셋을 우선 검토한다.

AI Hub에 한정하지 않고 UCI, Zenodo, Figshare, PhysioNet 등 공개 데이터 저장소를 함께 검토한다. 보행 또는 일반 운동 데이터는 러닝 데이터가 부족할 경우 feature 설계 참고용으로만 검토한다.

---

## 2. 검색 키워드

- running
- runner fatigue
- fatigued runners
- running IMU
- wearable running dataset
- heart rate running dataset
- smartphone IMU
- human activity recognition
- 러닝
- 달리기
- 웨어러블
- IMU
- 센서
- 심박
- 피로
- 보행
- 헬스케어
- 운동 로그

---

## 3. 후보 데이터셋 정리

| 번호 | 데이터셋 이름 | 출처 | 데이터 유형 | 러닝 관련성 | 라벨 유형 | 활용 가능성 |
|---|---|---|---|---|---|---|
| 1 | Multivariate Time Series Data of Fatigued and Non-Fatigued Runners | Zenodo | 허리 부착 IMU 시계열 | 매우 높음 | 피로/비피로 러닝 구간 | 모델 학습 후보 / 최우선 |
| 2 | PAMAP2 Physical Activity Monitoring | UCI | 3개 IMU, 심박수, activity label | 높음 | 활동 종류, 운동 강도 추정 가능 | baseline 모델 및 feature 설계 |
| 3 | Running Exercise IMU Dataset | Figshare | 러닝 drill raw IMU | 높음 | 러닝 exercise 종류 확인 필요 | 러닝 IMU feature 설계 |
| 4 | Human Activity Recognition Using Smartphones | UCI | 허리 착용 스마트폰 가속도·자이로 | 직접 러닝은 없음 | 걷기/계단/앉기 등 activity label | 스마트폰 IMU 전처리 참고 |
| 5 | PPG-DaLiA | UCI | 손목/가슴 웨어러블 생체신호, 가속도 | 러닝 직접성 낮음 | 심박 추정용 ground truth | 심박수·움직임 융합 참고 |
| 6 | PhysioNet Wearable Device Dataset from Exercise Sessions | PhysioNet | 웨어러블 생체신호, 운동 세션 | 러닝 직접성 확인 필요 | 운동 세션 범주 | 보조 생체신호 참고 |

---

## 4. 검토 기준

| 기준 | 설명 |
|---|---|
| 러닝 관련성 | 실제 러닝 또는 러닝과 유사한 이동 데이터가 포함되어 있는가 |
| 센서 데이터 여부 | IMU, 심박수, 웨어러블 로그 등이 포함되어 있는가 |
| 라벨 존재 여부 | 피로도, 운동 강도, 운동 상태 등의 라벨이 있는가 |
| 직접 데이터와의 유사성 | Galaxy 스마트폰 IMU 데이터와 비교 가능한 구조인가 |
| 모델 학습 가능성 | 지도학습에 사용할 수 있는 라벨이 있는가 |
| 라이선스 | 연구/교육 목적으로 사용 가능한가 |
| 다운로드 가능성 | 회원가입, 신청, 용량, 파일 구조를 실제로 처리할 수 있는가 |

---

## 5. 우선순위 기준

| 우선순위 | 데이터 유형 | 활용 방식 |
|---|---|---|
| 1순위 | 러닝 + IMU + 피로도/강도 라벨 | baseline 모델 학습 후보 |
| 2순위 | 러닝 + IMU/웨어러블 센서 | feature 설계 및 모델 학습 후보 |
| 3순위 | 러닝 로그 + 심박수/페이스 | 보조 feature 설계 |
| 4순위 | 보행 + IMU | 러닝 데이터 부족 시 참고용 |
| 5순위 | 일반 피트니스/재활운동 | 원칙적으로 제외 또는 참고만 |

---

## 6. 초기 판단

현재 가장 우선적으로 검토할 데이터셋은 다음 세 가지이다.

1. **Multivariate Time Series Data of Fatigued and Non-Fatigued Runners**
   - 러닝 피로 분석과 직접적으로 관련되어 있으므로 최우선 후보이다.
   - 허리 부착 IMU 데이터이므로 직접 수집할 Galaxy 스마트폰 허리 고정 데이터와 비교 가능성이 있다.

2. **PAMAP2 Physical Activity Monitoring**
   - 러닝 활동, IMU, 심박수를 포함하므로 baseline feature 설계에 유용하다.
   - 피로도 라벨은 없을 가능성이 높으므로 피로도 모델로 과장하지 않는다.

3. **Running Exercise IMU Dataset**
   - 러닝 동작의 raw IMU 데이터이므로 러닝 IMU feature 설계에 활용 가능하다.
   - 피로도 라벨 여부는 추가 확인이 필요하다.

---

## 7. 참고 링크

| 데이터셋 | 링크 |
|---|---|
| Multivariate Time Series Data of Fatigued and Non-Fatigued Runners | https://zenodo.org/records/7997851 |
| PAMAP2 Physical Activity Monitoring | https://archive.ics.uci.edu/dataset/231/pamap2%2Bphysical%2Bactivity%2Bmonitoring |
| Running Exercise IMU Dataset | https://figshare.com/articles/dataset/Running_Exercise_IMU_Dataset/22117235 |
| Human Activity Recognition Using Smartphones | https://archive.ics.uci.edu/dataset/240/human%2Bactivity%2Brecognition%2Busing%2Bsmartphones |
| PPG-DaLiA | https://archive.ics.uci.edu/ml/datasets/PPG-DaLiA |
| PhysioNet Wearable Device Dataset | https://physionet.org/content/wearable-device-dataset/ |

---

## 8. 정리

공개 데이터셋은 직접 수집 데이터의 대체재가 아니라, baseline 모델 학습 또는 feature 설계 참고용으로 활용한다.

최종 연구 범위는 **러닝 피로 변화 분석**으로 유지한다.

직접 수집 데이터는 대규모 모델 학습용이 아니라, 공개 데이터 기반 분석 방법과 개인 기준선 RFCI가 실제 개인 러닝 데이터에 적용 가능한지 확인하는 외부 파일럿 테스트 데이터로 사용한다.
