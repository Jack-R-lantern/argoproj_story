# [ISSUE-17956](https://github.com/argoproj/argo-cd/issues/17956) - git ls-remote failure counter

## PR 제출 여부
- [ ] PR

## 연관 이슈/PR
* [ISSUE-15658](https://github.com/argoproj/argo-cd/issues/15658)

## 이슈 내용
[PR-15657](https://github.com/argoproj/argo-cd/pull/15657#issuecomment-2074882760)에서 언급된 내용을 확인하면, git fetch, ls-remote를 요청해서 실패한 경우 확인할 metric이 없음.
그로 인해 문제가 발생했을때 정확하게 파악하지 못하는 이슈 발생.
### 구현 목록
- [ ] ls-remote request fail 측정 매트릭 추가/반영

## 문제 해결

## 학습 내용
### git command 학습
* git ls-remote
* git ls-files
* git lfs
