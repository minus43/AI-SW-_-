# 사생활침해 멈춰! 🔒

> SNS나 사진을 통한 **의도치 않은 사생활 노출**을 방지하기 위한 **AI 기반 이미지 보호 시스템** 개발 프로젝트입니다.

---

## 📌 프로젝트 개요

- **프로젝트명**: 사생활침해 멈춰!
- **참여 인원**:
  - 김민우 (201910778)
  - 최미희 (201710922)
  - 김정민 (201910791)
  - 박채은 (201710931)

---

## ❓ 주제 및 필요성

사진 공유가 일상화된 사회에서, **SNS 속 배경 정보만으로도** 사생활이 침해될 수 있는 사건들이 발생하고 있음.

### 🔍 사례
- 셀카 속 눈동자에 비친 풍경으로 주소 유추 → 스토킹 (BBC, 2019)
- 유명인 SNS 속 집 사진으로 범죄 표적 → 절도 피해 (연합뉴스, 2020)
- SNS 사진 노출로 인해 고독사 또는 살해 피해 증가 (아시아경제, 2021)

---

## 🧠 사용된 주요 모델 소개

### 📌 U-Net (for Segmentation)
- **이미지 내 사람을 찾아내는 모델**
- 의료영상 분석용으로 설계된 **픽셀 단위 분할(Semantic Segmentation)** 모델
- 이미지의 세부 구조(사람과 배경 등)를 정확하게 분리하는 데 사용됨
- **특징**: 적은 데이터로도 높은 정확도, 사람 위치 파악에 탁월

### 📌 CRAFT (for OCR)
- **이미지 속 글자를 감지하는 모델**
- 글자 모양의 "경계 상자(Bounding Box)"를 잡아내고 문자 영역을 예측함
- **특징**: 단어 단위가 아닌 글자 단위까지 정교하게 인식 가능 → 개인정보 포함된 문자를 자동 마스킹 가능

---

## 🛠️ 기술 개발 전략

### 1. 사람 인식 및 분리 (Semantic Segmentation)
- **모델**: U-Net
- **오픈소스**: [People Segmentation GitHub](https://github.com/ternaus/people_segmentation)
- **기능**: 이미지 내 인물 영역 분리 → 배경 블러 처리 등 사생활 보호 가능

### 2. 문자 인식 및 제거 (OCR)
- **프레임워크**: [EasyOCR](https://github.com/JaidedAI/EasyOCR)
- **모델**: CRAFT
- **기능**: 사진 속 문자 탐지 및 마스킹 → 전화번호, 주소, 명패 등 민감 정보 보호

---

## 📊 활용 데이터셋

- **COCO**: 객체 감지 및 분할용 일반 이미지 데이터셋
- **Vistas**: 거리 수준의 복잡한 환경 이미지
- **Matting Humans**: 사람 영역 정밀 분리 데이터셋
- **Pascal VOC**: 이미지 분류, 객체 검출, 세분화 평가용 데이터셋

---

## 💡 사업화 전략

- **타깃**: SNS 사용자, 크리에이터, 연예인, 일반인 등
- **방식**: 앱 또는 API로 제공 → 카메라 앱, SNS, 사진 편집 도구와 연동
- **출처**: [KISDI 미디어 패널 조사 인포그래픽(2019)](https://stat.kisdi.re.kr/kor/board/BoardList.html?board_class=BOARD17)

---

## 🧪 프로토타입 및 구현

- 인물 영역 분리 → 마스킹 or 블러
- 문자 영역 탐지 → 자동 마스킹 처리
- Python 기반 시연 환경에서 작동하는 초기 프로토타입 구현 완료

---

## 🚧 한계점 및 개선 방향

| 한계 | 개선 방향 |
|------|-----------|
| 다양한 환경에서의 인식률 낮음 | 더 많은 학습 데이터 확보 및 강화 학습 도입 |
| 오탐지 발생 가능성 존재 | 후처리 필터링 알고리즘 적용 |
| 이미지 해상도에 따라 성능 변화 | 멀티스케일 처리 기술 도입 고려 |

---

## 📆 역할 및 일정

| 팀원 | 역할 |
|------|------|
| 김민우 | U-Net 모델 구현 및 테스트 |
| 최미희 | OCR 처리 파이프라인 개발 |
| 김정민 | 기술 조사 및 사업화 자료 수집 |
| 박채은 | 문서 정리 및 발표 자료 구성 |

---

## 🔗 참고자료

- People Segmentation: https://github.com/ternaus/people_segmentation
- EasyOCR: https://github.com/JaidedAI/EasyOCR
- 논문: U-Net (Ronneberger et al.), CRAFT OCR (Clova AI)
- 기사 출처: 연합뉴스, BBC, 아시아경제 등

---

## 🙏 프로젝트 의의

이 프로젝트는 **AI 기술을 활용한 이미지 기반 사생활 보호**의 가능성을 보여줍니다.  
실제 서비스로 확장 시, 개인의 **프라이버시 보장**과 **디지털 안전 환경 조성**에 기여할 수 있습니다.


## how to use
1. download file "Stop_Invasion of privacy.ipynb"
2. open file "Stop_Invasion of privacy.ipynb"
3. store image file you want(if you want sample, download "s9.png") with same directory with "Stop_Invasion of privacy.ipynb"
4. if you run with your image file, you must chage cell fourth ("s9.png"->your own file)
