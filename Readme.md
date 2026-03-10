# Что скачать перед занятием по аудиту

## Вариант 1. WSL + Ubuntu (рекомендуется)

### 1. WSL и Ubuntu
Открой PowerShell от имени администратора и выполни:
```
wsl --install
```

Перезагрузи компьютер. После перезагрузки Ubuntu установится автоматически.

Если нужна конкретная версия:
```
wsl --install -d Ubuntu
```

### 2. Инструменты Kali Linux
После установки Ubuntu добавь репозиторий Kali и установи инструменты:

```bash
# Обнови пакеты
sudo apt update && sudo apt upgrade -y

# Добавь репозиторий Kali
echo "deb http://http.kali.org/kali kali-rolling main non-free contrib" | sudo tee /etc/apt/sources.list.d/kali.list
wget -q -O - https://archive.kali.org/archive-key.asc | sudo apt-key add -

# Обнови список пакетов
sudo apt update

# Установи основные инструменты
sudo apt install -y nmap sqlmap nikto burpsuite curl wget git python3 python3-pip
```

Минимальный набор для занятия:
- nmap — сканирование сети
- sqlmap — поиск SQL-инъекций
- nikto — сканер веб-уязвимостей
- curl, wget — работа с HTTP
- git — работа с репозиториями
- python3, pip — запуск скриптов

### 3. Docker Desktop
Скачай с https://www.docker.com/products/docker-desktop/

После установки включи интеграцию с WSL в настройках Docker.

Проверь работу в Ubuntu:
```bash
docker --version
docker-compose --version
```

### 4. Visual Studio Code
Скачай с https://code.visualstudio.com/

Установи расширение «WSL» для работы с Linux-окружением.

Рекомендуемые расширения:
- Docker
- GitLens
- Python
- Pylance

### 5. Браузер с DevTools
Подойдёт любой современный браузер:
- Google Chrome
- Mozilla Firefox
- Microsoft Edge

Убедись, что умеешь открывать инструменты разработчика (F12).

## Вариант 2. Kali Linux на виртуальной машине

### Важно
Сайт kali.org сейчас заблокирован в России. Используй VPN для скачивания.

### 1. Виртуализация
Скачай и установи одно из:
- VirtualBox: https://www.virtualbox.org/
- VMware Workstation Player: https://www.vmware.com/products/workstation-player.html

### 2. Образ Kali Linux
Скачай готовый образ с официального сайта (нужен VPN):
https://www.kali.org/get-kali/#kali-virtual-machines

Выбери образ для своей платформы виртуализации.

### 3. Запуск
Импортируй образ в виртуальную машину и запусти.

Стандартные учётные данные:
- Логин: kali
- Пароль: kali

### 4. Обновление
После первого запуска обнови систему:
```bash
sudo apt update && sudo apt upgrade -y
```

### 5. Docker в Kali
Установи Docker внутри Kali:
```bash
sudo apt install -y docker.io docker-compose
sudo usermod -aG docker $USER
```

Перелогинься для применения прав.

## Проверка перед занятием

К началу занятия у тебя должны работать:
- WSL с Ubuntu или Kali на виртуальной машине
- Docker и docker-compose
- Python 3 и pip
- Базовые инструменты: nmap, sqlmap, nikto, curl, git
- Редактор кода
- Браузер с DevTools

Если что-то не работает — напиши в чат заранее.
