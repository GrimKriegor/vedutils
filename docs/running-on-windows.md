# vedutils on Windows

- Open a `Windows PowerShell` window as administrator and run

```
wsl --install
```

- Reboot

- Open a `Windows PowerShell` window and run

```
wsl
```

- On the Linux shell run

```
sudo apt update
sudo apt install ffmpeg git bc
git clone --recursive https://github.com/GrimKriegor/vedutils.git $HOME/vedutils
bash $HOME/vedutils/contrib/vedutils-upgrade
```

- Close `Windows PowerShell`

- On your desired directory press **Shift+MouseRight** and select `Open Linux shell here`

- Enjoy
