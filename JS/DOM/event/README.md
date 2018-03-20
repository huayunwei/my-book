阻止冒泡和默认事件的兼容性写法

ev.preventDefault\(\);//

event.returnValue=false;//IE

event.cancelBubble=true;  

event.stopPropagation\(\); 

