# my arch configuration

all of this is done in the live environment, maybe restarting the system would have been better lol

## base text editor
for basic setup in the live environment i use vim
```bash
pacman -S vim
```
## network

install a dhcp client and enable it
```bash
pacman -S dhcpcd
systemctl enable dhcpcd@wlan0.service # enable dhcpcd service
```

install a network manager (for wifi!)
```bash
pacman -S iwd
systemctl enable --now iwd.service
iwctl --help | less # show help for iwctl
iwctl # start iwctl command utility
```

## user
```
useradd -m -G wheel davide
passwd davide
passwd -l root # disable root login
pacman -S sudo # install sudo utilities
```

***visudo*** configuration:
```bash
Defaults passwd_timeout=0
Defaults timestamp_type=global
Defaults timestamp_timeout=15
Defaults:%wheel targetpw

%wheel ALL=(ALL:ALL) ALL
```

## gui - sway
``` bash
pacman -S sway
```

## after reboot...
