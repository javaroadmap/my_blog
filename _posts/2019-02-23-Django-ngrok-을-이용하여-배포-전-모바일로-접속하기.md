---
comments: true
title: Django 노트&#58; ngrok을 이용하여 배포 전 모바일로 접속하기
key: 201902230
picture_frame: shadow
tags:
  - Django
---

ngrok을 이용하여 간단하게 모바일로 접속하자

<!--more-->

[ngrok 다운로드 링크](https://ngrok.com/download)

먼저 ngrok을 다운로드합니다.

장고 서버 가동 후 ngrok을 아래 명령어로 실행합니다.

    python manage.py runserver 8000
    ./path/to/ngrok http 8000

<br>

![text](https://raw.githubusercontent.com/q0115643/my_blog/master/assets/images/django/ngrok/0.png){:width="500px"}

<br>

ngrok.io로 끝나는 주소가 보입니다.

그 주소를 통해 접속을 하면 되는데, 먼저 settings.py의 ALLOWED_HOSTS에 해당 주소를 추가합니다.

    ALLOWED_HOSTS = ['~~~~.ngrok.io']

헌데, 이렇게 하면 ngrok을 재실행할 때마다 ALLOWED_HOSTS에 등록해야하는 url이 변하므로 아래와 같이 합니다.

    ALLOWED_HOSTS = ['*']
