# 第二章 导入数据到 SAS

## 2.1 导入数据到 SAS 的办法

+ 直接输入
+ 利用文件创建
+ 其他软件数据文件转化，比如 Stata 的 dta
+ 直接读取其他软件数据文件

## 2.2 使用 VIEWTABLE 窗口输入数据

不建议

## 2.3 使用导入向导读取文件

**第一步**

![image-20251110134326263](./Chapter2/image-20251110134326263.png)

如果要导入 csv 就选择下面那行

**第二步**

![image-20251110134917022](./Chapter2/image-20251110134917022.png)

**第三步**

![image-20251110134932976](./Chapter2/image-20251110134932976.png)

**第四步**

![image-20251110135117744](./Chapter2/image-20251110135117744.png)

**第五步**

![image-20251110140257682](./Chapter2/image-20251110140257682.png)

## 2.4 指定原始数据位置

**内部原始数据**

使用 CARD 语句创建数据集

```SAS
DATA uspresidents;
    INPUT Presidents $ Party $ Number;
    CARDS;
        Adams F 2
        Lincoln R 16
        Grant R 18
        Kennedy D 35
    ;
RUN;
PROC PRINT DATA = uspresidents;
RUN;
```

![image-20251110140832302](./Chapter2/image-20251110140832302.png)

**外部数据文件**

使用 INFILE 语句

```SAS
DATA Presidents;
    INFILE './training/data/Presidents.txt' LRECL=2000;
    INPUT President $ Party $ Number;
    PUT President= Party= Number=;
RUN;
```

![image-20251110141147012](./Chapter2/image-20251110141147012.png)

## 2.5 读取空格分隔的原始数据

我们现在导入一个叫做 ToadJump 的数据

```
Lucky 2.3 1.9 . 3.0
Spot 4.6 2.5 3.1 .5
Tubs 7.1 . . 3.8
Hop 4.5 3.2 1.9 2.6
Noisy 3.8 1.3 1.8 
1.5
Winner 5.7 . . .
```

可以看到，第五行的数据串行了，那么 SAS 能否准确读取呢？

```SAS
DATA toads;
    INFILE './training/data/ToadJump.dat';
    INPUT ToadName $ Weight Jump1 Jump2 Jump3; /* Specify variables' names */
    /* Notice the log: NOTE: SAS went to a new line when INPUT statement reached past the end of a line. */
RUN;
PROC PRINT DATA = toads;
    TITLE 'SAS Data Set Toads'; /* Specify title of result table */
RUN;
```

![image-20251110141745905](./Chapter2/image-20251110141745905.png)

可以看到，只要当前行数低于变量数，那么 SAS 就会继续将下一行数据读取为变量值，SAS 的日志中也记录了这一个事件

![image-20251110142059478](./Chapter2/image-20251110142059478.png)

这里注意一个细节，代码中用了 \$ 声明 ToadName 的变量类型为字符型，而数值型则不需要特别声明

## 2.6 读取按列排列的原始数据

























