# Anaconda

## 地址

<https://mirrors.ustc.edu.cn/anaconda/>

## 说明

Anaconda 仓库镜像

## 使用说明

Anaconda 安装包可以在 <https://mirrors.ustc.edu.cn/anaconda/archive/> 下载。

Miniconda（Anaconda 的轻量级替代）安装包可以在 <https://mirrors.ustc.edu.cn/anaconda/miniconda/> 下载。

向 `.condarc` 写入配置以使用镜像站，其中各个操作系统对应的文件：

- Linux & macOS: `$HOME/.condarc`
- Windows: `%USERPROFILE%\.condarc`
    - 由于 Windows 资源管理器的限制，可能需要先运行 `conda config --set show_channel_urls yes` 来生成这个文件。

内容如下：

```yaml
channels:
  - defaults
show_channel_urls: true
default_channels:
  - https://mirrors.ustc.edu.cn/anaconda/pkgs/main
  - https://mirrors.ustc.edu.cn/anaconda/pkgs/r
  - https://mirrors.ustc.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.ustc.edu.cn/anaconda/cloud
  bioconda: https://mirrors.ustc.edu.cn/anaconda/cloud
```

!!! info "Anaconda Cloud channels"

    目前我们为以下第三方频道提供**动态缓存**。与 [pypi](./pypi.md) 类似，未命中的包（包括未同步的频道）会重定向到 TUNA。

    - conda-forge
    - bioconda

之后运行 `conda clean -i` 清除缓存后，使用 `conda create -n myenv numpy` 测试配置是否正确。

## 相关链接

官方主页

:   <https://www.continuum.io/>
