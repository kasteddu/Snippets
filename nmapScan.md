***Scan rete locale***

nmap -sn 192.168.1.100-254 -oG - | awk '/Up$/{print $2 "\t" $3 }'


alternativa
nmap -n -sn 192.168.1.100-254 -oG - | awk '/Up$/{print $2}' > pippo.txt

while IFS='' read -r line || [[ -n "$line" ]]; do

	if ! ( [[ $line == *"192.168.1.114"* ]] || [[ $line == *"192.168.1.253"* ]] || [[ $line == *"192.168.1.254"* ]]    ) ;	then
  		echo "Nuovo host $line"
	fi

done < "pippo.txt"
