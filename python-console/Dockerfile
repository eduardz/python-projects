FROM python:3.12-rc-bullseye

RUN apt-get update && apt-get install -y openssl curl openssh-client sudo shellinabox && apt-get clean && rm -rf /var/lib/apt/lists/*

# expose default port 
EXPOSE 4200

CMD: ["shellinabox", "/usr/bin/python3"]