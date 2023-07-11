# linux-server-management
record how to manage linux server for deep learning

## 常见命令
du -h –max-depth=1 *   可以查看当前目录下各文件、文件夹的大小，这个比较实用。   
du -sh   查询当前目录总大小可以使用，其中s代表统计汇总的意思，即只输出一个总和大小  
du -h –max-depth=0 *   可以只显示直接子目录文件及文件夹大小统计值。  

free  #显示服务器内存情况  
free -m    # 以M为单位显示  
free -h    # 以人可读的方式显示，单位G  

在nvidia-smi发现GPU占用时，查找使用docker，通过PID寻找  
cat /proc/<process-pid>/cgroup  # 将这里的pid替换成具体pid，注意去掉<> ,查找对应的contrainerId  
docker inspect --format '{{.Name}}' "${containerId}" | sed 's/^\///'   # 根据contrainerId查找对应的docker名称，注意将${}也去掉  

