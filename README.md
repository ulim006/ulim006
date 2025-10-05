# 👋 안녕하세요, 프론트엔드 개발자 이조이(Joy Lee)입니다.

사용자 중심의 UI와 구조적인 코드 설계를 지향하는 프론트엔드 개발자입니다.  
React 기반 환경에서 **Context API, 상태 관리, 데이터 구조화, 로컬 스토리지 영속화** 등을 설계하고 구현할 수 있습니다.

---

## ⚙️ 기술 스택 (Tech Stack)

**Frontend**
- React / Vite / React Router  
- Context API / Hooks 기반 상태 관리  
- Styled Components / TailwindCSS  
- HTML5 / CSS3 / JavaScript (ES6+)  

**Backend & Infra**
- Node.js / Express (기초 수준)
- Firebase (Auth / Firestore)
- RESTful API 연동  

**Tools & Environment**
- Git / GitHub / VS Code  
- Figma / Postman / Notion  
- ESLint / Prettier  

---

## 🧩 구현 경험

### 💡 TouchOrder (카페 오더 시스템)
> React 기반 터치형 카페 주문/관리 시스템

- `CategoryTabs`를 통한 카테고리별 메뉴 분류 및 동적 추가  
- `CartContext` & `CartProvider`를 이용한 전역 장바구니 상태 관리  
- `Order.data.js`를 활용한 메뉴 데이터 구조화 및 자동 분류 (커피 / 차 / 음료 / 디저트)  
- `localStorage` 연동으로 로컬 데이터 유지 및 수정 내역 저장  
- `OrderPage` 내에서 섹션 추가·삭제·수정 로직 구현  
- 메뉴 CRUD 로직을 Context 및 useState 기반으로 모듈화

```js
// 예시: Context API를 활용한 장바구니 로직
const addToCart = (item) => {
  setCartItems((prev) => {
    const exists = prev.find((p) => p.id === item.id);
    return exists
      ? prev.map((p) =>
          p.id === item.id ? { ...p, quantity: p.quantity + 1 } : p
        )
      : [...prev, { ...item, quantity: 1 }];
  });
};
