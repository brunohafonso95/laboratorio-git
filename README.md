# Introdução 
---
Framework java criado para facilitar o desenvolvimento de testes automatizados, bem como aumentar a produtividade e a padronização do desenvolvimento de rotinas de testes automatizados.

## Comandos Básicos (Web)
---
Classe responsável por por conter comandos que executam interações em páginas web. Os métodos contidos na classe são todos públicos e para utiliza-los, não é necessário passar o WebDriver como parametro.

Possui as seguintes propriedades: 

<code>**protected WebDriver**</code> driver

<code>**protected Actions**</code> action

<code>**protected WebDriverWait**</code> wait

E comporta os seguintes métodos:

### ComandosBasicos
---
Método construtor da classe que recebe o **WebDriver** como parâmetro.

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
```

### mudarAba
---
Método resposanvel por mudar a aba atual do navegador recebe um <code>**int**</code> como parâmetro, as abas são lidas em um array dessa forma, são zero indexadas, ou seja, os números passados vão de 0 à quantidade de abas abertas no momento menos 1.

> <span style="color: blue;">**Parâmetro**</span>: <code>**int**</code> indiceAba

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.mudarAba(0);
```

No exemplo acima mudamos navegamos para a primeira aba do navegador.

Caso seja informado o indice uma aba inexistente como parâmetro será lançada a seguinte <code>**Exception**</code>:

> <span style="color: red;">**Exception**</span>: Este Indice de Aba não existe! Use um valor Valido!

Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>


### trocarJanela
---
Método responsável trocar a janela ativa do navegador que recebe um <code>**int**</code> como parâmetro, as janelas são lidas em um array dessa forma, são zero indexadas, ou seja, os números passados vão de 0 à quantidade de abas abertas no momento menos 1.

> <span style="color: blue;">**Parâmetro**</span>: <code>**int**</code> indiceJanela

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.trocarJanela(0);
```

No exemplo acima mudamos navegamos para a primeira janela ativa.

Caso seja informado o indice uma janela inexistente como parâmetro será lançada a seguinte <code>**Exception**</code>:

> <span style="color: red;">**Exception**</span>: Este Indice de janela não existe! Use um valor Valido!

Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>

### borda
---
Método responsável por localizar um elemento no navegador e destacar o mesmo com um borda vermelha para exibir qual fluxo ou ação está sendo realizado, recebe um <code>**WebElement**</code> como parâmetro.

> <span style="color: blue;">**Parâmetro**</span>: <code>**WebElement**</code> elemento

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
WebElement menuLink = comBasico.findElement(By.id("menu-link"));
comBasico.borda(menuLink);
```

Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>

### encontra
---
Método responsável por encontrar um elemento no navegador,
o método recebe uma <code>**String**</code> como parâmetro e busca o elementro através dos seguintes seletores <code>**id**</code>, <code>**name**</code>, <code>**tagName**</code>, <code>**cssSelector**</code>, <code>**linkText**</code>, <code>**partialLinkText**</code>, <code>**xpath**</code>.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
WebElement menuLink = comBasico.encontra("menu-link");
```

Caso nenhum elemento seja encontrado através da <code>**String**</code> passada como parâmetro o método retorna a seguinte <code>**Exception**</code>

> <span style="color: red;">**Exception**</span>: Nenhum elemento foi identificado!

Caso não ocorra nenhum erro retorna um <code>**WebElement**</code>

> <span style="color: green;">**Return**</span>: <code>**WebElement**</code>

### elementoExiste
---
Método responsável por validar se um elemento existe no *DOM* (Document Object Model), recebe uma <code>**String**</code> como parâmetro que é seletor do elemento.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.elementoExiste("menu-link");
```

Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>


### elementoEstaVisivel
---
Método responsável por validar se um elemento está visível, recebe uma <code>**String**</code> como parâmetro.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.elementoEstaVisivel("menu-link");
```
Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>


### elementoEstaHabilitado
---
Método responsável por validar se um elemento está habilitado, recebe uma <code>**String**</code> como parâmetro.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.elementoEstaHabilitado("menu-link");
```
Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>


### esperarElemento
---
Método responsável por aguardar de forma explicita até que um elemento esteja visível, tem duas forma de implementação aceitando sobrecarga de método, a primeira assinatura recebe apenas uma <code>**String**</code> com o seletor do elemento, a segunda implementação recebe 2 parâmetros, uma <code>**String**</code> e um <code>**int**</code>.

Parametros da primeira implementação:
> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

Ex primeira implementação:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.esperarElemento("menu-link");
```

Parametros da segunda implementação:
> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento
> <span style="color: blue;">**Parâmetro**</span>: <code>**int**</code> tempo

Ex segunda implementação:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.esperarElemento("menu-link", 10);
```
Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>


### escrever
---
Método responsável por selecionar um elemento do tipo input e inserir um determinado texto nele, tem duas forma de implementação aceitando sobrecarga de método, a primeira assinatura recebe uma <code>**String**</code> com o seletor do elemento e uma <code>**String**</code> com o texto a ser inserido no input, a segunda implementação recebe 2 parâmetros, um um <code>**WebElement**</code> e uma <code>**String**</code> com o texto que será inserido no input.

