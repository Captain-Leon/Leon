---
title: yum本地仓库使用说明
tags: centos
slug:  storywriter/tutorial
---

挂载光驱：   mount /dev/cdrom   /mnt

yum clean all 清除所有仓库缓存
yum makecache 重建仓库
yum repolist all 列出所有仓库
yum provides 根据特定条件搜索软件包
yum whatprovides 文件名 查看文件属于哪个软件包安装的
yum list 列出仓库中所有软件包
yum info 查看软件包信息
yum install 安装 跟-y的话，无需手动去确认是否安装。
yum reinstall 重新安装软件包
yum remove 卸载
yum update 更新 (需要联网)
yum check-update 检查可更新的软件包 (需要联网)
yum grouplist 查看组服务
yum groupinstall 安装组服务

---------------------------本地yum仓库-----------------------------
cd /etc/yum.repos.d/ //进入到yum仓库的配置目录下
vi local.repo  //后面一定要跟.repo,因为yum只识别以.repo结尾的文件
[local] //仓库唯一标识，避免与其他仓库冲突
name=local //当前仓库名称说明
baseurl=file:///mnt //指向仓库的路径，即url访问路径，可指向多个备用
enabled=1 //1，表示此仓库被使用；0，表示此仓库不被使用
gpgcheck=0 //0，不验证软件包。1，验证