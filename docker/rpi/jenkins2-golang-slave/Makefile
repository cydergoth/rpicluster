SHELL=bash

jenkins-golang:
	read -s -p "Jenkins PW >" jenkinspw && docker build --build-arg jenkinspw="$${jenkinspw}" -t jenkins-golang . 

.PHONY: jenkins-golang
