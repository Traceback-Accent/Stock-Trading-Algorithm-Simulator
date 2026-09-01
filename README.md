# Stock-Trading-Algorithm-Simulator

브라우저에서 바로 실행되는 개인용 주식 전략 백테스팅 도구입니다. 서버 없이 순수 HTML/JS로 동작하며, 자유롭게 작성한 JavaScript 전략 함수를 여러 개 동시에 돌려서 성과를 비교할 수 있습니다.

🇰🇷 한국어 / 🇺🇸 English UI 전환을 지원합니다.

주요 기능
데이터 로드: 내장 샘플 데이터(상승장/하락장/횡보/고변동성) 또는 직접 CSV 업로드
자유 코드 전략: function strategy(context) { ... } 형태로 나만의 매매 로직 작성
다중 전략 비교: 여러 전략을 동시에 실행하고 자산 곡선·수익률·MDD·승률 등을 비교
시장 고증 설정: 한국(거래세 포함)/미국(환율 변환)/커스텀 프리셋으로 수수료·세금·슬리피지 반영
뉴스/시장상황 레이어: 특정 날짜에 경기 국면(BOOM~FAILURE)을 수동 태깅하거나, AI API로 뉴스 텍스트를 분석해 자동 태깅
바이브 코딩: 자연어로 원하는 전략을 설명하면 AI가 전략 코드를 생성
View Timeline: 시간 흐름에 따라 포트폴리오가 어떻게 변해가는지 재생/탐색
Instant Exit: 무한루프나 오래 걸리는 전략을 Web Worker 타임아웃으로 즉시 감지·중단
사용 방법
backtest.html 파일을 다운로드해서 브라우저로 열기 (별도 설치/서버 불필요)
좌측 패널에서 데이터 소스 선택 → 데이터 불러오기
전략 목록에서 기본 골든크로스 전략을 수정하거나 새 전략 추가
모든 전략 동시 실행으로 결과 비교

AI 관련 기능(뉴스 분석, 바이브 코딩)을 쓰려면 OpenRouter 등 API 키가 필요합니다. 입력한 키는 브라우저 localStorage에만 저장되며 서버로 전송되지 않고, 실제 API 호출도 사용자 브라우저에서 직접 발생합니다.

기술 스택
순수 HTML / CSS / JavaScript (프레임워크·빌드 도구 없음)
Web Worker 기반 전략 실행 엔진 (메인 스레드 블로킹 방지, 타임아웃 감지)
Canvas API로 직접 구현한 차트 (외부 차트 라이브러리 미사용)
⚠️ 디스클레이머

이 프로젝트는 교육 및 개인 연구 목적으로 만들어졌으며, 투자 자문이나 매매 추천이 아닙니다.

샘플 데이터는 의사난수로 생성한 가상 시뮬레이션이며 실제 시세가 아닙니다.
백테스트 결과는 과거(또는 가상) 데이터 기반 시뮬레이션일 뿐, 미래 수익을 보장하지 않습니다.
이 도구를 이용한 실제 투자 결정 및 그 결과에 대해 개발자는 어떠한 책임도 지지 않습니다.
이 코드를 자동매매 등 실거래에 연동하기 전에는 관련 법규(자본시장법, 증권사 API 약관 등)를 반드시 확인하시기 바랍니다.
라이선스

MIT License — 자유롭게 사용, 수정, 배포(상업적 이용 포함) 가능합니다. 원저작자 표시만 유지해주세요. 

English Version

A personal stock-strategy backtesting tool that runs entirely in the browser. No server required — it's pure HTML/JS, and lets you write your own JavaScript strategy functions, run several at once, and compare their performance.

Supports switching the UI between 🇰🇷 Korean and 🇺🇸 English.

Features
Data loading: Use built-in sample data (bull / bear / sideways / high-volatility) or upload your own CSV
Free-form code strategies: Write your own trading logic as function strategy(context) { ... }
Multi-strategy comparison: Run several strategies simultaneously and compare equity curves, return, MDD, win rate, and more
Market realism settings: Korean (incl. transaction tax) / US (FX conversion) / custom presets for fees, taxes, and slippage
News / market-condition layer: Manually tag economic stages (BOOM–FAILURE) on specific dates, or have an AI API analyze news text and tag them automatically
Vibe coding: Describe the strategy you want in plain language and let AI generate the strategy code
View Timeline: Play back or scrub through how the portfolio evolves over time
Instant Exit: Detects and immediately stops runaway strategies (infinite loops, long-running code) via a Web Worker timeout
How to Use
Download backtest.html and open it in a browser (no install or server needed)
Pick a data source in the left panel and click Load Data
Edit the default golden-cross strategy or add new ones from the strategy list
Click Run All Strategies to compare results

AI-powered features (news analysis, vibe coding) require an API key (e.g. from OpenRouter). Any key you enter is stored only in your browser's localStorage, is never sent to a server, and all API calls are made directly from your own browser.

Tech Stack
Pure HTML / CSS / JavaScript (no frameworks or build tools)
Web Worker–based strategy execution engine (keeps the main thread responsive, detects timeouts)
Charts implemented directly with the Canvas API (no external charting library)
⚠️ Disclaimer

This project was built for educational and personal research purposes only and is not investment advice or a trading recommendation.

The sample data is a pseudo-random simulation, not real market data.
Backtest results are simulations based on historical (or synthetic) data and do not guarantee future returns.
The developer assumes no responsibility for any real investment decisions made using this tool, or their outcomes.
Before connecting this code to any live trading or automated execution, be sure to check applicable regulations (securities laws, brokerage API terms, etc.) in your jurisdiction.
License

MIT License — free to use, modify, and distribute, including for commercial purposes. Please keep the original copyright notice.
