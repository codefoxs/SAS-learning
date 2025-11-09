# SAS-learning

> The Little SAS Book 学习笔记

## 0 SAS 安装

+ 自行搜索，本学习资料采用 9.4 Windows 版本的 SAS
+ 安装后没有增强型编辑器，参考（我也忘了是哪篇解决的了，应该是缺少了 VC 组件，最后通过 `regsvr32`注册）：
    + https://blog.csdn.net/qq_37911115/article/details/110766336
    + https://blog.csdn.net/qq_44127863/article/details/106164237?spm=1001.2014.3001.5506
    + https://zhuanlan.zhihu.com/p/435985302
    + [相关文件](./EnhancedEditor)

+ 相关配置

    + 建议使用英文版，中文版可能因为编码问题，无法下载 WRDS 内容

    + 设置前先勾选 `Save settings on exit`，否则无法保存设置

        ![image-20251109182608485](./README/image-20251109182608485.png)

    + 字体建议选择 Consolas 或者 Consolas-with-Yahei，自定义一个工作目录

        + 进入 ~/SASHOME/SASFoundation/9.4/nls/en 文件夹

        + 输入下面两行代码即可，字号自己看着来

            ```SAS
            /* 写入 sasv9.cfg 最后一行 */
            -SASINITIALFOLDER "path/to/your/work/directory"
            -SYSGUIFONT "Consolas-with-Yahei" 12
            ```

    + 由于序列号过期，可能需要搭配 `RunAsDate` 才能正常使用，回答正确时间，自行搜索操作

+ 运行界面

![image-20251109183435268](./README/image-20251109183435268.png)

## 1 SAS 软件使用入门

 [1.1 SAS 语言](./Chapter1/content.md#11-SAS-语言) 

 [1.2 SAS 数据集](./Chapter1/content.md#12-SAS-数据集)



















