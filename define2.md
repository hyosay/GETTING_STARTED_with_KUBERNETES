# 1. 파드(pod)
* k8s에서 **컨테이너**를 묶어서 관리하는 **기본 단위**
* 웹서버, 로그 수집기, 볼륨 컨테이너 등 여러 컨테이너를 하나의 컨테이너 안에 넣게 되면, 즉 프로세스를 2개 이상 실행하도록 설정하는 것이 쉽지는 않지만 파드를 통해 관리하면 편하다


#### pod-sample.yaml(Pod 예시)
```
apiVersion: v1
kind: pod
metadata:
  name: kubernetes_simple-pod
  labels:
    app: kubernetes-simple-pod
spec:
  containers:
  - name: kubernetes-simple-pod
    image: arisu1000/simple-container-app:latest
    ports:
    - containerPort:8080
```
*9번쨰 줄에서 '-'를 쓰는 이유는 spec.containers의 하위 필드를 배열 형태로 묶겠다는 뜻이다. 그래서 .spec.containers[]라고 표기한다.*



## 📌 1.1 헬스체크(health check)
**컨테이너의 접속이나 명령어를 실행하여 제대로 작동하고, 건강한지 확인 하는 것이다.**

### 1.1.1 container probe(컨테이너 프로브)
컨테이너를 **조사**하는 것이다.

1. livenessProbe : 컨테이너의 상태를 확인하고 Failure일 결우 restartpoilcy에 의해서 container가 재실행 된다.
2. readinessProbe : livenessProbe와 같이 상태를 확인하지만 failure일 경우에 엔드포인트부분을 제거한다. 즉 재실행을 하는것이 아닌 컨테이너를 배재(제거)해버린다.
3. startupProbe

### 1.1.2 핸들러(handler)
kubelet이 호출해서 실행하며 핸들러에는 **세가지**가 존재한다.

1. execaction : exec를 통해서 명령어가 실행 되는지 확인 한다. 종료코드가 **0**이면 Success라고 진단.
2. TCPsocketaction : container 안에 지정된 IP와 포트로 TCP의 statu를 확인하고 port가 연려있으면 Success라고 진단.
3. HTTPgetaction : container 안에 지정된 ip, port, 경로로 HTTP GET요청을 보냄. 응답 상태 코드가 200 ~ 400 사이면 Success라고 진단.

#### 진단결과
* success
* Failure
* Unknown

## 📌 1.2 PodtopologySpread
우선 **topology**(토폴로지)란 노드,링크를 잊는 네트워크 방식이다.

**k8s에서 파드를 노드에 배치할 떄 상황에 따라 다르지만 대부분 skew의 차가 적게 나도록 하여 노드에 파드를 배포하기 때문에 이것을 관리하여야한다.**



