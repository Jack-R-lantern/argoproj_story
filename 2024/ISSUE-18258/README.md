# [ISSUE-18258](https://github.com/argoproj/argo-cd/issues/18258) - otelgrpc package should use interceptors in favor of stats handlers

## PR 제출 여부
- [ ] PR

## 연관 이슈/PR
* [opentelemetry-go-contrib/ISSUE-4318](https://github.com/open-telemetry/opentelemetry-go-contrib/issues/4318)
* [opentelemetry-go-contrib/PR-15657](https://github.com/open-telemetry/opentelemetry-go-contrib/pull/4546)

## 이슈 내용
argocd에서 grpc 추적을 위해 사용중인 otelgrpc interceptor가 opentelemetry-go-contrib v0.46.0에서 deprecated로 mark됨.\
이를 사용중인 argocd역시 향후 호환성을 고려해 migration을 진행해야함.
### 구현 목록
- [ ] go.opentelemetry.io/contrib/instrumentation/google.golang.org/grpc/otelgrpc >= v0.46.0 이상으로 업데이트
- [ ] interceptor 사용하는 부분 stats handler로 migration 필요

## 문제 해결

## 학습 내용