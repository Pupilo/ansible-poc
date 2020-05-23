# LAB K8s 
Versão: 0.0.1
Pré-requisitos
* VPC configurado
* Duas subnetes

### Provisionar o AWX
```sh
cd awx_provisioning
ansible-playbook -i hosts main.yml
```

### Instalar o AWX
```sh
cp hosts ../awx_install/hosts
cd awx_install/
ansible-playbook -i hosts main.yml --key-file /path/yourkey
```

### Instalando k8s
```sh
cd provisioning
ansible-playbook -i hosts main.yml
cd ../install_k8s
#Edite o arquivo host como os ips das instancias criadas.
ansible-playbook -i hosts main.yml
```

### Observação
Restrinja o acesso aos ips de suas infâncias no security group.

### Roadmap
* Documentação para deploy usando AWX
* Implementação de segurança para security groups
