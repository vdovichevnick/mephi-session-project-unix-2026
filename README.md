# МИФИ — Сессионный проект по курсу «Операционные системы семейства Unix»

Студент: Никита Вдовичев  
Бухгалтерский шифр: 369936  
Репозиторий: https://github.com/vdovichevnick/mephi-session-project-unix-2026

---

## Об окружении

Проект выполнен на Ubuntu 25.10 (ARM64) в VirtualBox для ARM-архитектуры на MacOS.

Отличия от Fedora:

- вместо dnf/rpm использовался apt/dpkg
- вместо SELinux на Ubuntu работает AppArmor
- tcpdump находится в /usr/bin/, а не /usr/sbin/
- вместо RPM-пакета скачан и установлен DEB-пакет tcpdump_4.99.5-2ubuntu2_arm64.deb

---

## Пояснение по SELinux и AppArmor

Ubuntu не использует SELinux. Вместо него система мандатного контроля доступа (MAC) - AppArmor. 
Команды getenforce, restorecon, semanage на Ubuntu недоступны без ручной установки SELinux, 
который на этом дистрибутиве официально не поддерживается.

В файле selinux_status.txt — вывод aa-status, который показывает что AppArmor
работает в режиме enforce: загружено 228 профилей, 150 из них в enforcing.

В файле file_contexts.txt — права директории /data/mephi-web и статус профиля
nginx в AppArmor.

---

## Файлы в репозитории

project_history.txt — история команд  
network_check.txt — результаты ping  
nginx_recent_logs.txt — логи nginx  
fstab.txt — конфиг /etc/fstab  
selinux_status.txt — статус AppArmor  
file_contexts.txt — права /data/mephi-web  
tcpdump_capabilities.txt — capabilities tcpdump  
permissions.txt — stat /data/mephi-web  
users_groups.txt — пользователи и группы  
index.html — страница веб-сервера  
curl_output.txt — вывод curl http://192.168.1.100  
screenshot.jpg — скриншот браузера  
tcpdump_4.99.5-2ubuntu2_arm64.deb — deb-пакет tcpdump (аналог RPM)  