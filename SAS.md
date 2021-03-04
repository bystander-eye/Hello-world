SAS 包含多个模块
- base
- insight(可以进行回归、相关性分析)
- analyse




基本语法：
  - 分号结尾
  - ///*。。。/*// 进行注释
  - 书写格式没有强制的规范写法
  - SAS数据集：样本（观测、记录）、变量（字段、域）、表（数据集）、数据库
  - 绝大部分的SAS语句都可分为两步 DATA步和PROC步
  - SAS语句以关键词开始，识别语句的类型




SAS实例：
程序运行中 包含 数据步、过程步
1. 
``` SAS
helloworld.sas
data a;
file print;
put 'hello world';
run;

proc print;
run;
```
2. 
``` SAS
data oranges;
    input variety $ flavor texture looks;
    /* variety 后跟 $ 表示该变量为字符型*/
    total=flavor+texture+looks;
    label total = "总数";
    cards;
navel 9 8 6
temple 7 7 7
valencia 8 9 9
mandarin 5 7 8
;

proc sort data=oranges;
    by descending total;
    run;

proc print data=oranges;
    var _numeric_;
    title '对ORANGES数据集的品尝检验结果';
run;
  