Parametros da primeira implementação:
> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> texto

Ex primeira implementação:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.escrever("input-exemplo", "texto de exemplo");
```

Parametros da segunda implementação:
> <span style="color: blue;">**Parâmetro**</span>: <code>**WebElement**</code> seletorElemento

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> texto

Ex segunda implementação:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
WebElement elementoExemplo = comBasico.encontra("input-exemplo");
comBasico.escrever(elementoExemplo, "texto de exemplo");
```

Caso o elemento selecionado no método não exista ou não possa receber entrada de texto, ou seja, não seja do tipo input o método retornara a segunda <code>**Exception**</code>:

> <span style="color: red;">**Exception**</span>: Este elemento não tem entrada para texto!

Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>


### limpar
---
Método responsável por limpar os dados presentes em um determinado input, recebe uma <code>**String**</code> como parâmetro com o seletor do elemento que será limpo.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento`

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.limpar("input-exemplo");
```

Caso o elemento selecionado no método não exista ou não possa receber entrada de texto, ou seja, não seja do tipo input o método retornara a segunda <code>**Exception**</code>:

> <span style="color: red;">**Exception**</span>: Este elemento não tem entrada para texto!

Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>


### clicar
---
Método responsável por clicar em determinado elemento, localizando o mesmo através da <code>**String**</code> passada como parâmetro.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.clicar("elemento-exemplo");
```

Caso o elemento não seja localizado ou não seja clicável o método retornará a seguinte <code>**Exception**</code>:

> <span style="color: red;">**Exception**</span>: Este elemento não é clicavel!

Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>


### clicarElementos
---
Método responsável por clicar em um ou mais elementos de acordo com o parâmetro passado, recebe uma <code>**List**`<String>`</code> como parâmetro.

> <span style="color: blue;">**Parâmetro**</span>: <code>**List`<String>`**</code> seletorElementos

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
List<String> elementos = Arrays.asList("elemento1","elemento2");
comBasico.clicarElementos(elementos);
```

Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>


### verificarSeRadioEstaMarcado
---
Método responsável por verificar se um input do tipo radio está marcado, recebe uma <code>**String**</code> como parâmetro.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.verificarSeRadioEstaMarcado("input-radio-exemplo");
```

Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>


### obterTexto
---
Método responsável por capturar o texto de um determinado elemento,recebe uma <code>**String**</code> como parâmetro.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.obterTexto("elemento-exemplo");
```

Caso o elememento não seja encontrado ou não tenha a propriedade texto o método retornará a seguinte <code>**Exception**</code>:

> <span style="color: red;">**Exception**</span>: Este elemento não é clicavel!

Caso não ocorra nenhum erro o método retorna <code>**String**</code>.

> <span style="color: green;">**Return**</span>: <code>**String**</code>


### limparValorComBackspace
---
Método responsável por limpar uma determinado elemento do tipo input usando método de backspace do teclado, recebe uma <code>**String**</code> como parâmetro.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.limparValorComBackspace("input-exemplo");
```

Caso o elemento não seja encontrado ou não seja do tipo que aceite entrada de de dados (input) o método retornará a seguinte 
<code>**Exception**</code>:

> <span style="color: red;">**Exception**</span>: Este elemento não tem entrada para texto!

Método não tem retorno.

> <span style="color: green;">**Return**</span>: <code>**void**</code>


### pegarValorCss
---
Método responsável por pegar o valor de uma propriedade CSS de um determinado elemento, recebe 2 parâmetros do tipo <code>**String**</code><code></code>.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> propriedadeCSS

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.pegarValorCss("elemento-exemplo", "color");
```

Caso o elemento não seja encontrado ou o mesmo não possua a propriedade procurada o metodo retornará a seguinte <code>**Exception**</code>:

> <span style="color: red;">**Exception**</span>: Este elemento não tem um valor de CSS para a propriedade informada!

Caso não ocorra nenhum erro o método retornará uma <code>**String**</code>.

> <span style="color: green;">**Return**</span>: <code>**String**</code>


### obterAtributoElemento
---
Método responsável por pegar o valor de um determinado atributo de um determiando elemento, recebe 2 parâmetros do tipo <code>**String**</code>.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> atriutoElemento

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.obterAtributoElemento("elemento-exemplo", "value");
```

Caso não ocorra nenhum erro o método retornará uma <code>**String**</code>.

> <span style="color: green;">**Return**</span>: <code>**String**</code>


### verificarSeOcheckBoxEstaMarcado
---
Método resposável por verificar se um checkbock está marcado, recebe uma parâmetro do tipo <code>**String**</code>.

> <span style="color: blue;">**Parâmetro**</span>: <code>**String**</code> seletorElemento

Ex:

```java
ComandosBasicos comBasico = new ComandosBasicos(driver);
comBasico.verificarSeOcheckBoxEstaMarcado("checkbox-exemplo");
```

Retorna um <code>**boolean**</code>.

> <span style="color: green;">**Return**</span>: <code>**boolean**</code>
