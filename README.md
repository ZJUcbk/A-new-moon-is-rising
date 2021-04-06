# A-new-moon-is-rising
## 服务器需要注意事项及可靠操作

跑程序时指定显卡和利用率，避免全占挤掉别人的进程
nvidia-smi 查看服务器显卡使用情况

误操作可以用ctrl+c结束程序

pytorch 在训练前可以加入
```python 
os.environ["CUDA_DEVICE_ORDER"] = "PCI_BUS_ID"    ##按照PCI_BUS_ID顺序从0开始排列GPU设备
os.environ["CUDA_VISIBLE_DEVICES"] = "0"          ##【0表示由nvidia-smi查得可用的gpu序号】
```
**python 限制程序占用内存**

```python
import signal
import resource
import os

def limit_memory(maxsize):
    soft, hard = resource.getrlimit(resource.RLIMIT_AS)    
    resource.setrlimit(resource.RLIMIT_AS, (maxsize, hard)) 
 ```

## 常用命令

df -h 查看存储空间

htop 查看进程  退出 q


## something about files

Deeplearing cheating sheet include some basic concepts of pytorch and python 

There is also a superresolution code with note for you to better understand pytorch
