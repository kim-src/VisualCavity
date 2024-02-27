## 🔔 1. Methodology
### 📌 AI 초기 모델 구축에 사용된 이미지 데이터
> - AI 초기 모델 구축을 위해 준비된 싱크홀 및 지장물 이미지 데이터는 총 192,120장이었습니다.
> - 이 데이터 세트 중 VisualCavity AI v0.1.0 구축에 사용된 이미지 데이터는 1장(단일)입니다.
> - 이는 향후 AI 모델의 프로토타입(prototype) 구축을 위한 테스트 목적이었습니다.
> - 전체 이미지 데이터는 3차원 중 일부였으며 종단면(Y-Z) 및 평단면(X-Y)으로 구성되었습니다.

### 📌 보다 빠른 AI 초기 모델 구축
> - 이번 프로젝트의 목적은 AI 초기 모델의 빠른 구축입니다.
> - 3D-GPR 데이터에서 AI가 학습하기 가장 좋은 단면은 종단면(Y-Z plane)입니다.
> - 왜냐하면 종단면에서는 싱크홀, 맨홀, 배관을 가장 쉽게 구분할 수 있기 때문입니다.
> - 따라서 3차원의 이미지 데이터 중 우선적으로 필요한 것은 종단면 데이터였습니다.

### 📌 보다 나은 AI 모델 개발 기획
> - 종단면에 해당되는 이미지 데이터의 개수는 70,732장이었습니다.
> - 그리고 AI의 이미지 데이터 구조를 Train, Validation, Test 세트로 관리하고 싶었습니다.
> - 왜냐하면 실무에서 사용되는 딥러닝 모델 훈련/검증/테스트 세트를 희망하기 때문입니다.
> - 기획에 따른 이미지 데이터 구조의 변화가 필요하였고 아래와 같이 변경하였습니다.

<br>

## 🔔 2. Results
### 📌 변경 전 이미지 데이터 구조 (상세)
> - Number of Total Data : 192,120개
> - Training : 170,774개
>   - Source
>      - 종단면 : 66,523개
>         - 싱크홀(대칭) GPR 이미지
>         - 싱크홀(비대칭) GPR 이미지
>         - 싱크홀(기타) GPR 이미지
>         - 맨홀 GPR 이미지
>         - 배관(종방향) GPR 이미지
>         - 배관(횡방향) GPR 이미지
>      - 평단면 : 104,251개
>         - 싱크홀(대칭) GPR 이미지
>         - 싱크홀(비대칭) GPR 이미지
>         - 싱크홀(기타) GPR 이미지
>         - 맨홀 GPR 이미지
>         - 배관(종방향) GPR 이미지
>         - 배관(횡방향) GPR 이미지
>   - Label
>      - 종단면 : 66,523개
>         - 싱크홀(대칭) GPR 이미지
>         - 싱크홀(비대칭) GPR 이미지
>         - 싱크홀(기타) GPR 이미지
>         - 맨홀 GPR 이미지
>         - 배관(종방향) GPR 이미지
>         - 배관(횡방향) GPR 이미지
>      - 평단면 : 104,251개
>         - 싱크홀(대칭) GPR 이미지
>         - 싱크홀(비대칭) GPR 이미지
>         - 싱크홀(기타) GPR 이미지
>         - 맨홀 GPR 이미지
>         - 배관(종방향) GPR 이미지
>         - 배관(횡방향) GPR 이미지
> - Validation : 21,346개
>   - Source
>      - 종단면 : 8,315개
>         - 싱크홀(대칭) GPR 이미지
>         - 싱크홀(비대칭) GPR 이미지
>         - 싱크홀(기타) GPR 이미지
>         - 맨홀 GPR 이미지
>         - 배관(종방향) GPR 이미지
>         - 배관(횡방향) GPR 이미지
>      - 평단면 : 13,031개
>         - 싱크홀(대칭) GPR 이미지
>         - 싱크홀(비대칭) GPR 이미지
>         - 싱크홀(기타) GPR 이미지
>         - 맨홀 GPR 이미지
>         - 배관(종방향) GPR 이미지
>         - 배관(횡방향) GPR 이미지
>   - Label
>      - 종단면 : 8,315개
>         - 싱크홀(대칭) GPR 이미지
>         - 싱크홀(비대칭) GPR 이미지
>         - 싱크홀(기타) GPR 이미지
>         - 맨홀 GPR 이미지
>         - 배관(종방향) GPR 이미지
>         - 배관(횡방향) GPR 이미지
>      - 평단면 : 13,031개
>         - 싱크홀(대칭) GPR 이미지
>         - 싱크홀(비대칭) GPR 이미지
>         - 싱크홀(기타) GPR 이미지
>         - 맨홀 GPR 이미지
>         - 배관(종방향) GPR 이미지
>         - 배관(횡방향) GPR 이미지

### 📌 변경 후 이미지 데이터 구조 (상세)
> - Total Number of Images : 70,732
> - Training Dataset : 49,514 Images
>   - Raw Data
>      - Longitudinal Sections : 49,514 Images (70%)
>         - Cavity : 26,883 Images (38%)
>         - Manhole : 21,565 Images (30%)
>         - Pipe : 1,066 Images (2%)
>      - Plan Views : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -
>      - Cross Sections : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -
>   - Annotated Data
>      - Longitudinal Sections : 49,514 Images (70%)
>         - Cavity : 26,883 Images (38%)
>         - Manhole : 21,565 Images (30%)
>         - Pipe : 1,066 Images (2%)
>      - Plan Views : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -
>      - Cross Sections : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -
> - Validation Dataset : 10,609 Images
>   - Raw Data
>      - Longitudinal Sections : 10,609 Images (15%)
>         - Cavity : 5,760 Images (8%)
>         - Manhole : 4,621 Images (7%)
>         - Pipe : 228 Images (0.3%)
>      - Plan Views : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -
>      - Cross Sections : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -
>   - Annotated Data
>      - Longitudinal Sections : 10,609 Images (15%)
>         - Cavity : 5,760 Images (8%)
>         - Manhole : 4,621 Images (7%)
>         - Pipe : 228 Images (0.3%)
>      - Plan Views : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -
>      - Cross Sections : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -
> - Testing Dataset : 10,609 Images
>   - Raw Data
>      - Longitudinal Sections : 10,609 Images (15%)
>         - Cavity : 5,760 Images (8%)
>         - Manhole : 4,621 Images (7%)
>         - Pipe : 228 Images (0.3%)
>      - Plan Views : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -
>      - Cross Sections : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -
>   - Annotated Data
>      - Longitudinal Sections : 10,609 Images (15%)
>         - Cavity : 5,760 Images (8%)
>         - Manhole : 4,621 Images (7%)
>         - Pipe : 228 Images (0.3%)
>      - Plan Views : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -
>      - Cross Sections : Not applicable
>         - Cavity : -
>         - Manhole : -
>         - Pipe : -

<br>

## 🔔 3. Conclusions
### 📌 변경된 데이터 구조
> - 각 디렉토리명을 보다 명시적으로 변경하였습니다.
> - Training, Validation, Testing Dataset의 비율을 수정하였습니다.
> - 3D-GPR 데이터에서 가장 중요하다고 판단되는 종단면 데이터를 먼저 사용하였습니다.
> - 변경된 데이터 구조를 이용하여 VisualCavity AI 모델 v1.0.0을 구축할 예정입니다.
