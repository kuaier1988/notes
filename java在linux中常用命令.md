---


---

<h1 id="、查看linux进程及占用空间">1、查看linux进程及占用空间</h1>
<blockquote>
<p>top</p>
</blockquote>
<h1 id="、常用命令">2、常用命令</h1>
<blockquote>
<h1 id="先找到java进程的pid">1.先找到Java进程的PID</h1>
<p>ps -ef | grep java<br>
#2. 假设你的Java进程PID是1234，<br>
kill -3 1234 #杀掉进程</p>
</blockquote>
<h1 id="、使用arthas工具（深度诊断）">3、使用Arthas工具（深度诊断）</h1>
<p>如果想更深入地排查CPU问题，强烈推荐阿里开源的Arthas工具。它无需重启就能做很多事，非常强大。首先需要下载它：</p>
<pre><code>curl -o https://arthas.aliyun.com/arthas-boot.jar
</code></pre>
<p>之后就可以用 thread命令直接查看最耗CPU的线程堆栈了：</p>
<pre><code># 1. 运行 Arthas，它会自动列出所有 Java 进程，让你选择
java -jar arthas-boot.jar

# 2.在 Arthas 的命令行界面中，输入以下命令即可直接打印出最忙的 3 个线程的堆栈
thread -n 3
</code></pre>

