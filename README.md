[!insert_aisdata](https://github.com/xu6/insert_aisdata/blob/master/insert_aisdata.ipynb)
# 将ais数据插入到Mongodb中
2018年1-9月所有数据，大约500G，62亿条
# 环境
OS: centos7
CPU: 4 * Intel(R) Xeon(R) CPU E5-2620 v3 @ 2.40GHz
Mem: 32 GB
# 遇到的问题
**遇到数次内存溢出，线程拥堵，插入速度很慢**
解决办法：在corntab中每隔一秒，释放一次内存，没有多大效果。
然后，将要插入的数据分割成很多份
**每次插入中断，还要从头插入。
不知道数据插入的进度**
经过多次修改，目的达到
**使用for循环插入数据内存溢出**
**使用yeild生成器一条数据也插不进去**
# 最终将每个月数据分割为10-20份，充分利用内存，采用128线程，五天插完所有数据


2018.12.1-2018.12.21
