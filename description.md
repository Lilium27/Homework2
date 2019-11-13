### 首先试着画了朵花

图片如下

![](https://github.com/Lilium27/Homework2/blob/master/flower.PNG)

### 之后尝试画了棵树

长这样

![](https://github.com/Lilium27/Homework2/blob/master/tree_noflower.PNG)

### 最后加了花

画成了这个样子（太过密集运行了很长时间……）

![](https://github.com/Lilium27/Homework2/blob/master/tree_withflower.PNG)


代码如下：

```
from turtle import *
import random

#画心形上面的半圆
def halfcircle(r):
     circle(-7.5 * r,210,200)
        
#画心形
def heart(r):
    pensize(1)
    color("red","pink")
    begin_fill()
    speed(0)
    left(120)
    forward(28 * r)
    halfcircle(r)
    left(180)
    halfcircle(r)
    forward(28 * r)
    end_fill()

#画花朵
def flower(r):
    for i in range(5):
        heart(r)
        right(168)   

    
#画带花朵的树    
def draw_tree(size):
    a=1.5 * random.random()
    if size > 10:
        forward(size)
        right(25 * a)
        draw_tree(size * 0.75)
        flower(0.2)
        left(50 * a)
        draw_tree(size * 0.75)
        right(25 * a)
        color('brown')
        if size>=10:
            pensize(2) 
        backward(size)


def main():
    speed(0)
    hideturtle()
    penup()
    goto(0,-150)
    left(90)
    backward(100)
    showturtle()
    pendown()
    pensize(2)
    color('brown')
    draw_tree(100)


if __name__ == '__main__':
    main()
done()
```
