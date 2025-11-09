# SAS 软件使用入门

## 1.1 SAS 语言

**基本知识**

+ SAS 程序是按顺序执行的

+ SAS 遵循一些语法规则
    + 每一条 SAS 语句都以分号结尾
    + SAS 语句不区分大小写
    + 一条语句可以写在多行
    + 多条语句可以写在一行
    + 语句可以从任意列开始

**注释**

SAS 的注释有两种方式：

```SAS
* 第一种方式;

/* 第二种方式 */
```

## 1.2 SAS 数据集

和大多数软件一样，SAS 也将每一列叫做变量，每一行叫做观测

<img src="./Chapter1/image-20251109184737157.png" alt="image-20251109184737157" style="zoom: 80%;" />

**数据类型**

+ 数值型
+ 字符型

**缺失值**

句点表示

**数据集大小**

变量与观测的最大数量取决于电脑性能

**变量名注意事项**

其实和 Python 这些变量名要求差不多，不要用数字开头就好

## 1.3 DATA 步和 PROC 步

DATA 步：读取和修改数据，创建 SAS 数据集

PROC 步：完成特定分析或功能，产生结果或报表

代码示例：

```SAS
DATA distance;
    Miles = 26.22;
    Kilometers = 1.61 * Miles;
RUN;
PROC PRINT DATA = distance;
RUN;
```

结果展示：

<img src="./Chapter1/image-20251110021619256.png" alt="image-20251110021619256" style="zoom: 50%;" />

## 1.4 DATA 步的内置循环

这部分解释了 DATA 步是如何逐行执行语句和逐条处理观测的，下图即可概括：

<img src="./Chapter1/image-20251110022154539.png" alt="image-20251110022154539" style="zoom:80%;" />

关于如何逐条输出数据，可以看后续讲解中的 OUTPUT 语句

## 1.5 选择提交 SAS 程序的模式

**窗口提交**

<img src="./Chapter1/image-20251110022449946.png" alt="image-20251110022449946" style="zoom:50%;" />

**SAS Enterprise Guide 远程提交**

这个不用管

**批处理或者后台模式**

使用 CMD 或者 BATCH 进行批处理（应该

## 1.6 SAS 窗口环境下的窗口和命令

<img src="./Chapter1/image-20251110023013193.png" alt="image-20251110023013193" style="zoom: 50%;" />

## 1.7 在 SAS 窗口环境中提交程序

见 1.5，提交后会在日志窗口看到运行步骤

<img src="./Chapter1/image-20251110023210213.png" alt="image-20251110023210213" style="zoom: 67%;" />

## 1.8 阅读 SAS 日志

日志包含的内容大致如下：

![image-20251110023338364](./Chapter1/image-20251110023338364.png)

![image-20251110023356224](./Chapter1/image-20251110023356224.png)

## 1.9 查看结果

<img src="./Chapter1/image-20251110023542322.png" alt="image-20251110023542322" style="zoom:50%;" />

## 1.10 SAS 数据逻辑库

数据的临时存放区

<img src="./Chapter1/image-20251110023825296.png" alt="image-20251110023825296" style="zoom: 50%;" />

Work 是默认的逻辑库，其他的都是 SAS 自带的示例数据

![image-20251110023919684](./Chapter1/image-20251110023919684.png)

他其实对应电脑上的一个文件夹，如下：

![image-20251110024050160](./Chapter1/image-20251110024050160.png)

可以看到里面包含了刚刚运行的产生的数据文件（sas7bdat）、生成的结果（htm）、数据信息（sas7bitm）

## 1.11 在 VIEWTABLE 窗口中查看数据集



