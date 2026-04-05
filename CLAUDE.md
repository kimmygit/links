# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

Bento 스타일의 개인 링크 페이지(LinkHub). 빌드 도구 없이 순수 HTML/CSS로 구성된 정적 웹페이지로, GitHub Pages로 배포된다.

## 로컬 실행

```bash
open index.html
```

빌드, 린트, 테스트 도구는 없다. 브라우저에서 직접 확인한다.

## 아키텍처

- **index.html** — 전체 페이지를 구성하는 단일 HTML 파일. 프로필 섹션 + Bento Grid(카드 목록)로 구성
- **style.css** — CSS Grid 기반 Bento 레이아웃, 호버 애니메이션, 반응형(모바일 428px 기준)
- **resources/** — 이미지 리소스 (프로필, 아이콘, 프리뷰, 소셜 미디어 이미지)

## 카드 타입

`index.html`의 `.bento-grid` 안에 4가지 카드 타입이 존재한다:

| 클래스 | 용도 | 특징 |
|---|---|---|
| `card-link` | 외부 링크 (프리뷰 이미지 포함) | `card-full`, 좌측 아이콘+텍스트 / 우측 프리뷰 |
| `card-simple` | 간단한 링크 | `card-half`, 아이콘+제목+서브타이틀 |
| `card-social` | SNS 카드 (Instagram, Behance) | `card-full`, 헤더+6개 이미지 그리드 |
| `card-text` | 텍스트 전용 (마감 강좌 등) | `card-full`, 아이콘+제목만, 높이 77px |

새 카드를 추가할 때는 기존 카드의 HTML 구조를 복사하여 사용한다.

## 주의사항

- Instagram, Behance 아이콘은 인라인 SVG로 작성되어 있다 (이미지 파일이 아님)
- 카드 순서가 곧 페이지 표시 순서이며, 최신/활성 강좌가 상단에 위치한다
- `card-half` 카드 2개는 반드시 연속으로 배치해야 한 행에 나란히 표시된다
