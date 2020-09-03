# 233v2ray
要求：Ubuntu 16+ / Debian 8+ / CentOS 7+ 系统
推荐使用 Debian 9 系统，脚本会自动启用 BBR 优化。

备注：不推荐使用 Debian 8 系统，因为 Caddy 申请证书可能会出现一些莫名其妙的问题

V2Ray 配置文件路径：/etc/v2ray/config.json
Caddy 配置文件路径：/etc/caddy/Caddyfile
脚本配置文件路径: /etc/v2ray/233blog_v2ray_backup.conf


WS+TLS / HTTP2
如果你使用了这两个协议，那么就会使用了脚本自带的 Caddy 集成
不管如何，不建议直接去更改 Caddy 的配置：/etc/caddy/Caddyfile
如果你需要配置其他网站相关，请将网站的配置文件放到 /etc/caddy/sites 目录下，然后重启 Caddy 进程即可，脚本默认生成的 Caddy 的配置会加载 /etc/caddy/sites 这个目录下的所有配置文件。
所以，请将你的网站配置文件放到 /etc/caddy/sites 目录下，完完全全不需要去更改 /etc/caddy/Caddyfile
记得重启 Caddy 进程：service caddy restart


Caddy 插件相关
本脚本集成了 Caddy，但不集成任何 Caddy 插件，如果你需要安装某些 Caddy 插件，你可以使用官方的 Caddy 安装脚本来一键安装。
本人的脚本集成的 Caddy 的安装路径，跟 Caddy 官方的安装脚本是一致的。所以可以直接安装，不会有任何问题

举个例子，安装包含 http.filebrowser 插件的 Caddy，执行如下命令即可

curl https://getcaddy.com | bash -s personal http.filebrowser
你可以在 https://caddyserver.com/download 找到 Caddy 更多插件和安装命令。
