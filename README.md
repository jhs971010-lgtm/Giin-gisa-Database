# Giin-gisa-Database
본 프로젝트는 1920년대 근대 매체에 연재된 한글 야담 『기인기사(奇人奇事)』 총 88편의 서사 구조를 디지털 인문학적 방법론으로 재구성한 관계형 데이터베이스(RDB)입니다. 단순한 텍스트 집계를 넘어, 일화 속 인물·장소·공간·시대·물품을 5개의 기본 모듈로 분할하고 인물 욕망에 따른 '추락과 복귀의 반전 서사'를 데이터로 연동했습니다. 이를 통해 당대 대중이 소비한 야담의 지리적 상상력, 국난의 기억, 세속적 욕망을 정량적·입체적으로 조망하며, 고전문학과 데이터 과학이 교차하는 새로운 연구 지평을 제시합니다.

# 1920년대 신문 연재 야담 『기인기사(奇人奇事)』 서사 데이터베이스
**The Narrative Database of 1920s Serialized Yadam *Giingisa***

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19808482.svg)](https://doi.org/10.5281/zenodo.19808482) 

## 🇰🇷 프로젝트 개요 (Overview in Korean)
본 데이터베이스는 1920년대 근대 매체(매일신보)에 연재된 한글 야담 **『기인기사(奇人奇事)』** 총 88편의 서사 구조를 디지털 인문학적 방법론을 통해 분석하기 위해 구축되었습니다. 

단순한 텍스트의 집합을 넘어, 개별 일화 속에 등장하는 ** 인물(Character), 장소(Location), 공간(Space), 시대(Time), 물품(Item) **을 기본 모듈로 분할하고, 인물의 욕망에 따른 ** 서사적 반전(하강과 상승) **을 확장 모듈로 구조화한 관계형 데이터베이스(RDB)입니다. 이를 통해 1920년대 독자들이 소비했던 야담의 지리적 상상력, 역사적 기억의 소환, 그리고 세속적 욕망의 양상을 정량적이고 입체적으로 추적할 수 있습니다.

* **연구자:** *****
* **분석 대상:** 송순기 편저, 『기인기사록』 상·하 (1921, 1923) 및 신문 연재본 총 88편

---

## 🇺🇸 Project Overview (Overview in English)
This database was constructed to analyze the narrative structure of ***Giingisa* (Bizarre People and Strange Events)**, a collection of 88 Korean *Yadam* (historical anecdotes) serialized in modern newspapers in the 1920s, using Digital Humanities methodologies.

It is a relational database (RDB) that breaks down individual anecdotes into basic modules—**Character, Location, Space, Time, and Item**—and structures the narrative twists (downfall and rise) driven by characters' desires as an extended module. This allows for a quantitative and multidimensional tracking of the geopolitical imagination, historical memory, and secular desires within the *Yadam* consumed by 1920s readers.

* **Researcher:** Cho Hyun-seok (Ph.D. Student, Classical Korean Literature, Korea University)
* **Primary Source:** 88 anecdotes from *Giingisa* (1921-1923)

---

## 📊 데이터 명세서 (Data Dictionary)

본 저장소는 다음의 CSV 파일들로 구성되어 있습니다. 각 파일은 `AnecdoteID(일화 식별자)`를 중심으로 상호 연결됩니다.
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

### 4. `Space.csv` (서사적 공간 데이터 / Narrative Space Data)
* 단순 좌표를 넘어선 인물의 구체적 생활 및 활동 무대 (예: 집, 길, 관아, 주막 등).
* **Columns:** `SpaceID`, `Category(분류)`, `Name(공간명)`, `기초지명 매핑`

### 5. `Time.csv` (시대 데이터 / Time & Era Data)
* 서사가 설정하고 있는 역사적 연대기. 국난(전란)과 평화기를 구분하는 지표.
* **Columns:** `TimeID`, `왕(King)`, `연도(Year)`, `문면 시대(Textual Time)`

### 6. `Item.csv` (물품 데이터 / Material Item Data)
* 서사 전개의 매개체로 작동하는 물질적 토대 (예: 문서, 복식, 재물, 음식 등).
* **Columns:** `ItemID`, `Category(대분류)`, `Sub_Category(중분류)`, `Name(물품명)`, `설명(Description)`

### 7. `Attrivute.csv` (인물 속성 및 서사 반전 데이터 / Character Attribute & Narrative Twist Data)
* 입신, 재산, 혼인 등 서사 내에서 인물이 겪는 하강과 상승의 '역전(반전) 구조' 데이터.
* **Columns:** `AttributeID`, `속성유형(Type)`, `방향성(Direction - 상승/하강)`, `변화전(Before)`, `변화후(After)`

---

## 📌 인용 방법 (How to Cite)
이 데이터를 학술적 목적으로 활용할 경우, 아래의 논문(발표문)을 인용해 주시기 바랍니다.
If you use this dataset for academic purposes, please cite the following presentation/paper:

**[한국어]**
> ***. (2026). "논문 제목"

**[English]**
> 

---

## 📜 라이선스 (License)
이 데이터베이스는 **크리에이티브 커먼즈 저작자표시 4.0 국제(CC BY 4.0)** 라이선스에 따라 배포됩니다. 적절한 출처(저자 및 논문)를 표기하는 조건으로 자유롭게 공유 및 변경, 상업적/비상업적 활용이 가능합니다.
This project is licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)**. You are free to share and adapt the material for any purpose, even commercially, as long as you give appropriate credit.

## 📬 문의 (Contact)
투고 완료 전까지 익명 처리합니다.
