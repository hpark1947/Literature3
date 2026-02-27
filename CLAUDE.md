# CLAUDE.md - 프로젝트 규정 및 참고사항

## GitHub 한글 파일명 깨짐 문제 해결

GitHub 웹에서 한글 파일명이 `\354\202\254\353\236\8C` 같은 이스케이프 시퀀스로 표시되는 경우가 있다.
이는 GitHub의 트리 렌더링 캐시 문제로, 새로운 commit을 push하면 캐시가 갱신되어 해결된다.

### 해결 방법
```bash
git commit --allow-empty -m "GitHub 트리 캐시 갱신"
git push
```

### 주의사항
- 이 문제는 파일 자체의 인코딩 문제가 아니라 GitHub 웹 UI의 캐시 문제이다.
- 빈 커밋(empty commit)으로도 캐시가 갱신되므로 코드 변경 없이 해결 가능하다.
- 한글 파일명이 GitHub에서 깨져 보일 때마다 이 방법을 적용한다.
