# IT Audit Pro - 정보시스템 감리 원페이지 웹사이트

정보시스템 감리 서비스를 제공하는 전문 기업의 원페이지 랜딩 페이지입니다. 모던하고 전문적인 블랙 테마와 오렌지 악센트 컬러를 사용하여 신뢰감과 전문성을 강조했습니다.

## 프로젝트 개요

- **유형**: 원페이지 랜딩 페이지
- **주요 색상**: 블랙 (#0a0a0a) + 오렌지 악센트 (#ED985F)
- **기술 스택**: 순수 HTML5, CSS3, JavaScript (프레임워크 없음)
- **반응형**: 모바일, 태블릿, 데스크톱 지원

## 주요 섹션

1. **Hero Section**: 비디오 배경과 함께 메인 메시지 전달
2. **About**: 서비스의 강점 4가지 소개
3. **Services**: 6가지 감리 서비스 상세 설명
4. **Team**: 전문가 경력 및 자격증 정보
5. **Location**: 오시는 길 및 사무실 정보
6. **Reviews**: 고객 후기 6건
7. **Contact**: 문의 폼 및 연락처 정보

## 핵심 기술 및 기법

### 1. CSS 고급 기법

#### CSS Variables (Custom Properties)
```css
:root {
    --primary-color: #ED985F;
    --bg-primary: #0a0a0a;
    --text-primary: #E6E6E6;
    /* ... */
}
```
테마 색상을 중앙 집중식으로 관리하여 유지보수성 향상

#### CSS Grid & Flexbox
- **Grid**: 서비스 카드, 리뷰 카드, 자격증 등 복잡한 레이아웃 구성
- **Flexbox**: 네비게이션, 버튼 그룹 등 1차원 레이아웃

#### 그라디언트 및 그림자 효과
```css
background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.7);
```

#### CSS Filters
아이콘에 브랜드 컬러 통일 적용:
```css
filter: grayscale(100%) brightness(1.2) sepia(100%) hue-rotate(340deg) saturate(1.5);
```

#### Backdrop Filter
```css
backdrop-filter: blur(10px);
```
네비게이션 바의 블러 효과로 모던한 느낌 연출

### 2. JavaScript 인터랙티브 기능

#### Intersection Observer API
스크롤 시 요소가 뷰포트에 들어올 때 애니메이션 실행:
```javascript
const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            entry.target.style.opacity = '1';
            entry.target.style.transform = 'translateY(0)';
        }
    });
}, observerOptions);
```

**장점**:
- `scroll` 이벤트보다 성능 효율적
- 자동으로 요소의 가시성 감지
- 이미지 레이지 로딩에도 활용

#### 스무스 스크롤
```javascript
window.scrollTo({
    top: targetPosition,
    behavior: 'smooth'
});
```
네비게이션 클릭 시 부드러운 스크롤 이동

#### 동적 네비게이션 하이라이트
현재 보고 있는 섹션에 맞춰 네비게이션 링크 활성화

#### 모바일 메뉴 토글
햄버거 메뉴 아이콘 애니메이션과 슬라이드 메뉴

#### 폼 검증 및 포매팅
- 실시간 입력 검증
- 전화번호 자동 포매팅 (000-0000-0000)
- blur 이벤트로 필수 필드 검사

#### 패럴랙스 효과
```javascript
hero.style.transform = `translateY(${scrolled * 0.5}px)`;
```
히어로 섹션에 약간의 시차 효과 적용

#### Scroll to Top 버튼
500px 이상 스크롤 시 자동 표시되는 상단 이동 버튼

### 3. 반응형 디자인

#### 모바일 우선 접근법
```css
@media (max-width: 968px) { /* 태블릿 */ }
@media (max-width: 640px) { /* 모바일 */ }
```

#### 적응형 그리드
```css
grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
```
화면 크기에 따라 자동으로 열 개수 조정

#### 반응형 타이포그래피
화면 크기별로 폰트 사이즈 조정하여 가독성 확보

### 4. UX/UI 디자인 패턴

#### 호버 효과
- 카드 호버 시 상승 효과 (`translateY`)
- 테두리 색상 변경
- 아이콘 컬러 강조
- 그림자 강화

```css
.service-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 12px 24px rgba(0, 0, 0, 0.5);
    border: 0.5px solid rgba(237, 152, 95, 0.8);
}
```

#### 트랜지션 애니메이션
```css
transition: all 0.3s ease;
```
모든 인터랙티브 요소에 부드러운 전환 효과

#### Fade-in 애니메이션
```css
@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

### 5. 성능 최적화

#### 이미지 레이지 로딩
```javascript
const imageObserver = new IntersectionObserver(...);
lazyImages.forEach(img => imageObserver.observe(img));
```

#### CSS 하드웨어 가속
```css
transform: translateY(-8px);  /* GPU 가속 사용 */
will-change: transform;        /* 브라우저에 힌트 제공 */
```

#### 비디오 최적화
```html
<video autoplay loop muted playsinline>
```
- `playsinline`: iOS에서 전체화면 방지
- `muted`: 자동재생을 위한 필수 속성

## 파일 구조

```
corporate-onepage-black/
├── index.html          # 메인 HTML 파일
├── styles.css          # 모든 스타일시트
├── script.js           # JavaScript 인터랙션
├── landing.mp4         # 히어로 섹션 배경 비디오
└── README.md           # 프로젝트 문서
```

## 브라우저 지원

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

**주요 기능별 지원**:
- CSS Grid: 모든 모던 브라우저
- Intersection Observer: IE 제외 모든 브라우저
- CSS Custom Properties: IE 제외 모든 브라우저
- backdrop-filter: Safari 9+, Chrome 76+

## 설치 및 실행

### 로컬 실행
```bash
# 저장소 클론
git clone https://github.com/jeonck/corporate-onepage-black.git

# 디렉토리 이동
cd corporate-onepage-black

# 로컬 서버 실행 (Python 3)
python -m http.server 8000

# 또는 Node.js의 http-server 사용
npx http-server
```

브라우저에서 `http://localhost:8000` 접속

### GitHub Pages 배포
1. GitHub 저장소의 Settings > Pages
2. Source를 `main` 브랜치로 설정
3. 자동 배포 완료

## 커스터마이징 가이드

### 색상 변경
`styles.css`의 `:root` 섹션에서 CSS 변수 수정:
```css
:root {
    --primary-color: #your-color;
    --bg-primary: #your-bg-color;
}
```

### 콘텐츠 수정
`index.html`에서 각 섹션의 텍스트, 이미지, 링크 수정

### 섹션 추가/제거
1. HTML에서 섹션 추가/제거
2. 네비게이션 메뉴 업데이트
3. JavaScript의 `sections` 변수가 자동으로 인식

## 주요 학습 포인트

이 프로젝트를 통해 학습할 수 있는 내용:

1. **모던 CSS 레이아웃**: Grid, Flexbox의 실전 활용
2. **CSS 변수**: 테마 관리 및 유지보수성
3. **Intersection Observer**: 성능 최적화된 스크롤 이벤트
4. **반응형 디자인**: 모바일 우선 설계
5. **JavaScript DOM 조작**: Vanilla JS로 인터랙티브 기능 구현
6. **폼 검증**: 실시간 유효성 검사
7. **애니메이션**: CSS 애니메이션과 JavaScript의 조화
8. **접근성**: 시맨틱 HTML, ARIA 레이블

## 라이선스

MIT License

## 제작자

Created with [Claude Code](https://claude.com/claude-code)

## 버전 히스토리

- **v1.1.0** (2025-12-30)
  - 디자인 일관성 개선: 모든 서비스 카드를 블랙 테마로 통일
  - 아이콘 컬러 통일: 오렌지 톤으로 브랜드 일관성 확보
  - 호버 효과 추가: 카드 호버 시 아이콘 색상 강조
  - UX 개선: 문의 폼 버튼 크기 및 여백 조정

- **v1.0.0** (2025-12-30)
  - 초기 릴리즈
  - 원페이지 레이아웃 구현
  - 6개 섹션 완성
  - 반응형 디자인 적용

## 문의

프로젝트 관련 문의나 개선 제안은 GitHub Issues를 통해 남겨주세요.
