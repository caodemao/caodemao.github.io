#Vim常用命令：
输入模式：`i`   
行首:`fn+home`  
行尾：`fn+end`    
##在命令模式下## 
显示行数：`set nu`  
跳转到某行：`行数+G`   
选择:`v+方向键`        
复制：`yy`  
粘贴：`p`  
撤销：`u`  
查找：`/xxx`  
保存：`wq`  
不保存:`q!`  
全部替换：`%s/bb/aa/g`(把bb全部替换成aa)  
全部删除：`gddG`  
水平分屏显示：`vim -on filename1 filename2 ...`  
垂直分屏显示：`vim -On filename1 filename2 ...`  
（其中n 为文件数量，在水平模式下sp filename 再打开新的文件，在垂直末实现vsp filename 打开新的文件;cril+w+w 切换文件）  
跳到第一行:`gg`
最后一行：`G`  
