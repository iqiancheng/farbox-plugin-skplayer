# farbox-plugin-skplayer
一个简洁的Farbox博客的音乐播放器插件
---

## 下载插件包

**方法** #1

```bash
$ git clone git@github.com:iqiancheng/farbox-plugin-skplayer.git template
```

**方法** #2 
直接 [戳这里下载](https://codeload.github.com/iqiancheng/farbox-plugin-skplayer/zip/master)，即可得到插件下载包。
## 快速安装
把刚才下载的插件包，解压出来放在 Farbox 自定义模版路径 `template` 下，如图所示结构。

```
template
├── plugins
│   └── skPlayer
│       ├── css
│       │   └── skPlayer.min.css
│       ├── js
│       │   ├── skPlayer.js
│       │   └── skPlayer.min.js
│       └── segment.jade
```
给想要加入音乐播放器的页面添加引用。比如说，我要给我的每一篇博文都加上播放器，这样我的每一个访客在看文章的时候就可以听音乐。找到文章的对应 jade 文件是`post.jade`，在`post.jade` 末尾加上

```js
	include plugins/skPlayer/segment
```
下面的截图是我添加在`about.jade` 页面的示例，最下面的位置添加一个include
![](media/14729730287951.jpg)￼
`注意` 添加这段引用要注意代码的结构，不要顶格写，要有`tab`或者空格保证代码的结构才可以生效。

## 设置歌单
找到刚才解压插件包里的一个文件`template/plugins/skPlayer/segment.jade` 里面，修改`playlistId`为自己喜欢的网易云音乐的歌单ID就好了。

```javascript
script
	playlistId = 1704968;//网易云歌单ID

	(function(playlistId){
		skPlayer({
		    music: playlistId,
		    autoplay: false,
		    loop: true, 
		    showList: false
		});
	})(playlistId);
```
怎么找到自己的歌单ID呢？登录网页版的云音乐，随便打开一个歌单，浏览器地址里面最后有个`?id＝1704968` 这串数字就是ID 



