# CSS深入理解之border开始学习 

## border-width不支持百分比

### border-width不支持百分比

不支持百分比是因为设备边框不会因为设备屏幕的增大而增大。

与此类似，outline/box-shadow/text-shadow/...等边框也不支持百分比。

border-with属性的取值可以是：thick(5px)、medium(默认值，3px)和thin(1px)。默认值是3px是因为，`border-style:double`至少要3px才能出效果。


## 了解各种border-style类型

### dashed虚线

浏览器差异：Chrome/Firefox宽高是3:1，IE宽高是2:1。


### dotted点线

浏览器差异：Chrome是方形小点，IE是圆形小点。可以借助圆形小点实现IE下的圆角效果，因为IE不支持border-redius。


### double双实线

兼容性非常好。

双线宽度永远相等，中间间隔+/-1。


### groove/ridge/inset/outset

风格过时，兼容性差。


## border-color与color

border-color的默认颜色就是color。即：当没有指定border-color时，会使用color作为边框颜色。

类似使用color作为默认颜色的属性还有：outline，box-shadow，text-shadow等。

精彩案例：border与边框变色。



















