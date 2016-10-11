### **Engenharia de Software - Relatório 1**


## **Introdução**

*Seafile* é um sistema de software de armazenamento de ficheiros. Os ficheiros são guardados num servidor central e podem ser sincronizados não só com computadores pessoais e dispositivos móveis via o *Seafile Client*, como também podem ser acedidos através da interface web do servidor.

O *Seafile* tem as seguintes componentes:
	
        - Sync client daemon;
        - Sync client GUI;
        - Server code;
        - Server Web UI;
        - iOS app;
        - Android app;
        - WebDAV.

Tendo em conta que não é possível fazer uma análise de todos os repositórios disponíveis, o grupo optou por escolher trabalhar com o *Server Web UI*. 
	

## **Processo de Desenvolvimento de Software**

Este projeto, tal como em tantos outros projetos *open source*, baseia-se no **método ágil**. Contrariamente aos métodos preditivos, que procuram um planeamento detalhado do projeto, este método destaca-se pela rápida capacidade de adaptação a mudanças que vão surgindo no decorrer do desenvolvimento do projeto.

Deste modo, este método valoriza essencialmente a:
    
        - funcionalidade do software;
        - colaboração e satisfação do cliente;
        - capacidade de resposta a mudanças.

Como consequência desta volatilidade, é frequente lançarem-se novas funcionalidades no espaço de semanas, o que é vantajoso, pois transmite segurança ao cliente e denota um claro empenho por parte dos *developers*. 


## **Opiniões, Críticas e Alternativas**

### **Método Ágil**

Como alternativa a este método ágil, temos, por exemplo, o **modelo em cascata**. Este modelo é preditivo e sequencial e baseia-se na divisão do desenvolvimento do projeto em várias fases, em que cada fase depende da terminação da anterior.
Contudo, a este métodos estão associadas várias desvantagens: 

        - o tempo dispendido no desenvolvimento do projeto; 
        - a dificuldade em corresponder às mudanças que possam surgir;
        - a difícil colaboração por parte de contribuidores externos, essencial num projeto "open source".

Apesar da utilização do método ágil em *open source* ser vantajosa relativamente à utilização dos restantes métodos, este falha pela falta de documentação produzida.

### **Projeto *Seafile*** 
Em relação ao projeto escolhido, deparámo-nos com algumas dificuldades, nomeadamente:

        - fazer build ao projeto;
        - vasto número de repositórios associados;

