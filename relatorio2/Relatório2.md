### **Engenharia de Software - Relatório 2**

## **Introdução**
O *Seafile* é um projeto que se iniciou em 2009 por um grupo de estudantes da Universidade de Tsinghua, em Beijing, que tinham como ideia criar um projeto que permitisse a um número de utilizadores partilhar ficheiros entre si facilmente. Inicialmente, o objetivo era desenvolver um sistema de sincronização de ficheiros P2P onde não fosse preciso um servidor central. Contudo, com a elaboração de determinadas *features* para grupos, viram que tal não seria possível.

Atualmente, o *Seafile* é usado por mais de 300 000 mil pessoas. É também usado por empresas como a Universidade de Mainz e Karpersky Lab.


---
## **Requisitos**

Não é novidade alguma que a comunicação entre o cliente e prestadores de serviços é crucial para garantir um produto final satisfatório e capaz de corresponder às expectativas do cliente. No contexto de engenharia de *software*, a análise de requisitos é um processo indispensável na concretização desta mesma comunicação, garantindo, assim, que todas as partes estejam ativas no desenvolvimento do processo.

Os requisitos podem dividir-se em requisitos funcionais e requisitos não funcionais. 

### **Requisitos funcionais**
Os requisitos funcionais descrevem explicitamente as diversas funcionalidades e serviços do sistema. Documenta, assim, como o sistema deve comportar-se em situações específicas e aquilo que este não deve fazer. Uma imprecisão na especificação dos requisitos pode levar a ambiguidades.

O *Seafile*, para além da versão gratuita e disponível em *open source*, disponibiliza uma 
versão profissional para empresas. Esta versão Pro baseia-se na versão *open source*, no entanto, disponibiliza funcionalidades mais avançadas.

O *Seafile* disponibiliza várias **funcionalidades**.

Relativamente à **sincronização e partilha de ficheiros** permite:
- Sincronizar ficheiros entre várias plataformas;
- Partilhar e sincronizar ficheiros através da aplicação móvel;
- Uma sincronização seletiva, podendo organizar ficheiros em bibliotecas;
- Partilhar bibliotecas com grupos e/ou utilizadores;
- Versão de controlo completa enquanto que o número de revisões é configurável;
- Partilhar ficheiros em modo de leitura;
- Partilhar um ficheiro através de um link público;
- Bloquear um ficheiro para que outros utilizadores não o possam editar;
- Definir as permissões do ficheiros (modo leitura ou escrita);
- Edição de ficheiros e comentários online;
- Grupos com sincronização de ficheiros, wiki, chat;
- Enviar mensagem pessoal.

Em relação à **gestão do utilizador**, este pode:
- autenticar-se contra LDAP/AD;
- se um utilizador for eliminado do diretório(LDAP), este é automaticamente desativado no *Seafile*;
- autenticar-se como convidado, mas não pode criar grupos nem bibliotecas;


### **Requisitos Não Funcionais**

Os requisitos não funcionais definem propriedades e restrições do sistema, como por exemplo segurança e desempenho. Estes requisitos podem ser relativos a todo o sistema ou apenas partes dele.

Os requisitos não funcionais podem dividir-se em:
- requisitos de produto - especificam o comportamento do software (ex: desempenho);
- requisitos organizacionais - consequência de politicas e procedimentos das empresas;
- requisitos externos - derivados do ambiente ou fatores externos ao sistema (ex: legislacao)

**Requisitos de produto:**
- Encriptação das bibliotecas com palavra-chave escolhida pelo utilizador;
- Encriptação **client side**;
- Palavra-chave nunca é mandada para o servidor.
- Os ficheiros são encriptados antes de serem sincronizados com o servidor;
- O núcleo do servidor está escrito em C, o que garante um alto desempenho;
- Facilidade e rapidez em fazer *upgrade* devido à pouca informação existente na base de dados;
- Desenvolvimento de um algoritmo de sincronização robusto;
- Utilização de uma ferramenta que permite recuperar dados;
- Limpeza de dados remota;
- Uso de banda larga eficiente, apenas transferindo conteúdo que não se encontra no servidor e as transferências podem parar a meio e  continuar mais tarde;


**Requisitos Externos:**
- Os ficheiros dos utilizadores não podem ser vistos pelo administrador do sistema;

---
## **Diagrama de Casos de Uso**

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

![alt text][usecase]

[usecase]: ./usecase.jpg "Use case diagram"

---
## **Modelo de domínios**

![alt text][domainmodel]

[domainmodel]: ./domainmodel.jpg "Domain model"
