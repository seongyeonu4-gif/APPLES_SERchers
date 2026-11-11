# Demo Interface
## 1. Overview

본 시연 화면은 Friends 영상 속 대화 장면을 활용하여 화자 간 감정 정보가 다음 발화의 감정 예측에 어떻게 활용되는지 보여주는 것을 목표로 한다.

단순히 감정 분석 결과와 그래프를 시각화하는 데 그치지 않고, 관객이 먼저 다음 발화의 감정을 예상한 뒤 Model A와 Model B의 예측 결과를 확인하는 참여형 시연으로 구성한다.

**Demo Process**

1. 영상의 특정 구간을 재생한 후 감정 변화가 나타나기 직전에 일시정지한다.
2. 관객에게 다음 발화의 VAD 값을 예상하도록 요청한다.
3. Model A와 Model B의 예측 결과를 공개한다.
4. 실제 감정값과 모델 예측값을 비교한다.
5. 두 모델의 결과 차이를 통해 상대방 감정 정보의 추가 효과를 설명한다.

---

## 2. Screen Layout

시연 화면은 다음 다섯 가지 영역으로 구성한다.

### 2.1 Video Player

Friends 영상의 선택된 장면을 재생한다.

- 영상 재생 및 일시정지
- 영상 구간 이동
- 현재 영상 재생 시간 표시
- 감정 예측이 필요한 지점에서 일시정지

### 2.2 Current Utterance

현재 대화의 발화 정보를 표시한다.

- 현재 발화자의 이름 또는 ID
- 발화 시작 및 종료 시간
- 현재까지 진행된 발화 내용
- 다음 발화의 예측 대상 화자 표시

### 2.3 Audience Prediction

관객이 직접 다음 발화의 감정을 예상하는 영역이다.

- 다음 발화의 Valence 예상값
- 다음 발화의 Arousal 예상값
- 다음 발화의 Dominance 예상값
- 관객의 예상 결과 제출 및 표시

관객의 예상값은 모델의 예측값 및 실제 감정값과 비교하기 위한 별도의 참고 데이터로 활용한다.

### 2.4 Model Prediction Results

Model A와 Model B의 예측 결과를 비교하여 표시한다.

| Model | Input Information | Output |
|---|---|---|
| Model A | 자신의 이전 감정 정보 | 다음 발화의 VAD 예측값 |
| Model B | 자신의 이전 감정 + 상대방의 감정 정보 | 다음 발화의 VAD 예측값 |

- Model A의 VAD 예측값
- Model B의 VAD 예측값
- 두 모델의 예측 차이
- 실제 감정값과의 오차 비교

### 2.5 Actual Emotion & Comparison

실제 감정값과 관객 및 모델의 예측 결과를 비교한다.

- 실제 Valence 값
- 실제 Arousal 값
- 실제 Dominance 값
- 관객의 예상값과 실제값 비교
- Model A와 Model B의 예측값과 실제값 비교

실제 VAD 기준값은 확보된 주석 데이터 또는 별도 수작업 주석 결과를 활용한다. 수작업 주석을 사용하는 경우 이를 객관적인 정답값으로 단정하지 않고 주석 기준과 한계를 함께 명시한다.

---

## 3. Demo Process

시연은 다음 순서로 진행한다.

### Step 1. Video Playback

- 선정된 Friends 장면 재생
- 현재 화자 및 발화 내용 표시
- 감정 변화가 나타날 것으로 예상되는 구간 탐색

### Step 2. Pause & Audience Participation

- 하이라이트 부분 직전에서 영상 일시정지
- 다음 발화의 감정 예측 대상 화자 안내
- 관객에게 VAD 값 예상 요청
- 관객의 예상 결과 입력 및 저장

### Step 3. Model Prediction

- Model A의 예측 결과 공개
- Model C의 예측 결과 공개
- 두 모델의 VAD 값 비교

### Step 4. Actual Value Reveal

- 다음 발화 영상 재생
- 해당 발화의 실제 VAD 기준값 공개
- 관객 및 두 모델의 예측 결과 비교

### Step 5. Result Interpretation

- Model A와 Model B의 예측 차이 확인
- 실제값과 각 모델 예측값 사이의 오차 비교
- 상대방 감정 정보가 예측에 미친 영향 설명

---

## 4. Synchronization

영상과 발화별 감정 정보는 발화의 시작 시간 및 종료 시간을 기준으로 연결한다.

1. 영상의 현재 재생 시간을 확인한다.
2. 해당 시간에 대응하는 발화 데이터를 찾는다.
3. 현재 화자와 발화 내용을 표시한다.
4. 예측 대상 발화와 화자 정보를 확인한다.
5. 해당 발화에 대한 Model A와 Model B의 예측값을 연결한다.
6. 실제 VAD 기준값을 해당 발화에 연결한다.

영상의 재생, 일시정지 및 구간 이동 상황에서도 발화 정보와 감정 데이터가 올바르게 연결되는지 확인한다.

---

## 5. Main Features

| Feature | Description |
|---|---|
| Video Playback | 영상 재생 및 일시정지 |
| Time Navigation | 원하는 영상 구간으로 이동 |
| Speaker Display | 현재 및 예측 대상 화자 표시 |
| Utterance Display | 발화 내용 표시 |
| Audience Prediction | 관객의 VAD 예상값 입력 |
| Model A Prediction | Model A의 다음 발화 VAD 예측 |
| Model C Prediction | Model C의 다음 발화 VAD 예측 |
| Actual Value Display | 실제 VAD 기준값 표시 |
| Result Comparison | 관객 및 모델의 예측 결과 비교 |
| Timeline Synchronization | 영상 시간과 발화 정보 연결 |

---

## 6. Testing

시연 전 다음 항목을 확인한다.

- 영상 재생 시간과 발화 정보가 일치하는가?
- 예측 대상 화자와 다음 발화가 정확하게 연결되는가?
- 관객이 VAD 예상값을 입력할 수 있는가?
- Model A와 Model B의 예측값이 올바르게 표시되는가?
- 실제 VAD 기준값이 정확한 발화에 연결되는가?
- 모델 예측값과 실제값의 비교가 올바르게 표시되는가?
- 영상 재생 및 구간 이동 시 발화 정보가 올바르게 갱신되는가?

*Note: 실제 구현 기능과 화면 구성은 개발 진행 상황에 따라 업데이트한다.*
