sudo groupadd Admin
sudo groupadd Doscentes
sudo groupadd Alumnos

cd /home
sudo mkdir plantel

cd plantel
sudo mkdir Admin
sudo mkdir Doscentes
sudo mkdir Alumnos

chgrp Admin Admin
chgrp Doscentes Doscentes
chgrp Alumnos Alumnos
echo "Escoja la Opcion a realizar" 
echo "1. Create user Alumnos"
echo "2. Create user Doscente" 
echo "3. Create user Admin"
echo "0. Cambiar a root (Salir)"

read opcion
 
case $opcion in

1)
echo "Ingresa el nombre de usuario"
read user 
sudo useradd $user -d /home/plantel/Alumnos/$user -m -g Alumnos
sudo passwd $user 
cd /home/plantel/Alumnos/
sudo chmod 705 $user  
;;


2)
echo 'Ingresa el nombre del Doscente'
read user
sudo useradd $user -d /home/plantel/Doscentes/$user -m -g Doscentes
sudo passwd $user 
cd /home/plntel/Doscentes/
sudo chmod 750 $user
;;


3)
echo 'Ingresa el nombre del Admin'
read user 
sudo useradd $user -d /home/plantel/Admin/$user -m -g Admin
sudo passwd $user 
cd /home/plantel/Admin/ 
sudo chmod 770 $user 
;;


esac
done
exit 0e
