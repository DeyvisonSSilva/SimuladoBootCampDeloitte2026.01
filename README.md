<h1 align="center">SimuladoBootCampDeloitte2026.01</h1>
<p align="center">Aluno: Deyvison Francisco Soares Silva</p>


### 1-  Explique o que é Programação Orientada a Objetos e cite dois benefícios
         R - É um conceito de codificação onde transformamos Código em Objetos com atributos, por exemplo: Um Objeto/Classe Motocicleta onde seus atributos seriam: Cor, velocidade, marcha, freio. 
         R - Reuso do código e facilidade de manunteção.
### 2 - Explique o conceito de encapsulamento e qual problema ele resolve
        R -  o conceito do encapsulamenteo é a proteção de dados e o controle de acesso.
        R - os problemas que ele resolve podem ser por exemplo: estados inválidos, alterações indevidas em atributos, acoplamento.
### 3 - Analise o código abaixo e responda:
  public class Produto {
    public Long id;
    public String nome;
    public double preco;
  }
###  Qual princípio de POO está sendo violado? Justifique
      R - Encapsulamento.
      R - Os atributos estão como Public, o que permite que qualquer classe leia os valores diretamente.
### 4 - Por que o uso de getters e setters é preferível ao acesso direto aos atributos?
      R - Para evitar que o usuário tenha acesso a dados sensíveis/privados.
### 5 - Qual alternativa representa corretamente um atributo encapsulado?
      R - Aquela em que o atributo está privado e o acesso a ele é por via de métodos públicos.
### 6 - O que é Spring Boot e qual sua principal vantagem?
      R - É um framework que tem como objetivo simplificar e acelerar o desenvolvimento de aplicações Java.
      R - Sua principal vantagem acredito ser a Produtividade, o desenvolvedor pode focar na regra de negócio, escrever menos código e subir a aplicação rapidamente.
### 7 - Qual anotação define um controller REST?
      R - @RestController .
### 8 - Qual a função do @RequestMapping?
      R - Realiza uma Requisição ao Model para obter o métodos de Requisição HTTP .
### 9 - Analise o código abaixo:
  @GetMapping("/produtos")  
  public list<Produto> lista() {  
    return repository.findAll();  
  }  
###  Qual o problema arquitetural esse código apresenta?
    R - O Controller está acessando diretamente o Repositório, o que não é recomendado.
### 10 - Explique a diferença entre GET, POST, PUT e DELETE.
    R - GET: Obtem informações do banco.
    R - POST: Insere informações no banco.
    R - PUT: Atualiza informações de algum item do banco.
    R - DELETE: Deleta informações do banco.
### 11 - O que é JPA e qual o papel do Hibernate?
    R- JPA (Java Persistence API) Define como objetos Java devem ser persistidos em bancos de dados.
    R - Hibernate Implementa tudo que o JPA define, por exemplo: Geração de SQL, Persistência, Cache.
### 12 - Qual anotação define uma entidade JPA?
    R - @Entity
### 13 - Explique as anotações @Id e @GeneratedValue.
    R - São usadas para identificar e gerar a chave primária de uma entidade.
### 14 - Analise o código:
  public interface ProdutoRepository
          extends JpaRepository<Produto, Long> {
  }
### Explique duas responsabilidades fornecidas por essa interface.
    R - Operações CRUD e Persistência de dados
### 15 - Porque evitamos escrever SQL manual ao usar JPA?
    R - o JPA permite trabalhar com objetos em vez de tabelas e colunas, o que diminui o risco de erros, por sintaxe, injeção, etc.
### 16 - O que é um DTO e qual problema ele resolve?
    R - Um objeto usado para transportar dados entre camadas de uma aplicação, sem conter a lógica de negócio.
### 17 - Analise o código abaixo:
  @PostMapping
  public Produto salvar(@RequestBody Produto produto) {
      return repository.save(produto);
  }
