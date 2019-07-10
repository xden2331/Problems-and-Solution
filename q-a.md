# Web develop 网页

## 杂

- 如何找无版权图片？
  - <https://unsplash.com/>
- 如何找字体？
  - Google fonts

## 前端

- Bootstrap如何使图片的size一样？

  - Solution: <https://codepen.io/nax3t/pen/MJwpdb>

- Icon？

  - Solutions:
    - Bootstrap 的glyphicon
    - Font awesome: <https://fontawesome.com/>

- 如何固定nav bar?

  - Bootstrap下，在nav的tag里面添加class="navbar-fixed-top"

- 如果网页背景过大，要怎么处理？

  - 写css

  - ```css
    body {
        background: url(...);
        background-size: cover;
    }
    ```

    `background-size: cover;`表示的是尽可能的把图片全部cover到屏幕上

- 网页背景有重复怎么办？

  - 这是因为`background-size:cover;`考虑的是当前html的height，添加以下css可以解决

  - ```css
    html {
        height: 100%;
    }
    ```

- 如何给文字加阴影？ 

  - Text shadow阴影

  - ```css
    /* offset-x | offset-y | blur-radius | color */
    text-shadow: 1px 1px 2px black; 
    
    /* color | offset-x | offset-y | blur-radius */
    text-shadow: #fc0 1px 0 10px; 
    
    /* offset-x | offset-y | color */
    text-shadow: 5px 5px #558abb;
    
    ```

- 如何让网站responsive to移动mobile设备？

  - ```
    be sure to add the following meta tag to your <head>  element, above the <title>  tag:
    
    <meta name="viewport" content="width=device-width, initial-scale=1">
    ```

- 当鼠标覆盖一个东西的时候想要改变他的属性怎么做？

  - ​	

    ```css
    selector:hover {
        // do sth
    }
    ```

- 网页缩小时如何让对应的东西也缩小？

  - ```css
    @media (max-width: 1200px){
        #headingGroup h1{
            font-weight: 100;
            font-size: 3rem;
        }
    }
    ```

- Bootstrapt 4里的flex内容怎么排序？

  - <https://getbootstrap.com/docs/4.3/utilities/flex/#order>

- JS里面如何比较type和value是否相等？

  - ```javascript
    x === "5" //比较type和value
    x !== "5" //type不同 【或者】 value不同
    ```

- JS string转换成number

  - ```javascript
    var a = "55"
    Number(a)
    ```

- JS 检查string是否包含一个string

  - ```javascript
    var str = "Hello string";
    str.indexOf("H");
    // 如果存在就会返回index， 否则返回-1
    ```

- JS: function declaration vs. function expression

  - ```javascript
    // function declaration
    function func(str){
        return str;
    }
    
    // function expression
    // if func is changed, i.e., func = 10, the function content is lost.
    var func = function(str){
        return str;
    }
    ```

- JS: replace all occurrences of a string in a string

  - ```javascript
    var myStr = "Hehehe - he - he ";
    var newStr = myStr.replace(/-/g, "newChar");
    ```

- JS: scope

  - ```javascript
    var y = 99;
    function doMath(){
        y = 100; //如果是var y=100，就是local variable
        console.log(y);
    }
    
    --> y
    --> 99
    --> doMath()
    --> 100
    --> y
    --> 100 // The value of y has been changed
    ```

- JS: 如何循环跑一个function，以及如何停止

  - ```javascript
    function name(){
        ...
    }
    setInterval(name, [interval ms]);
    // 会返回一个数字， 当想停止循环的是用这个数字
    clearInterval(num);
    ```

- JS: array怎么创建？

  - ```javascript
    var array = [1,2,3,4,5];
    ```

- JS: array 怎么在index处加element？

  - 使用splice方法： arr.splice(idx, deleteItems, addItems);

- JS: 如何create objects

  - ```javascript
    var person = {};
    person.name = "balala";
    ...
    ```

- JS: 如何检查一个str是不是数字/number/digits？

  - ```javascript
    var str = "abc";
    isNaN(Number(str)) == true;
    ```

- JS: 去哪找方法？

  - <https://underscorejs.org/>

