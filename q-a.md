# Web develop 网页

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

- Text shadow阴影

  - ```css
    /* offset-x | offset-y | blur-radius | color */
    text-shadow: 1px 1px 2px black; 
    
    /* color | offset-x | offset-y | blur-radius */
    text-shadow: #fc0 1px 0 10px; 
    
    /* offset-x | offset-y | color */
    text-shadow: 5px 5px #558abb;
    
    ```

    