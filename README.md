### 🎁 Tunnel
- [VisualCavity 개발 현황 (깃허브 블로그)](https://kim-src.github.io/categories/visualcavity/)
- [Kim의 개발 프로젝트 모음 (깃허프 레포지토리)](https://github.com/Kim-src/All-Projects)
- [링크드인 프로필 (Chang-Seong Kim)](https://www.linkedin.com/in/chang-seong-kim-7826142a0/)

<br>

## ✅ VisualCavity AI 소개
> - 개발 환경 : Google Colab
> - 개발 목적 : GPR 데이터 분석 수준 하향
> - 개발 내용 : 싱크홀(공동) 자동 분석 프로그램(VIsualCavity) 제작을 위한 이미지 학습 AI 모델
> - 개발 역량 : Python 라이브러리, XML 파싱, AI의 이미지 학습 과정 및 딥러닝 모델 이해
> - 주요 자료 : 지하 물리 탐사로 획득한 70,732장의 싱크홀 또는 지장물 이미지
> - 개발에 필요했던 기능 :  
> <img alt="Google Colab" src="https://img.shields.io/badge/-Google_Colab-F9AB00?style=flat-square&logo=google-colab&logoColor=white" /> <img alt="Python" src="https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white" /> <img alt="tensorflow" src="https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=flat-square&logo=TensorFlow&logoColor=white" />
> 
> #### 🎯 개발 현황
> - VisualCavity AI는 싱크홀 데이터 분석 수준을 감소시키기 위해 개발중인 AI 모델입니다.
> - 현재 이미지 학습을 위한 초기 AI 모델은 구축되었습니다.
> - 추후 준비된 7만장 이상의 이미지를 학습시켜서 AI의 이미지 분석 수준을 상승시킬 예정입니다.
> 
> #### 🎯 GPR 데이터 분석
> - 싱크홀 이슈가 매년 꾸준히 대두되면서 국가에서는 땅꺼짐 사고를 예방하기 위한 사업을 진행중입니다.
> - 땅꺼짐 사고를 예방하기 위해서는 GPR이라는 레이더 장치를 이용하여 도로 하부를 조사해야 됩니다.
> - 이때 도로 하부에 빈 공간(싱크홀)이 어느 곳에 있는지, 또는 없는지는 조사하기 전까지 알 수 없습니다.
> - 따라서 도로 일부가 아닌 도로 전체에 대해 조사해야 되고 방대한 양의 GPR 데이터가 수집됩니다.
> - 수집된 GPR 전자기파 데이터는 전문 프로그램에서 시각화되어 보여집니다.
> - GPR 데이터 분석이란 이 시각화 된 데이터에서 싱크홀의 유무를 파악하는 것입니다.
> 
> #### 🎯 개발 목적의 이유
> - GPR 데이터의 형태는 지하 구조 또는 물질에 따라 다르게 보입니다.
> - 그래서 도로 하부 2m 이내의 관로, 자갈, 싱크홀 등의 분포 위치를 대략적으로 파악할 수 있습니다.
> - 그런데 이 형태는 분석가의 분석 역량에 따라 다르게 판단됩니다.
> - 예를들면 싱크홀 형태인줄 알고 복구를 위해 도로를 뚫었더니 가스관로인 경우입니다.
> - 이 경우 땅꺼짐으로 끝날 사고가 더욱 안타까운 가스배관 폭발 사고로 될 수 있습니다.
> - 따라서 데이터 분석에 심혈을 기울여야 되는데, 분석해야 되는 데이터량이 하루에 수 km로 방대합니다.
> - 그렇기 때문에 싱크홀 분석을 돕는 AI 모델이 개발되면 데이터 분석 수준이 일부 낮아질 것으로 예상됩니다.

<br>

## 🚀 VisualCavity AI 개발 전체 현황 (현재 ver. 0.1.3)
> - v0.1.0 : Trainin Dataset 싱크홀 이미지 1장 학습 (2024-01-09)
>   - 기초 모델 구축 및 단일 싱크홀 이미지 학습
> - v0.1.3 : 싱크홀 및 지장물 이미지에 대한 Training, Validation, Testing Dataset 구조 변경 (2024-02-27)
>   - 기존 : 총 192,120장, Training 170,774장, Validation Dataset 21,346장
>   - 변경 : 총 70,732장, Training 49,514장, Validation 10,609장, Testing Dataset 10,609장  
> - v0.1.7 : Testing Dataset을 포함한 VisualCavity AI 개발 계획 재구성
>   - 현재 : AI 모델 개발 초기에 기획했던 내용
>   - 추후 : 보다 전문적인 AI 모델 개발 기획 (v0.1.7 이후 전반적인 개발 계획 변경 예정)
> - v0.2.0 : Train 싱크홀 이미지 11,205장 학습 완료
>   - 기존 모델에 싱크홀 이미지만이 아닌 지장물 이미지를 추가적으로 학습시킴
>   - 싱크홀 및 지장물을 구분할 수 있는 능력을 상승시킴
> - v0.3.0 : Validation 싱크홀 이미지 1,401장을 이용하여 학습된 이미지 11,205장에 대한 검토 완료
> - v0.4.0 : Train 싱크홀 이미지 34,136장 학습 완료
> - v0.5.0 : Validation 싱크홀 이미지 장을 이용하여 학습된 이미지 34,136장에 대한 검토 완료
> - v0.4.0 : Train 싱크홀 이미지 34,136장 학습 완료
> - v0.5.0 : Validation 싱크홀 이미지 장을 이용하여 학습된 이미지 34,136장에 대한 검토 완료
> - v0.6.0 : Train 싱크홀 및 지장물 이미지 170,774장 학습 완료
> - v0.7.0 : Validation 이미지 21,346장을 이용하여 학습된 이미지 170,774장에 대한 검토 완료
> - v0.8.0 : Train 싱크홀 이미지 98,435장 학습 완료
> - v0.9.0 : Validation 싱크홀 이미지 12,304장을 이용하여 학습된 이미지 11,205장에 대한 검토 완료
> - v1.0.0 : AI를 이용한 싱크홀 분석 모델 생성(싱크홀 분석 프로그램에 본 AI 모델을 적용시킬 예정)

<br>

***

<br>
<br>
<br>