### Explique por que essa abordagem não é recomendada.
    R - O Usuário passa diretamente um produto JPA para a camada de persistência, gerando acoplamento entre a API e o modelo de dados, o que torna a aplicação menos flexível.
    R - Qualquer alteração na entedidade pode quebrar a API.
### 18 - Explique a responsabilidade da camada Service.
    R - Ela serve para implementar a Lógica de negócio e orquestra a chamada entre as camadas e componenentes
### 19 - Quem deve conter a regra de negócio? Justifique.
    R - No Service.
    R - o Controller deve lidar apenas com as requisições e respostas da API.
    R - O Repository deve apenas persistir os dados no banco.
### 20 - Porque o Controller não deve acessar diretamente o Repository?
    R - Por motivos como: Boa arquitetura e manutenção da aplicação.
    R - por exemplo: Se o controller tiver acesso ao Repository, ele mistura responsabilidades, o que torna o código difícil de manter.
### 21 - Explique o Single Responsibility Principle (SRP) com um exemplo.
    R - SRP é o primeiro princípio do SOLID e diz que uma classe deve ter apenas uma razão para mudar, uma única responsabilidade.
    R - Exemplo: public class NotificacaoService {
                    public void enviarProduto(Produto produto) {
                        System.out.println("Notificação: Produto cadastrado!")
                    }
                  } Serve apenas para realizar uma Notificação que um determinado produto foi cadastrado.
### 22 - Análise o código:
  public class ProdutoController [
    public void salvar () {
      // validação
      // regra de negócio
      // acesso ao banco
    }
  }
###  Qual princípio SOLID está sendo violado?
    R - SRP (A classe tem múltiplas responsabilidades)
### 23 - Explique o Open/Closed Principle (OCP)
    R - a classe deve estar aberta para extensão, mas fechada para modificação.
    R - exemplo: Nova regra de desconto = criar uma nova classe que implemente a estrategia de desconto.
### 24 - Explique o Liskov Substitution Principle (LSP)
    R - se você tiver uma classe base e uma classe filha, a filha deve poder ser usada no lugar da base sem quebrar nada.
### 25 - Explique o Interface Segregation Principle (ISP)
    R - O uso de interfaces pequenas e específicas ao invez de uma grande e genérica, cada cliente deve depender apenas dos métodos que realmente precisa.
### 26 - Analise o código:
  public interface ProdutoService {
  salvar();
  listar();
  exportarPdf();
  enviarEmail();
}
###  Qual princípio SOLID está sendo violado? Justifique.
    R - ISP (Uma interface grande e genérica onde mistura responsabilidades totalmente diferentes, forçando as classes(Cliente) a utilizar métodos que não usam.
### 27 - Explique o Dependency Inversion Principle (DIP)
    R - Código de alto nível não deve depender de implementações concretas como: detalhes de banco, serviços externos.
### 28 - Qual prática está alinha ao DIP?
    R - Uso de injeções de dependências por meio de abstrações.
### 29 - Explique o fluxo de uma requisição em uma API Spring Boot
    R - Requisição HTTP -> Controller -> Service -> Repository -> Controller
    R - Cliente faz requisição -> Controller recebe  a requisição -> Service aplica regras de negócio -> Repository persiste ou consulta os dados do banco -> Controller retorna resposta ao cliente.
### 30 - Explique por que DTO + Service + SOLID tornam o sistema mais fácil de manter e evoluir
    R - Facilidade de manutenção e evolução do código, testabilidade, baixo acoplamento e segurança DTO.
    R - O DTO isola a entidade de alterações externas, facilitando as mudanças internas sem quebrar a API.
    R - O Service centraliza a regra de negócio, evitando a duplicação e deixando o Controller simples.
    R - Aplicando os conceitos SOLID, a arquitetura é aprimorada.
    R - Assim o Controller é só API / o DTO protege a entidade e abstrai os dados / o Service aplica as regras de negócio e orquesta as chamadas / o Repository persiste os dados e o SOLID faz com que as camadas sejam coesas e testáveis.
