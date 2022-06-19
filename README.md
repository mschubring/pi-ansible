# pi-ansible
## Setup `ansible` User
```shell
useradd -mU ansible
usermod -aG sudo ansible
mkdir /home/ansible/.ssh
chmod 700 /home/ansible/.ssh
echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDLGAvhveLE2TejGRydo0CRbCVz6P+IW5cjhsOL/Mn55dTZ26CMyjrAKKB94gZ5//wnqRLveAc9UKPeELxKsbK2fpKZk8QShqp/KWSFACCsNyL2QkmnTeUfmedN0yZKbQuBgp1FG+KGaS1eUBi7ahnRFY7CGvYsFERVtJLPfOzGj2YX1Y4P+x+aq+UgJwG6UrU5zTQ9lNHyJVvwNOAXDPLIXG0DFaKbnjKy44eNm0Avb0xeuGrCDxO5uUkPaF866GuJ8scXjH/z2Nuh/mMmT0ZhDXJHz2QDCY+0UqZhEvchK2T7YzWlrFEdWcGt5z8hm5Fq4dg9JKxOpB7eDsf2wV7d 04-ansible.pub' > /home/ansible/.ssh/authorized_keys
chmod 600 /home/ansible/.ssh/authorized_keys
chown -R ansible:ansible /home/ansible/.ssh
```

## (Optional) SSH-Key for root
```shell
mkdir /root/.ssh
chmod 700 /root/.ssh
echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDHmO/FMV8er6Ds0IckVORq+tfdH7zrgEhbLlKhEmAsp65prC4br/UOi0ekLuwFSXW2JiY+d2X578JljXU5apA11jb1wKQ0QcVZqTlFfGgo90kv5VeSj40qlF++MO8W43odyya8kOyZIPvHJ43jl5E2iwzAKYljyXaoTOLwju/HvPsMW/hwexxPvA9yewt1WFPQZzD80Hw2Oek4nDQZYbQy8qprR9+8x4SiafOpmTRIa6Sk3/hFQ1v494moKhcoLY9mPmig8RtOwZTKL+ajbzo8ibmg5FCoGUCS4hRE/Tmb3RsiBZnsbu/MlKE/SvzdwbyFdswFsCF30twfKBZDcTBZ 03-raspberry-pi.pub' > /root/.ssh/authorized_keys
chmod 600 /root/.ssh/authorized_keys
```
