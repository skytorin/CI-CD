# GitLab в Linux

## Установка Gitlab Runner

### Добавления репозитария
Debian/Ubuntu/Mint:
```
curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | sudo bash
```
RHEL/CentOS/Fedora:
curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.rpm.sh" | sudo bash

### Установка
Debian/Ubuntu/Mint:
```
sudo apt-get install gitlab-runner
```
если нужна определенная версия:
```
apt-cache madison gitlab-runner
sudo apt-get install gitlab-runner=10.0.0
```
RHEL/CentOS/Fedora:
```
sudo yum install gitlab-runner
```
если нужна определенная версия:
```
yum list gitlab-runner --showduplicates | sort -r
sudo yum install gitlab-runner-10.0.0-1
```

## Регистрация GitLab Runner
```
sudo gitlab-runner register 
```
можно сразу указать параметры
```
sudo gitlab-runner register --url https://gitlab.example.com/ --registration-token GR43289467y7EHFpzaPbrRyvtoy8b
```

## Полномочия sudo
Чтобы УЗ gitlab-runner могла использовать привелигированные команды, необходимо предоставить УЗ доступ к sudo.
Для этого добавляем УЗ в файл /etc/sudoers
```
gitlab-runner ALL=(ALL) NOPASSWD: ALL
```
 
 
 
 
 
Links: 
https://docs.gitlab.com/runner/install/linux-manually.html
