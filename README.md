
# Padrões de Design Patterns

# Composite pattern
- Padrão Composite no contexto de formas geométricas.

  ![image](https://github.com/jxqlnm/Eng3/assets/128145943/3f5983fa-e52c-49b9-9099-e8ddc618dd38)

>Interface Shape: Esta interface define a estrutura básica para todas as formas na hierarquia. Ela contém um método draw(String color) que desenha a forma na cor especificada.

>Classe Circle: Esta classe implementa a interface Shape e desenha um círculo na cor especificada.

>Classe Square: Esta classe implementa a interface Shape e desenha um quadrado na cor especificada.

>Classe Group: Esta classe implementa a interface Shape e gerencia uma lista de objetos Shape. Ela fornece métodos para adicionar e remover formas da lista, além de um método draw(String color) que desenha todas as formas na lista na cor especificada
- Aplicação do Padrão Composite:
Na imagem, a classe Group é usada para compor os objetos Circle e Square. Isso cria uma estrutura de árvore, onde o objeto Group atua como o nó raiz e os objetos Circle e Square atuam como os nós folha. Ao chamar o método draw(String color) no objeto Group, todas as formas na lista (Circle e Square) serão desenhadas na cor especificada.

  # Facade pattern

- Padrão Facade no contexto do sistema de ingressos e lanches de um cinema.

![image](https://github.com/jxqlnm/Eng3/assets/128145943/0908e88f-e2a8-48bf-9668-cc379e9e45f6)
>TicketSystem: Esta classe representa o sistema de reserva de ingressos para filmes. Ela fornece métodos para reservar ingressos, cancelar reservas e recuperar informações dos ingressos.

>SnackSystem: Esta classe representa o sistema de pedidos de lanches. Ela fornece métodos para pedir lanches, cancelar pedidos e recuperar informações dos lanches.

>MovieSystem: Esta classe representa o sistema de exibição de filmes. Ela fornece métodos para iniciar a exibição, parar a exibição e recuperar informações dos filmes.

> CinemaFacade: Esta classe funciona como a fachada para todo o sistema. Ela fornece uma interface simplificada para os clientes interagirem com os sistemas de ingressos, lanches e filmes. O CinemaFacade oculta a complexidade dos subsistemas subjacentes e expõe apenas os métodos essenciais necessários para que os clientes realizem tarefas comuns.

- Aplicando o Padrão Facade:
Na imagem, a classe CinemaFacade oferece uma interface simplificada para os clientes comprarem ingressos, pedirem lanches e assistirem filmes. Os clientes podem interagir com o sistema usando o método watchMovie(), que recebe como parâmetros o nome do filme, a quantidade de ingressos e uma lista de lanches. A classe CinemaFacade então lida com as interações subjacentes com as classes TicketSystem, SnackSystem e MovieSystem, garantindo que o cliente não precise conhecer o funcionamento interno dos subsistemas.

# Observer Pattern
- Padrão Observer no contexto de um aplicativo de estação meteorológica.
  
![image](https://github.com/jxqlnm/Eng3/assets/128145943/c5f95a51-7b90-4f85-bb85-9ac9da1990c0)

>Estação: Esta classe representa o hardware da estação meteorológica. É responsável por coletar dados do sensor, como temperatura, umidade e pressão.

>Sensor: Esta classe representa um sensor conectado à estação meteorológica. É responsável por medir condições ambientais específicas, como temperatura ou umidade.

>Observador: Esta interface define um contrato para objetos que desejam ser notificados de alterações no modelo.

>Sujeito: Esta interface define um contrato para objetos que podem notificar observadores sobre alterações em seu estado.

>Visão (View): Esta classe representa a interface do usuário do aplicativo da estação meteorológica. É responsável por exibir os dados atuais do sensor e fornecer controles para o usuário interagir com o aplicativo.

>Gráfico: Esta classe representa um gráfico que exibe o histórico de dados do sensor. É um observador da classe Estação e é notificado sempre que os dados do sensor são alterados.

- Aplicando o Padrão Observer:

Na imagem, o Padrão Observer é implementado da seguinte forma:
Sujeito: A classe Estação implementa a interface Sujeito, pois pode notificar observadores de alterações em seu estado (ou seja, dados do sensor).
Observadores: As classes Visão e Gráfico implementam a interface Observador, pois desejam ser notificadas de alterações no estado da Estação.
Notificação: Sempre que os dados do sensor da Estação mudam, ela notifica todos os seus observadores registrados. As classes Visão e Gráfico então atualizam suas exibições com base nos dados atualizados do sensor.

# Singleton Pattern
- Padrão Singleton no contexto de um aplicativo de estação meteorológica.
![image](https://github.com/jxqlnm/Eng3/assets/128145943/a385a999-1bfe-451d-8d55-aa129389ad56)
>Estação: Esta classe representa o hardware da estação meteorológica. É responsável por coletar dados do sensor, como temperatura, umidade e pressão.

>Sensor: Esta classe representa um sensor conectado à estação meteorológica. É responsável por medir condições ambientais específicas, como temperatura ou umidade.

>GerenciadorEstação (StationManager): Esta classe representa a instância singleton da estação meteorológica. Ele fornece métodos para acessar e manipular os dados do sensor.

- Aplicando o Padrão Singleton:
Na imagem, o Padrão Singleton é implementado da seguinte forma:
Criação do Singleton: A classe GerenciadorEstação é declarada como um singleton usando uma variável de instância estática. Essa variável é inicializada apenas uma vez, quando a classe é usada pela primeira vez.
Acessando o Singleton: O método getInstance() fornece uma maneira de acessar a instância singleton da classe GerenciadorEstação. Esse método garante que apenas uma instância da classe seja retornada.
Usando o Singleton: As classes Visão e Gráfico usam o método getInstance() para obter uma referência à instância singleton da classe GerenciadorEstação. Elas podem então usar esta instância para acessar e manipular os dados do sensor.

# Strategy Pattern
-  Padrão Strategy (Estratégia) no contexto de um aplicativo de estação meteorológica.
![image](https://github.com/jxqlnm/Eng3/assets/128145943/ecc17c8c-a915-48c0-9dd5-0c11f5108eab)
>Estação: Esta classe representa o hardware da estação meteorológica. É responsável por coletar dados do sensor, como temperatura, umidade e pressão.

>Sensor: Esta classe representa um sensor conectado à estação meteorológica. É responsável por medir condições ambientais específicas, como temperatura ou umidade.

>Estratégia: Esta interface define um contrato para objetos que representam diferentes estratégias para processar dados do sensor.

>EstratégiaMédia (AverageStrategy): Esta classe implementa a interface Estratégia e fornece uma estratégia para calcular a média dos dados do sensor.

>EstratégiaMediana (MedianStrategy): Esta classe implementa a interface Estratégia e fornece uma estratégia para calcular a mediana dos dados do sensor.



- Aplicando o Padrão Strategy:
Na imagem, o Padrão Strategy é implementado da seguinte forma:
Interface de Estratégia: A interface Estratégia define os métodos que todas as estratégias devem implementar, como calcular() para processar dados do sensor.
Estratégias Concretas: As classes EstratégiaMédia e EstratégiaMediana implementam a interface Estratégia e fornecem suas respectivas implementações para calcular a média e a mediana dos dados do sensor.
Contexto: A classe Estação representa o contexto, pois mantém uma referência à estratégia atual (EstratégiaMédia ou EstratégiaMediana) e a usa para processar os dados do sensor.
Mudando Estratégias: A classe Estação pode alterar dinamicamente a estratégia que utiliza definindo o atributo estratégia para um novo objeto de estratégia. Isso permite que o aplicativo alterne entre diferentes métodos de processamento em tempo de execução.

# MVC Pattern
- Padrão Model-View-Controller (MVC) no contexto de um aplicativo de estação meteorológica.

![image](https://github.com/jxqlnm/Eng3/assets/128145943/3e78c17a-645b-4c5a-a4a5-70b389ff25a4)

>Estação: Esta classe representa o hardware da estação meteorológica. É responsável por coletar dados do sensor, como temperatura, umidade e pressão.

>Sensor: Esta classe representa um sensor conectado à estação meteorológica. É responsável por medir condições ambientais específicas, como temperatura ou umidade.

>Observador (Observer): Esta interface define um contrato para objetos que desejam ser notificados de alterações no modelo.

>Sujeito (Subject): Esta interface define um contrato para objetos que podem notificar observadores sobre alterações em seu estado.

>Visão (View): Esta classe representa a interface do usuário do aplicativo da estação meteorológica. É responsável por exibir os dados atuais do sensor e fornecer controles para o usuário interagir com o aplicativo.

- Aplicando o Padrão MVC:
Na imagem, o padrão MVC é implementado da seguinte forma:
Modelo (Model): A classe Estação representa o modelo, pois armazena os dados atuais do sensor e fornece métodos para recuperar e atualizar os dados.
Visão (View): A classe Visão representa a visão, pois exibe os dados atuais do sensor para o usuário e fornece controles para o usuário alterar o sensor exibido.
Controlador (Controller): O controlador da aplicação é responsável por tratar as interações do usuário, atualizar o modelo com base na entrada do usuário e notificar a visão para atualizar a exibição de acordo.




























<table>
    <tr>
        <th>Tipos de Padrões</th>
        <th>Antipadrões</th>
        <th>Definição</th>
        <th>O que resolve</th>
        <th>Funcionalidades em Java</th>
    </tr>
    <tr>
        <td>Strategy</td>
        <td>Switch Statements (Declarações Switch): O uso excessivo de instruções switch/case para selecionar a estratégia a ser usada pode levar a um código difícil de manter, pois novas estratégias exigirão modificações no código existente.</td>
        <td>O Padrão Strategy é um padrão comportamental que permite definir uma família de algoritmos, encapsulá-los e torná-los intercambiáveis. Ele permite que o cliente escolha um algoritmo específico de uma família de algoritmos durante o tempo de execução, sem alterar a estrutura do código.</td>
        <td>O Padrão Strategy resolve o problema de escolher e trocar algoritmos dinamicamente. É útil quando você tem diferentes algoritmos que podem ser usados em um contexto específico e deseja permitir que o cliente escolha qual algoritmo usar durante o tempo de execução, sem modificar o código cliente.</td>
        <td>Java Comparable/Comparator: A interface java.lang.Comparable e a interface java.util.Comparator são usadas para implementar o Padrão Strategy em Java. Elas permitem que você defina estratégias de comparação personalizadas para objetos, permitindo que os objetos sejam classificados de maneira flexível.</td>
    </tr>
    <tr>
        <td>Observer</td>
        <td>Observers Everywhere (Observadores em Todo Lugar): Quando você cria um grande número de observadores ou torna cada classe observável, isso pode levar a uma complexidade excessiva e dificuldade em rastrear todas as dependências.</td>
        <td>O Padrão Observer é um padrão comportamental que define uma dependência um-para-muitos entre objetos, de modo que quando um objeto sofre uma mudança de estado, todos os seus dependentes são notificados e atualizados automaticamente. É usado para implementar sistemas de eventos e publicação-subscrição.</td>
        <td>O Padrão Observer lida com o problema de estabelecer uma comunicação eficiente entre objetos quando um objeto muda de estado e vários outros objetos precisam ser notificados e atualizados automaticamente. É usado quando você precisa implementar sistemas de eventos, notificações ou publicação-subscrição.</td>
        <td>Event Handling (Manipulação de Eventos): A API de manipulação de eventos em Java, como o uso de listeners e a classe java.util.Observable, implementa o Padrão Observer. Componentes gráficos como botões e caixas de seleção podem ser observados por ouvintes que respondem a eventos, como cliques ou alterações de estado.</td>
    </tr>
    <tr>
        <td>Composite</td>
        <td>Unintentional Complexity (Complexidade Não Intencional): Um erro comum é adicionar métodos que não fazem sentido em um componente composto, o que pode levar a uma interface inchada e complicada.</td>
        <td>O Padrão Composite é um padrão estrutural que permite que você componha objetos em uma estrutura de árvore para representar hierarquias de parte-todo. Ele permite que os clientes tratem objetos individuais e composições de objetos de maneira uniforme.</td>
        <td>O Padrão Composite resolve o problema de criar estruturas de objetos hierárquicas e compostas. É útil quando você precisa tratar objetos individuais e composições de objetos de maneira uniforme, permitindo que você construa árvores de objetos onde cada objeto pode ser tratado da mesma forma, independentemente de ser um objeto simples ou uma composição complexa.</td>
        <td>Swing GUI Components (Componentes GUI Swing): A biblioteca Swing em Java usa o Padrão Composite para criar interfaces gráficas de usuário. Os componentes Swing, como painéis, botões e caixas de seleção, são organizados em uma hierarquia de composição, onde um contêiner pode conter outros componentes.</td>
    </tr>
    <tr>
        <td>Facade</td>
        <td>God Class (Classe Deus): O antipadrão "God Class" ocorre quando a classe Facade se torna uma classe gigante que lida com quase todas as operações do sistema. Isso viola o princípio de responsabilidade única e pode tornar o sistema difícil de entender e manter.</td>
        <td>O Padrão Facade é um padrão estrutural que fornece uma interface simplificada para um conjunto mais amplo de interfaces em um subsistema. Ele visa ocultar a complexidade do sistema e fornecer um ponto de entrada único e fácil de usar para os clientes.</td>
        <td>O Padrão Facade aborda o problema de simplificar interfaces complexas ou subsistemas. Ele fornece uma interface única e simplificada para um conjunto mais amplo de interfaces em um subsistema, ocultando a complexidade do sistema subjacente. Isso torna mais fácil para os clientes interagirem com o sistema sem precisar entender sua complexidade interna.</td>
        <td>Java Database Connectivity (JDBC): A API JDBC em Java fornece uma fachada para interagir com bancos de dados. Em vez de lidar diretamente com detalhes de conexão e gerenciamento de consultas, você pode usar métodos simplificados da API JDBC para executar operações de banco de dados.</td>
    </tr>
    <tr>
        <td>Singleton</td>
        <td>Global State (Estado Global): Ao usar o Singleton de forma excessiva, você pode criar um estado global compartilhado que dificulta a rastreabilidade das dependências e pode levar a problemas de concorrência em sistemas multi-threaded.</td>
        <td>O Padrão Singleton é um padrão de criação que garante que uma classe tenha apenas uma instância e fornece um ponto global de acesso a essa instância. É útil quando você deseja compartilhar uma única instância de uma classe em todo o sistema e controlar o acesso a essa instância.</td>
        <td>O Padrão Singleton resolve o problema de garantir que uma classe tenha apenas uma instância e fornece um ponto global de acesso a essa instância. É útil quando você deseja controlar o acesso a uma única instância de uma classe em todo o sistema, como configurações globais, conexões de banco de dados ou recursos compartilhados, evitando a criação de múltiplas instâncias acidentais.</td>
        <td>Runtime Environment (Ambiente de Execução): O ambiente de execução Java (JVM) é uma implementação do Padrão Singleton. Garante que apenas uma instância da máquina virtual Java seja criada em um processo. Além disso, a classe java.lang.Runtime é uma fachada singleton que fornece acesso ao ambiente de execução em tempo de execução, permitindo operações como coleta de lixo e execução de comandos do sistema.</td>
    </tr>
</table>
