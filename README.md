# 오운완 프로젝트 - 운동 기록 서포트


## 프로젝트 개요

### 사용 기술
- [![Svelte][Svelte.dev]][Svelte-url]
- [![Springboot][Spring.dev]][Spring-url]

MVC Architecture 사용

### 프로젝트 시작하는 방법
node.js(npm, npx) 설치 필요 (개발 당시 20.11.0 LTS 설치)

   - Windows

         > git clone https://github.com/elephantLikesApple/OhUnWan.git
         > cd OhUnWan
         > ./gradlew.bat build
         > ./gradlew.bat bootRun
         > cd frontend
         > npm install
         > npm run dev

   - Mac, Linux

         > git clone https://github.com/elephantLikesApple/OhUnWan.git
         > cd OhUnWan
         > ./gradle build
         > ./gradle bootRun
         > cd frontend
         > npm install
         > npm run dev

### 프로그램 필요성

- 각종 sns에 '갓생', '오운완' 키워드가 유행하며 운동 기록을 인증하는 이들이 늘어남을 체감한다.
- 주기적으로 운동하는 Z세대가 많고, 이들은 주로 스마트워치나 모바일 어플 등으로 이를 기록한다.
- 주 기록 수단과 운동 내용을 보면 타이머 기능을 많이 사용하는 것으로 추측할 수 있다.

![](https://s3.ap-northeast-2.amazonaws.com/univ-20slab/FileData/Board/Content/202304/38474/8cad5deb-1223-4b8a-a145-7dc5d3fffbf5.png)

출처 : [대학내일20대연구소 | 주기적으로 운동하는 Z세대가 91.2%나 된다고?](https://www.20slab.org/archives/38474)

출처 : [<2023년 MZ세대의 운동 트렌드>, 대학내일20대연구소, 2023.02.28](https://www.20slab.org/Archives/38432)

![](https://s3.ap-northeast-2.amazonaws.com/univ-20slab/FileData/Board/Content/202304/38475/56b3113c-dd5d-40d0-83c4-c33fffd429e1.png)

출처 : [대학내일20대연구소 | Z세대가 운동을 기록하는 방식 TOP 5](https://www.20slab.org/Archives/38475)


## 기능 설명

### 필수 기능

1. 운동 루틴을 지정할 수 있다.
   - 운동은 근력운동, 스트레칭, 휴식 세 가지 유형으로 구분할 수 있다.
   - 드롭다운으로 어떤 유형의 운동인지 선택할 수 있다.
   - '+버튼'을 누르면 새로운 루틴이 생성된다.
   - '-버튼'을 누르면 해당 루틴이 삭제된다.


2. 근력운동
   - 기구 이름이나 운동 이름을 지정할 수 있다.
   - 목표 횟수를 지정할 수 있다.
   - 스탑워치 기능을 시작하여 한 세트를 시작하는 데 얼만큼이 시간이 걸렸는지 측정할 수 있다.
   - 스탑워치를 종료하면 자동으로 다음 루틴을 시작한다.


3. 스트레칭
   - 스트레칭 이름을 지정할 수 있다.
   - 목표 시간을 지정할 수 있다.
   - 타이머 기능을 이용하여 운동 시간을 측정할 수 있다.
   - 타이머가 끝나면 자동으로 다음 루틴을 시작한다.


4. 휴식
   - 목표 시간을 지정할 수 있다.
   - 타이머 기능을 이용하여 휴식 시간을 측정할 수 있다.
   - 타이머가 끝나면 자동으로 다음 루틴을 시작한다.


### 업데이트 목표

1. 운동 결과창 표시
   - 전체 운동 시간을 표시한다.
   - sns 공유 기능을 사용할 수 있다.


2. 루틴 드래그 가능
   - 이미 작성된 루틴들을 드래그하여 위치를 변경할 수 있다.


3. 로그인
   - 특정 유저의 운동 기록을 저장할 수 있다.
   - 자신의 운동 결과창을 다시 확인할 수 있다.
   - 달력을 생성하여 이전 기록을 열람할 수 있다.


4. 전체 루틴 복사 기능
   - 특정 날짜의 루틴을 복사하고, 다른 날짜에 붙여넣기 할 수 있다.


## 개발 현황 및 사용 예시


## 연락처
[![github][github.profile]][github-url]  
[![naver][naver.mail]][naver-url]


[Svelte.dev]: https://img.shields.io/badge/Svelte_1.0.0-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Spring.dev]: https://img.shields.io/badge/SpringBoot_3.2.2-6CB52D?style=for-the-badge&logo=SpringBoot&logoColor=F4F4F4
[Spring-url]: https://spring.io/projects/spring-boot/
[github.profile]: https://img.shields.io/badge/elephantLikesApple-888888?style=for-the-badge&logo=github&logoColor=FFFFFF&label=github
[github-url]: https://github.com/elephantLikesApple
[naver.mail]: https://img.shields.io/badge/elephant890-F4F4F4?style=for-the-badge&logo=naver&logoColor=F4F4F4&label=naver&labelColor=03C75A
[naver-url]: https://mail.naver.com/write?to=elephant890@naver.com