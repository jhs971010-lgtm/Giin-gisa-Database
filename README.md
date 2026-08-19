# 1920년대 신문 연재 야담 『기인기사(奇人奇事)』 서사 데이터베이스
**The Narrative Database of 1920s Serialized Yadam *Giingisa***
본 데이터는 1921~1922년 매일신보에 연재된 송순기의 한글 연재물(야담 중심) 『기인기사(奇人奇事)』 총 88편의 서사 구조를 관계형 데이터베이스(RDB)로 구축한 것이다. 일화를 포함한 서지 정보 데이터 아래 인물·장소·공간·시대·물품을 5개의 기본 모듈로 추출하고, 그 뒤에 확장 모듈로 '인물 속성 변화'를 데이터로 연동하였다. 

# 원문 이미지 출처:
https://www.nl.go.kr/newspaper/keyword_search.do?search_keyword=%EA%B8%B0%EC%9D%B8%EA%B8%B0%EC%82%AC

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19808482.svg)](https://doi.org/10.5281/zenodo.19808482) 

---

## 🇺🇸 Project Overview (Overview in English)
This database was constructed to analyze the narrative structure of ***Giingisa* (Bizarre People and Strange Events)**, a collection of 88 Korean *Yadam* (historical anecdotes) serialized in modern newspapers in the 1920s, using Digital Humanities methodologies.

It is a relational database (RDB) that breaks down individual anecdotes into basic modules—**Character, Location, Space, Time, and Item**—and structures the narrative twists (downfall and rise) driven by characters' desires as an extended module. This allows for a quantitative and multidimensional tracking of the geopolitical imagination, historical memory, and secular desires within the *Yadam* consumed by 1920s readers.

* **Researcher:** Cho Hyun-seok (Ph.D. Student, Classical Korean Literature, Korea University)
* **Primary Source:** 88 anecdotes from *Giingisa* (1921-1923)

---

## 📊 데이터 명세서 (Data Dictionary)

본 저장소는 다음의 CSV 파일들로 구성되어 있다. 각 파일은 `AnecdoteID(일화 식별자)`를 중심으로 상호 연결된다.
The repository contains the following CSV files, which are interconnected via `AnecdoteID`.

### 1. `Anecdote.csv` (일화 기본 데이터 / Base Anecdote Data)
* 개별 야담 88편의 서지 및 메타 데이터.
* **Columns:** `AnecdoteID`, `원문제목(Original_Title)`, `역사적 사건(Historical Event)`, `형식 성격(Form)`

### 2. `Charater.csv` (등장인물 데이터 / Character Data)
* 일화에 등장하는 인물들의 속성 정보.
* **Columns:** `CharacterID`, `이름(Name)`, `역사성(Historicity)`, `생몰연도(Lifespan)`, `성별(Gender)`, `국적(Nationality)`, `신분(Status)`

### 3. `Location.csv` & `AnecdoteLocation.csv` (장소 및 좌표 데이터 / Geographic Location Data)
* 서사의 배경이 되는 물리적/지정학적 기초 지명과 GIS 매핑을 위한 위경도 좌표.
* **Columns:** `LocationID`, `국가(Country)`, `광역지명(Province)`, `기초지명(City/County)`, `위도(Latitude)`, `경도(Longitude)`

### 4. `Place.csv` (서사적 공간 데이터 / Narrative Place Data)
* 단순 좌표를 넘어선 인물의 구체적 생활 및 활동 무대 (예: 집, 길, 관아, 주막 등).
* **Columns:** `SpaceID`, `Category(분류)`, `Name(공간명)`, `기초지명 매핑`

### 5. `Time.csv` (시대 데이터 / Time & Era Data)
* 서사가 설정하고 있는 역사적 연대기. 국난(전란)과 평화기를 구분하는 지표.
* **Columns:** `TimeID`, `왕(King)`, `연도(Year)`, `문면 시대(Textual Time)`

### 6. `Item.csv` (물품 데이터 / Material Item Data)
* 서사 전개의 매개체로 작동하는 물질적 토대 (예: 문서, 복식, 재물, 음식 등).
* **Columns:** `ItemID`, `Category(대분류)`, `Sub_Category(중분류)`, `Name(물품명)`, `설명(Description)`

### 7. `Attrivute.csv` (인물 속성 변화 데이터 / Character Attribute & Narrative Twist Data)
* 입신, 재산, 혼인 등 서사 내에서 인물이 겪는 하강과 상승의 변화를 표시한 데이터.
* **Columns:** `AttributeID`, `속성유형(Type)`, `방향성(Direction - 상승/하강)`, `변화전(Before)`, `변화후(After)`

---

## 📌 인용 방법 (How to Cite)
이 데이터를 학술적 목적으로 활용할 경우, 아래의 논문(발표문)을 인용해 주시기 바랍니다.
If you use this dataset for academic purposes, please cite the following presentation/paper:

**[한국어]**
> 조현석. (2026). "야담 데이터베이스 구축 방안:신문 연재물 󰡔기인기사󰡕를 대상으로" 강원문화연구

**[English]**
> 

---

## 📜 라이선스 (License)
이 데이터베이스는 **크리에이티브 커먼즈 저작자표시 4.0 국제(CC BY 4.0)** 라이선스에 따라 배포됩니다. 적절한 출처(저자 및 논문)를 표기하는 조건으로 자유롭게 공유 및 변경, 상업적/비상업적 활용이 가능합니다.
This project is licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)**. You are free to share and adapt the material for any purpose, even commercially, as long as you give appropriate credit.

## 📬 문의 (Contact)
조현석(고려대학교 박사 수료, jhs971010@gmail.com)
