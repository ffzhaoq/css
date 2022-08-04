# 《CSS 知识总结》
## 浏览器渲染原理
1.主要是通过DOM API和CSSOM API来操作DOM Tree和CSS Rule Tree.
   
2.解析完成后，浏览器引擎会通过DOM Tree 和 CSS Rule Tree 来构造 Rendering Tree。 
   
3.(layout)布局与(paint)绘制
   
4.(compose)合成:根据层叠关系展示画面
## CSS 动画的两种做法（transition 和 animation）
1.transition（过渡）
* 作用  
补充中间帧
* transition: 属性名  时长  过渡方式  延迟
```
 transition: left 200ms linear
```
* 可以用逗号分隔两个不同的属性
```
transition:left 200ms,top 400ms
```
* 可以用all代表所有属性
```
transition:all 1s
```
* 过度方式
```
linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier | step-start | step-end | steps
```
## 并不是所有属性都可过渡
```
display:none ==> block 没法过渡
一般改成visibility:hidden ==> visibile (没有为什么，我也不知道)
```
2.animation(动画)
* 作用  
声明关键帧  
添加动画
* @keyframes
标准写法  
一种是from to
```
@keyframes 动画名 {
  from {
    transform: translateX(0%);
  }

  to {
    transform: translateX(100%);
  }
}
```
另一种是百分数
```
@keyframes 动画名 {
  0% { top: 0; left: 0; }
  30% { top: 50px; }
  68%, 72% { left: 50px; }
  100% { top: 100px; left: 100%; }
}
```
* 缩写方法
```
transform:时长| 过度方式 | 延迟 | 次数 | 方向 | 填充模式 | 是否暂停 | 动画名
```
