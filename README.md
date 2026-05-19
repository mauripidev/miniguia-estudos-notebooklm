Guia de Estudo: Arquitetura Modular com Spring Boot
Este repositório serve como um guia prático e teórico para o desenvolvimento de aplicações Java de nível de produção utilizando o ecossistema Spring Boot, com ênfase em modularização orientada ao domínio e recursos avançados do Spring Framework 7.0
.
🚀 Objetivos do Projeto
O foco principal é reduzir a complexidade no desenvolvimento de serviços robustos, adotando uma visão opinativa da plataforma Spring para acelerar o processo de entrega
.
Experiência de início rápido para novos desenvolvedores
.
Implementação de recursos não funcionais (segurança, métricas, health checks)
.
Adoção de arquiteturas modulares que evoluem com o negócio
.
Zero geração de código e eliminação de configurações XML
.
🧱 Modularização com Spring Modulith
O projeto utiliza o Spring Modulith para garantir que a aplicação permaneça bem estruturada à medida que cresce
.
Regras de Estrutura:
Arranjo de Pacotes: Os módulos de negócio devem ser criados como subpacotes diretos do pacote principal da aplicação
.
Modelo ApplicationModules: Através deste modelo, o framework permite:
Verificar a integridade das dependências entre módulos
.
Realizar testes de integração isolados para cada módulo
.
Gerar automaticamente snippets de documentação baseados na arquitetura real
.
🛠 Tecnologias e Baselines (Spring 7.0)
Este guia segue as recomendações e requisitos da nova geração do framework
:
Java: Baseline no JDK 17, com recomendação de uso do JDK 25 (LTS)
.
Jakarta EE: Adoção do Jakarta EE 11
.
Segurança de Nulos: Migração para anotações JSpecify, garantindo maior segurança em APIs Java e Kotlin
.
Resiliência Nativa: Uso de @Retryable e @ConcurrencyLimit integrados ao core para controle de carga e recuperação de falhas
.
🧪 Testes de Integração e Observabilidade
A estratégia de testes foca em ambientes fiéis à produção:
Testcontainers: Utilizado para subir containers reais (bancos de dados, brokers) durante os testes
.
RestTestClient: Nova ferramenta não reativa para testar servidores ativos ou mock setups com uma API fluida
.
Actuator: Monitoramento e gerenciamento via endpoints HTTP e JMX para observabilidade completa
.
🏁 Como Começar
Acesse o Spring Initializr para gerar a base do projeto
.
Organize seus pacotes seguindo o padrão de domínio exigido pelo Modulith
.
Configure o Docker Compose para orquestração local através da propriedade spring.docker.compose.enabled=true
.
📄 Licença
Este guia e o código associado são distribuídos sob a Licença Apache 2.0
.
--------------------------------------------------------------------------------
Este README foi gerado com base na documentação oficial do Spring Boot 4.0.6, Spring Framework 7.0 e Spring Modulith 2.0.6
.
