# OnlineEditor
基于SpringBoot的线上java编程网站

**网站地址**：www.sundan.club

**涉及技术**：SpringBoot框架、Java动态编译、java类文件的结构、java类加载器&java热替换、java反射	、如何将一个类变为线程安全类等。

**开发环境**：Idea+jdk1.8

**项目简介**：本项目灵感来源于leetcode，刷题时偶然想到是否可以做个类似leetcode在线编辑器的，于是在基于 SpringBoot 的基础上实现了一个在线的 Java Editor，技术要点如下：

1. **实现编译模块：** 使用动态编译技术，可将客户端发来的源代码字符串直接编译为字节数组。
2. **实现字节码修改器：** 根据 Java 类文件结构修改类的字节码，可将客户端程序对 System 的调用替换为对 System的替代类 HackSystem 的调用。
3. **实现运行模块：** 自定义类加载器实现类的加载 & 热替换，通过反射实现 main 方法的运行。
4. **解决多用户同时发送执行代码请求时的并发问题：** 通过 ThreadLoacl 实现线程封闭，为每个请求创建一个输出流存储标准输出及标准错误结果。
