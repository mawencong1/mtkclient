# MTKClient
based on [@bkerler's mtkclient](https://github.com/bkerler/mtkclient) and [cubinator'ext4](https://github.com/cubinator/ext4)

## 功能
MTKClient是一套mtk工具，用于读写MTK芯片的手机。具体的功能参见https://github.com/bkerler/mtkclient

我们拓展了它的功能，增加了在内存中浏览分区的功能。对于比较大的分区，如system、userdata，分区数据量较大，一次性传输时间较长。下载完成后，需要通过挂载的方式，打开分区内容。

经过分析，手机中较大的分区往往是ext4格式的分区。对于这些分区，定位超级块位置获取分区信息；定位根目录的inode，以图形化界面的形式展现根目录内容。依次递归，以磁盘形式在内存中呈现分区内容。

## 使用
以coolpad手机为例，如图所示，Load Partition(s)模块提供在线读取固件功能。点击任何ext4格式的分区，将以磁盘形式呈现分区内容。

<img width="382" alt="image" src="https://user-images.githubusercontent.com/76193596/207268179-7e8db99a-afd5-46f6-99b2-9eb16586817a.png">

如图所示，是磁盘形式呈现的system分区。对于目录文件，点击后，进入目录内部。

<img width="383" alt="image" src="https://user-images.githubusercontent.com/76193596/207270706-5a94a835-6738-440a-a57e-337ac7f9d606.png">

对于普通文件，点击后，通过十六进制和字符串两种形式展现文本内容。

<img width="382" alt="image" src="https://user-images.githubusercontent.com/76193596/207270756-5a822ff3-fa57-4888-8977-07f1a0199325.png">

