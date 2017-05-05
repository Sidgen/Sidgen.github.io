#git学习一 之 (常用命令)

###1. 在windows上安装git 国内下载链接[网盘](https://pan.baidu.com/s/1kU5OCOB#list/path=%2Fpub%2Fgit&parentPath=%2F)下载
###2. 打开git bash命令行 绑定用户名和email
<pre><code>$git config --global user.name "你的名字"
$git config --global user.email "你的email"

$ git config --list //查看配置

修改绑定了的用户名和email:
$ git config --global --replace-all user.name "新名字"
$ git config --global --replace-all user.email "new email"

</code></pre>


###3. 绑定版本库文件夹
<pre><code>//打开要绑定版本库的文件夹
cd 文件夹名称
$git init
</code></pre>
版本库创建好之后会增加一个.git 的文件


###4. 添加文件,提交至git
<pre><code>
//例如在版本库文件中新建了一个abc.txt文件
$ git add abc.txt  //添加文件
$ git commit -m "这里填写备注" 
</code></pre>


###5. 查看文件状态和不同
<pre>
$ git status
$ git diff abc.txt
</pre>
###6. 版本回退
<pre>//查看log日志:
$ git log
或
$ git log --pretty=oneline

//回退至上个版本
$ git reset --hard HEAD^

//回退至上上个版本:
$ git reset --hard HEAD^^

//回退至前8个版本:
$ git reset --hard HEAD~8

//假如要前进到某个版本: 
$ git reset --hard 记录id

//如不知道版本号可以查询log历史记录:
$ git reflog
</per>

###7. 撤销修改和删除
<pre>
1) 删除当前工作区中修改的的内容,在add之前
//将工作区文件的内容恢复到版本库的状态
$ git checkout -- 文件名
2) 删除缓存区中内容至当前工作区: 
$ git reset HEAD 文件名 //HEAD表示最后一次提交时的状态

3) 删除
①$ rm abc.txt //删除工作区中的文件abc

②-1 删除版本库中的文件abc
 	$ git rm abc.txt (方式1)
 	$ git add abc.txt (方式2)
②-2 恢复版本库中的文件abc
	$ git reset HEAD abc.txt
//这个时候版本库中还有文件,工作区中没有文件

//再使用git reset --hard HEAD^ 来恢复为版本库中的状态

③ $ git commit -m "删掉了abc文件"  //此时版本库中的文件也删掉了


</pre>



