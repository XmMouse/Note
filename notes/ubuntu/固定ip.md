## service
    /etc/netplan/50-*
    network:
    ethernets:
        ens160:
            addresses:
                - 210.72.92.28/24 # IP及掩码
            gateway4: 210.72.92.254 # 网关
            nameservers:
                addresses:
                    - 8.8.8.8 # DNS
    version: 2
## desktop  
    /etc/network/interface
    iface ens160 inet static
    address 210.72.92.25
    gateway 210.72.92.254
    netmask 255.255.255.0
    dns-nameservers 8.8.8.8