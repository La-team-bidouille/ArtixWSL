# Install instructions

## Initial setup

Download a zip from the [Releases](https://github.com/La-team-bidouille/ArtixWSL/releases) section with your preferred init system.

<aside class="available-init-systems">
  <h3>Available init systems</h3>
  <ul>
    <li>OpenRC</li>
    <li>Runit</li>
    <li>S6</li>
    <li>Dinit</li>
  </ul>
</aside>

Unzip and run the Artix.exe file.

## Post instal setup

### pacman keyring

```
pacman-key --init
pacman-key --populate
```

### sudo

```
pacman -Sy sudo
```
then for sudo with password prompt
```
echo "%wheel ALL=(ALL) ALL" > /etc/sudoers.d/wheel
```
or for sudo **without** password prompt
```
echo "%wheel ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/wheel
```

### Users


```
passwd

useradd -m -G wheel -s /bin/bash {username}

passwd {username}
```

then from the Artix.exe folder :
```
Arch.exe config --default-user {username}
```