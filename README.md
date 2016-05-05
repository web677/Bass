###这是什么？
当前我们的移动端项目中使用的base.css，也就是样式初始化
###关于bass.css
* 主要适用于移动端，更确切的说，是微信内置浏览器-webkit内核
* 样式初始化主要在解决重置css属性导致的预料之外的样式
* 所使用的选择器避免使用通配符和后代选择器，避免引起解析性能问题和样式权重过高，重写困难

###主要样式详解
```javascript
//消除滚动条
::-webkit-scrollbar {
    width:0px;border:solid 0px rgba(0,0,0,0); 
}
//自定义placeholder样式
::-webkit-input-placeholder {color: #465d75;}
//消除type="number"的input输入框右边数字调节按钮
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button{
    -webkit-appearance: none !important;
    margin: 0; 
}
//消除自带的点击颜色变更效果
* {-webkit-tap-highlight-color:rgba(255,255,255,0);outline:0;}
body,h1,h2,h3,h4,h5,h6,hr,p,blockquote,dl,dt,dd,ul,ol,li,pre,form,fieldset,legend,button,input,textarea,th,td{
    margin:0;
	padding:0;	
	border: 0 none;
	-webkit-appearance: none;   //消除默认样式特别是button在ios上被自动添加圆角以便看起来像是一个button
	-webkit-user-select:none;   //禁止复制文本
	-webkit-touch-callout: none;//禁止呼出长按菜单例如ios中长按可以选择在safari中打开
}
img {border: 0 none;}           //去除img边框
ul,li {list-style-type:none;}   //去除list默认li效果
a:link,a:hover,a:active,a:visited {text-decoration: none;color:#333;}   //去除a标签默认颜色
.disabled,[disabled] {opacity:1;}   //去除disabled属性的button在ios上半透明效果
input:not([type="button"]),textarea {-webkit-user-select:auto;}//禁止复制文本会导致输入框无法输入，在此重置
.clear {clear: both;}//清除浮动通用类（已不建议使用空标签方法清除浮动，改用overflow属性或者伪类去除浮动）
//rem适配基准值划分
@media only screen and (max-width: 320px){html{font-size: 9px;} }
@media only screen and (min-width: 320px) and (max-width: 352px){html{font-size: 10px;} }
@media only screen and (min-width: 352px) and (max-width: 384px){html{font-size: 11px;} }
@media only screen and (min-width: 384px) and (max-width: 416px){html{font-size: 12px;} }
@media only screen and (min-width: 416px) and (max-width: 448px){html{font-size: 13px;} }
@media only screen and (min-width: 448px) and (max-width: 480px){html{font-size: 14px;} }
@media only screen and (min-width: 480px) and (max-width: 512px){html{font-size: 15px;} }
@media only screen and (min-width: 512px) and (max-width: 544px){html{font-size: 16px;} }
@media only screen and (min-width: 544px) and (max-width: 576px){html{font-size: 17px;} }
@media only screen and (min-width: 576px) and (max-width: 608px){html{font-size: 18px;} }
@media only screen and (min-width: 608px) and (max-width: 640px){html{font-size: 19px;} }
@media only screen and (min-width: 640px){html{font-size: 20px;} }
```
##关于作者
* 前端小白，插件更多是整理自己的解决思路，写法上也是入门级水平，自知一定有极大改进空间，欢迎大神批评、指正、鼓励
* 个人博客[李小白的学习园地](http://www.web677.com/)
