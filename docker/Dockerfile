FROM fedora

RUN dnf install -y -q vim openssh-server openssh-clients iproute bash nano
RUN ssh-keygen -A
RUN usermod -p "\$6\$Cya6Q7UV\$r88j9s1.RxTaW.abzj4R9DKA4TZoAEnfTV7oVMvnknPer2t2QrMSdWb3UPeKSwNFH2RCJrtsXd0Cgn66NYJ1Q0" root

COPY task /root/
