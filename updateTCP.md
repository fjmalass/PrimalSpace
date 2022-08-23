# Update `TCP` Packet max size

## Append `/etc/sysctl.conf`

```txt
net.core.default_qdisc=fq
net.ipv4.tcp_congestion_control=bbr

net.ipv4.tcp_limit_output_bytes = 4194304
net.ipv4.tcp_mem = 33554432 33554432 33554432
net.ipv4.tcp_slow_start_after_idle = 0
net.core.netdev_max_backlog = 5000

# allow testing with buffers up to 64MB
net.core.rmem_max = 67108864
net.core.wmem_max = 67108864
# increase Linux autotuning TCP buffer limit to 32MB
net.ipv4.tcp_rmem = 4096 87380 33554432
net.ipv4.tcp_wmem = 4096 65536 33554432
```

## Run `/etc/sysctl.conf`

`sudo sysctl -p`
