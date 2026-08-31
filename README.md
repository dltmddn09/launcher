# launcher

자주 쓰는 업무 도구 모음. GitHub Pages로 서비스한다 → https://dltmddn09.github.io/launcher/

| 경로 | 내용 | 수정 방법 |
|---|---|---|
| `index.html` | 런처 페이지 (도구 카드 목록) | 직접 수정 |
| `monitor/index.html` | 종토방 모니터링 대시보드 | **직접 수정 금지 — 자동 생성물** |

## monitor/ 는 손대지 말 것

`monitor/index.html`은 `claude-work` 레포의 `종토방 모니터링/` 파이프라인이
**30분마다 덮어쓴다.** 여기서 고쳐봐야 다음 갱신에 사라진다.

내용을 바꾸려면 `종토방 모니터링/template.html`을 고쳐야 한다.

## 커밋 히스토리에 대해

대시보드 갱신 커밋(`chore(monitor):`)은 **하나를 계속 amend 해서** 히스토리가 늘지 않게 한다.
30분마다 새 커밋을 쌓으면 1년에 250MB가 되기 때문이다.

따라서 이 레포는 **자동화가 force push를 한다.** 다만 직전 커밋이 `chore(monitor):`로
시작할 때만 amend 하므로, 사람이 만든 커밋은 덮어쓰지 않는다.

로컬에 클론해 두고 작업했다면, 자동 갱신 이후에는 `git pull` 대신
`git fetch && git reset --hard origin/main`으로 맞추는 편이 안전하다.
