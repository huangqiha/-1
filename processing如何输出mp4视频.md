## processing如何输出mp4视频

### 1-安装VideoExport库

VideoExport库的GitHub地址：

https://github.com/hamoid/video_export_processing



### 2-安装FFmpeg

库运行时需要指定FFmpeg.exe，须事先安装好。

FFmpeg的下载地址：

https://www.gyan.dev/ffmpeg/builds/



**FFmpeg**具体细节如下：

You need to download and install [FFmpeg](http://ffmpeg.org/) on your system before you can use this library. Note that you might already have it installed! You can find out by typing ffmpeg or ffmpeg.exe in the terminal. If the program is not found:

- GNU/Linux systems: use your favorite package manager.
- Windows: get a static 32bit or 64bit binary
- Mac: get a static 64bit binary

For more details and download links, check the official FFmpeg website: [http://ffmpeg.org](http://ffmpeg.org/)

When you start a Processing sketch that uses this library you may be asked to indicate the location of your FFmpeg executable.



### 3-样例代码

安装好后，运行一下如下程序以检测部署是否成功：

```java
import com.hamoid.*;

VideoExport videoExport;

void setup() {
  size(600, 600);
  videoExport = new VideoExport(this, "hello.mp4");
  videoExport.startMovie();
}
void draw() {
  background(#224488);
  rect(frameCount * frameCount % width, 0, 40, height);
  videoExport.saveFrame();
}
void keyPressed() {
  if (key == 'q') {
    videoExport.endMovie();
    exit();
  }
}     
```

​       

如果得到视频输出，部署成功！