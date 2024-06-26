# Linux0.11的内存管理2

## 1. memory.c程序

文件：mm/memory.c

### 1.1 功能描述

![image-20240417130328008](Linux0.11的内存管理2.assets/image-20240417130328008.png) 

![image-20240417130427485](Linux0.11的内存管理2.assets/image-20240417130427485.png) 

![image-20240417130354031](Linux0.11的内存管理2.assets/image-20240417130354031.png) 

![image-20240417130448235](Linux0.11的内存管理2.assets/image-20240417130448235.png) 

![image-20240417130503444](Linux0.11的内存管理2.assets/image-20240417130503444.png) 

### 1.2 重要声明

![image-20240417133338004](Linux0.11的内存管理2.assets/image-20240417133338004.png) 

### 1.3 重要函数

#### 1.3.1 mem_init

![image-20240417133830774](Linux0.11的内存管理2.assets/image-20240417133830774.png) 

![image-20240417135908886](Linux0.11的内存管理2.assets/image-20240417135908886.png) 

执行完这个函数之后的状态：

![image-20240417130354031](Linux0.11的内存管理2.assets/image-20240417130354031.png) 

#### 1.3.2 put_page

##### 1.3.2.1 完整代码

![image-20240417175833002](Linux0.11的内存管理2.assets/image-20240417175833002.png) 

![image-20240417180114910](Linux0.11的内存管理2.assets/image-20240417180114910.png) 

##### 1.3.2.2 片段一

![image-20240417180412119](Linux0.11的内存管理2.assets/image-20240417180412119.png) 

+ 如果该目录项有效（P=1），即指定的页表在内存中，则从中取得指定页表地址放到page_table变量中；
+ 否则就申请一块空闲页面给页表使用，并在对应目录项中置相应标志；

##### 1.3.2.3 片段二

![image-20240417182422680](Linux0.11的内存管理2.assets/image-20240417182422680.png) 

把物理页面page的地址填入到对应的页表中；

## 2. page.s程序

![image-20240417140611167](Linux0.11的内存管理2.assets/image-20240417140611167.png) 

![image-20240417141106251](Linux0.11的内存管理2.assets/image-20240417141106251.png) 



