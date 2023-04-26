# -
系统监控工具：实现对系统资源和进程的监控和管理。
可以用Python实现一个系统监控工具，以下是一些实现思路：

1. 获取系统资源信息：使用psutil模块获取CPU、内存、磁盘、网络等系统资源信息。
2. 获取进程信息：使用psutil模块获取系统上运行的所有进程的信息，例如进程ID、进程名称、CPU占用率、内存占用率等。
3. 监控系统资源：实现一个循环，每隔一定时间获取一次系统资源信息，并进行监控，例如当CPU占用率超过一定阈值时进行报警。
4. 管理进程：实现对进程的管理，例如查看进程信息、杀死进程、启动新进程等。

以下是一个简单的示例代码，可以实现对CPU、内存和磁盘使用情况的监控：

```python
import psutil
import time

while True:
    # 获取CPU、内存、磁盘使用情况
    cpu_percent = psutil.cpu_percent()
    memory_percent = psutil.virtual_memory().percent
    disk_percent = psutil.disk_usage('/').percent
    
    # 输出系统资源使用情况
    print(f"CPU: {cpu_percent}%  Memory: {memory_percent}%  Disk: {disk_percent}%")
    
    # 判断是否需要报警
    if cpu_percent > 90 or memory_percent > 90 or disk_percent > 90:
        print("Warning: System resource usage is high!")
        
    # 休眠一定时间后再次获取系统资源信息
    time.sleep(10)
```

这是一个简单的示例代码，可以根据需求进行进一步的扩展和优化，例如加入进程管理功能等。
