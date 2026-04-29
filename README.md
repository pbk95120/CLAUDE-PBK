# CLAUDE-PBK

개인적으로 사용하는 [Claude Code](https://claude.com/claude-code) 서브에이전트 모음입니다.

## 포함된 에이전트

### `next-code-reviewer`
Next.js / TypeScript / React 프로젝트를 위한 코드 리뷰 전문 서브에이전트입니다.

- **모델**: sonnet
- **주요 검토 항목**:
  - 보안 취약점 (XSS, CSRF, 인젝션, 인증/인가)
  - TypeScript 타입 안정성
  - React 19 / Next.js 16 App Router 모범 사례
  - Shadcn/UI, Tailwind CSS, React Hook Form + Zod, Zustand 패턴
  - 접근성 (WCAG)
  - 프로젝트 컨벤션 준수 (pnpm 사용, `@/*` 경로 별칭, src/ 구조 등)
- **리뷰 형식**: 심각도(🔴/🟡/🟢)별로 분류된 구조화된 피드백 + 요약

## 설치

서브에이전트 파일을 Claude Code 에이전트 디렉토리에 복사하면 됩니다.

### 프로젝트별 설치 (해당 레포에서만 사용)

```bash
mkdir -p .claude/agents
cp next-code-reviewer.md .claude/agents/code-reviewer.md
```

### 전역 설치 (모든 프로젝트에서 사용)

```bash
mkdir -p ~/.claude/agents
cp next-code-reviewer.md ~/.claude/agents/code-reviewer.md
```

복사 후 Claude Code를 재시작하면 자동으로 인식됩니다.

## 사용법

Claude Code 세션 안에서 다음과 같이 호출할 수 있습니다.

```
방금 작성한 UserProfile 컴포넌트를 code-reviewer 에이전트로 검토해줘
```

또는 논리적인 작업 단위(컴포넌트, API 라우트, 유틸 함수 등)를 마쳤을 때 자동으로 트리거되도록 두어도 됩니다.

## 사용 시점

다음과 같은 상황에서 사용하면 효과적입니다.

- 새 React 컴포넌트 / 훅 작성을 마쳤을 때
- API 라우트(예: `app/api/**/route.ts`)를 추가/수정했을 때
- 인증, 결제, 입력 검증 등 보안 민감한 로직을 작성했을 때
- PR 올리기 전 셀프 리뷰가 필요할 때
- 프로젝트 컨벤션(CLAUDE.md) 준수 여부를 확인하고 싶을 때

## License

[MIT](./LICENSE)
