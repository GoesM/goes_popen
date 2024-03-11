# English
## Problem Statement:
#### When executing shell commands in C++, if not managed properly, the inability to exit autonomously may lead to the proliferation of zombie processes. How can we address this issue?
#### This project provides an API interface `goes_popen()` implemented by the author to achieve the following objectives:
- True `terminate()` functionality:
> Actively closing shell commands that do not terminate automatically, completely cleaning up the shell subprocess group; unlike some libraries, which only close the shell subprocess without terminating the command line process group.
- Blocking/Non-blocking reading of command feedback `get_output()` and `get_output_noblock()`:
> Many existing library interfaces, if you use `get_output()`, will inevitably block the main process, leading to complex process management; this repository provides **non-blocking `get_output()`** for user convenience.
- User-selectable support for stdout and stderr:
> In many existing library interfaces, if you use `get_output()`, you cannot output to stdout to the terminal because they use pipe redirection; however, this repository allows you to print to the terminal while using `get_output()`.
- For API usage examples, refer to src/demo.cpp.

# References
Except for the partial function naming reference to the Python library `subprocess` package, there are no other references. The content is entirely the author's own thoughts.

If cited, please indicate the source as this account @GoesM.

# Welcome to Contribute to Further Enhancements
As this is entirely the author's own creation, there may be deficiencies.

If you also wish to have a perfect concurrency management template in C++ programming like me, please submit an ISSUE or PR to contribute to the repository ^_^


# 中文
## 面向问题：
#### C++执行无法自主退出的shell指令，如果不合理管理，可能会导致野进程泛滥，我们该如何解决？
#### 本项目提供本人实现的API接口 `goes_popen()`以实现以下目标
- 真正意义的`terminate()`：
> 主动关闭不会自动结束的shell命令，完全清理shell子进程组；而非像某些呆瓜库一样，只是关了shell子进程，没有关命令行进程组
- 阻塞/非阻塞地读取命令反馈`get_output()` 和 `get_output_noblock()`
> 很多现有库的接口实现，如果你get_output()就一定会阻塞主进程，从而导致进程管理复杂；本仓库提供**非阻塞get_output**以供用户使用
- 用户自选 stdout和stderr支持
> 很多现有库的接口实现，如果你get_output()就无法stdout到终端，这是因为他们使用了管道重定向；然而本仓库支持你在get_output()的同时依然可以打印到终端
- API使用方式详见 src/demo.cpp



# 参考文献
本仓库除部分函数命名参考了python库的`subprocess`包，无其他任何参考文献，完全是作者本人拍脑袋乱写出来的。

如有引用，请注明出处为我这个帐号 @GoesM 即可。

# 欢迎大家帮助完善更多细节部分
因为完全是本人拍脑袋想出来的，那也势必会有缺陷之处；

如果你也和我一样希望在C++编程中拥有一个完美的并发管理模板，那请提交ISSUE或PR为仓库贡献吧 ^_^
