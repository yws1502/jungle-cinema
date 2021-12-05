# jungle-cinema

## 회고 및 배운점

### scss 적용하기
- scss의 다양한 기능을 경험할 수 있었다.
- 기존의 css만을 이용했을 때 선택자를 길게 늘어 뜨렸지만 scss를 사용하여 더 깔끔하게 코드를 작성 하는 경험을 했습니다.
- scss의 mixin기능과 변수 지정 기능을 사용하고 자주 사용되는 코드를 미리 저장하여 필요할 때마다 꺼내 쓰는 경험을 했습니다.(여러 줄에 걸쳐야 되거나 컬러 코드를 일일히 작성할 수고가 줄었습니다.)
- 하나의 scss파일에 관리하는 것이 아닌 역할 별로 파일을 분리하여 관리하였습니다. (mixin파일의 경우 특정  mixin에 문제가 있을 때 찾기 수월하였습니다.)
- 하지만 html을 작성할 떄와 같이 scss를 작성하여 이렇게 작성하는 것이 다른 분들에게도 읽기 편한 코드가 되는지에 대한 의문이 들었습니다.

### flex
- flex를 사용한 이유
    - 화면이 줄었을 때 별도의 media query를 지정하지 않고 container에 크기에 맞게 동적으로 한행의 item들을 배치하기 위해 flex-wrap을 사용했습니다.

### ellipsis
- 영화의 제목, 혹은 출연진이 많아 짐에 따라 item의 크기를 넘어가는 문제를 방지하기 위해 ellipsis를 적용하였습니다.
- single-line-ellipsis와 multi-line-ellipsis가 있지만 해당 작업에서는 single line으로 처리할 수 있다고 판단하여 single-line-ellipsis를 사용했습니다.
- ellipsis code
```scss
// single line ellipsis
@mixin sl-ellipsis {
    display: inline-block;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

// multi line ellipsis
@mixin multi-ellipsis {
    display: -webkit-box;
    overflow: hidden;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
}
```

### media query
- 스크린의 길이가 1100px 이하로 작아지는 경우 container와 footer-container의 width를 820px로 설정해준다.
- 왜 mobile first라는 말이 나온건지 이해가 된다. 모바일 스타일을 먼저하자!!

### skip navigation
- 누구도 소외되지 않기 위한 웹사이트를 위해 처음 웹페이지에 접근했을 경우 처음으로 웹페이지에 대한 전체적인 navigation을 제공 (웹 접근성 고려)
- position을 absolute로 설정한 후 top을 -200px로 숨긴다.
- 사용자가 웹페이지에 접근하여 tab을 누르면 아래와 같이 navigation이 화면에 보여진다.

- tab 누르기 전

![image](https://user-images.githubusercontent.com/77317312/144740194-8b5f24fa-b140-4eb5-a057-d625f422b7d4.png)

- tab 누른 후

![image](https://user-images.githubusercontent.com/77317312/144740177-4f192681-086b-4b53-b7c3-701d7ecc4288.png)

## 배운점
- 웹 페이지를 구성하는 것들이 단순히 눈에만 보여지는 것들이 전부가 아니라는 것을 알게 되었습니다. 앞으로 웹 접근성을 고려하며 코드를 작성하는 습관을 들여야겠다는 생각을 했습니다.

- 유저의 화면 크기를 신경 쓰면서 코드를 작성하다 보니 item들의 정렬과 크기가 찌그러지는 등 다양한 문제들으르 직면 했지만 그만큼 상황에 따라 어떻게 코드를 작성해야되는지를 깨닫게 되었습니다.

- 아직 ellipsis에 대한 개념이 확실하지가 못해 일단은 물리적으로 width의 pixel을 정해주어 적용되게 했지만 이렇게 적용하는 것이 맞는가에 대한 의문을 가지게 되었습니다.
