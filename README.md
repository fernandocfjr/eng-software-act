# eng-software-act
Atividade Engenharia de Software - SOLID

#### Trecho de código Java extraído do projeto Spring Boot, mais especificamente da classe JettyReactiveWebServerFactory. O qual é responsável por criar instâncias de servidores web Jetty reativos, que são servidores capazes de lidar com requisições de forma assíncrona e reativa (não bloqueante).

A seguir, os 4 princípios SOLID aplicados neste código:

## Single Responsibility Principle (Princípio da responsabilidade única):
Este princípio é observado em várias partes do código. Por exemplo, a classe JettyReactiveWebServerFactory tem a responsabilidade única de criar instâncias de servidores web Jetty reativos. Ela não se preocupa com a implementação detalhada dos servidores, mas apenas com a criação deles.
## Open-Closed Principle (Princípio Aberto-Fechado):
Este princípio está presente na forma como a classe é projetada para ser facilmente estendida sem precisar ser modificada. Por exemplo, é possível adicionar customizadores de servidor Jetty (JettyServerCustomizer) sem modificar diretamente a classe JettyReactiveWebServerFactory, simplesmente chamando o método addServerCustomizers.
## Interface Segregation Principle (Princípio da Segregação da Interface):
Este princípio é observado no design das interfaces fornecidas pela classe. Por exemplo, a interface ReactiveWebServerFactory define métodos relevantes apenas para a criação de servidores web reativos, sem exigir que implementações específicas incluam funcionalidades desnecessárias.
## Dependency Inversion Principle (Princípio da inversão da dependência):
Este princípio é aplicado em várias partes do código. Por exemplo, a classe JettyReactiveWebServerFactory depende de abstrações como HttpHandler e ThreadPool, em vez de depender de implementações concretas. Isso facilita a substituição dessas dependências por outras implementações sem modificar o código da classe.  

## Conclusão
O código em si é uma implementação de uma fábrica de servidores web reativos Jetty. Ele fornece métodos para configurar diferentes aspectos dos servidores, como número de aceitadores (acceptors), número de selecionadores (selectors), limite máximo de conexões (maxConnections), entre outros. A classe também permite a adição de customizadores de servidor Jetty, que podem personalizar o comportamento do servidor antes que ele seja iniciado.

No método createJettyServer, é onde ocorre a criação efetiva do servidor Jetty. Ele configura e inicializa o servidor Jetty com base nas opções fornecidas, como número de portas, configurações SSL, manipulação de cabeçalhos etc.

O problema que este código resolve é fornecer uma maneira flexível e extensível de criar servidores web reativos Jetty, seguindo os princípios de design SOLID para manter o código organizado, reutilizável e de fácil manutenção.
