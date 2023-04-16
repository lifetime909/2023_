# NodeList
- 노드 리스트는 getElementsByTagName() 메소드나 childNodes 프로퍼티의 값으로 반환되는 객체입니다.
- 이 객체는 HTML 문서와 같은 순서로 문서 내의 모든 노드를 리스트 형태로 저장하고 있습니다.
- 노드 트리의 가장 상위의 루트 노드(부모 노드 : parent node)에 다른 모든 요소 노드는 자식 노드(child)를 가진다. 


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

## 사용법
- 추가
  - appendChild()
    - 해당 요소의 맨 마지막 자식 노드로 추가함
  - insertBefore()
    - 해당 노드를 기준으로 자식 노드의 바로 앞에 추가
  - insertData()
    - 텍스트 노드의 텍스트 데이터에 새로운 텍스트를 추가합니다.
- 생성
  - createElement()
    - 새로운 요소 노드를 만듬
  - createAttribute()
    - 새로운 속성 노드를 만듬
  - createTextNode()
    - 새로운 텍스트 노드를 만듬
- 제거
  - removeChild()
    - 자식 노드 리스트에서 특정 자식 노드를 제거
  - removeAttribute()
    - 속성 이름을 이용하여 특정 노드를 제거
- 복제
  - cloneNode()
    - 기존에 존재하는 노드와 똑같은 새로운 노드를 생성하여 반환
