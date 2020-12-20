# linux_rsnapshot

### Guia para instalar el servicio Rsnapshot en equipos con linux *solo en entornos controlados*

---
#### Actualizar la cache de los repos e instalar los programas necesarios 
apt update && sudo apt install -y rsync rsnapshot

#### Crear las llaves y copiarlas al cliente del que queremos hacer backups
ssh-keygen -t rsa -C rsnapKeys

ssh-copy-id -i /home/root/.ssh/id_rsa.pub root@ip-cliente

#### Editar el archivo sshd.config en el cliente 
PermitRootLogin yes

Pubkeyauthentication yes

#### Editar etc/rsnapshot.conf en servidor

#### Chequear que la configuracion sea valida
rsnapshot configtest 

#### Prueba 
rsnapshot hourly 

#### Crear cronjob en /etc/cron.d/rsnapshot en servidor

