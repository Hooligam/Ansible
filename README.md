# Gerenciando, automatizando, implando e configurando servidores
![Ansible](https://datascientest.com/en/wp-content/uploads/sites/9/2023/11/ansible.webp)

**Objetivo**:
O projeto visa simplificar e automatizar o gerenciamento de três servidores distintos, executando os sistemas operacionais Ubuntu, Debian e CentOS. Utilizando a poderosa ferramenta de automação Ansible, nosso objetivo é instalar pacotes essenciais, configurar o servidor web Nginx e realizar o deploy de um site de forma eficiente e consistente.

**Benefícios**: 
Eficiência Operacional: A automação reduz a carga de trabalho manual, economizando tempo e minimizando erros.

Consistência: Todos os servidores são configurados de forma consistente, reduzindo discrepâncias e facilitando a manutenção.

Facilidade de Escala: A estrutura modular do Ansible permite a fácil adição de novos servidores e funcionalidades.

## 📌 Iniciando

Recomendo criar um servidor central onde será instalado o Ansible, permitindo o controle remoto e automação dos outros servidores.

Caso necessite segue o link da documentação oficial do [Documentação de Instalação do Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-specific-operating-systems)

Também foi criado chave SSH, para simplificar a comunicação entre os servidores.

## 📦 Documentação

**ansible.cfg**

 é um arquivo de configuração do Ansible que permite personalizar o comportamento padrão do Ansible, ajustando diversas opções. Ele é usado para definir configurações globais ou específicas do projeto que afetam a execução de playbooks, roles e comandos Ansible.

**Arquivo de Invetario**

Nosso arquivo de invetario "hosts" contem o IP dos 3 servidores, também utilizamos variaveis de ambiente para nomear os servidores.

**Playbook**

Construimos apens um Playbook para chamar e executar nossas roles, em alguns senarios poderiamos ter varios pleybooks para diferentes ações e para facilitar.

**Roles**

A principio foi criada duas roles:

*checklist_Servidores*
 Onde temos uma variavel chamada "pacotes" que lista os pacotes necessarios para os servidores, simplificando o codigo. 
 Também criamos as "tasks" para a atualização e instalação nas 3 distros.

*install_nginx*

Nessa role, e feita a instalação e configuração do nginx nos 3 servidores, também criamos um "handlers" para startar o serviço do nginx.
Nessa mesma role, fazemos o deploy do site.

⌨️ com ❤️ por [Elias Assunção](https://github.com/Hooligam) 🔥