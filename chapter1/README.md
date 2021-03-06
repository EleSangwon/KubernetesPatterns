# Chapter1 개요

## 클라우드 네이티브로 가는 길
```
쿠버네티스 같은 클라우드 네이티브 플랫폼에서 가장 인기 있는 애플리케이션 아키텍처는 마이크로서비스 망식

운영 복잡성 대신 개발 복잡성을 활용하고 비즈니스 기능의 모듈화를 통해 소프트웨어 복잡성을 해결 
```

<img width="622" alt="image" src="https://user-images.githubusercontent.com/50174803/159155359-b8341c5d-d550-4a49-8da3-b807f97de2c5.png">

## 분산 애플리케이션 컴포넌트 
```
JVM은 애플리케이션을 생성하기 위한 로컬 인프로세스 빌딩 블록 제공

쿠버네티스는 멀티 노드와 멀티 프로세스로 퍼져 있는 분산 시스템을 구축하기 위한 새로운 분산 기본 요소와
런타임을 제공함으로써 빌딩 블록으로 알려진 사고방식에 완전히 새로운 관점 추가 
쿠버네티스를 사용하면 전체 애플리케이션 동작을 구현하기 위해 로컬 기본 요소에만 의존하지 않는다
```

<img width="865" alt="image" src="https://user-images.githubusercontent.com/50174803/159155553-0bb6d695-88ea-49b6-8be4-312838b531c7.png">

## 컨테이너
```
쿠버네티스 기반 클라우드 네이티브 애플리케이션의 빌당 블록

자바와 비교한다면, 컨테이너 이미지는 클래스와 비슷하며 컨테이너는 객체와 비슷하다.
클래스를 확장해 동작을 재사용하고 변경하는 방과 유사하게, 컨테이너 이미지를 확장해 동작을 재사용하고 
변경하는 컨테이너 이미지를 만들 수 있다.

쿠버네티스는 JVM과 비슷하지만, 멀티 호스트로 분산시켜 컨테이너를 실행하고 관리하는 책임을 진다.

초기화 컨테이너는 객체 생성자 같은 것이고, 데몬세트는 자바 가비지 콜렉터 같은 백그라운드로 실행되는 데몬스레드와 비슷하다.

모듈화된 재사용 가능한 단일 목적의 컨테이너 이미지를 만드는 것은 모든 프로젝트는 물론이고 컨테이너 에코시스템을 통틀어
장기적인 성공을 거두는 데 기본이 된다.
```

## 분산 애플리케이션 영역에서 컨테이너의 목적 
```
컨테이너 이미지는 하나의 문제를 해결하는 기능 단위
"" 는 하나의 팀에 의해 소유되며 릴리즈 주기가 있다
"" 는 자기 완비적이며 런타임 의존성을 정의하고 수행
"" 불변적이며, 한번 만들어지면 변경되지 않는다
"" 런타임 의존성과 자원 요구사항이 정의됨
"" 기능을 노출시키기 위해 잘 정의된 API가 있다
"" 일회용이며 언제든지 스케일업과 스케일다운을 안전하게 수행
```

## 파드 
```
대부분의 클라우드 네이티브 플랫폼은 컨테이너 그룹의 수명주기를 관리하기 위해 기본 요소를 제공하는데
쿠버네티스에는 이를 파드라고 한다.

파드란 컨테이너 그룹의 스케줄링과 배포, 격리된 런타임에 대한 최소 단위다.
파드 안의 모든 컨테이너는 항상 같은 호스트에 스케줄링되고, 호스트 이전이나 스케일 목적으로 함께 배포되며
파일시스템, 네트워킹, 프로세스 네임스페이스를 공유할 수 있다.

동시에 적용되는 수명주기 덕분에 파드 안의 컨테이너는 파일 시스템이나 로컬호스트 혹은 호스트 간 프로세스 통신 매커니즘을 통한
네트워크 통신으로 컨테이너 간의 상호작용할 수 있다.
```
<img width="636" alt="image" src="https://user-images.githubusercontent.com/50174803/159156202-5fed637c-1f11-4646-b6cd-425d49967edd.png">

## 파드의 특성
```
스케줄링의 최소 단위다. 이 말은 스케줄러가 파드에 속한 모든 컨테이너의 요구 사항을 만족하는 호스트를 찾으려 시도한다는 것이다.


```
