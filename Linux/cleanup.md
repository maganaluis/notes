# Arch Linux Cleanup

## System Update
```bash
sudo pacman -Syu
```

## Remove Unused Packages
```bash
sudo pacman -Rns $(pacman -Qtdq)
sudo pacman -Sc
```

## Clear System Logs
```bash
sudo journalctl --vacuum-time=7d
sudo rm -rf /var/log/*.gz /var/log/*.[0-9]
```

## Clean Cache
```bash
sudo pacman -Scc
```

## User Cache
```bash
rm -rf ~/.cache/*
```

## Clean Up Hatch Environments
```bash
rm -rf ~/.local/share/hatch/env/
```

## Minikube
```bash
minikube stop
minikube delete
```
## Cargo
```bash
rm -rf ~/.rustup/tmp
rm -rf ~/.cargo/target
```

## Go
```bash
go clean -cache
go clean -modcache
rm -rf ~/go/pkg ~/go/src ~/go/bin
```

## Node
```bash
rm -rf node_modules
npm cache clean --force
yarn cache clean
```

## Clean Up Docker Nuke
```bash
docker system prune -a --volumes -f
```

## Reboot System
```bash
sudo reboot
```

## Check Disk Usage
```bash
df -h
```

## Check Detailed Folder View
```bash
du -sh .[!.]* * | sort -hr
```