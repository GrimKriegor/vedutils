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
sudo apt install -y ffmpeg git bc vainfo mesa-va-drivers
echo "export LIBVA_DRIVER_NAME=d3d12" >> ~/.profile
git clone --recursive https://github.com/GrimKriegor/vedutils.git $HOME/vedutils
bash $HOME/vedutils/contrib/vedutils-upgrade
```

- Close `Windows PowerShell`

- On your desired directory press **Shift+MouseRight** and select `Open Linux shell here`

- Check the [project documentation](../README.md) for usage details

- Check the helper scripts in [contrib/](../contrib) if you aren't familiar with shell scripting

- Enjoy
