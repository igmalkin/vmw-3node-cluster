# Установка Red Hat Openshift на платформу VMware

В данной статье будет рассмотрена установка 3х-узлового кластера Опеншифт с использованием автоматического инсталлятора (IPI) на платформу виртуализации от VMware.

Используемые версии ПО:
* VMware vSphere 6.7.0
* Red Hat Openshift 4.7.13

Документация:
https://docs.openshift.com/container-platform/4.7/installing/installing_vsphere/installing-vsphere-installer-provisioned-customizations.html

## Сетевая инфраструктура

В текущей инсталляции установка производилась в отдельный VLAN. 

DHCP-сервер настроен на выдачу адресов в диапазоне 10.17.49.65-10.17.49.127

Статические адреса, необходимые для функционирования платформы:

1. 10.17.49.5 - API VIP
2. 10.17.49.6 - Ingress (apps) VIP

## Настройка DNS-сервера

Потребуется использование и минимальная настройка DNS-сервера.

Необходимо внести 2 записи типа A для следующих имен:

1. api.vmw-cluster01.ocp4.test
2. *.apps.vmw-cluster01.ocp4.test (wildcard)

-где _vmw-cluster01_ имя кластера, а _ocp4.test_ используемый домен.
На примере рассматриваемой инсталляции, в качестве DNS-сервера используется Red Hat Identity Management:
![](images/dns-records.JPG)

## Генерация и использование ssh-ключа (опционально)

Набор команд для генерации ssh-ключа и его добавления в ssh-agent:

```
$ ssh-keygen -t ed25519 -N '' -f ~/.ssh/id_rsa
$ eval "$(ssh-agent -s)"
$ ssh-add .ssh/id_rsa
```

