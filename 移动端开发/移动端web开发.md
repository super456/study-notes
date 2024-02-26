# （一）、viewport设置

- 语法设置：
`<meta name='viewport' content='name=value,name=value'>`

- 五个属性值：
```html
width:设置布局viewport的特定值（“device-width”），默认是980px，如width=320(不需要添加引号)
initial-scale:设置页面的初始缩放
minimum-scale:最小缩放
maximum-scale:最大缩放
user-scalable:用户能否缩放
```


- 获取当前屏幕的尺寸大小（布局）
`document.body.clientWidth`

- 获取当前度量（视化）的屏幕大小
`window.innerWidth`

- 布局viewport=设备宽度=度量viewport
`<meta name='viewport' content='width=device-width,initial-scale=1,user-scalable=no'`

# （二）、响应式设计

- 媒体查询
```css
@media screen and (max-width:1024px){
    #pagewrap{
        width:95.5%
    }
    #content{
        width:62%
    }
    #content,
}
```

- 百分比布局

- 1像素边框
```css
li:before{
    position:absolute;
    top:-1px;
    left:0;
    content:'';
    width:100%;
    height:1px;
    border-top:1px solid #ddd;
    -webkit-transform:scaleY(0.5);
}
```


- 相对单位rem
em:是根据父节点的font-size为相对单位
rem:是根据html的font-size为相对单位(rem=screen.width/20)

```css
html{font-size:32px}
@media screen (min-device-width:375px){
    html{font-size:37.5px}
}
```

- 局部滚动开启弹性滚动
```css
voerflow:scroll;
-webkit-voerflow-scrolling:touch;
```