# 파드(pod)
* #### 컨테이너를 묶어서 관리하는 기본 단위
* #### 웹서버, 로그 수집기, 볼륨 컨테이너 등 여러 컨테이너를 하나의 컨테이너 안에 넣게 되면, 즉 프로세스를 2개 이상 실행하도록 설정하는 것이 쉽지는 않지만 파드를 통해 관리하면 편하다

파드 설정 예
#### pod-sample.yaml
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
#### 9번쨰 줄에서 '-'를 쓰는 이유는 spec.containers의 하위 필드를 배열 형태로 묶겠다는 뜻이다. 그래서 .spec.containers[]라고 표기한다. 


### container probe란 컨테이너를 조사하는 것이다.

# 헬스체크(health check)
1. livenessProbe : 컨테이너의 상태를 확인하고 Failure일 결우 restartpoilcy에 의해서 container가 재실행 된다.
2. readinessprobe : livenessProbe와 같이 상태를 확인하지만 failure일 경우에 엔드포인트부분을 제거한다. 즉 재실행을 하는것이 아닌 컨테이너를 배재(제거)해버린다.
3. startupprobe

## 핸들러(handler)를 kubelet이 호출해서 실행
#### 3가지의 핸들러가 있다. 
1. execaction : exec를 통해서 명령어가 실행 되는지 확인 한다.
2. tcpsocketaction
3. httpgetaction

#### 진단결과
* success
* Failure
* Unknown



