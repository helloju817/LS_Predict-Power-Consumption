# 🏆 프로젝트: DACON 공모전 최종 결과물

LS 빅데이터 교육과정에서 진행한 DACON 공모전 프로젝트 최종 결과물입니다.  
본 프로젝트에서는 시계열 분석(ARIMA, SARIMA, Prophet) 및 회귀 분석(XGBoost) 기반의 모델 연구를 진행했습니다.  
다양한 시계열 모델을 비교 분석하여 주기성과 패턴을 심층적으로 이해하고, 이를 기반으로 최적의 예측 모델을 구축하였습니다.  
또한, 분석 결과를 바탕으로 비즈니스 모델 목업을 제시하여 실무 적용 역량을 배양하였습니다.  
이러한 경험을 통해 데이터 분석과 비즈니스 통찰을 결합하여 실질적인 솔루션을 제안할 수 있는 능력을 갖추게 되었습니다.  

## 📌 프로젝트 설명

### 개요
- **건물 정보와 기상 정보를 활용한 전력사용량 예측**
- **평가 기준:** SMAPE

### 데이터 설명
#### `train.csv`
- `num` : 건물 번호 (1~60)  
- `date_time` : 2020년 6월 1일 부터 2020년 8월 24일까지의 데이터 1시간 단위  
- `전력사용량(kWh)` : y값 (타겟컬럼)  
- `기온(°C)` : 기온 (1시간 단위 관측 데이터)  
- `풍속(m/s)` : 풍속 (1시간 단위 관측 데이터)  
- `습도(%)` : 습도 (1시간 단위 관측 데이터)  
- `강수량(mm)` : 강수량 (1시간 단위 관측 데이터)  
- `일조(hr)` : 일조 (1시간 단위 관측 데이터)  
- `비전기냉방설비운영` : 비전기 냉방 설비 운영 여부 (0 또는 1)  
- `태양광보유` : 태양광 보유 여부 (0 또는 1)  
- **`train.shape`: (122400, 10)**  

#### `test.csv`
- `num` : 건물 번호 (1~60)  
- `date_time` : 2020년 8월 25일 부터 2020년 8월 31일까지의 데이터 1시간 단위  
- `기온(°C)` : 기온 (3시간 단위 예측 데이터)  
- `풍속(m/s)` : 풍속 (3시간 단위 예측 데이터)  
- `습도(%)` : 습도 (3시간 단위 예측 데이터)  
- `강수량(mm)` : 강수량 (6시간 단위 예측 데이터)  
- `일조(hr)` : 일조 (3시간 단위 예측 데이터)  
- `비전기냉방설비운영` : 비전기 냉방 설비 운영 여부  
- `태양광보유` : 태양광 보유 여부 (1만 있음)  
- **`test.shape`: (10080, 9)**  

## 📊 결론: SMAPE
- **ARIMA** : 1.156  
- **SARIMA** : 0.804  
- **Prophet** : 0.833  
- **XGBoost** : 0.212  

다양한 시계열 모델을 비교 분석하였으며, 최종적으로 XGBoost 모델을 활용한 회귀 분류 예측이 가장 우수한 성능을 보였습니다.  
예측 모델의 성능을 평가한 결과, XGBoost 모델이 다른 모델들에 비해 SMAPE와 RMSE 지표에서 가장 낮은 값을 기록하였습니다.  
최종적으로, XGBoost를 통해 DACON public점수 5.69, private점수 5.03을 기록하였습니다.  

## 🚀 앞으로 보완할 점 및 느낀 점

선행 연구: [2022 한이음 ICT멘토링 프로젝트](https://github.com/helloju817/HANIUM_ICT_Predict-Power-Consumption)  
상단의 2022 한이음 ICT멘토링에서 수행한 전력 예측 프로젝트에서는 종관기상관측(ASOS) 데이터와 한국전력 거래소의 5분 단위 전력 수급 현황 데이터를 활용하여 회귀 모델에 중점을 두고 분석을 진행하였습니다.  
이를 통해 전력 수요와 기상 데이터 간의 관계를 규명하고, 회귀 분석을 통해 예측 모델을 구축하는 데 집중하였습니다.  
회귀 모델을 활용한 이 프로젝트는 데이터 분석 기법의 기초를 다지는 데 큰 도움이 되었으며, 다양한 회귀 모델을 비교하고 최적의 성능을 도출하는 경험을 쌓을 수 있었습니다.  
<br>  
반면, 이번 빅데이터 교육 과정에서 진행한 DACON 전력 예측 프로젝트에서는 시계열 분석에 중점을 두었습니다.  
전통적인 시계열 모델인 ARIMA를 시작으로, SARIMA, Prophet까지 다양한 주기성을 파악하며 분석을 진행하였습니다.  
이러한 과정에서 통계적 방법론에 대한 깊이 있는 이해를 바탕으로, 시계열 분석의 고급 기법들을 적용하고, 데이터의 주기성과 패턴을 심층적으로 분석하였습니다.  
특히, 시계열 분석에 대한 학습은 단순히 교육 과정에 그치지 않고, 논문이나 다양한 해외 자료를 참고하여 스스로 공부하며 적용하였습니다.  
이 프로젝트의 결과는 단순한 모델 적용을 넘어, 데이터의 주기성과 패턴을 이해하고 분석하는 능력을 배양하는 데 큰 의미가 있었습니다.  
<br>  
문제 분석에서 그치지 않고, 분석 결과를 바탕으로 비즈니스 모델까지 구축하였습니다.  
전력 수요 예측 데이터를 활용하여 전력 사용량을 최적화하고, 효율적인 에너지 관리 시스템을 설계하는 데 필요한 기초 자료를 제공하였습니다.  
이를 통해 에너지 절감과 비용 효율화를 동시에 달성할 수 있는 솔루션을 제안하였으며, 실제 비즈니스에 적용할 수 있는 모델을 구축하는 데 성공하였습니다.  
이와 같은 경험은 데이터 분석 분야에서 회귀 모델과 시계열 데이터의 중요성을 깨닫게 해주었으며, 다양한 모델과 방법론을 활용하여 데이터를 심층적으로 분석하고, 이를 통해 실질적인 비즈니스 가치를 창출하는 능력을 배양하는 데 큰 도움이 되었습니다.  

## 📅 빅데이터 교육 프로젝트
(2024/06 ~ 2024/06)
