# Git

* `git clone https://github.com/anaclumos/hello-wtc.git` 저장소를 복제한다
* `git add file` 파일을 Stage한다
* `git commit -m` Stage된 파일들의 변화를 브랜치에 기록한다 (`-m`은 "메시지"라는 뜻! 한줄 메시지를 작성하는 것으로, 안 좋은 개발 습관이다)
* `git push origin master` 저장소의 정보를 origin 저장소의 master 브랜치에 업로드한다
* `git pull origin master` origin 저장소의 master 브랜치에서 정보를 다운로드한다

# 좋은 커밋이란 무엇인가?

* 한 커밋은 하나의 액션을
* 커밋 메시지만 보고도 변화를 예상할 수 있어야 함

# Github flow란?

* 총 5가지의 브랜치를 사용해서 운영
* master: 기준이 되는 브랜치로 제품을 배포하는 브랜치
* develop: 개발 브랜치로 개발자들이 이 브랜치를 기준으로 각자 작업한 기능들을 합침
* feature: 단위 기능을 개발하는 브랜치로 기능 개발이 완료되면 develop 브랜치
* release: 배포를 위해 master 브랜치로 보내기 전에 먼저 QA를 하기 위한 브랜치
* hotfix: master 브랜치로 배포를 했는데 버그가 생겼을 때 긴급 수정하는 브랜치

* 일단 master 브랜치에서 시작을 합니다.
* 동일한 브랜치를 develop에도 생성을 합니다. 개발자들은 이 develop 브랜치에서 개발을 진행합니다.
* 개발을 진행하다가 회원가입, 장바구니 등의 기능 구현이 필요할 경우 A개발자는 develop 브랜치에서 feature 브랜치를 하나 생성해서 회원가입 기능을 구현하고 B개발자도 develop 브랜치에서 feature 브랜치를 하나 생성해서 장바구니 기능을 구현합니다.
* 완료된 feature 브랜치는 검토를 거쳐 다시 develop 브랜치에 합칩니다.(Merge)
* 이제 모든 기능이 완료되면 develop 브랜치를 release 브랜치로 만듭니다. 그리고 QA(품질검사)를 하면서 보완점을 보완하고 버그를 픽스합니다.
* 모든 것이 완료되면 이제 release 브랜치를 master 브랜치와 develop 브랜치로 보냅니다. master 브랜치에서 버전추가를 위해 태그를 하나 생성하고 배포를 합니다.
* 배포를 했는데 미처 발견하지 못한 버그가 있을 경우 hotfixes 브랜치를 만들어 긴급 수정 후 태그를 생성하고 바로 수정 배포를 합니다.
