# Linux 常用命令

## diff

比较文件之间的差异。
```bash
# -y 参数平铺文档
# -b 忽略空格差异
# -B 忽略空行差异
diff a.c b.c -y -b -B
```
比较结果的符号说明：
- “|”表示前后2个文件内容有不同  
- “<”表示后面文件比前面文件少了1行内容  
- “>”表示后面文件比前面文件多了1行内容  

## 常用命令

```bash
# 复制文件夹 ~/scope/ 到当前目录
cp -r ~/scope/ .

# 去用户主目录
cd ~

# 返回之前的目录
cd -

# 查看内存占用
free -m

# 删除文件夹 scope
mv -r scope

# 查看内存和 CPU 占用
top

# 复制文件到远程主机
scp /path/file root@ipaddr:/path/
# 例如：
scp index.js wangding@192.168.59.148:/home/wangding/wd/auto/

# 从远程主机复制文件到本地
scp root@ipaddr:/path/file .
# 例如：
scp wangding@192.168.59.144:/home/wangding/wd/auto/index.js .
```
