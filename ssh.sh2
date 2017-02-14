#/bin/bash
for ((i=2;i<=2;i++))
do
/usr/bin/sshpass -p Huawei12#$ ssh root@192.168.122.$i "
port=`grep Port /etc/ssh/sshd_config | awk 'NR==1{print $2}'`
if [ "$port" -eq "22" ];then
	echo "SSH port is default 22,do you want to modify it?";
	echo "input yes/no to modify it"
	read -p "Enter selection: ";
	if [ $REPLY == yes -o $REPLY == YES ];then
	   echo "modifying ssh port now ...";
	   read -p "Please input you want to change number: ";
	   sed -i "s/#Port 22/Port $REPLY/g" /etc/ssh/sshd_config;
	   systemctl restart sshd.service;
	  elif [ $REPLY == no -o $REPLY == NO ];then 
	      echo "SSH port is default 22";
	   else 
	   echo "please try again: ";
	fi	
else 
	echo "SSH port is save"; 
fi
"
done
