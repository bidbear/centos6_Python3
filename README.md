# centos6_Python3
1. 下载   
`wget https://www.python.org/ftp/python/3.5.2/Python-3.5.2.tgz`

2. 编译安装
```
[root@myserver01 local]# tar -zxvf Python-3.5.2.tgz
[root@myserver01 local]# cd Python-3.5.2
[root@myserver01 Python-3.5.2]# mkdir /usr/local/python3/     --创建新的python目录，防止覆盖老的python
[root@myserver01 Python-3.5.2]# ./configure --prefix=/usr/local/python3/  
[root@myserver01 Python-3.5.2]# make && make install
[root@myserver01 Python-3.5.2]# ln -s /usr/local/python3/bin/python3 /usr/bin/python3
```
3. 验证
`python3 --version`
