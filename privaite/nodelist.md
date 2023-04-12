# NodeList

## 객체
- HTMLCollection 객체와 거의 유사  
  - array와는 다르나 index를 통해서 노드에 접근가능
- (구)브라우저는 getElementsByClassName()과 같은 메소드에 대해 HTMLCollection 대신 NodeList 객체 반환.
- 모든 브아우저는 childNodes 속성에 대해 NodeList 객체 반환.
- 대부분의 브라우저는 querySelectorAll() 메소드에 대해 NodeList 객체 반환.

ex)
```html
<h2>홈짱닷컴 Homzzang.com</h2>

<p>HTML</p>

<p>CSS</p>

<p>JS</p>

<p id="demo"></p>

<script>
var ps = document.querySelectorAll("p");

var text = ps[1].innerHTML; // 2번째 P요소 텍스트

document.getElementById("demo").innerHTML = text;
</script>
```

## 갯수
- length 속성 : NodeList안의 노드 개수를 반환
```html
<h2>홈짱닷컴 Homzzang.com</h2>

<p>HTML</p>

<p>CSS</p>

<p>JS</p>

<button onclick="homzzang()">클릭</button>

<script>
function homzzang() {

  var ps = document.querySelectorAll("p");

  var i;

  for (i = 0; i < ps.length; i++) {

    ps[i].style.color = "red";

  }
}
</script>
```
## HTMLCollection / NodeList 비교
- ### [유사점]
- 배열은 아니지만 index로 접근 가능
- index 번호는 0부터 시작(반복문 가능)
- 배열은 아니기 때문에 배열 메서드 사용불가  
  ex) valueOf(), push(), pop(), join()
- ### [차이점]
- HTMLCollection
1. 이름, ID, 색인번호로 요소에 접근 가능.
2. 속성노드와 텍스트노드를 갖을 수 없음.
  
- NodeList
1. index만으로 각 노드에 접근 가능.
2. 속성노드와 텍스트노드를 갖을 수 있음.