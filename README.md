# KOBIS 박스오피스 미니프로젝트 (2020–2026)

영화진흥위원회(KOBIS) 박스오피스 7년치 데이터를 활용한 **탐색적 데이터 분석(EDA)** 미니프로젝트입니다.

## 🚀 시작하기 (설치 0, 3단계)

**필요한 것**: Google 계정 하나.

```
[1] Open in Colab 클릭  →  [2] 드라이브에 사본 저장  →  [3] 작업하고 LMS에 제출
```

### 1단계. Colab으로 열기

아래 배지를 클릭하세요.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/RAKKUNN/kobis-mini-project/blob/main/student_starter.ipynb)

### 2단계. 본인 Google Drive에 사본 저장 (⚠️ 반드시!)

Colab 메뉴: **파일 → 드라이브에 사본 저장**

- 본인 Google Drive의 `Colab Notebooks/` 폴더에 비공개로 저장됩니다 (다른 사람은 볼 수 없음)
- 새 탭이 열리면서 사본으로 자동 전환됩니다 — 이후 작업은 모두 이 사본에서
- 파일명을 **`학번_이름.ipynb`** 로 변경 (예: `20251234_홍길동.ipynb`)
  - Colab 좌상단의 파일명을 클릭하면 바로 수정 가능

> ⚠️ 이 단계를 건너뛰고 작업하면 변경사항이 저장되지 않습니다. 반드시 사본 저장 후 작업하세요.

### 3단계. 작업하고 LMS에 제출

- **셀을 위에서부터 순서대로 실행** — 첫 셀이 한글 폰트와 데이터를 자동으로 준비합니다 (Colab 첫 실행 시 30초 소요)
- 빈 코드 셀에 답을 작성하고, 마크다운 셀에 해석 한 줄을 적습니다
- **자동저장됨** — Colab 우상단에 "저장됨"이 보이면 OK
- 마감 전: **파일 → 다운로드 → .ipynb 다운로드** → 학교 LMS에 업로드

## 📦 파일 구성

| 파일 | 설명 |
|---|---|
| `student_starter.ipynb` | 학생용 시작 노트북 (이것을 작성) |
| `assignment_brief.md` | 과제 안내 + 분석 질문 6개 |
| `data/kobis_boxoffice_2020_2026.csv` | 분석 데이터 (29,724행) |

자세한 분석 질문은 [`assignment_brief.md`](./assignment_brief.md)를 먼저 읽어 주세요.

## 📅 제출

- **마감**: 2026/06/14
- **파일명**: `학번_이름.ipynb`
- **제출처**: 사이버캠퍼스

## 💻 (선택) 로컬에서 작업하고 싶다면

Colab을 권장하지만, 로컬에서도 가능합니다.

```bash
# 데이터 + 노트북만 받기 (Git 몰라도 됨)
# 1) 위 GitHub 페이지에서 Code → Download ZIP → 압축 해제
# 2) 압축 푼 폴더에서:
python3 -m venv .venv
source .venv/bin/activate    # Windows: .venv\Scripts\activate
pip install pandas numpy matplotlib seaborn jupyterlab
jupyter lab student_starter.ipynb
```

한글 폰트가 깨지는 경우:
- **macOS**: 자동 (`AppleGothic`)
- **Windows**: 자동 (`Malgun Gothic`)
- **Linux**: `sudo apt-get install fonts-nanum` 후 노트북 첫 셀 재실행

## ❓ 자주 막히는 부분

1. **한글이 깨져요** — 첫 셀을 다시 실행하세요. 그래도 안 되면 **런타임 → 런타임 다시 시작** 후 첫 셀부터 재실행
2. **데이터를 못 찾아요** — 첫 셀이 끝까지 실행됐는지 확인. Colab 좌측 폴더 패널에 `kobis_boxoffice_2020_2026.csv` 가 보여야 합니다
3. **저장이 안 돼요** — **2단계(드라이브에 사본 저장)** 를 건너뛰면 저장 권한이 없습니다. 좌상단 파일명 옆에 "이 노트북에 대한 변경사항을 저장할 수 없습니다" 가 뜨면 사본 저장부터 하세요
4. **세션이 끊겼어요** — Colab은 90분 idle 후 종료됩니다. 코드는 Drive에 저장되지만 **변수와 데이터는 휘발**됩니다. 다시 들어오면 첫 셀부터 재실행하세요
5. **`개봉일`로 월 추출이 안 돼요** — 첫 셀의 `parse_dates=['개봉일']` 덕분에 이미 datetime입니다. `df['개봉일'].dt.month`로 바로 추출됩니다
6. **그래프 X축 라벨이 겹쳐요** — `plt.xticks(rotation=45)` 또는 `plt.figure(figsize=(12, 4))` 로 가로 늘리기
