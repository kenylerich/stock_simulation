2017/01/19
修复了一个bug，调用erase删去正向迭代器时，影响到了本应相互独立的反迭代器，导致内部红黑树结构中的无限探测右子树。
怀疑是内存变动，和map源码有关。
不再使用反迭代器，用正向迭代器加一个哑头来代替。

发现两个问题需要解决：
1. 把代码从clion环境移植到Windows下的vs2015中，发现大量出错,打算先写完再移植。
2. 一次模拟1000股票需要0.04s,3000股需要0.15s 实际需要时间更多，可能导致模拟时间过长。

2017/01/20
为了优化效率，将部分容器改成数组

2017/01/21
将vector全部换成普通数组，目前耗时从0.3ms -> 0.2ms，性能提升近1/3。

2017/01/23
以半秒为单位，270s 模拟出半小时的市场。（只记录总体订单，不记录具体交易订单）

2017/02/01
完成基本版，v1.0。
两只股票，运行一天，10000个单位，不涉及IO记录，需一秒即可模拟出行情。




由于这个项目涉及部分利益，进一步的开发和优化暂时无法在开源平台公布，希望能谅解^_^
项目代码仅供参考，其中定有大量可优化之处，希望不吝赐教。

