### **Engenharia de Software - Relatório 2**

## **Introdução**


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
## **Casos de Uso**
*Actors:*

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
- Receber mensagens no chat de grupo ou de ficheiro.


---
## **Modelo de domínio**
