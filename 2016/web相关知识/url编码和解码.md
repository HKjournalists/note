##vim 学习简记
入门博客:[http://www.jianshu.com/p/bcbe916f97e1]()

###简单配置
将配置文件复制一份到个人目录下，修改配置文件。  
详细操作：

    步骤1：
    cp /usr/share/vim/vimrc ~/.vimrc
    先复制一份vim配置模板到个人目录下
    注：redhat 改成 cp /etc/vimrc ~/.vimrc
 
    步骤2：
    vi ~/.vimrc
    进入insert模式，在最后加二行
    syntax on
    set nu!
###基础操作
    vim filename      打开或创建文件  
    i                 进入插入模式  
    :wq (shift zz)    w --> write    q --> quit  退出 
    :w  
    :n                光标启动到第n行
    :q  　　　         正常退出  
    :q!  　　　        退出不保存修改**　  
    ctrl b、f         上下翻页  
    fa　　　　         到下一个为 a 的字符处，你也可以fs到下一个为s的字符
 

###移动光标
  

    w                右移光标到下一个字的开头
    b                左移光标到前一个字的开头
    0                数字０，左移光标到本行的开始
    $                右移光标，到本行的末尾
 

    H                将光标移到屏幕上的起始行（或最上行）
    M                将光标移到屏幕中间
    L                将光标移到屏幕最后一行
###翻页
    向前翻页：CTRL+F
    向下移动半屏：CTRL＋G
    向后翻页：CTRL+B
###删除
    ：d      删除行
    dd       删除当前行。
    cc       删除当前行然后进入insert模式
###撤销
    u        撤销删除或者其他操作