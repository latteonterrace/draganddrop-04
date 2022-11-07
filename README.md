# HTML과 XML 드래그하기

HTML 문자열을 전송객체의 타입으로 사용하려면 text/html을 사용합니다. XML 문자열은 text/xml을 사용합니다.  전송된 데이터 객체를 꺼낼 때도 같은 타입을 사용합니다. 참고로 text는 text/plain으로 전송하고 꺼냅니다. 

* text/html
* text/xml
* text/plain


dragstart 핸들러에서 text/html을 전송합니다. 

```jsx
// 드래그할 대상 
const source = document.querySelector("#source");
source.addEventListener("dragstart", (ev) => {
    ev.dataTransfer.clearData();
    console.log(ev.target.innerHTML);
    ev.dataTransfer.setData("text/html", ev.target.innerHTML); 
});
```

drop 핸들러에서 getData("text/html")을 사용하여 전송된 객체를 꺼냅니다. 
```jsx
target.addEventListener("drop", (ev) => {
    ev.preventDefault();
    const htmlString = ev.dataTransfer.getData("text/html");
    console.log(htmlString);
    ev.target.innerHTML = htmlString;
});
```








