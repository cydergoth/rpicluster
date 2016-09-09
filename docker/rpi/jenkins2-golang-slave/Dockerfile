FROM hypriot/rpi-golang

ARG jenkinspw

RUN apt-get update && apt-get install -y openjdk-7-jre-headless openssh-server sudo && \
    sed -i -e 's/#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config && mkdir -p /var/run/sshd && \
    useradd -m jenkins -p $(openssl passwd $jenkinspw) -G sudo && \
    echo "jenkins ALL=(ALL) NOPASSWD:ALL" >/etc/sudoers.d/91-jenkins && \
    echo >>/etc/profile "export GOLANG_VERSION=1.5\nexport GOROOT=/goroot1.5\nexport GOPATH=/gopath1.5\nexport GOARM=6\nexport PATH=${GOROOT}/bin:${GOPATH}/bin:${PATH}\n"

EXPOSE 22
CMD ["/usr/sbin/sshd","-D"]
RUN go get github.com/mitchellh/gox
RUN go get github.com/hashicorp/vault/cli
