# hyper_thearead
引用自：https://www.cnblogs.com/scandit/p/14784483.html 

Intel的超线程技术能让一个物理核上并行执行两个线程，大多数情况下能提高硬件资源的利用率，增强系统性能。对于cpu密集型的数值程序，超线程技术可能会导致整体程序性能下降. 鉴于此，执行OpenMP或者MPI数值程序时建议关闭超线程技术。


该程序是github上找到的动态打开、关闭超线程技术的脚本。其原理是根据/sys/devices/system/cpu/cpuX/topology/thread_siblings_list文件找到逻辑核的关系，然后编辑/sys/devices/system/cpu/cpuX/online文件实现动态开启和关闭超线程技术。


使用时需注意两点：
1. 脚本需要root执行；
2. 完成后用lscpu查看Thread(s) per core是否为1。
