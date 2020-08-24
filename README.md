[https://www.udemy.com/course/html5-game-development-2d-platform-game-fundamentals/learn/lecture/17748270#overview](https://www.udemy.com/course/html5-game-development-2d-platform-game-fundamentals/learn/lecture/17748270#overview)

1. Sprite free resources
   - [https://opengameart.org/](https://opengameart.org/)
   - [https://itch.io/game-assets/free](https://itch.io/game-assets/free)

project 에 사용된 sprite resource : [https://finalbossblues.itch.io/pixel-platformer-pack](https://finalbossblues.itch.io/pixel-platformer-pack)

project 에 사용된 github url : [https://github.com/jedhastwell/platform-game-fundamentals](https://github.com/jedhastwell/platform-game-fundamentals)

2. 파일 구성

- Game.js
  - game 의 틀을 구성하는 요소
  - game 에 필요한 image / spritesheet / map / layer / 로딩
  - game 에 사용되는 entities 를 initilizing 함
  - 사용되는 함수
    - preload
      - 게임에 사용되는 assets 들을 로딩
    - create
      - 게임 사용되는 요소들을 create
      - map / 캐릭터 / images 등을 생성
      - 카메라 설정
    - addHero
      - 새로운 캐릭터를 생성하고 필요한 요소값들을 설정
    - addMap
      - 게임의 지도 및 레이어 등을 설정
      - 레이어들의 depth (index) 를 설정
      - 각 레이어 및 Object 들의 collision 설정
    - update
      - 게임이 시작됨에 따라 끊임없이 반복되어 호출되는 함수
      - 게임의 어떤 흐름이나 로직을 처리함
- Hero.js

  - 예제에 사용되는 캐릭터 entities
  - constructor
    - 캐릭터의 시작 위치, 필요한 설정을 initializing
    - 캐릭터의 상태는 javascript-state-machine 이라는 라이브러리 사용
      - 각 상태를 지정하고, a 상태에서 b 상태로 변경시, 가능한지 여부를 설정한다.
      - 상태에 따른 함수를 설정하여 캐릭터의 animation 과 연동함
    - 캐릭터 시작시 필요한 함수를 호출
      - this.setupAnimations()
        - 캐릭터의 상태에 따라서 animation 을 처리
        - idle, run, pivot, jump, flip, die 등의 상태를 지정하고 관리
      - this.setupMovement()
        - 키보드 입력 키에 따라서 캐릭터의 상태를 업데이트
        - standing, jump, flip, fall, touchdown, die 등의 캐릭터 행동 관리
  - preUpdate
    - Sprite 의 animation 을 반복하여 호출

- config.js
  - 게임의 config 를 설정함
  - game의 화면, 배경 색, scale, render, 등을 처리
  - game 에 사용되는 physics 요소들을 설정가능
    - 중력 등
    - game Object 들에 대해 debug 출력가능

3. Tiled

- 주어진 sprite 이미지를 활용하여 게임의 배경을 생성가능한 외부 프로그램

  ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/09c63281-fdff-4e11-884f-6582fa77c75c/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/09c63281-fdff-4e11-884f-6582fa77c75c/Untitled.png)

- 설정한 배경들과 Phaser 의 코드를 연동가능 (⭐️⭐️⭐️⭐️⭐️)

4. Texture Packer

- 게임에 사용되는 Sprite 들을 게임에 맞추어 수정이 가능
- margin / padding 등 수정가능
- 그 외에 많은 기능이 있어 편리하다고 함 (길게는 소개 안함)

- demo 링크 : [https://kangisworking.github.io/html5-game-development-2d-platform-game-fundamentals/dist/index.html](https://kangisworking.github.io/html5-game-development-2d-platform-game-fundamentals/dist/index.html)
