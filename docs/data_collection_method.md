# 데이터 수집 방법

## 1. 목적

본 문서는 러닝 피로 변화 분석 연구에서 사용할 데이터 수집 방법을 정리하기 위한 문서이다.

본 연구는 Galaxy 스마트폰의 IMU 센서 데이터를 핵심 데이터로 사용하고, Galaxy Fit3와 Samsung Health에서 확인할 수 있는 운동 기록, 심박수, 수면 시간 등은 선택 보조 데이터로 활용한다.

---

## 2. 현재 테스트 환경

| 구분 | 내용 |
|---|---|
| 스마트폰 | Galaxy 스마트폰 |
| 웨어러블 | Galaxy Fit3 |
| 건강 앱 | Samsung Health |
| 개발 환경 | Python, PyCharm |
| 데이터 형식 | CSV 중심 |

---

## 3. 데이터 수집 구조

본 연구의 데이터 수집 구조는 다음과 같다.

```text
Galaxy 스마트폰
  └─ IMU 센서 데이터 수집
      ├─ accelerometer: acc_x, acc_y, acc_z
      └─ gyroscope: gyro_x, gyro_y, gyro_z

Galaxy Fit3 + Samsung Health
  └─ 선택 보조 데이터 확인
      ├─ 평균 심박수
      ├─ 최대 심박수
      ├─ 수면 시간
      ├─ 최근 운동 기록
      └─ 운동 거리 / 시간 / 페이스