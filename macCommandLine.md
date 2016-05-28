一些简单常用的mac命令行，主要摘自[Mac OS X Terminal 101：终端使用初级教程](https://www.renfei.org/blog/mac-os-x-terminal-101.html)
- command+k 清屏
- **Notice:**
如果你输入了一些错误的命令，系统会返回一些错误信息。但是系统却不会阻止你做傻事（例如删除整个用户文件夹）。

- 想要知道一个命令怎么用（然而实际上还是搜索引擎来得更快更容易233）
> 使用指南往往很长，所以可以使用▲（上箭头）或▼（下箭头）来上下移动，使用空格来翻页，输入/和关键字来按照关键字搜索，按Q来退出使用指南页面。


```
man command-name

```


- 切换到其他路径和目录
> 如果你想将当前 command line 会话切换到其他目录，需要用到三个命令：pwd，ls和cd。
pwd的含义是“print working directory”，会显示当前目录的绝对路径。
ls的含义是“list directory contents”，它会列出当前目录的内容。这个命令还有其他参数可选。
cd的含义是“change directory”，它会改变当前目录到你指定的目录。如果你不指定，则会返回你的 home folder

- 处理特殊字符
> 如果目录中有特殊字符（空格，括号，引号，[]，!，$，&，*，;，|，\），那么直接输入空格会造成系统识别困难，必须使用特殊的语法来表示这些字符。例如上例中，空格前添加反斜杠“\”（back slash）即可：cd Punlic/Drop\ Box/。除了反斜杠，也可以用引号的方法：cd "Public/Drop Box"。
<br/><br/>
——如果不想手动输入，也可以把文件从 Finder 拖到 Terminal 窗口来创建绝对路径，这会方便一些，因为上面提到的所有特殊字符在拖动后都会自动变成系统可识别的表示方法。其实，更有效率的解决方案是使用 Tab Complete 功能。

- Tab Complete
> 是 command line 中最能给你节省时间的特性之一，利用它的自动完成文件、目录名称功能还可以防止你输入错误。使用cd进入你的 home folder，使用cd P命令，然后按下tab按键。你可能会听到错误音，因为你的 home folder 内有多个 P 开头的文件夹。再按一次tab，Terminal 将会为你列出 P 开头的两个文件夹：Public 和 Pictures。按U，再按tab，Terminal 则会自动为你补全Public/。Tab complete 同样会处理那些特殊字符。注意，这会在末尾保留/符号，大部分时候这没问题，但如果出错，移除多余的/试一试。
<br/><br/>
另外，鄂化符~（tilde）在command line 中可以代表当前用户的 home folder。例如~/Public/Drop\ Box/是合法的。

- 使用通配符
下面是常用的通配符：
>星号（＊，Asterisk）——代表任何长度的任何字符。例如*.tiff代表所有格式为tiff的文件。<br/>
问号（?，Question mark）——代表任何单个字符。例如b?ok匹配 book 但是不匹配 brook。<br/>
方括号（[]，Square brackets）——定义一定范围的字符，例如[Dd]ocument匹配 Document 以及 document；doc[1-9]匹配doc1, doc2, …, doc9。
配合使用上面三种通配符可以大大提高效率。

- 编辑文件和文件夹
> mkdir<br/>
“make diretory”的缩写，用来创建文件夹，语法为mkdir后接新文件夹的目录。可以用-p选项，来一起创建路径中不存在的文件夹（这样你就不用挨层创建了）。
<br/><br/>
cp<br/>
“copy”的缩写，用来把文件从一处复制到另一处。语法为cp后接原始路径，后接目标路径。如果你想复制整个文件夹和所有内容，需要添加-R选项。如果指定的目标路径不含文件名，则 cp 命令会按原名复制。如果指定的目标路径包括文件名，则会复制为你指定的文件名。如果仅指定新文件名，则会在原处以新名称创建文件副本。注意，系统会自动替换同名文件而不出现提示。
<br/><br/>
mv
<br/>“move”的缩写，用来移动文件。语法为mv后接原路径，后接新路径。mv 的指定路径规则和 cp 是一样的（没错，如果仅指定新文件名，它就成了重命名命令）。
<br/><br/>
rm<br/>
“remove”的缩写，会永久删除文件。注意，command-line中没有废纸篓。语法为rm后接文件路径。然而，使用 rm 命令删除的文件有可能可以通过数据恢复工具恢复。如果希望安全删除文件，可以使用srm命令。
