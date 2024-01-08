# Networking documentation

## Experiment tools

Network traffic monitoring:
- Iperf: 
    - https://iperf.fr/ 
    - https://iperf.fr/iperf-doc.php  introduction of command
    - https://www.volcengine.com/theme/1637603-U-7-1     
  
- pktgen: 
    - https://blog.csdn.net/hhd1988/article/details/123916491
    - https://gnuser.github.io/lpo/network/pktgen 
  

Traffic generator: 

- Moongen: 
  - https://github.com/emmericp/MoonGen
  
MoonGen 是一款用于网络流量生成和分析的工具，可用于测试网络设备、协议和应用程序的性能和稳定性。要安装 MoonGen，可以按照以下步骤进行：

安装依赖项：在安装 MoonGen 之前，需要先安装一些依赖项。在 Ubuntu 中，可以使用以下命令安装：

sudo apt-get update
sudo apt-get install build-essential cmake libnuma-dev libpcap-dev git

克隆 MoonGen 仓库：在安装依赖项后，可以使用 Git 克隆 MoonGen 仓库。在终端中执行以下命令：

git clone https://github.com/emmericp/MoonGen.git

编译和安装 MoonGen：在克隆仓库后，可以使用以下命令编译和安装 MoonGen：

cd MoonGen
make
sudo make install

上述命令将编译 MoonGen，并将可执行文件安装到 /usr/local/bin 目录中。

运行 MoonGen：在安装完成后，可以使用以下命令运行 MoonGen：

sudo moon

该命令将启动 MoonGen，并显示 MoonGen 的命令行界面。在该界面中，可以使用各种命令来生成和分析网络流量。

需要注意的是，MoonGen 需要使用 DPDK（Data Plane Development Kit）来实现高性能的数据包处理。在安装 MoonGen 前，需要先安装 DPDK 并配置环境变量。可以参考 DPDK 的官方文档或社区中的教程进行安装和配置。

- Numa node:

https://winddoing.github.io/post/36923.html
Numa（Non-Uniform Memory Access）是一种内存访问模型，用于处理具有多个处理器和内存子系统的计算机系统中的内存访问问题。在使用 Numa 架构的系统上安装软件时，可以使用以下步骤：

检查 Numa 系统：在安装软件前，需要确认系统是否支持 Numa 架构。可以使用以下命令检查系统是否支持 Numa：

sudo lshw -class memory

该命令将列出系统中所有的内存信息，并显示每个内存节点的 ID 和大小。如果系统支持 Numa，每个节点的 ID 和大小将不同。

安装软件：在确认系统支持 Numa 后，可以按照正常的方式安装软件。例如，在 Ubuntu 中，可以使用以下命令安装软件包：

sudo apt-get update
sudo apt-get install <package_name>

其中，<package_name> 表示要安装的软件包的名称。在安装软件包时，系统会自动识别系统的 Numa 架构，并在安装时进行相应的优化。

配置 Numa 系统：在安装软件后，可以使用 numactl 命令来配置 Numa 系统。例如，要将一个进程绑定到特定的 Numa 节点上，可以使用以下命令：

numactl --cpubind=<cpu_list> --membind=<node_id> <command>

其中，<cpu_list> 表示要绑定的 CPU 列表，<node_id> 表示要绑定的内存节点 ID，<command> 表示要执行的命令。该命令将使指定的进程仅使用指定的 CPU 和内存节点，以优化系统性能和稳定性。

需要注意的是，Numa 系统的配置和优化需要根据具体的硬件、操作系统和应用程序来进行调整。在使用 Numa 架构的系统时，建议参考相关文档和社区的建议，以获得最佳的性能和稳定性。