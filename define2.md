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


### probe란

# 헬스체크(health check)
1. livenessprobe
2. readinessprobe
3. startupprobe

## 핸들러(handler)를 kubelet이 호출해서 실행
#### 3가지의 핸들러가 있다. 
1. execaction
2. tcpsocketaction
3. httpgetaction

#### 진단결과
* success
* Failure
* Unknown



