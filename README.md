#Spring

### Problemas do Spring

- Configurações de bens em arquivos xml;
- Dispatcher Servet e view resolver em web.xml;
- Setup manual de Banco de Dados;
- Muito tempo gasto em configuração;
- Perda de foco e valor;



## O que é Spring Boot?

- Criado pela Spring Source em 2012;
- Facilita setup de projetos Spring;
- Sem necessidade de criar arquivos de configuração;
- Foco em produtividade;
- Maior tempo no desenvolvimento de valor;

### Exercício 

- Criação de um projeto no site `http://start.spring.io`;
- Importar o projeto na sua IDE favorita;
- Adicionar spring-boot-starter-mvc no pom.xml;
- Adicionar classe Hellocontroller e o método `hello()`;
- Executar o projeto através do terminal; 



## Auto Configurator

### Configuração manual

- Múltiplos Arquivos XML;
- Configuração manual do Spring MVC:Dispatcher Servlet, web.xml, spring-mvc.xml;
- Configuração manual dos bens Spring;
- Aplicado também ao Spring Data, Spring Security, etc;

### Auto Configuration

- Starters: dependências simplificadas e auto configuráveis;
- Identificação e configuração automática da dependência;
- Spring Boot. detecta as dependencias e configura;
- Projeto simplificado e pronto para foco no valor;

###Exercício

- Adicionar propriedade debug=true no application.properties;
- Executar projeto no terminal e analisar o log;
- Identificar e visualizar o auto configuration do spring mvc;
- Visualizar a dependência do auto configuration do projeto;



## Fatjar UberJar

### Antes do Spring Boot

- Depenência. de um container web ou servidor de aplicação;
- Complexidade para configurações;
- Atualizações frequentes, junto com a versão do projeto;
- Gerenciamento manual de configurações;

### FatJar/ UberJar

- Artefato do projeto pronto para execução;
- Constainer web embutido na geração e execução(Tomcat);
- Deploy embarcado com outros containers são opcionais;
- Dependências principais do projeto embarcado;
- Execução direta. através de um único java -jar;
- Podemos também gerar o mar tradicional;

### Exercício

- Fazer o build do projeto;
- Explorar conteúdo do arquivo .jar gerado;
- Executar o projeto no terminal com java -jar;
- trocar o formato do artefato para .war e executar no Tomcat;



## Importância dos Profiles

### Múltiplos ambientes

- Bancos de dados para cada ambiente;
- Execução de testes unitários em ambiente local;
- Suíte de testes completas em ambiente de teste;
- Simulação do ambiente real em staging;
- Deploy simplificado em produção;

### Spring Boot Profiles

- Configurações próprias para cada ambiente;
- Ambientes com sua configuração: dev, production;

### Exercício

- Projeto com spring.initialzr e importar na IDE;
- Arquivos application.properties para dev e prod;
- Classe de configuração de BD e anotar com @Configuration;
- Mapear propriedades com @ConfigurationPropeties;
- Criar métodos para instanciar Beans de cada env;
- Criar classe anotada com @RestControler;
- Injetar propriedade appMessage com @Value;
- Criar método que retorna a mensagem acima;
- Executar projeto no browser;

## Configurações com YAML e command line

 #### Configurações com YAML

- Troca no formato de configurações: formato .YML

####Exercício

- Migrar app.properties do profile dev para YML;
- Executar o projeto pelo terminal;

#### Uso de command line

- Propriedades do arquivo de configuração na linha de comando;
- Sobrescreve as propriedades definidas no arquivo de configurações padrão;
- Valores passados como argumento na execução do projeto;

## Variáveis de ambiente

- Variável de ambiente. pode ser injetada através da anotação @Value no projeto;

- Linux e Mac: export comum de variável

  - `export ENV_DB_URL=jdbc:h2:mem:db;DB_CLOSE_DELAY=-1`

- Windows: padrão de variável de ambiente

- Injeção com anotação @Value({NOME_VARIAVEL});

- Definição de valor default quando não há variável:

  - > @Value("${ENV_DC_URL:NENHUMA}")
    >
    > private String. DbenvironmenntVariable;

    

#### Exercício

- Injetar a variável com @Value em AppController;
- Definição de valor default junto com a anotação @Value;
- Criar método para chamada do novo método e exibir valor;
- Executar projeto no terminal e exibir no browser;

