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

```yaml
# http://docs.travis-ci.com/user/languages/android/
language: android

sudo: false
jdk: oraclejdk8
android:
  components:
      - tools
      - platform-tools
      - build-tools-23.0.2
      - android-23
      - extra-android-support
      - extra-android-m2repository
 
script:
    - cp app/key.properties.example app/key.properties
    - cp app/key.properties.example app/debugkey.properties
    - keytool -genkey -v -keystore app/debug.keystore -alias AndroidDebugKey -keyalg RSA -keysize 2048 -validity 1 -storepass android -keypass android -dname "cn=TEST, ou=TEST, o=TEST, c=TE"
    - ./gradlew clean assemble


# reference https://docs.travis-ci.com/user/languages/android
```

Atualmente a versão atual do github encontra-se com a **build failing** (<https://travis-ci.org/haiwen/seadroid>).
O projeto tinha por vezes versões que não passavam na build mas eram corrigidas, voltando a passar. Nos últimos dois meses todas as integrações de código têm falhado e motivo não é conhecido por nós pois os comentários aos commits são inconclusivos.

---
<a name="bug"/>
## **Bugs e correção**

### **Bug #1**

O primeiro bug detetado fazia com que a aplicação quando estava no ecrã das contas e não havia nenhuma conta atual permitia carregar no botão *back* que provocava a destruição da *activity* atual, a criação da *activity* que mostra os ficheiros de uma conta seguida da sua destruição e da criação de uma nova *activity* de contas.

A correção do bug passou por esconder o botão *back*  enquanto não houver qualquer conta ou não houver uma conta atual selecionada

**Commits associados à correção:**

https://github.com/haiwen/seadroid/pull/601/commits/c221487d5964ba2a289d8bb65aafb1328e48ee35
https://github.com/haiwen/seadroid/pull/601/commits/410f7bdf8087ab4fbee6f50b98931d8365663b6c

**Imagens da solução corrigida:**

<img src="resources/bug1_1.png" width="49%" alt="Bug 1_1"/>
<img src="resources/bug1_2.png" width="49%" alt="Bug 1_2"/>

--

### **Bug #2**

O segundo bug detetado foi encontrado no ecrã das definições e fazia com que o botão *switch* do padrão de desbloqueio ficasse sempre ativo ainda que não houvesse nenhum padrão definido. O seguinte acontecia quando se cancelava ou se retrocedia a partir da página para definição de um novo padrão de desbloqueio.

O bug foi corrigido fazendo a interpretação do valor de retorno da página acima referida, e implementar valores de retorno diferentes na página.

**Commits associados à correção:**

https://github.com/haiwen/seadroid/pull/601/commits/4a9ec855dec5897d0c2149c4540e0d7b3ce5278d

**Imagens da solução corrigida:**

<img src="resources/bug2_1.png" width="49%" alt="Bug 2_1"/>
<img src="resources/bug2_2.png" width="49%" alt="Bug 2_2"/>

--

### **Bug #3**

O terceiro bug detetado permitia repetir a introdução do padrão de desbloqueio mais de 5 vezes sem ter de esperar os 30 segundos exigidos.

A correção do bug passou por esconder o botão *back* que permitia fazer *reset* no timer de 30 segundos.

**Commits associados à correção:**

https://github.com/haiwen/seadroid/pull/601/commits/93528cdbbdad95713ad63b89eeae2973373fa65f

**Imagens da solução corrigida:**

<img src="resources/bug3_1.png" width="49%" alt="Bug 3_1"/>

--

O estado atual do **PULL REQUEST** pode ser consultado em https://github.com/haiwen/seadroid/pull/601 .

---
<a name="contribuition"/>
## **Contribuição do Grupo**

A contribuição de todos os elementos do grupo foi igual.
