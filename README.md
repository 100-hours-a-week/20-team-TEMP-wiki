# 20-team-daeng-ddang-wiki

### [WIKI 페이지](https://github.com/100-hours-a-week/20-team-daeng-ddang-wiki/wiki)에 기록되어 있습니다.
* [🖥️ BE WIKI](https://github.com/100-hours-a-week/20-team-daeng-ddang-wiki/wiki/%F0%9F%96%A5%EF%B8%8F-Backend-Wiki)
* [📱 FE WIKI](https://github.com/100-hours-a-week/20-team-daeng-ddang-wiki/wiki/Frontend-Wiki)
* [🤖 AI WIKI](https://github.com/100-hours-a-week/20-team-daeng-ddang-wiki/wiki/AI-Wiki)
* [☁️ CLOUD WIKI](https://github.com/100-hours-a-week/20-team-daeng-ddang-wiki/wiki/Cloud-Wiki)

# 🐾 댕동여지도
<img width="3840" alt="image" src="https://github.com/user-attachments/assets/c1ae28ec-395b-4215-92cf-f06d4d7d6ff5" />

### 프로젝트 기간: 2025.12.22 ~ 2026.03.26
### [댕동여지도 서비스 바로가기](https://daeng-map.store)
### [댕동여지도 디스콰이엇 바로가기](https://disquiet.io/product/%EB%8C%95%EB%8F%99%EC%97%AC%EC%A7%80%EB%8F%84-1770131135153)
[✅ 스프린트 백로그 바로가기](https://confused-rate-def.notion.site/2f2089541f70800bbc51f6aae2da7dd5?source=copy_link)

<br>

##  목차

- [프로젝트 소개](#프로젝트-소개)
- [서비스 한 줄 소개](#서비스-한-줄-소개)
- [서비스 기획 배경](#서비스-기획-배경)
  * [문제 정의](#문제-정의)
  * [문제 원인](#문제-원인)
  * [해결 방안](#해결-방안)
- [주요 기능](#주요-기능)
  * [땅따먹기 (산책)](#땅따먹기-산책)
  * [땅따먹기 > 돌발 미션](#땅따먹기--돌발-미션)
  * [땅따먹기 > 표정 분석](#땅따먹기--표정-분석)
  * [헬스케어 및 챗봇](#헬스케어-및-챗봇)
- [주요 사용자 흐름](#주요-사용자-흐름)
- [팀원 소개](#팀원-소개)
- [기술 스택](#기술-스택)
- [개발 일정](#개발-일정)
- [아키텍처 구조](#아키텍처-구조)
- [문서](#문서)
- [하위 위키](#하위-문서)

<br>
<br>

## 프로젝트 소개

> `혁심실험 서비스`

- **이름**: 댕동여지도
- **목표**: 반려견과의 산책 데이터를 기반으로 게임처럼 즐기는 산책 경험과 건강 인사이트를 제공해 사용자의 산책 동기를 부여하는 모바일 산책 서비스

<br>
<br>

## 서비스 기획 배경

### 문제 정의

- 산책을 통한 활동량 충족은 반려견의 중요한 행복 요소
- 그러나 반복되는 반려견 산책이 루틴화되면서 동기 저하와 지루함을 느끼는 경우가 많음

<br>

### 문제 원인

반려견 산책과 관련된 기존 서비스들은

- 이동 거리·시간 기록에 한정
- 사용자가 체감할 수 있는 성과(눈에 보이는 결과물) 부족
- 게임 요소가 약해 반복 사용 동기가 낮음

<br>

### 해결 방안

- 게이미피케이션 요소 추가
	- 산책 경로를 따라 블록 단위로 영역 점유(땅따먹기)
	- 산책 중 주어진 미션에 성공하거나 헬스케어 분석을 받으면 포인트 지급
- 지속적인 참여를 유도하는 구조
    - 개인/지역 랭킹을 통해 자연스러운 비교와 목표 설정 제공
- 반려견의 건강상태 확인
	- 반려견의 건강정보를 분석하고 결과를 기록
	- 산책과 더불어 점점 건강해지는 반려견 관찰

<br>
<br>

## 주요 기능

### 땅따먹기 (산책)
<img width="3840" alt="image" src="https://github.com/user-attachments/assets/95db6fb5-106f-428e-9f73-53871bef8401" />


- `땅따먹기`
	- 산책 경로를 따라 블록 단위로 영역을 점유하는 게임
- `침범`
	- A 사용자가 점유한 블록을 B 사용자가 지나가는 행위로, 침범 당한 블록은 가장 최근에 해당 블록을 지나간 B의 소유로 변경됨
- `포인트`
	- 5포인트: 아무도 점유하지 않은 블록을 최초로 점유할 경우
	- 2포인트: 다른 사용자가 점유한 블록을 침범할 경우
		- 본인이 소유한 블록을 다시 지나갈 때는 포인트 없음

<br>

### 땅따먹기 > 돌발 미션

- `돌발 미션`
	- 땅따먹기 산책 도중에 랜덤한 주기로 활성화되는 미션 버튼을 클릭해 참여할 수 있는 영상 기반 돌발 미션
	- 돌발 미션 버튼 클릭 시 60초의 준비 시간 제공 (촬영 버튼을 클릭해 준비 시간을 스킵할 수 있음)
	- 미션 영상은 5초 뒤 자동 종료
	- 돌발 미션의 성공/실패 결과는 산책 종료 후 요약 화면에서 일괄 제공
- `미션 종류`
	- 반려견 자유 영상
	- `앉아` 수행 영상
	- `엎드려` 수행 영상
	- `기다려` 수행 영상
	- `손` 수행 영상
	- `돌아` 수행 영상
- `포인트`
	- 미션 난이도에 따라 1, 3, 5포인트 지급

### 땅따먹기 > 표정 분석
<img width="3840" alt="image" src="https://github.com/user-attachments/assets/362f2a20-c302-4746-b9c9-998702471683" />

- `표정 분석`
	- 땅따먹기 산책이 종료된 후 반려견의 표정을 분석해 감정을 분석하는 기능
	- 표정 분석 진행 여부 선택 후 사용 가능
- `포인트`
	- 3포인트: 반려견 표정 분석 결과에서 행복도가 70% 이상일 경우
	- 1포인트: 반려견 표정 분석에 참여할 경우

> ※ 표정 분석 참여(1포인트) + 행복도 70% 이상 달성(3포인트) → 총 4포인트 지급

<br>

### 헬스케어 및 챗봇
<img width="3840" alt="image" src="https://github.com/user-attachments/assets/e18af1a8-2339-4d29-bd64-fdaea476c850" />

- `헬스케어`
	- 반려견 촬영 기반 헬스케어 분석
	- 주로 관절 건강 체크
	- 일 3회 사용 제한 (과도한 분석 요청 및 서버 부하 방지 목적)
- `챗봇`
	- 헬스케어 내에서 사용 가능
	- 기본적으로 텍스트 기반 대화
	- 반려견 코와 피부에 한해 이미지 기반 대화 가능
- `포인트`
	- 5포인트: 하루 중 첫 번째 분석일 경우
	- 2포인트: 하루 중 두 번째 혹은 세 번째 분석일 경우

<br>

### 발자국
<img width="3840" alt="image" src="https://github.com/user-attachments/assets/f30b724d-0370-4b98-bca5-42c8df5585b0" />

- `산책/표정분석/헬스케어 기록`
	- 캘린더 기반 산책과 건강 기록 확인
        - 산책 횟수기반 히트맵 시각화
<br>

### 랭킹

<img width="3840" alt="image" src="https://github.com/user-attachments/assets/2de6df0e-3ee8-44f1-97fa-3ee9aa73a9ac" />

- `개인랭킹`
	- 이동거리 기반 전국 및 지역 단위에서의 랭킹 확인
- `지역 랭킹`
	- 지역별 순위를 보여주는 랭킹
        - 사용자의 이동거리가 지역랭킹에 얼마만큼 기여했는지 확인 가능 
<br>
<br>

## 주요 사용자 흐름

<img width="800" alt="image" src="https://github.com/user-attachments/assets/b7b3a24d-d2c4-4e5f-8e43-03cb07d2a27a" />

<br>
<br>

## 팀원 소개

| 이름 | 역할 | 주요 업무 |
|------------------|------|------------|
| comi.park | DevOps / 대표 | 협업 리딩 / 인프라 구축 및 배포  |
| danny.kwak | DevOps | 인프라 구축 및 배포 |
| dori.ka | Backend | 산책·영역 도메인 설계 |
| jacob.lee | AI | -ㅅ- |
| ellin.won | AI | -0- |
| sian.song | Frontend | 지도 및 산책 UI 구현 |

<br>
<br>

## 기술 스택  

| 분류 | 기술 |
|------|------|
| Frontend | React / TypeScript / vite / Map SDK |
| Backend | Java 21 / Spring Boot / Spring Data JPA / Spring Security / Spring Webflux |
| Infra / DevOps | Docker / Docker Compose / AWS EC2 / AWS RDS / Caddy / GCP |
| AI | FastAPI / PyTorch / Python / TensorFlow |

<br>
<br>

## 개발 일정

> 2025년 12월 ~ 2026년 3월 기준

| 기간 | 주요 작업 |
|------|-----------|
| 12/22 ~ 01/04 | 기획 |
| 01/05 ~ 01/18 | 설계 |
| 01/19 ~ 02/01 | MVP 개발 |
| 02/02 ~ 02/08 | 1차 배포 및 출시 |
| 02/09 ~ 03/01 | V2 업데이트 개발 |
| 03/02 ~ 03/08 | 2차 업데이트 |
| 03/09 ~ 03/22 | V3 업데이트 개발 |
| 03/23 ~ 03/26 | 문서 총 정리 |

<br>
<br>

## 아키텍처 구조
- **추후 추가 예정**

<br>
<br>

## 문서
- [API 명세서](https://docs.google.com/spreadsheets/d/1bLjLezC4-XIqviSz4H0t9BAwv7pYo1nnQeeSBlXi0kA/edit?gid=1352995101#gid=1352995101)

<br>
<br>

## 하위 위키
- [FE WIKI](https://github.com/100-hours-a-week/20-team-daeng-ddang-wiki/wiki/%F0%9F%93%B1Frontend-Wiki)
- [BE WIKI](https://github.com/100-hours-a-week/20-team-daeng-ddang-wiki/wiki/%F0%9F%96%A5%EF%B8%8F-Backend-Wiki)
- [AI WIKI](https://github.com/100-hours-a-week/20-team-daeng-ddang-wiki/wiki/AI-Wiki)
- [CLOUD WIKI](https://github.com/100-hours-a-week/20-team-daeng-ddang-wiki/wiki/cloud-wiki)

<br>
