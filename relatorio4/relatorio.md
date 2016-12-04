### **Engenharia de Software - Relatório 4**

<a name="index"/>
## **Índice**
1. [Introdução](#introduction)
2. [Software Testability and Reviews](#testability)
3. [Estatísticas e análise dos testes](#tests)
4. [Bugs e correção](#bug)
5. [Contribuição do Grupo](#contribuition)

---
<a name="introduction"/>
## **Introdução**

O objetivo deste relatório consiste em analisar os processos de verificação e validação seguidos no desenvolvimento da aplicação android do *Seafile*.
Deste modo, irá ser explorada a testabilidade do *software*, analisando os graus de controlabilidade, de observabilidade, de isolabilidade, de separação, de inteligibilidade e de heterogeneidade associados aos componentes do projeto.
Posto isto, serão apresentadas estatísticas relativas à verificação e validação do *software*, como por exemplo, o número de testes.
Por fim, será revelado o processo efetuado para a correção do *bug* escolhido pelo grupo.

---
<a name="testability"/>
## **Testabilidade do *Software***


---
<a name="tests"/>
## **Estatísticas e análise dos testes**

Uma plataforma utilizada pelo Seadroid é **Travis CI**.
Esta plataforma permite garantir que todos os commits e pull requests podem ser integrados no código atual sem o afetar através da realização de builds automáticas.

Ficheiro para a criação de builds automatizadas (*.travis.yml*):

> #http://docs.travis-ci.com/user/languages/android/
> language: android
> 
> sudo: false
> jdk: oraclejdk8
> android:
>   components:
>       - tools
>       - platform-tools
>       - build-tools-23.0.2
>       - android-23
>       - extra-android-support
>       - extra-android-m2repository
> 
> script:
>     - cp app/key.properties.example app/key.properties
>     - cp app/key.properties.example app/debugkey.properties
>     - keytool -genkey -v -keystore app/debug.keystore -alias AndroidDebugKey -keyalg RSA -keysize 2048 -validity 1 -storepass android -keypass android -dname "cn=TEST, ou=TEST, o=TEST, c=TE"
>     - ./gradlew clean assemble
> 
> 
> # reference https://docs.travis-ci.com/user/languages/android

Atualmente a versão atual do github encontra-se com a **build failing** (<https://travis-ci.org/haiwen/seadroid>).
O projeto tinha por vezes versões que não passavam na build mas eram corrigidas, voltando a passar. Nos últimos dois meses todas as integrações de código têm falhado e motivo não é conhecido por nós pois os comentários aos commits são inconclusivos.

---
<a name="bug"/>
## **Bugs e correção**


---
<a name="contribuition"/>
## **Contribuição do Grupo**

A contribuição de todos os elementos do grupo foi igual.
