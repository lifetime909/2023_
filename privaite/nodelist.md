# NodeList

## 객체
- HTMLCollection 객체와 거의 유사  
  - array와는 다르나 index를 통해서 노드에 접근가능
- (구)브라우저는 getElementsByClassName()과 같은 메소드에 대해 HTMLCollection 대신 NodeList 객체 반환.
- 모든 브아우저는 childNodes 속성에 대해 NodeList 객체 반환.
- 대부분의 브라우저는 querySelectorAll() 메소드에 대해 NodeList 객체 반환.

ex)
```html
<script>

var ps = document.querySelectorAll("p");

var text = ps[1].innerHTML; // 2번째 P요소 텍스트

document.getElementById("demo").innerHTML = text;

</script>
```