## 敌人AI（巡逻）

+ 敌人移动

```c#
public float speed;
private float waitTime;
public float startWaitTime;//记录等待时间

public transform move;//下一次移动的位置
public transform lefr;
public transform right;
```

然后首先在start里面获得start wait time的时间

`waittime = startwaittime`

然后我需要random函数来获得随机值作为移动位置

实现方法 需要movetoward （a，b，c）当前位置，目标位置，速度*time.deltatime

还需要random.range（x，y）表示在大于x小于等于y内生成随机值



还有一个函数是movetowards //前往某地，可穿墙

`Vector2.MoveTowards(transform.position, playerController.position, FlySpeed*Time.deltaTime);`

然后就OK了！
