### **Engenharia de Software - Relatório 2**

## **Introdução**
O *Seafile* é um projeto que se iniciou em 2009 por um grupo de estudantes da Universidade de Tsinghua, em Beijing, que tinham como ideia criar um projeto que permitisse a um número de utilizadores partilhar ficheiros entre si facilmente. Inicialmente, o objetivo era desenvolver um sistema de sincronização de ficheiros P2P onde não fosse preciso um servidor central. Contudo, com a elaboração de determinadas *features* para grupos, viram que tal não seria possível.

Atualmente, o *Seafile* é usado por mais de 300 000 mil pessoas. É também usado por empresas como a Universidade de Mainz e Karpersky Lab.


---
## **Specific Requirements**


---
## **Features**

Completa Sincronização de ficheiros e avançada:

- Sincronização seletiva, podendo organizar ficheiros em bibliotecas. Podendo cada uma destas ser sincronizada separadamente;
- Correta gestão de conflitos em ficheiros baseada no historial e não na ordem temporal;
- Uso de banda larga eficiente, apenas transferindo conteúdo que não se encontra no servidor e as transferências podem parar a meio e  continuar mais tarde;
- Sincrozação com sub-pastas;
- Versão de controlo completa enquanto que o número de revisões é configurável.

Colaboração completa da equipa de suporte:
- Grupos com sincronização de ficheiros, wiki, chat;
- Edição de ficheiros e comentários online;
- Partilha de sub-pastas para utilizadores/grupos;
- Partilha de ficheiros únicos entre utilizadores;
- Partilha de links;
- Mensagem Pessoal.

Proteção de Privacidade avançada:

- Encriptação das bibliotecas com palavra-chave escolhida pelo utilizador;
- Encriptação **client side**;
- Palavra-chave nunca é mandada para o servidor.

---
## **Diagrama de Casos de Uso**
<!-- *Actors:*

- Utilizador;
- Servidor.

*Usos:*

- Registar uma nova conta;
- Entrar com uma conta já existente;
- Upload de ficheiros;
- Download de ficheiros;
- Criar um grupo;
- Editar ficheiros;
- Renomear ficheiros/pastas;
- Partilhar ficheiros/pastas;
- Apagar ficheiros/pastas;
- Encriptar ficheiros/pastas com password;
- Restaurar versões anteriores do ficheiro;
- Criar wiki pessoal/grupo;
- Editar wiki pessoal/grupo;
- Enviar mensagens no chat de grupo ou de ficheiro;
- Receber mensagens no chat de grupo ou de ficheiro. -->

![alt text][usecase]

[usecase]: ./usecase.jpg "Use case diagram"

---
## **Modelo de domínios**

![alt text][domainmodel]

[domainmodel]: ./domainmodel.jpg "Domain model"
