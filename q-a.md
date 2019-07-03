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