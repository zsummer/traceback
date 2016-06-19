# traceback简述  
C++ traceback library cross-plat win &amp; linux.  
C++运行时堆栈信息获取, 支持win,linux,mac  

# 使用方法  
使用方法为在需要获取堆栈信息的位置如下调用即可:  
``` C++   
  std::string tb = traceback();  
```  
  
# 部分说明  
在gcc下traceback在动态符号库中获取符号名, 如果是静态链接 可能获取不到符号名, 但依然可以获取到堆栈的地址信息.  
通过gdb或者addr2line可以从外部正确获取实际的符号信息. 该函数的返回已经自动排版好地址的格式可以直接复制通过shell命令获取符号信息.  
命令和使用方法如下,具体man手册:  
```shell  
gdb info line * 0x40000000
addr2line -f -C -e ./test  0x400fce  0x401027  0x7f2bfb401b45  0x400ee9
```
#About The Author  
**Auther**: YaweiZhang  
**Mail**: yawei.zhang@foxmail.com  
**GitHub**: https://github.com/zsummer  
