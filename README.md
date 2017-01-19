# VSFTP-Usuarios-Virtuales-Fedora
Crear usuarios virtuales de VSFTP en Fedora


## 1.Instalar Berkeley Database
  > yum install db4-utils db4 -y

## 2.Crear archivo de database para los usuarios virtuales
  > nano /home/virtual_users.txt
  >> senthil
  >> centos
  
Se escribe usuario y contrasenya respectivamente

Es decir sethill es usuario y centos contrasenya

**Si queremos añadir mas seria cuestion de ponerlos debajo**

## 3.creamos la base de datos apartir de este archivo
> db_load -T -t hash -f /home/virtual_users.txt /etc/vsftpd/virtual_users.db
ahora virtual.db es la base de datos de los usuarios

## 4. Pegamos este archivo a /etc/pam.d/vsftpd_virtual
> [vsftpd_virtual](https://github.com/Wiki-SMX/VSFTP-Usuarios-Virtuales/blob/master/vsftpd_virtual)

## 5. Pegamos este archivo a /etc/vsftpd/vsftpd.conf

> [vsftpd.conf](https://github.com/Wiki-SMX/VSFTP-Usuarios-Virtuales/blob/master/vsftpd.conf)

## 6. Creamos el home del usuario creado 
> mkdir -p /ftp/virtual/senthil
> chown -R ftp:ftp /ftp/virtual/senthil/
> chmod 555/ftp/virtual/senthil

## 7. carpeta para subir archivos
> mkdir -p /ftp/virtual/senthil/pull
> chmod 777 /ftp/virtual/senthil
## Ya esta :D  
