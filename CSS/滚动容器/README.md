# CSS 滚动容器

    今天在了解css新特性的时候看到个好玩的东西，叫做滚动容器，这个东西其实不新了，但是有个新的能力，就是**滚动捕获**。

> CSS 滚动捕捉允许用户完成滚动之后将视口锁定到某个元素的位置

简单的说，就是在滚动的时候，可以滚动到一个具体的位置，类似于轮播图，滚动一下，然后切换到下一张图片。

听起来似乎很常见，但是！这个能力非常强大。

通常情况下，我们的滚动都是不会定位的，如果想实现轮播图那样的功能，就必须配合 js 来实现，现在的第三方库内置的轮播图都是通过 js 来实现的，而现在我们只需要通过 css 样式来实现这样的功能，非常厉害。

## 基本使用

```
// 父容器
scroll-snap-type: x mondatory;
// 子容器
scroll-snap-align: center;
scroll-snap-stop: always;
```

`scroll-snap-type`设置了滚动的基本属性，该属性的第一个值是滚动轴，除了设置 x 轴 y 轴，还可以通过设置 both 实现 xy 两轴都可以滚动。

第二个值是捕捉方式，有两个取值`mondatory`和`proximity`。

- `mondatory`代表捕捉是强制性的，也就是说只要你有滑动操作都会进行自动滑到定位的地方。

- `proximity`代表接近的，意思是并不是每次滑动都会进行定位，只会在接近定位点时进行定位。

`scroll-snap-align`负责设置滚动定位的位置，有三个可取值，center，start 和 end，分别是中间，元素起始位置和元素结束位置。

`scroll-snap-stop`负责设置滚动何时停止，有两个取值，`normal`和`always`，normal 情况下，用户快速滑动时会一连跳过好几个元素，设置 always，则可以保证再快速的滑动也只会在就近的元素上定位。
