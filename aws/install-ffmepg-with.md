---
description: How to install ffmpeg in aws EC2 instance
---

# Install ffmepg with

#### Donwload [ffmpeg-git-amd64-static.tar.xz](https://johnvansickle.com/ffmpeg/builds/ffmpeg-git-amd64-static.tar.xz)

#### Unzip .tar 

```text
tar xvf ffmpeg-git-amd64-static.tar.xz
```

#### Check shell's path

```bash
echo $PATH
/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/home/ec2-user/.local/bin:/home/ec2-user/bin
```

#### Move the static binaries ffmpeg and ffprobe into the shell's path.

Be careful with the folder's name \(in this case ffmpeg-git-20200324-amd64-static\)

```text
sudo mv ffmpeg-git-20200324-amd64-static/ffmpeg ffmpeg-git-20200324-amd64-static/ffprobe /usr/local/bin/
```

