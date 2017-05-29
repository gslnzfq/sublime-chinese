下载代码：
```bash
git clone https://github.com/xkadmin/sublime-chinese.git
```

代码结构是：
```text
- bin
    - subl                  # sublime的命令行快捷方式
    - sublime_text.desktop  # sublime 的桌面快捷方式
- lib
    - libsublime-imfix.so   # 编译后的共享库
- src
    - sublime_imfix.c       # c代码，使用build.sh 编译到libsublime-imfix.so
- build.sh                  # 编译脚本，sublime_imfix.c => libsublime-imfix.so
```

操作：

1、 复制共享库libsublime-imfix.so到 /opt/sublime_text
```bash
sudo cp ./lib/libsublime-imfix.so /opt/sublime_text
```
2、 将bin/subl 复制到 /usr/bin下面
```bash
# 在命令行执行subl就可以输入中文了
sudo cp ./bin/subl /usr/bin
```
3、 让快捷方式打开也能输入中文，复制sublime_text.desktop到/usr/share/applications
```bash
# 使用快捷方式打开也可以输入中文了
sudo cp ./bin/sublime_text.desktop /usr/share/applications
```
4、 如果sublime_text快捷方式还是输入不了中文，请检查是否有其他的快捷方式并删除
```bash
rm ~/.local/share/applications/sublime_text.desktop
# 就可以删除中文了
```
