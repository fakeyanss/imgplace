# Blog_Album
* 博客的相册源文件，go to [my album](https://foreti.me/gallery/)
* 文件夹结构:
```
├─game
│  ├─min_pic      压缩后的缩略图
│  └─pic          原图
├─photo           
│ ├─min_pic       压缩后的缩略图
│ └─pic           原图
├─appveyor.yml    CI脚本
└─build.py        缩略图和生成json脚本
```

* 图片或视频名格式为`2019-01-01_xxxxxx`

* **图片仅支持jpg格式**。

* 添加新图片之前记得 `git pull` 或 `git rebase`，因为appveyor会将压缩的图片和json文件重新push到source分支，这样远程库会领先本地库一个版本。

* 新图片前加`new_`前缀，作为标记，compress.py脚本只压缩有`new_`前缀的图片，压缩完后会自动改名去掉前缀。

* 若要上传视频，会比较麻烦，有以下步骤。
  1. 对视频的某一帧截图，作为视频封面，图片名有`new_`前缀，视频名无。
  2. 将视频和截图放在`/photo/`下
  5. 上传