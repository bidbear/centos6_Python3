# centos6_Python3
## 升级python
1. 下载   
`wget https://www.python.org/ftp/python/3.5.2/Python-3.5.2.tgz`

2. 编译安装
```
[root@myserver01 local]# tar -zxvf Python-3.5.2.tgz
[root@myserver01 local]# cd Python-3.5.2
[root@myserver01 Python-3.5.2]# mkdir /usr/local/python3/     --创建新的python目录，防止覆盖老的python
[root@myserver01 Python-3.5.2]# ./configure --prefix=/usr/local/python3/  
[root@myserver01 Python-3.5.2]# make 
[root@myserver01 Python-3.5.2]# make install
[root@myserver01 Python-3.5.2]# ln -s /usr/local/python3/bin/python3 /usr/bin/python3
```
3. 验证
`python3 --version`
-----------------------
## 安装pip3 

1. 下载     
wget https://bootstrap.pypa.io/get-pip.py

2. 然后用python解释器运行                        
`python3 get-pip.py`                     
报错`zipimport.ZipImportError: can’t decompress data; zlib not available   `            

先去下载有关的包             
yum -y install zlib*                

然后重新编译安装python                   

到你的python安装包目录下之后                
1. `./configure `                
2. 然后修改安装模块文件vim Modules/Setup                  
找到#zlib zlibmodule.c -I$(prefix)/include -L$(exec_prefix)/lib -lz                   
去掉注释                

zlib zlibmodule.c -I$(prefix)/include -L$(exec_prefix)/lib -lz              

你可以在vim命令模式中输入`/查找的字符 `               
3. `make `          
4. `make install `           
5. 然后重新python get-pip.py                  
