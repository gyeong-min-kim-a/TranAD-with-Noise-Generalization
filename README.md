# TranAD-with-Noise-Generalization

### 연구 개요

본 연구는 **산업 환경에서 수집되는 시계열 데이터에 포함될 수 있는 노이즈를 제어함으로써**, 이상 탐지 모델의 실질적인 성능 개선을 목표로 하였습니다. 일반적으로 실제 산업 환경에서는 센서 오류, 외부 간섭 등 다양한 원인으로 인해 노이즈가 포함되며, 이는 이상 탐지 모델의 성능 저하로 이어질 수 있기 때문입니다. 이에 따라 본 연구에서는 **노이즈 제거 및 일반화를 위한 레이어를 TranAD 모델에 추가**하여, 성능 변화 여부를 분석했습니다.

- 배경 연구 : 동일 github 내 SmartFactory_AnomalyDetection 레포지터리 확인

---

### 제안 방법

<img width="736" alt="image" src="https://github.com/user-attachments/assets/decc090c-8e53-4cb7-9a8c-ba87c8831114" />

- 인코더의 출력(latent vector)을 기반으로, 가우시안 분포에서 새로운 벡터를 샘플링
- 기존 벡터를 해당 가우시안 기반 벡터로 **치환**
- 노이즈 제거 레이어 적용 비율을 **0%부터 100%까지 10% 단위**로 점진적으로 증가시키며 실험 진행

---

### 실험 결과

- 일부 데이터셋에서 **20~40% 구간의 적용 비율에서 의미 있는 성능 향상**이 관찰됨
- 이는 적절한 수준의 노이즈 제거가 이상 탐지 성능을 높일 수 있음을 시사함

![image](https://github.com/user-attachments/assets/27eef1e8-edad-4d4b-b714-63ead6d6cc67)

---

### 참고 및 기반 연구

본 연구는 아래 TranAD 모델 및 공식 구현 코드를 기반으로 진행되었습니다:

- [TranAD GitHub Repository](https://github.com/imperial-qore/TranAD)

---

