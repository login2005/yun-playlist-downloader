# yun-playlist-downloader
网易云音乐 - 歌单 - 下载器

[![npm version](https://img.shields.io/npm/v/yun-playlist-downloader.svg)](#)
[![node version](https://img.shields.io/node/v/yun-playlist-downloader.svg)](#)
[![license](https://img.shields.io/npm/l/yun-playlist-downloader.svg)](#)


## 安装
需要 node.js 4.x (Argon LTS)

```sh
$ npm i yun-playlist-downloader -g
```

## 使用
```sh
$ yun

  网易云音乐 歌单/专辑 下载器 v0.4.4

  使用:
    yun [选项] <地址>

  选项:
    -h,--help         查看此帮助信息
    -c,--concurrency  设置同时下载数量, 默认5
    -f,--format       设置文件格式, 默认 ':name/:singer - :songName.:ext'
    -q,--quality      设置音质, 可选值为 128,192,320(kbits/s), 默认320

  帮助 & 文档:
    https://github.com/magicdawn/yun-playlist-downloader

  示例:
    # 10首同时下载
    yun -c 10 http://music.163.com/#/playlist?id=12583200

    # 下载格式为 '歌手 - 歌名'
    yun -f ':singer - :songName.:ext' http://music.163.com/#/playlist?id=12583200
```

### 自定义文件名 -f,--format

|token|含义|
|-----|---|
|:type| = `album` or `playlist`|
|:typeText| = `专辑` or `列表` |
|:name| 专辑名称 or 播放列表名称 |
|:singer| 歌手名 |
|:songName| 歌曲名(不含扩展名) |
|:ext| 文件后缀,如 `mp3` 不带 `.` |
|:index| `01` , `02` ... `12` |
|:rawIndex| `0`, `1`, ... `11` |

默认值 = `:name/:singer - :songName.:ext`

### 自定义下载音质 -q,--quality

|取值|含义|备注|
|---|---|---|
|128| 128kbits/s | |
|192| 192kbits/s | |
|320| 320kbits/s | 默认 |

## 截图
![](https://raw.githubusercontent.com/magicdawn/yun-playlist-downloader/master/yun.png)

## 已知问题
- [x] 并发过大会导致某些一开始任务即便机器处于空闲状态也会block住, 请根据自己网速酌情设置 `concurrency` 参数

## 更新记录
see [CHANGELOG.md](CHANGELOG.md)

## License
the MIT License http://magicdawn.mit-license.org
