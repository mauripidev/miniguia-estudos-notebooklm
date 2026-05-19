# Guia de Estudo: Arquitetura Modular com Spring Boot

Este repositório serve como um guia prático e teórico para o desenvolvimento de aplicações Java de nível de produção utilizando o ecossistema **Spring Boot**, com ênfase em **modularização orientada ao domínio** e recursos avançados do **Spring Framework 7.0** [1].

## 🚀 Objetivos do Projeto

O foco principal é reduzir a complexidade no desenvolvimento de serviços robustos, adotando uma visão opinativa da plataforma Spring para acelerar o processo de entrega [1, 2].

*   **Experiência de início rápido** para novos desenvolvedores [2].
*   Implementação de **recursos não funcionais** (segurança, métricas, health checks) [2].
*   Adoção de **arquiteturas modulares** que evoluem com o negócio [2, 3].
*   **Zero geração de código** e eliminação de configurações XML [2].

## 🧱 Modularização com Spring Modulith

O projeto utiliza o **Spring Modulith** para garantir que a aplicação permaneça bem estruturada à medida que cresce [3].

### Regras de Estrutura:
1.  **Arranjo de Pacotes:** Os módulos de negócio devem ser criados como **subpacotes diretos** do pacote principal da aplicação [3, 4].
2.  **Modelo ApplicationModules:** Através deste modelo, o framework permite:
    *   **Verificar** a integridade das dependências entre módulos [3].
    *   Realizar **testes de integração isolados** para cada módulo [3, 4].
    *   Gerar automaticamente **snippets de documentação** baseados na arquitetura real [3, 4].

## 🛠 Tecnologias e Baselines (Spring 7.0)

Este guia segue as recomendações e requisitos da nova geração do framework [5]:

*   **Java:** Baseline no **JDK 17**, com recomendação de uso do **JDK 25** (LTS) [5].
*   **Jakarta EE:** Adoção do **Jakarta EE 11** [5].
*   **Segurança de Nulos:** Migração para anotações **JSpecify**, garantindo maior segurança em APIs Java e Kotlin [5].
*   **Resiliência Nativa:** Uso de `@Retryable` e `@ConcurrencyLimit` integrados ao core para controle de carga e recuperação de falhas [5].

## 🧪 Testes de Integração e Observabilidade

A estratégia de testes foca em ambientes fiéis à produção [4]:

*   **Testcontainers:** Utilizado para subir containers reais (bancos de dados, brokers) durante os testes [4].
*   **RestTestClient:** Nova ferramenta não reativa para testar servidores ativos ou mock setups com uma API fluida [4].
*   **Actuator:** Monitoramento e gerenciamento via endpoints HTTP e JMX para observabilidade completa [4].

## 🏁 Como Começar

1.  Acesse o [Spring Initializr](https://start.spring.io) para gerar a base do projeto [4].
2.  Organize seus pacotes seguindo o padrão de domínio exigido pelo Modulith [4].
3.  Configure o **Docker Compose** para orquestração local através da propriedade `spring.docker.compose.enabled=true` [4].

## 📄 Licença

Este guia e o código associado são distribuídos sob a **Licença Apache 2.0** [6].

---
*Este README foi gerado com base na documentação oficial do Spring Boo
