
# Sharing files between containers using bind mount

Bind mount allows you to share folder/files between multiple containers.

Launch another container from the Alpine Linux image and use the `-v` option to bind `/tmp/data` in the host. Execute:

> <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> docker run --name c3 -v /tmp/data:/data alpine ls -l /data </span>
>
> <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> docker run --name c4  -v /tmp/data:/data alpine  cat /data/ping.txt </span>

You will also find the file `hello.txt` under `/data` inside the containers.

<br/>
