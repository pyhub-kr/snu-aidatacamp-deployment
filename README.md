# fly.io 배포

> 새로운 계정에 대해서는 free plan을 더 이상 지원하지 않습니다. :-(

## 회원가입

https://fly.io 사이트에 회원가입하고, 해외결제가 가능한 신용카드를 등록합니다. 신용카드를 등록하지 않으면 배포를 진행할 수 없습니다.

## 저장소 복제

장고 배포 준비가 된, 저장소를 복제합니다.

```
git clone https://github.com/pyhub-kr/snu-aidatacamp-deployment.git
```

## flyctl 유틸리티 설치

fly.io 에서는 다양한 배포 방법을 지원하고 있습니다. 그 중 로컬에서 flyctl 유틸리티를 활용한 배포를 사용하면, 배포 시에 설치 옵션을 지정할 수 있어 편리합니다.

```
# 윈도우 파워쉘
powershell -Command "iwr https://fly.io/install.ps1 -useb | iex"

# macOS에서는 homebrew를 활용
brew install flyctl
```

## 터미널에서 fly 인증 수행

```
flyctl auth login
```

## 지원 데이터센터 목록

```
flyctl platform regions
```

## 배포 수행

아래 명령을 수행하시기 전에 먼저 배포 이름을 정하셔야 합니다.

+ 추천 : `여러분의아이디-django`

아래 명령에서 아이디 부분을 변경하시고, 아래 명령으로 배포를 진행하실 수 있습니다.

```
fly launch --name 여러분의아이디-django --env ALLOWED_HOSTS=여러분의아이디.fly.dev --region nrt
```

코드 변경 후에 재배포는 아래 명령으로 가능합니다.

```
fly deploy
```

## 더 알아보기

fly.io에서의 django 배포에 대해서는 아래 문서를 참고하세요.

+ https://fly.io/docs/django/

