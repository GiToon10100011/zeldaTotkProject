# 🏹 The Legend of Zelda: Tears of the Kingdom 팬 웹사이트

![Zelda TOTK 메인 이미지](https://zeldatotkfullpage.web.app/images/totkbg/logo-intro-2x.webp)

## 📋 프로젝트 소개

이 프로젝트는 닌텐도의 인기 게임 '젤다의 전설: 티어스 오브 더 킹덤'의 팬 웹사이트입니다. 풀페이지 스크롤링과 인터랙티브 요소를 활용하여 게임의 세계관, 캐릭터, 능력 시스템 등을 소개합니다.

## 📋 프로젝트 정보

- **개발 기간**: 2024.08 ~ 2024.09
- **개발자**: 전진우
- **배포 주소**: [https://zeldatotkfullpage.web.app](https://zeldatotkfullpage.web.app)

## 🛠️ 사용 기술
- HTML5
- CSS3
- JavaScript
- jQuery
- 라이브러리:
  - Featherlight (라이트박스)
  - Slick (슬라이더)
  - ScrollTo (스크롤 애니메이션)
  - PSE (페이지 스크롤 효과)

## ✨ 주요 기능

### 1. 풀페이지 스크롤 내비게이션
사용자가 마우스 휠을 사용하여 섹션 간 이동할 수 있는 풀페이지 스크롤 내비게이션을 구현했습니다.

```javascript
new fullpage("#fullpage", {
  autoScrolling: true,
  scrollHorizontally: true,
  slidesNavigation: true,
  controlArrows: true,
  anchors: ["home"],
});
```

### 2. 인터랙티브 애니메이션
마우스 움직임에 반응하는 '루모스' 효과와 같은 인터랙티브 애니메이션을 구현했습니다.

```javascript
const loop = () => {
  targetX += (x - targetX) * speed;
  targetY += (y - targetY) * speed;

  lumos.style.transform = `translate(${targetX - lumosSize / 2}px, ${
    targetY - lumosSize / 1.4
  }px)`;

  window.requestAnimationFrame(loop);
};
```

### 3. 반응형 디자인
다양한 화면 크기에 대응하는 반응형 디자인을 구현했습니다.

```javascript
function checkWindowSize() {
  const windowWidth = window.innerWidth;
  if (windowWidth <= 768) {
    $(".trailers").slick({
      dots: true,
      infinite: true,
      speed: 300,
      slidesToShow: 1,
      slidesToScroll: 1,
      arrows: false,
      autoplay: true,
      autoplaySpeed: 4000,
    });
  } else {
    $(".trailers").slick("unslick");
  }
}
```

### 4. 캐릭터 인터랙션
캐릭터 섹션에서 마우스 호버 시 캐릭터 정보가 표시되는 인터랙션을 구현했습니다.

```javascript
characters.forEach((character, index, arr) => {
  character.addEventListener("mouseover", () => {
    arr.forEach((item, i) => {
      if (index !== i) {
        characters[i].style.flex = 0;
        characters[i].style.opacity = 0;
      }
    });
    // 추가 효과
  });
});
```

### 5. 비디오 트레일러 섹션
게임 트레일러를 볼 수 있는 비디오 섹션을 구현했습니다.

## 📁 프로젝트 구조

```
zeldaTotkProject/
├── index.html              # 메인 페이지
├── project-detail-01.html  # 프로젝트 상세 페이지
├── style.css               # 컴파일된 CSS
├── style.scss              # SCSS 소스
├── reset.css               # 리셋 CSS
├── reset.scss              # 리셋 SCSS
├── script.js               # 메인 JavaScript
├── modal.js                # 모달 관련 JavaScript
├── fonts/                  # 폰트 파일
│   └── HyliaSerifBeta-Regular.otf
├── images/                 # 이미지 파일
│   ├── totkbg/             # 배경 이미지
│   ├── totkmodal/          # 모달 이미지
│   └── totksvgs/           # SVG 아이콘
└── Libraries/              # 외부 라이브러리
    ├── Feather/            # Featherlight 라이브러리
    ├── PSE/                # Page Scroll Effects
    ├── Slick/              # Slick 슬라이더
    └── scrollTo/           # ScrollTo 라이브러리
```

## 🎨 디자인 특징

### 1. 게임 테마에 맞는 폰트 사용
HyliaSerif 폰트를 사용하여 게임의 분위기를 살렸습니다.

```scss
@font-face {
  font-family: "HyliaSerif";
  src: url("./fonts/HyliaSerifBeta-Regular.otf");
}
```

### 2. 애니메이션 효과
다양한 CSS 애니메이션을 활용하여 웹사이트에 생동감을 부여했습니다.

```scss
@keyframes scale-easeOutBounce {
  0% { transform: scale(1); }
  12% { transform: scale(0.89); }
  // ...
  100% { transform: scale(0); }
}
```

### 3. SVG 아이콘 활용
SVG 아이콘을 활용하여 시각적 요소를 강화했습니다.

## 📱 반응형 디자인

모바일 및 태블릿 환경에서도 최적화된 사용자 경험을 제공하기 위해 미디어 쿼리를 활용한 반응형 디자인을 구현했습니다.

## 🚀 설치 및 실행 방법

1. 저장소를 클론합니다:
   ```
   git clone https://github.com/GiToon10100011/zeldaTotkProject.git
   ```
2. 프로젝트 폴더로 이동합니다:
   ```
   cd zeldaTotkProject
   ```
3. 웹 브라우저에서 `index.html` 파일을 엽니다.

## ⚠️ 면책 조항

이 프로젝트는 팬이 제작한 비공식 사이트입니다. '젤다의 전설: 티어스 오브 더 킹덤'과 관련된 모든 콘텐츠의 저작권은 닌텐도에 있습니다.

## 👥 기여
이슈 제기 및 풀 리퀘스트는 언제나 환영합니다. 대규모 변경사항은 먼저 이슈를 통해 논의해주세요.

## 📞 연락처
프로젝트 관리자: boon10034@gmail.com
