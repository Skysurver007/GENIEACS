#BUKA AKSES ROOT 

sudo -I

#ALTERNATIF 

sudo su

nano /etc/ssh/sshd_config

# Jika ingin IZIN root login (dengan password) --> (kurang aman)
PermitRootLogin yes
PasswordAuthentication yes

# Lebih aman: IZIN root HANYA dgn kunci publik
# PermitRootLogin prohibit-password
# PasswordAuthentication no



#GANTI REPOSITORI   IKUTI  PANDUAN DI  https://github.com/Skysurver007/LINUX


#INTSAL GENIE ACS 

sudo apt-get install dos2unix

git clone https://github.com/Skysurver007/GENIEACS

cd axcxsx

chmod +x GO.sh

dos2unix GO.sh

bash GO.sh


mkdir /root/db
cd /root/db

#UPLOAD FILE YANG DI DOWNLOAD DI https://github.com/Skysurver007/PARAMETER-GENIEACS.git

mongorestore --db genieacs --drop /root/db
systemctl start genieacs-{cwmp,ui,nbi}
