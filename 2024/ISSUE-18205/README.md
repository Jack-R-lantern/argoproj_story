# [ISSUE-18205](https://github.com/argoproj/argo-cd/issues/18205) - option to disable writing k8s events

## PR 제출 여부
- [x] [PR](https://github.com/argoproj/argo-cd/pull/18441)

## 연관 이슈/PR
* [ArgoCD/ISSUE-10529](https://github.com/argoproj/argo-cd/issues/10529)
* [ArgoCD/ISSUE-18310](https://github.com/argoproj/argo-cd/issues/18310)

## 이슈 내용
argocd가 발행하는 kubernetes event로 인해 etcd에게 부하를 생성.\
argocd가 etcd에게 주는 부하를 감소시키기 위한 구현 필요.

### 구현 목록
- [ ] application, applicationset, project k8s event 옵션화
- [ ] appcontroller k8s event 옵션화

## 문제 해결
### ArgoCD K8S Event Logging 주체
* util/argo/audit_logger.go
	> ```go
	> type AuditLogger struct
	> ```
ArgoCD의 K8S Event와 관련된 Logging은 `util/argo/audit_logger.go`의 `AuditLogger` 구조체가 담당.

### AuditLogger 의존관계
* server/application/application.go, server/applicationset/applicationset.go, server/project/project.go
	> ```go
	> type Server struct {
	> ...
	>	auditLogger *argo.AuditLogger	
	> }
	> ```
* controller/appcontroller.go
	> ```go
	> type ApplicationController struct {
	> ...
	>	auditLogger *argo.AuditLogger	
	> }
	> ```
총 4곳에서 `AuditLogger`를 통해 K8S Event를 발행하고 있음을 확인.


## 학습 내용