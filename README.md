# ProtoLib.js e Util.js: Uma Visão Abrangente das Bibliotecas

Este documento detalha as funcionalidades e o uso das bibliotecas `ProtoLib.js` e `Util.js`, bem como seus módulos de suporte e padrões de projeto.

## Sumário

  - [Util - Biblioteca de Utilitários](https://www.google.com/search?q=%23util---biblioteca-de-utilit%C3%A1rios)
      - [Manipulação e Definição de Propriedades](https://www.google.com/search?q=%23manipula%C3%A7%C3%A3o-e-defini%C3%A7%C3%A3o-de-propriedades)
      - [Reflexão e Comparação](https://www.google.com/search?q=%23reflex%C3%A3o-e-compara%C3%A7%C3%A3o)
      - [Clonagem e Extensão](https://www.google.com/search?q=%23clonagem-e-extens%C3%A3o)
      - [Algoritmos e Estruturas de Dados](https://www.google.com/search?q=%23algoritmos-e-estruturas-de-dados)
  - [ProtoLib.js - Programação Orientada a Objetos em JavaScript](https://www.google.com/search?q=%23protolibjs---programa%C3%A7%C3%A3o-orientada-a-objetos-em-javascript)
      - [Conceitos Principais](https://www.google.com/search?q=%23conceitos-principais)
          - [Módulos](https://www.google.com/search?q=%23m%C3%B3dulos)
          - [Tipos](https://www.google.com/search?q=%23tipos)
          - [Objeto Global](https://www.google.com/search?q=%23objeto-global)
          - [Encapsulamento](https://www.google.com/search?q=%23encapsulamento)
      - [Uso Básico](https://www.google.com/search?q=%23uso-b%C3%A1sico)
          - [1. Criando um Módulo](https://www.google.com/search?q=%231-criando-um-m%C3%B3dulo)
          - [2. Definindo Classes e Interfaces](https://www.google.com/search?q=%232-definindo-classes-e-interfaces)
          - [3. Herança](https://www.google.com/search?q=%233-heran%C3%A7a)
          - [4. Instanciando e Usando](https://www.google.com/search?q=%234-instanciando-e-usando)
      - [Exemplo Prático: Gerenciador de Documentos](https://www.google.com/search?q=%23exemplo-pr%C3%A1tico-gerenciador-de-documentos)
  - [Documentação dos Módulos de Suporte: Estendendo o ProtoLib](https://www.google.com/search?q=%23documenta%C3%A7%C3%A3o-dos-m%C3%B3dulos-de-suporte-estendendo-o-protolib)
      - [1. DataClass: Estruturas de Dados Declarativas e Seguras](https://www.google.com/search?q=%231-dataclass-estruturas-de-dados-declarativas-e-seguras)
          - [Funcionalidades Principais](https://www.google.com/search?q=%23funcionalidades-principais)
          - [Exemplo de Uso: VersionData](https://www.google.com/search?q=%23exemplo-de-uso-versiondata)
      - [2. ProtoProxy: Interceptação e Extensão de Funcionalidades](https://www.google.com/search?q=%232-protoproxy-intercepta%C3%A7%C3%A3o-e-extens%C3%A3o-de-funcionalidades)
          - [Funcionalidades Principais](https://www.google.com/search?q=%23funcionalidades-principais-1)
          - [Exemplo de Uso: RelationalManager](https://www.google.com/search?q=%23exemplo-de-uso-relationalmanager)
      - [Extensão do ProtoLib com Módulos de Suporte](https://www.google.com/search?q=%23extens%C3%A3o-do-protolib-com-m%C3%B3dulos-de-suporte)
          - [Módulo Generic](https://www.google.com/search?q=%23m%C3%B3dulo-generic)
          - [Módulo Ref](https://www.google.com/search?q=%23m%C3%B3dulo-ref)
          - [Módulo Task](https://www.google.com/search?q=%23m%C3%B3dulo-task)
          - [Módulo ObjectIterator](https://www.google.com/search?q=%23m%C3%B3dulo-objectiterator)
          - [Módulo Box](https://www.google.com/search?q=%23m%C3%B3dulo-box)
  - [Resumo dos Módulos Patterns e DCI](https://www.google.com/search?q=%23resumo-dos-m%C3%B3dulos-patterns-e-dci)
      - [Processamento de Dados com Algebraic Data Types (ADTs)](https://www.google.com/search?q=%23processamento-de-dados-com-algebraic-data-types-adts)
          - [Product Types: Record e Tuple](https://www.google.com/search?q=%23product-types-record-e-tuple)
          - [Sum Types: Enum](https://www.google.com/search?q=%23sum-types-enum)
      - [Criação de Tipos Específicos com ADTs](https://www.google.com/search?q=%23cria%C3%A7%C3%A3o-de-tipos-espec%C3%ADficos-com-adts)
      - [Troca de Mensagens: Métodos toString e parse](https://www.google.com/search?q=%23troca-de-mensagens-m%C3%A9todos-tostring-e-parse)
          - [toString() para Serialização](https://www.google.com/search?q=%23tostring-para-serializa%C3%A7%C3%A3o)
          - [parse() para Desserialização](https://www.google.com/search?q=%23parse-para-desserializa%C3%A7%C3%A3o)
      - [Algebraic Data Types e o Padrão Interpreter](https://www.google.com/search?q=%23algebraic-data-types-e-o-padr%C3%A3o-interpreter)

-----

## Util - Biblioteca de Utilitários

A biblioteca `Util` oferece um conjunto de ferramentas para manipulação de baixo nível de objetos, iteração e algoritmos.

### Manipulação e Definição de Propriedades

  * `def(obj, propName, value)`: Um atalho para definir uma propriedade simples em um objeto.
  * `define(obj, propName, objDef)`: Um wrapper para `Object.defineProperty`, permitindo controle total sobre os atributos de uma propriedade.
  * `final(obj, propName, value)`: Define uma propriedade de valor enumerável e não regravável.
  * `var(obj, propName, value)`: Define uma propriedade de valor que é gravável e enumerável.
  * `lazy(obj, propName, getFn)`: Define uma propriedade lazy. O valor só é calculado pela função `getFn` na primeira vez que a propriedade é acessada e, em seguida, é substituído pelo resultado.
  * `pseudo(obj, propName, objFn)`: Define uma propriedade com getters e setters personalizados.

### Reflexão e Comparação

  * `hasOwn(Type, propName)`: Verifica se um objeto possui uma propriedade diretamente (não herdada).
  * `isEqual(obj1, obj2)`: Realiza uma comparação profunda (deep equal) bidirecional entre dois objetos.
  * `isSameOf(obj, Type, checker)`: Verifica se um objeto corresponde à "forma" ou estrutura de um `Type`, opcionalmente usando um `checker` customizado.
  * `typeof(Class, Interface)` e `instanceof(Class, Interface)`: Funções de verificação de tipo que lidam com primitivos e objetos.
  * `checkPattern(value, pattern, checker)`: Verifica se um valor corresponde a um padrão, que pode ser um valor, um tipo, uma estrutura ou uma função de validação.

### Clonagem e Extensão

  * `copyDiscriptors(Type, newType)`: Copia os descritores de propriedade de um objeto para outro.
  * `extend(Type, extention)`: Cria um novo objeto que herda de `Type` e copia as propriedades de `extention` para ele.

### Algoritmos e Estruturas de Dados

  * `sort(arr, getNodeId)`: Implementa um algoritmo de ordenação (merge sort). Ele opera em uma cópia da matriz e usa um objeto `FatPtr` para gerenciar sub-arrays e comparações.
  * `searchNode(arr, id, getNodeId)`: Realiza uma busca em uma estrutura semelhante a uma árvore (heap) dentro de um array. As funções `getLayer`, `getColumn`, `leftIndex`, `rightIndex` e `startIndex` são auxiliares para navegar nesta estrutura de árvore implícita.

## ProtoLib.js - Programação Orientada a Objetos em JavaScript

`ProtoLib` é uma biblioteca para programação orientada a objetos em JavaScript que utiliza o sistema de protótipos de forma estruturada. Com ela, você pode organizar seu código em módulos, definir classes, interfaces e classes abstratas.

### Conceitos Principais

A biblioteca introduz vários conceitos para estruturar o código de forma organizada.

#### Módulos

Todo o código deve ser encapsulado dentro de um módulo, criado com `Proto.module('NomeDoModulo', ...)`. Isso evita a poluição do escopo global e ajuda na organização e no carregamento de dependências. É verificado se existem dependências circulares entre módulos, e quando detectadas, um erro é lançado.

#### Tipos

A `ProtoLib` permite a criação de diferentes "tipos" de objetos:

  * **`Proto.class`**: Para classes concretas que podem ser instanciadas.
  * **`Proto.interface`**: Para definir contratos que as classes devem seguir.
  * **`Proto.abstract`**: Para classes que servem como modelo para outras, mas não podem ser instanciadas diretamente.

#### Objeto Global

Ao definir um tipo, você recebe um objeto global. É através dele que você acessa as funcionalidades da biblioteca, como herança e encapsulamento.

#### Encapsulamento

A biblioteca oferece um mecanismo para dados privados através de `global.private(this)`. Ele retorna um objeto que só pode ser acessado de dentro da instância da classe, garantindo que os dados internos fiquem protegidos.

### Uso Básico

Veja como usar as principais funcionalidades da biblioteca.

#### 1\. Criando um Módulo

Sempre comece definindo um módulo. Todas as suas classes e interfaces devem estar dentro dele.

```javascript
Proto.module('MeuModulo', function (imports) {
  // Seu código vai aqui

  return {
    // O que você quer exportar do módulo
  };
});
```

#### 2\. Definindo Classes e Interfaces

Dentro do módulo, você pode definir seus tipos.

**Interface**: Define um contrato. Propriedades ou métodos com valor `undefined` devem ser implementados pela classe.

```javascript
var MinhaInterface = Proto.interface('MinhaInterface', function (global) {
  return {
    metodoObrigatorio: undefined, // Deve ser implementado
    propriedadeOpcional: 'valorPadrao'
  };
});
```

**Classe**: A implementação concreta de um tipo. Use o método `new` como construtor.

```javascript
var MinhaClasse = Proto.class('MinhaClasse', function (global) {
  // Implementa uma interface
  global.implements([MinhaInterface]);

  return {
    // Construtor
    new: function (valorInicial) {
      const _this = global.private(this); // Acessa o escopo privado
      _this.valor = valorInicial;
    },

    metodoObrigatorio: function () {
      const _this = global.private(this); // Acessa o escopo privado
      return `O valor é: ${_this.valor}`;
    }
  };
});
```

#### 3\. Herança

Use `global.extends()` para herdar de uma classe abstrata. `ProtoLib` aceita apenas que uma classe herde de uma classe base abstrata, e não estende objeto simples, uma interface ou uma classe JavaScript padrão. Se uma classe que estende outra que implementa uma interface, ela também implementa essa interface. Erros serão lançados ao definir uma classe com um nome já em uso no mesmo módulo, no uso de nomes de classe inválidos, como `undefined`, uma string vazia, que não inicie por uma letra ou que contenha outros caracteres além de letras ou números.

```javascript
// Classe base (abstrata)
var ClasseBase = Proto.abstract('ClasseBase', function() {
    return {
        new: function() {
            console.log('Construtor da classe base chamado!');
        }
    };
});

// Classe derivada
var ClasseDerivada = Proto.class('ClasseDerivada', function(global) {
    global.extends(ClasseBase); // Herda de ClasseBase

    return {
        new: function() {
            // É obrigatório chamar o construtor da superclasse
            global.super();
            console.log('Construtor da classe derivada chamado!');
        }
    };
});
```

**Importante**: Em uma classe derivada, você deve chamar `global.super()` no construtor antes de tentar acessar o escopo privado com `global.private(this)`. As classes podem ter métodos manualmente estendidos (ex.: `Util.extend`). As instâncias criadas desta forma são corretamente identificadas como sendo da mesma classe e seus membros privados podem ser acessados corretamente.

#### 4\. Instanciando e Usando

Para usar suas classes, execute o módulo e acesse o que foi exportado.

```javascript
// Fora da definição do módulo
Proto.executeModule(function (imports) {
  var MinhaClasse = imports.MeuModulo.MinhaClasse;
  var instancia = MinhaClasse.new('Teste');

  console.log(instancia.metodoObrigatorio()); // Saída: "O valor é: Teste"
});
```

### Exemplo Prático: Gerenciador de Documentos

O código fornecido é um excelente exemplo de como usar a biblioteca para criar um sistema flexível de gerenciamento de arquivos.

```javascript
var ObjFile = Proto.interface('ObjFile', function () {
   return {
     getDataObj: Util.noProp,
     getCode: Util.noAction,
     setDataObj: Util.this,
     setDataText: Util.this,
     getDataText: Util.noText,
     getName: Util.noAction,
     getId: Util.noAction,
     hasData: Util.false
   }
 })
 var ObjFileNull = Proto.class('ObjFileNull', function (global) {
   global.implements([ObjFile])
 })
 var SpreadsheetObjFile = Proto.class('SpreadsheetObjFile', function (global) {
   global.implements([ObjFile])
   return {
     new (document) {
       Util.var(this, 'document', document)
       Util.var(this, 'docObj', {})
     },
     async getDataObj () {
       return JSON.parse(await this.getDataText() || '{}')
     },
     async getDataText () {
       return this.document.getRange(1,1).getNote()
     },
     async setDataObj (obj) {
       return this.setDataText(JSON.stringify(obj) || {})
     },
     async setDataText (text) {
       return this.document.getRange(1,1).setNote(text)
     },
     getName () {
       return this.document.getName()
     },
     getId () {
       return this.getName()//this.document.getId()
     },
     hasData () {
       return this.document ? true : undefined
     }
   }
 })
 var DocManager = Proto.interface('DocManager', function () {
   return {
     ObjFileNull: ObjFileNull.new(),
     getObjFile: undefined,
     removeFile: undefined,
     createFile: undefined
   }
 })
 var SpreadsheetDocManager = Proto.class('SpreadsheetDocManager', function (global) {
   global.implements([DocManager])
   function getManager (instance) {
     const _this = global.private(instance)
     if (!Util.hasOwn(_this, 'manager')) {
       _this.manager = Task.resolve(SpreadsheetApp.openById(_this.id))
     }
     return _this.manager
   }
   return {
     new: function newFn (id) {
       const _this = global.private(this)
       _this.id = id
     },
     getObjFile: function getFile (id) {
       if (id) {
         return getManager(this)
         .then(function (manager) {
           return manager.getSheetByName(id)
         })
         .then(function (document) {
           return SpreadsheetObjFile.new(document)
         })
       }
       return Task.resolve(this.ObjFileNull)
     },
     createFile: function createFile (name) {
       return getManager(this)
       .then(function (manager) {
         return manager.insertSheet().setName(name)
       })
       .then(function (document) {
         return SpreadsheetObjFile.new(document)
       })
     },
     removeFile: function removeFile (id) {
       alert("Please, remove the file: " + id)
     }
   }
 })
```

**Análise do Exemplo:**

  * **`ObjFile` (Interface)**: Define o contrato para qualquer objeto que se comporte como um arquivo. Ele especifica métodos como `getDataObj`, `setDataObj`, `getName`, etc. Isso garante que qualquer classe que o implemente terá uma estrutura consistente.
  * **`SpreadsheetObjFile` (Classe)**: É a implementação concreta de `ObjFile`. Ela gerencia um arquivo que está em uma planilha do Google. Note como ela implementa todos os métodos definidos na interface `ObjFile`.
  * **`DocManager` (Interface)**: Define o contrato para um gerenciador de documentos, que deve ser capaz de `getObjFile`, `createFile` e `removeFile`.
  * **`SpreadsheetDocManager` (Classe)**: É a implementação concreta de `DocManager`, projetada para trabalhar com o Google Sheets. Ela usa `global.private(this)` em seu construtor (`new`) para armazenar o `id` da planilha de forma privada e segura. A função interna `getManager` também utiliza `global.private` para inicializar e armazenar de forma "preguiçosa" (lazy) o objeto principal do gerenciador, garantindo que ele seja criado apenas uma vez.

## Documentação dos Módulos de Suporte: Estendendo o ProtoLib

A biblioteca `ProtoLib` oferece uma base robusta para a programação orientada a objetos em JavaScript. Os módulos presentes em `SuportTypes.js` estendem essas funcionalidades, introduzindo padrões de projeto avançados como classes de dados imutáveis e proxies, que permitem um desenvolvimento mais declarativo, seguro e flexível.

### 1\. DataClass: Estruturas de Dados Declarativas e Seguras

O módulo `DataClass` é uma ferramenta para a criação de classes focadas em armazenar dados. Ele automatiza a definição de propriedades, construtores e validações de tipo. Para toda classe criada é uma instância vazia que fica disponível como campo estático "void" (Class.void). Toda classe criada também herda um método `isEmpty()`, que verifica se ele uma instância vazia. A imutabilidade sempre será parcial, até o ponto que o mecanismo de prototipação do JavaScript permite. Não é possível impedir que um objeto que represente uma classe seja estendido manualmente através do método `Object.create`. Ele não poderá executar os métodos que utilizem dados privados através da chamada `global.private(this)`, mas ele será reconhecido nas checagem de tipo como em `Util.protototypeof`.

#### Funcionalidades Principais:

  * **Definição Declarativa**: `DataClass` permite que você declare a estrutura da classe por meio de um array de `[nome, tipo]`.
  * **Validação de Tipos**: É possível associar tipos (como `String`, `Number`, `Record`) a cada propriedade. O `DataClass` garante que apenas valores do tipo correto sejam atribuídos, lançando um erro em caso de incompatibilidade.
  * **Propriedades Constantes**: `DataClass.const()` define propriedades que, uma vez inicializadas, não podem ser alteradas.
  * **Restrições (Guards)**: Permite adicionar lógicas de validação e especificar um erro que será lançado se houver alguma falha.

#### Exemplo de Uso: VersionData

```javascript
VersionData: DataClass.create('VersionData', [
    ['tableName', DataClass.const(String)],
    ['id', DataClass.const(String)],
    ['author', DataClass.const(String)],
    ['values', DataClass.const(Record)],
    ['time', DataClass.const(Number)],
    ['oldVersion', DataClass.const(Box.of(Number).guard(n => n > -2, 'Version must not be less than -1.'))]
])
```

### 2\. ProtoProxy: Interceptação e Extensão de Funcionalidades

O `ProtoProxy` implementa o padrão de projeto Proxy, permitindo que uma classe (o proxy) atue como uma interface para outra (o alvo), interceptando e modificando suas operações.

#### Funcionalidades Principais:

  * **Delegação Automática**: O proxy encaminha automaticamente chamadas de métodos para a classe alvo, a menos que um método seja sobrescrito.
  * **Interceptação de Métodos**: Você pode fornecer uma nova implementação para qualquer método da classe alvo. Isso permite adicionar lógica antes, depois ou em vez da execução original.
  * **Composição de Comportamentos**: Facilita a adição de responsabilidades a uma classe, como logging, cache, controle de acesso ou, como no exemplo, gerenciamento de relações.

#### Exemplo de Uso: RelationalManager

O `RelationalManager` em `Exemplos.js` é um proxy para o `TableManager`. Enquanto o `TableManager` cuida das operações básicas de CRUD (criar, ler, atualizar, deletar) em uma tabela, o `RelationalManager` estende esse comportamento para gerenciar as relações entre tabelas.

```javascript
var RelationalManager = ProtoProxy.create('RelationalManager', Manager, function (global) {
  global.extends(Manager)
  global.implements([ManagerInterface])

  // ... lógica de gerenciamento de relações ...

  return {
    new (treeManager, target) {
      global.super(treeManager)
      const _this = global.private(this)
      _this.treeManager = treeManager
      _this.target = target || TableManager.new(treeManager) // O alvo é uma instância de TableManager
    },
    async setData (values, oldId) {
      var _this = global.private(this)
      var treeManager = _this.treeManager
      // Lógica adicional antes de chamar o setData original
      var fullValues = await setRelatedIds(treeManager, values)
      await _this.target.setData(fullValues, oldId) // Delega a chamada para o TableManager
    },
    async remove (id, indexId) {
      var _this = global.private(this)
      var treeManager = _this.treeManager
      // Delega a chamada para o TableManager primeiro
      var node = await _this.target.remove(id, indexId)
      // Lógica adicional após a execução do remove original
      await removeRelatedIds(treeManager, node.content)
      return node
    }
    // Outros métodos são delegados automaticamente
  }
})
```

**Análise do Exemplo:**

  * `ProtoProxy.create('RelationalManager', Manager, ...)` define `RelationalManager` como um proxy que estende a funcionalidade de um `Manager`.
  * No construtor (`new`), ele recebe ou cria uma instância de `TableManager`, que se torna seu `target`.
  * **Interceptação de `setData`**: Antes de salvar os dados, o `RelationalManager` primeiro executa a lógica `setRelatedIds` para lidar com as chaves estrangeiras e, só então, chama o `setData` original do `TableManager` (`_this.target.setData`).
  * **Interceptação de `remove`**: Ele primeiro chama o `remove` do `TableManager` e, com o resultado dessa operação, executa a lógica `removeRelatedIds` para limpar as referências na tabela relacionada.

Dessa forma, o `ProtoProxy` permite que a responsabilidade de gerenciar relações seja separada da responsabilidade de manipular dados da tabela, resultando em um código mais coeso e de fácil manutenção. O `TableManager` permanece agnóstico em relação às relações, e o `RelationalManager` foca exclusivamente em orquestrar essas conexões.

### Extensão do ProtoLib com Módulos de Suporte

A `ProtoLib` oferece diversos módulos de suporte para manipulação de tipos genéricos, referências, operações assíncronas, iteração de objetos e encapsulamento de valores. Estes módulos servem como pilares para o funcionamento de outros componentes, como o módulo `DataProxy`.

#### Módulo Generic

O módulo `Generic` provê um conjunto de funcionalidades para trabalhar com tipos genéricos e garantir a segurança de tipos em tempo de execução.

**Principais funcionalidades:**

  * **`GenericType`**: Define um tipo genérico padrão.
  * **`of(Type, args)`**: Cria uma instância de um tipo genérico, garantindo que o tipo fornecido esteja em conformidade com o `GenericType` da instância.
  * **`getType()`**: Retorna o tipo genérico associado a uma instância.
  * **`assert(obj, Type)`**: Verifica se um objeto é do tipo esperado e lança um `TypeError` caso contrário.
  * **`method(instance, GenericType, fn)`**: Permite a criação de métodos genéricos que podem ser aplicados a diferentes tipos.
  * **`typeof(Class, Type)`**: Estende a verificação de tipo do `ProtoLib` para incluir tipos genéricos.

#### Módulo Ref

O módulo `Ref` introduz o conceito de referências abstratas, genéricas e de tipo, permitindo a criação de ponteiros para tipos ou valores que podem ser resolvidos em tempo de execução. Isso é útil para lidar com dependências circulares ou para adiar a resolução de tipos.

**Principais funcionalidades:**

  * **`Ref`**: Uma classe abstrata base para todas as referências.
  * **`GenericRef`**: Uma referência que resolve para um tipo genérico.
  * **`TypeRef`**: Uma referência que resolve para um tipo específico.
  * **`get(Type, GenericType)`**: Método para obter o valor ou tipo ao qual a referência aponta.

#### Módulo Task

O módulo `Task` oferece um conjunto de ferramentas para lidar com operações assíncronas de forma estruturada, similar ao conceito de `Promises`. Ele facilita a composição e o gerenciamento de tarefas que não são executadas imediatamente, melhorando a legibilidade e a manutenção do código assíncrono.

**Principais funcionalidades:**

  * **`new(callback)`**: Construtor para criar uma nova tarefa.
  * **`fulfill(result)` / `reject(result)`**: Métodos para resolver ou rejeitar uma tarefa.
  * **`then(callback, rejectCallback)`**: Encadeia callbacks para serem executados quando a tarefa for resolvida ou rejeitada.
  * **`resolve(obj)` / `reject(obj)`**: Cria tarefas resolvidas ou rejeitadas a partir de um valor ou promessa.
  * **`all(tasks)`**: Executa várias tarefas em paralelo e retorna uma única tarefa que é resolvida quando todas as tarefas forem resolvidas.
  * **`race(tasks)`**: Retorna uma tarefa que é resolvida ou rejeitada assim que uma das tarefas fornecidas for resolvida ou rejeitada.
  * **`isPending()` / `isResolved()` / `isRejected()`**: Métodos para verificar o estado da tarefa.

#### Módulo ObjectIterator

O módulo `ObjectIterator` fornece interfaces e classes para iterar sobre objetos e coleções de maneira padronizada, oferecendo métodos semelhantes aos encontrados em arrays para manipulação de dados.

**Principais funcionalidades:**

  * **`Iterable`**: Interface que define o contrato para objetos iteráveis.
  * **`Iterator`**: Classe que implementa a lógica de iteração.
  * **`ObjectMethods`**: Interface com métodos utilitários para objetos, como:
      * `map(callback, objThis)`: Transforma cada item de um objeto.
      * `forEach(callback, thisObj)`: Itera sobre cada item de um objeto.
      * `filter(callback, thisObj)`: Retorna um novo objeto contendo apenas os itens que satisfazem uma condição.
      * `some(callback, thisObj)`: Verifica se pelo menos um item satisfaz uma condição.
      * `every(callback, thisObj)`: Verifica se todos os itens satisfazem uma condição.
      * `asyncMap` / `asyncForEach`: Versões assíncronas dos métodos `map` e `forEach`, utilizando o módulo `Task`.
  * **`Break`**: Classe utilitária para interromper iterações.

#### Módulo Box

O módulo `Box` oferece um mecanismo para aplicação de validações de valores em tempo de execução.

**Principais funcionalidades:**

  * **`TypeBox`**: Uma interface para a criação de "caixas de tipo" genéricas.
  * **`Box`**: Uma caixa que verifica se um valor é do tipo contido.
  * **`InBox`**: Uma caixa que verifica se o tipo contido é do tipo do valor.
  * **`JustBox`**: Uma caixa que verifica a igualdade de tipo e tipo genérico.
  * **`TypeContainer`**: Interface para contêineres de tipos, como objetos ou arrays.
  * **`BoxContainer` / `InBoxContainer` / `JustBoxContainer`**: Contêineres que aplicam as regras de `Box`, `InBox` e `JustBox` aos seus elementos.
  * **`with(value)`**: Define um valor padrão para a caixa.
  * **`guard(checkGuard, guardMessage)`**: Adiciona uma função de guarda para validação.

## Resumo dos Módulos Patterns e DCI

### Processamento de Dados com Algebraic Data Types (ADTs)

ADTs são compostos por Product Types (como `Record` e `Tuple`) e Sum Types (como `Enum`), oferecendo uma maneira estruturada de definir e manipular dados complexos. `Enum`, `Record` e `Tuple` oferecem imutabilidade desde que todos os seus elementos internos também sejam imutáveis e também só contenham itens imutáveis. `Dict` e `List` são coleções de estrutura fixa mas com os campos mutáveis (eles podem ser removidos e também exigem a validação de tipo).

#### Product Types: Record e Tuple

  * **`Record`**: Representa um conjunto de campos nomeados, similar a objetos em JavaScript, mas com uma estrutura de tipo definida.
  * **`Tuple`**: Representa uma sequência ordenada de valores, similar a arrays, mas com tipos fixos em posições específicas.

#### Sum Types: Enum

  * **`Enum`**: Permite definir um tipo que pode ser um de vários valores possíveis, mas apenas um por vez. Cada "caso" do `Enum` pode ter um tipo associado.

**Exemplo de uso (de DataTypes.js):**

```javascript
// DataTypes.js: Definição de um Enum (Result)
var Result = Enum.create('Result', [
    ['Ok', GenericRef.type], // O caso 'Ok' tem um tipo genérico
    ['Error', Error],        // O caso 'Error' tem o tipo Error
    ['TypeError', TypeError],
    ['RangeError', RangeError],
    ['ReferenceError', ReferenceError],
    ['SyntaxError', SyntaxError]
  ],
  {
    GenericType: ADT // Result é um tipo algébrico de dado (ADT)
  })

// Exemplo de uso de Result (conceitual)
let operationResult = Result.Ok(someValue); // Ou Result.Error(new Error('Something went wrong'))
```

Este `Result Enum` é uma forma de modelar operações que podem ter sucesso (com um valor `Ok`) ou falha (com diferentes tipos de `Error`), incentivando o tratamento explícito de todos os resultados possíveis.

### Criação de Tipos Específicos com ADTs

ADTs, especialmente quando combinados com `DataClass` e o módulo `Box`, permitem a criação de tipos de dados específicos e auto-validáveis. O método `create` cria uma nova classe que estende o tipo ADT (`Enum` por extensão, `Tuple` e `Record` por implementação de interfaces).

### Troca de Mensagens: Métodos toString e parse

A `ProtoLib` estende a funcionalidade dos ADTs (`Record`, `Tuple`, `Enum`) com métodos `toString` e `parse`, permitindo a serialização e desserialização de dados de e para representações em string. Isso é crucial para a troca de mensagens, persistência de dados e interoperabilidade.

#### toString() para Serialização

O método `toString()` de um ADT converte sua estrutura de dados em uma representação de string padronizada, que pode ser transmitida ou armazenada.

#### parse() para Desserialização

O método `parse()` de um ADT permite reconstruir uma instância do tipo a partir de sua representação em string, validando a estrutura e os tipos de dados, usando sua estrutura e os tipos de seus próprios dados como referência.

```javascript
const questRelationalStr = (token) => `ReqMessage({communication: Request({
  rows: All,
  select: ["link"],
  table: "visits",
  index: Primary,
  id: String("202409200840")
}),
  token: "${token}"
})`
```

### Algebraic Data Types e o Padrão Interpreter

Algebraic Data Types em conjunto com o padrão de projeto Interpreter pode ser projetado para modelar e processar operações em um sistema, traduzindo uma representação estruturada em ações executáveis. É possível definir uma gramática (Abstract Syntax Tree - AST) com um `Enum Term` representando `Operator`, `Operand`, `Expression`, e executado operações recursivas com implementação de métodos `calc` e `exec`.

Quando essa estrutura precisa ser processada, o interpretador (`exec methods`) percorre a árvore, avaliando cada nó (operador ou termo) e combinando os resultados. Isso permite que a lógica de execução seja encapsulada dentro das próprias definições dos tipos de dados. Novas operações ou termos podem ser adicionados simplesmente novos casos no `Enum` e implementando seus respectivos métodos `calc` ou `exec`.

```javascript
var Operator = Proto.interface('Operator', function () {
    return {
      calc () {
        return BasicTerm.Invalid()
      },
      exec (terms, index) {
        const thisOperator = this
        return this.resolve(Term, {
          default () {
            let task0
            const index0 = 2 * index + 1
            if (Util.hasOwn(terms, index0)) {
              task0 = terms[index0].exec(terms, index0)
            } else {
              return BasicTerm.Invalid()
            }
            var task1 = task0.then(function (term0) {
              if (term0.isKindOf('Invalid')) {
                return term0
              }
              const index1 = 2 * index + 2
              if (Util.hasOwn(terms, index1)) {
                return terms[index1].exec(terms, index1)
              }
              return term0
            })
            return Task.join(task0, task1).mix(function (term0, term1) {
              if (term0 === term1 || term1.isKindOf('Invalid')) {
                return term1
              }
              return thisOperator.calc(term0, term1.modTerm(term0))
            })
          }
        })
      },
      return (operandType, result) {
        try {
          return BasicTerm[operandType](result)
        }
        catch (e) {
          return BasicTerm.Invalid()
        }
      }
    }
  })
const BasicTerm = Enum.create('BasicTerm', [
    ['Expression', refTerm, [ExpressionTerm]],
    ['EmbeddedExpression', refTerm, [EmbeddedExpressionTerm]],
    Operand,
    ['Operator', GenericRef.type,
    {
      exec (terms, index) {
        return this.enum.resolve(Term, {
          Operator (operator) {
            return operator.exec(terms, index)
          }
        })
      },
      getString () {
        return this.ExtendedEnum.get(String, {
          Operator: (op) => op.get(String, {default: (str)=> str})
        })
      },
      getPriority () {
        return this.enum.force('Operator').priority
      },
      isLowPriority (termOperator) {
        return this.enum.get(Boolean, {
          Operator: (op) => op.priority < termOperator.getPriority()
        })
      },
      isSamePriority (termOperator) {
        return this.enum.get(Boolean, {
          Operator: (op) => termOperator.getPriority() === op.priority
        })
      }
    }],
    ['Invalid']
  ],
  [
    Term
  ])
const Expression = Record.create('Expression', {
    lastTerm: 0,
    terms: Box.ref(Record.boxOf(GenericRef.type))
  }, {
    GenericType: Term
  }, [
    Generic
  ])
```