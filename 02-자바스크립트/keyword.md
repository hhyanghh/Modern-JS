# 폴리필
> 📝 정리: 박하은

구글에 **Polyfill**을 검색하면 아래와 같다.

<img width="300" alt="Polyfill 구글이미지 검색" src="https://github.com/pullingoff/Modern-JS/assets/50111853/8eac99f1-6836-4776-ab1b-6228fd457d9f"/>

[MDN 문서](https://developer.mozilla.org/en-US/docs/Glossary/Polyfill)에 따르면 폴리필은 이전 버전의 브라우저가 지원하지 않는 현대의 기능을 제공하기 위한 코드를 말한다. 즉 **브라우저의 새로운 버전이 나오면서 지원하지 않던 JS 코드를 지원할 수 있도록 구현을 채워주는 코드**를 말한다.

한 예시로 제이쿼리 1세대에서 이런 문제가 많았는데, 각 브라우저가 지원하지 않는 기능들이 많아 개발자들이 각 브라우저를 위한 코드를 짜줘야해서 불편했다. 

Polyfill을 추가하면 오래된 브라우저에서도 코드를 동일하게 실행할 수 있다. 다만 실행하는 폴리필 스크립트가 많아지면 _성능에도 영향을 끼칠 수 있다_. 그래서 꼭 필요한 폴리필 스크립트만 선택적으로 불러오는 방법이 몇개 있는데 그 중에서도 가장 많이 사용되는 것은 바벨이다.

# 바벨

바벨이란 **폴리필을 해주는 트랜스파일러**다. 바벨 내부의 [core-js](https://github.com/zloirock/core-js)라는 라이브러리가 폴리필을 해준다.
`@babel/preset-env`의 스마트 프리셋을 사용하면 원하는 브라우저/버전을 지원할 폴리필만 불러온다. 이 프리셋은 이미 정의된 브라우저 목록에 따라 필요없는 폴리필을 알아서 제거해준다. `babel.config.js`에서 `presets`의 `targets`로 지원해야하는 브라우저와 버전을 명시하면 된다.

# 트랜스파일러


### 참고
- [토스의 똑똑하게 브라우저 Polyfill 관리하기](https://toss.tech/article/smart-polyfills)
