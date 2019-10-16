# VLC for Android 修改版
由于市面上的播放器大多都有广告，比如Mx,体验不好，加上展示视频的界面不大喜欢，因此决定使用VLC-Android进行定制，然后自用。
大致修改如下：
## 1、图标
VLC本身的图标不是很喜欢，于是找了个喜欢的图标替换掉原本的图标
## 2、取消自动重新扫描
VLC原本是默认每次应用启动时候就会自动扫描设备中新增或删除的视频，感觉有点烦，于是改成默认启动应用不自动扫描设备
## 3、修改默认主题为黑色主题
VLC默认是跟随系统主题，但是系统目前一般都是亮色，我比较喜欢暗黑的主题风格，于是改成默认黑色主题
## 4、修改默认视频显示形式
VLC默认显示形式是网格形式，我主要是要列表形式，于是改成默认列表形式
## 5、修复显示缩略图
VLC原本应用启动后会去获取视频缩略图，但是获取成功会判断视频是否有变化，没有变化就不更新缩略图，导致有很多时候有的缩略图没有显示，于是改成只要加载了缩略图就要更新到视图
## 6、修改生成缩略图方法
VLC原本使用的是ThumbnailUtils.createVideoThumbnail方法，但是有很多视频生成的缩略图都是全黑的，体验不好，于是使用MediaMetadataRetriever生成缩略图，每次生成后对其进行判断，是否是全黑色的，如果是就生成下5秒的缩略图，最多尝试15次
## 7、修改列表形式的单视频显示布局
VLC原本的显示单纯视频的列表形式的布局不喜欢，文件夹的列表形式保持原本的布局，于是修改成一张大图，下面有标题，时长和分辨率，修改生成分辨率字符串函数，除了720p,1080p,4k的分辨率用width×height形式显示
## 8、修改视频分组默认方式
VLC原本的视频分组默认是禁用了，我改成了默认按文件夹分组
  
### 注：编译vlc-android源码在国内需要使用VPN，然后设置好Androidstudio的代理

## Downloads
 **[universal-image-loader-1.9.5.jar](https://github.com/xushihai/VLC-Android/raw/master/apk/VLC-Android-3.3.0-dev-all.apk)**
