# Wireshark Filters Used

| Filter                          | Description                                         |
|---------------------------------|-----------------------------------------------------|
| `ip.addr == 142.250.1.139`      | Packets to or from the IP address                  |
| `ip.src == 142.250.1.139`       | Packets *from* the IP address                      |
| `ip.dst == 142.250.1.139`       | Packets *to* the IP address                        |
| `eth.addr == 42:01:ac:15:e0:02` | Packets involving specific MAC address             |
| `udp.port == 53`                | DNS query/response packets                         |
| `tcp.port == 80`                | Web traffic packets (HTTP)                         |
| `tcp contains "curl"`           | TCP packets containing the string `"curl"`         |
