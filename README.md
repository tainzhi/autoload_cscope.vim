##introduction
This is a mirror of http://www.vim.org/scripts/script.php?script_id=157

This plugin will automatically load **cscope.out** databases into vim when you open a C file. (headers included)

It does a search starting at the directory that the file is in, and checking the parent directories until it find the cscope.out file.  The idea being that you can start editing a source file deep in a project dir, and it will find the correct cscope database a couple dirs up.

This version also creates some macros and a menu that can be useful.  If you don't like them, you can set g:autocscope_menus to 0 and they won't load.

##my modifies
```
set nocst    "在cscope数据库添加成功的时候不在命令栏现实提示信息.
set cspc=6 "cscope的查找结果在格式上最多显示6层目录.
let g:autocscope_menus=0 "关闭autocscope插件的快捷健映射.防止和我们定义的快捷键冲突.
"个人cscope的快捷键映射
""cscope相关的快捷键映射
"s:查找即查找C语言符号出现的地方
nmap fs :cs find s <C-R>=expand("<cword>")<CR><CR>
"g:查找函数、宏、枚举等定义的位置
nmap fg :cs find g <C-R>=expand("<cword>")<CR><CR>
"c:查找光标下的函数被调用的地方
nmap fc :cs find c <C-R>=expand("<cword>")<CR><CR>
""t: 查找指定的字符串出现的地方
nmap ft :cs find t <C-R>=expand("<cword>")<CR><CR>
"e:egrep模式查找,相当于egrep功能
nmap fe :cs find e <C-R>=expand("<cword>")<CR><CR>
""f: 查找文件名,相当于lookupfile
nmap fn :cs find f <C-R>=expand("<cfile>")<CR><CR>
""f: 查找文件名,相当于lookupfile
nmap ff :cs find f <C-R>=expand("<cword>")<CR><CR>
"i: 查找当前文件名出现过的地方
nmap fi :cs find i <C-R>=expand("<cfile>")<CR><CR>
""d: 查找本当前函数调用的函数
nmap fd :cs find d <C-R>=expand("<cword>")<CR><CR>
```
