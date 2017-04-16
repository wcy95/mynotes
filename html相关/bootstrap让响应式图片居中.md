我们在用bootstrap排版内容的时候，有的时候在内容中需要图片水平居中对齐。

一般情况下，我们的图片都使用了 .img-responsive 类来实现响应式图片。如果需要实现响应式图片水平居中，那么我们要使用 .center-block 类

    <p><img class="img-responsive center-block" src="..." /></p>

Ps：上述代码中，我们一定要注意.center-block 类的添加位置，一定要把 .center-block 添加到img中，如果添加到别的地方，那么不会实现响应式图片水平居中，比如，如下的代码就不能实现响应式图片水平居中。

    <p  class="center-block"><img class="img-responsive" src="..." /></p>  我是错误的，不能实现图片居中。
