# GC + DAQ Segment Merge

DAQ 로그 → 안정구간(온도·유량이 모두 안정된 구간) 자동 탐지 → 색 구분 → GC injection과 시간 매칭까지 브라우저에서 바로 처리하는 도구입니다.
서버나 설치 없이 정적 HTML 하나로 동작하며, 업로드한 파일은 모두 브라우저 안에서만 처리됩니다 (외부로 전송되지 않음).

## 온라인에서 바로 쓰기

GitHub Pages로 배포하면 아래 주소에서 바로 사용할 수 있습니다.

```
https://[사용자명].github.io/[저장소이름]/
```

## 사용법

1. **DAQ 로그** — Time_day, Time_hour + SV/PV 컬럼이 있는 test station CSV를 넣습니다. 여러 날짜 파일을 한 번에 선택할 수 있습니다.
2. **GC raw data** — Compound별 Area 표와 injection schedule(Inj.Date)이 있는 Excel(.xlsx) 또는 CSV를 넣습니다.
3. Reactor(A/B)를 고르면 유량·온도·GC Signal 컬럼이 자동으로 채워지고, GC에서 인식된 성분(가스) 중 볼 것만 체크합니다.
4. 두 파일을 모두 넣고 분석을 실행하면 안정구간 자동탐지 → GC injection 시간 매칭까지 자동으로 진행되고, 구간마다 색으로 구분됩니다. 목표 유량/온도를 입력하면 그 조건에 맞는 구간만 걸러볼 수 있고, 최종 결과는 구간별 색상이 그대로 들어간 Excel로 다운로드할 수 있습니다.

## 로컬에서 열기

인터넷 연결이 없다면 `index.html`을 더블클릭해서 브라우저로 바로 열어도 동일하게 동작합니다. 단, xlsx.js, Plotly, ExcelJS 라이브러리를 CDN에서 불러오므로 시간대별 그래프와 Excel 저장 기능은 인터넷 연결이 필요합니다.

https://github.com/kmyune/gc-daq-merge
