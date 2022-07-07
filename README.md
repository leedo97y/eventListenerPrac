# eventListenerPrac

JS eventListener - JS 챌린지 과제 4

이벤트 리스너의 옵션을 이용하여 주어진 html과 css를 이용해서 과제를 수행했다.

이벤트 리스너에는 키보드, 마우스, 창 등에 붙는 다양한 옵션들이 있는데
<br>
그 중에서 mouseenter, mouseleave, resize, contextmenu를 이용하였다.

<br>

---

<br>

## MouseEnter 옵션

마우스의 동작에 관련된 옵션이며, 마우스가 html의 h2 요소에 닿으면 코드가 실행된다.
<br>

코드 실행방식은 거의 비슷했는데, innerText를 바꿔주고 색을 바꿔주는 것이다.

```js
const title = document.querySelector("h2");

function handleMouseEnter() {
  title.innerText = "Your Mouse is here!";
  title.style.color = "green";
  // *챌린지 코드는 임의로 색이 지정되어 있어서 array 요소를 이용하는 것이었다.
}

title.addEventListener("mouseenter", handleMouseEnter);
```

<br>

---

<br>

## MouseLeave 옵션

마우스가 요소에서 떠날때(?) 실행되며, 실행방식은 위와 같다.
<br>
여기까지는 h2에 적용되는 이벤트 리스너였다면 밑의 두 이벤트 리스너 옵션은 조금 다르다.

```js
function handleMouseLeave() {
  title.innerText = "Your Mouse is gone!";
  title.style.color = "blue";
}

title.addEventListener("mouseleave", handleMouseLeave);
```

<br>

---

<br>

## ContextMenu 옵션

이 옵션은 마우스 오른쪽 키를 눌렀을 때 코드가 실행되는 것이다.
<br>
마우스 왼쪽 키는 `click` 이라는 옵션이 있다.

정리해보자면,

```
왼쪽 : click
오른쪽 : contextmenu
```

내가 작성한 코드는 이와 같다.

```js
const body = document.querySelector("html");

function handleContextMenu() {
  title.innerText = "That was a right click!";
  title.style.color = "red";
}

body.addEventListener("contextmenu", handleContextMenu);
```

우선 위의 마우스 이벤트와 가장 다른 점은 h2가 아니라 html 전체에 이벤트 리스너를 달았다는 점이다.
<br>

우선 이렇게 구성한 이유는 챌린지 과제 영상 때문인데, 챌린지 과제 요구서에는 전체에 적용하라는 말은 없었지만,
<br>
영상에서 시연할 때 h2 부분이 아닌 바깥 부분을 우클릭했는데도 실행되었기 떄문이다.

따라서, 이것이 정답이 아닐 수도 있겠지만 h2가 아닌 부분에서도 실행되야하면 html 부분이 필요하다 싶었다.

<br>

---

<br>

## Resize 옵션

resize는 말 그대로 창 크기를 조절했을 시 실행되며,
<br>
h2, html이 아닌 window에 적용해야한다.

```js
function handleResize() {
  title.innerText = "You just resized!";
  title.style.color = "purple";
}

window.addEventListener("resize", handleResize);
```

<br>

---

<br>

## TIL

이벤트 리스너 옵션들이 생각보다 더 다양하다는 것을 알게되었고, 요구서를 찬찬히 뜯어보면 전혀 어렵지 않다는걸 알 수 있었다.

사실 챌린지 코드에는 핸들러 function들을 object로 넣으라는(?) 요구가 있었고, 코드를 구현했는데 이런 식으로는 코드를 한번도 안짜봐서 아 이게 이렇게 하는건가..? 싶었다.

4일차 과제 코드 리뷰 끝..! 이게 사실 맞는 코드인지는 모르겠으나, 오류 없고 영상이랑 똑같으면 밎는거겠지!