- JS: DOM:

  - 获取elements的方法都写在了document这个object里面

    - 

    ```javascript
    document.getElementById();
    document.getElementsByClassName();
    document.getElementsByTagName();
    
    // 返回第一个符合CSS-selector style的元素
    document.querySelector();
    document.querySelectorAll();
    ```

  - Manipulation

    - ```javascript
      // Change an element style
      // Not recommand, not OO. Instead, we could name a class, then add style, then use JS to add this class to the targets.
      var tag = document.getElementsByTagName();
      
      tag.style.color = "blue";
      tag.style.border = "10px solid red";
      tag.style.fontSize = "70px";
      tag.style.background = "yellow";
      tag.style.marginTop = "200px";
      
      
      // adding/removing classes
      var tag = document.getElementById("highlight");
      tag.classList.add("some-class");
      tag.classList.remove("another-class");
      
      // If has this class, remove it; else turn it on.
      tag.classList.toggle("another-class");
      
      // changing the content of a tag
      // <p> This is an <strong>awesome</strong> paragraph</p>
      var tag = document.querySelector("p");
      // erase all tag inside <p>
      tag.textContent = "balabla";
      
      tag.innerHTML; // This is an <strong>awesome</strong> paragraph
      
      // changing attributes(src, href, etc.)
      // <a href = "www.google.com">I am a link</a>
      // <img src = "logo.png">
      var link = document.querySelector("a");
      link.getAttribute("href"); //"www.google.com"
      link.setAttribute("href", "www.dogs.com"); 
      // <a href="www.dogs.com">I am a link</a>
      ```

    - ```javascript
      // The event
      // Select an element, and then add an event listener
      var button = document.querySelector("button");
      
      // addEventListener([type], [function])
      // Event types: https://developer.mozilla.org/en-US/docs/Web/Events
      button.addEventListener("click", function(){
          console.log("Some one clicked the button");
      });
      ```

      

- JS:如何获得随机的颜色？

  - ```javascript
    function getRandomColor() {
        var letters = '0123456789ABCDEF';
        var color = '#';
        for (var i = 0; i < 6; i++) {
          color += letters[Math.floor(Math.random() * 16)];
        }
        return color;
      }
    ```

- JS: 如何循环一个NodeList

  - ```javascript
    不能用forEach， 只能用classical for loop； lists.length;
    ```

- HTML: 如果想要一个input，然后可以上下点数字加减1的怎么做？

  - ```html
    <input type="number">
    ```

- HTML: 想贴合页面怎么办？

  - body里面设置margin 0;

- HTML: 想要一个element消失怎么办？

  - 用display property, `style.display = 'none'`, 想要回来的时候把none改成block

- HTML: button不想要边框怎么办？

  - Border: none

- jQuery: 如何一次性apply多个style？

  - ```javascript
    var style = {
        background : blue,
        color : white,
        // css里面是font-size， 但是jQuery是fontSize
        fontSize : "10px"
    };
    $("selector").css(style);
    ```

- HTML/CSS: 如何去除list/ul/li的点/dot/bullet point？

  - ```css
    ul {
        list-style-type : none;
    }
    ```

- jQuery: 如何触发子元素的事件而不触发母元素的事件？

  - ```javascript
    $("span").click(function(event){
        alert('click on a span');
        // 加下面这句话
        event.stopPropagation();
    });
    ```

- jQuery: 如何给future的element添加listener？

  - ```javascript
    // Delegated event handlers
    // Check off specific todos by clicking
    $('ul').on("click", "li", function () {
        $(this).toggleClass('completed');
    });
    ```

- CSS: 想要隔几个元素不同的背景怎么做？

  - ```css
    li {
        background: white;
    }
    
    li:nth-child(2n){
        background: #f7f7f7;
    }
    ```

- CSS: input的width超过了parent的width怎么处理？

  - box-sizing: border-box;
  - <https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing>

- CSS: 渐变色背景怎么设置？

  - <https://uigradients.com/#Twitch>

- CSS: move an element to the right; 把一个元素移到右边

  - `float: right;`

- CSS: 一个元素width为0的时候依然可以看见里面的东西要怎么处理？

  - `opacity: 0;`

- JS/CSS: fontawesome导致不一样的行为要怎么处理？

  - 首先fontawesome的版本要是5
  - 用span把i包围起来，同时给i一个id
  - CSS处理的时候要选择li span， js处理的时候要选择这个id