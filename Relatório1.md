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

---

## **Processo de Desenvolvimento de Software**

O processo de desenvolvimento do Seafile baseia-se no **processo de desenvolvimento e entrega incremental** (incremental development and delivery). Este método caracteriza-se pelo desenvolvimento do produto em porções e na avaliação de cada parte antes de iniciar o desenvolvimento da próxima. Um bom exemplo desta prática é o lançamento mais recente da empresa, um novo cliente Desktop para o seu sitema de partilha de ficheiros e que se encontra em baixo descrito pelo fundador e CEO após o nosso contacto.

>*"Our approach can be described best as incremental development and delivery.*

>*Taking our new desktop client Seafile Drive client for example (https://blogs.seafile.com/2016/09/02/announcing-seafile-drive-client-a-new-way-to-map-seafile-storage-as-virtual-drive/), we spent 3 months to build a first testing version 0.1, and let the community test it. Then we fixes bugs according to feedbacks, and released a new version 0.2 for testing within one month."*

>*Daniel Pan*

A utilização deste processo possibilita:

- o desenvolvimento de partes(incrementos) direcionadas às necessidades de clientes específicos;
- uma avaliação realizada pelo utilizador;
- a aplicação do modelo cascata em cada iteração/desenvolvimento de uma nova parte.

<!--- Este projeto, tal como em tantos outros projetos *open source*, baseia-se no **método ágil**. Contrariamente aos métodos preditivos, que procuram um planeamento detalhado do projeto, este método destaca-se pela rápida capacidade de adaptação a mudanças que vão surgindo no decorrer do desenvolvimento do projeto.

Deste modo, este método valoriza essencialmente a:
    
        - funcionalidade do software;
        - colaboração e satisfação do cliente;
        - capacidade de resposta a mudanças.

Como consequência desta volatilidade, é frequente lançarem-se novas funcionalidades no espaço de semanas, o que é vantajoso, pois transmite segurança ao cliente e denota um claro empenho por parte dos *developers*.  --->

---

## **Opiniões, Críticas e Alternativas**

### **Processo de Desenvolvimento e Entrega Incremental**

Este processo apresenta vários pontos que favorecem a sua escolha para o uso num projeto deste tipo e dimensão. Apesar de ser um processo adaptativo permite incorporar um planeamento antes de se partir para a execução da parte seguinte. Além disso apresenta várias vantagens:
	
	- Apresenta um custo baixo de adaptação a novos requisitos e sugestões dos utilizadores;
	- As reações ao software são mais frequentes e mais precoces o que o previne de ser um fracasso;
	- Os requisitos mais morosos podem ficar pendentes para as partes a serem produzidas mais tarde sem afetar a entrega das restantes partes.

Contudo existem alguns aspetos que é preciso ter em conta ao utilizar este processo:

	- A estrutura global do sistema tende a degradar-se com todas as alterações efetuadas;
	- A reutilização do código pode ser comprometida visto que não é possível prever com precisão as alterações a efetuar nas partes seguintes;
	- O estabelecimento de um contrato inicial pode não ser possível visto que os requisitos vão incrementando a par com o software.

O último aspeto não afeta no entanto o projeto Seafile visto que provém de uma iniciativa de um grupo de estudantes e que não foi sujeita a qualquer tipo de investimento inicial externo.

### **Modelo de Boehm’s spiral**

Como alternativa, temos o **modelo de Boehm’s spiral**. Este modelo é iterativo, baseando-se em 4 fases ordenadas:
planeamento, análise de risco, engenharia e avaliação.
Com este método os desenvolvedores iriam tirar proveito de várias maneiras, tais como:
	
	-modelo muito vantajoso em relaçao a projetos de grande dimensao;
	-o software apresenta-se cedo;
	-elevada análise de risco.

Por outro lado, este projeto começou por um grupo de estudantes,e nesse aspeto este modelo tem desvantagens 
que poderiam levar a este modelo não ser escolhido tais como:

	-modelo de muito custo;
	-elevada quantidade de análise exige muitas especificações;
	-o sucesso depende muito da análise de risco.


<!--- ### **Método Ágil**

Como alternativa a este método ágil, temos, por exemplo, o **modelo em cascata**. Este modelo é preditivo e sequencial e baseia-se na divisão do desenvolvimento do projeto em várias fases, em que cada fase depende da terminação da anterior.
Contudo, a este métodos estão associadas várias desvantagens: 

        - o tempo dispendido no desenvolvimento do projeto; 
        - a dificuldade em corresponder às mudanças que possam surgir;
        - a difícil colaboração por parte de contribuidores externos, essencial num projeto "open source".

Apesar da utilização do método ágil em *open source* ser vantajosa relativamente à utilização dos restantes métodos, este falha pela falta de documentação produzida. --->

---

### **Projeto Seafile** 
Em relação ao projeto escolhido, deparámo-nos com algumas dificuldades, nomeadamente:

        - fazer build ao projeto, essencialmente nas secções mais relacionadas com a parte servidora;
        - vasto número de repositórios associados;

