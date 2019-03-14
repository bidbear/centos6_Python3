# centos7_Python3_pip3_scrapy
1. 安装依赖   

` yum -y install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel 

2. 下载python3安装包  
        
`wget https://www.python.org/ftp/python/3.6.5/Python-3.6.5.tgz`

3. 解压   

`tar -xvf Python-3.6.5.tgz `

4. 安装依赖

yum install zlib*


5. 进入到解压后的文件夹编译安装
```
cd Python-3.6.5
./configure --prefix=/usr/local/python3 --enable-optimizations
make && make install
```

6. 配置软连接

 `ln -s /usr/local/python3/bin/python3  /usr/bin/python3`

7. 转到根目录

输入 python3  看到提示信息表示安装成功

8. 安装setuptools

```
wget --no-check-certificate  https://pypi.python.org/packages/source/s/setuptools/setuptools-19.6.tar.gz#md5=c607dd118eae682c44ed146367a17e26

tar -zxvf setuptools-19.6.tar.gz

cd setuptools-19.6

python3 setup.py build

python3 setup.py install
```
9. 设置软链接

`ln -s /usr/local/python3/bin/pip3 /usr/bin/pip3`

如软链接设置错误,删除软链接命令

rm -rf /usr/bin/pip3(后面/usr/bin/pip为软链接名称,切记不能加结尾/  如:/usr/bin/pip3/则表示删除软连接及真实文件)

10.回到根目录

cd /

输入pip3 -V查看pip版本,安装成功则正确显示版本

11. pip3升级

`sudo pip3 install --upgrade pip`

12. 安装scrapy

`pip3 install scrapy`

13. scrapy检查
	未找到命令
	
14. 设置软连接
`ln -s /usr/local/python3/bin/scrapy   /usr/bin/scrapy`
15. scrapy检查

成功
