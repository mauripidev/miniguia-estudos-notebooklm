# Relatório de Estudo: Arquitetura Moderna e Modularização com Spring Boot

## 1. Contexto e Objetivos
Este caderno temático foi criado para servir como um guia de referência sobre o ecossistema **Spring Boot**, focando na evolução para o **Spring Framework 7.0** e na implementação de **arquiteturas modulares** [1, 4]. O objetivo principal é capacitar o desenvolvedor a criar aplicações de nível de produção com o mínimo de esforço, utilizando práticas modernas de **modularização orientada ao domínio** e recursos avançados de **resiliência** [5-7].

## 2. Curadoria de Fontes
Para este estudo, foram selecionadas as seguintes fontes técnicas fundamentais:
*   **Arquitetura Modular e Inovações no Spring Boot 7.0:** Modelo de README e diretrizes de modularização [1].
*   **Spring Framework 7.0 Release Notes:** Detalhes sobre baselines tecnológicos e remoção de APIs [8].
*   **Spring Modulith (Documentação Oficial):** Guia para verificação e testes de módulos [9].
*   **Common Application Properties:** Referência de propriedades para configuração externa e Actuator [10, 11].
*   **Repositório Oficial Spring Boot:** Metas de design e instalação do framework [6, 12].

* https://docs.spring.io/spring-boot/index.html
* https://spring.io/projects/spring-modulith
* https://github.com/spring-projects/spring-boot/tree/main
* https://docs.spring.io/spring-boot/appendix/application-properties/index.html
* https://github.com/spring-projects/spring-framework/wiki/Spring-Framework-7.0-Release-Notes


## 3. Engenharia de Prompts e "Cicatrizes" (Troubleshooting)
Durante a extração de informações, foram aplicados prompts estratégicos para garantir a precisão técnica:
*   **Pergunta:** "Como as regras de dependência entre módulos são validadas?"
    *   **Resultado:** Identificou-se que a validação ocorre através do modelo **ApplicationModules**, que analisa se os subpacotes diretos do pacote principal respeitam as fronteiras de domínio [13, 14].
*   **Troubleshooting:** Inicialmente, houve dúvida sobre o suporte ao Docker Compose em testes.
    *   **Solução:** A análise das propriedades revelou que, por padrão, o suporte é desabilitado em testes via `spring.docker.compose.skip.in-tests=true`, sendo necessário alterar para `false` para integração total [2, 15].
*   **Refinamento:** Para entender a resiliência nativa, foi necessário cruzar dados das notas de lançamento, descobrindo a migração das funcionalidades de **Spring Retry** para o core do framework [4, 7].

## 4. Miniguia de Estudo (Entrega Final)

### Resumos Estruturados
*   **Modularização:** O uso do **Spring Modulith** permite verificar a integridade das dependências e realizar testes de integração isolados para cada módulo de negócio [13, 14].
*   **Novos Baselines:** O Spring 7.0 exige **JDK 17**, recomenda o **JDK 25** e adota o **Jakarta EE 11**, além de migrar para as anotações **JSpecify** para segurança de nulos [4, 16, 17].
*   **Resiliência e Testes:** O framework agora conta com as anotações `@Retryable` e `@ConcurrencyLimit` de forma nativa e introduziu o **RestTestClient** para testes não reativos de servidores ativos [2, 4, 7, 18].

### Glossário de Conceitos
*   **Actuator:** Fornece recursos não funcionais como métricas, health checks e monitoramento [2, 19].
*   **ApplicationModules:** Modelo programático para introspecção e verificação de arranjos modulares [13, 20].
*   **Testcontainers:** Ferramenta para subir containers reais (como bancos de dados) durante a execução dos testes [2, 21].
*   **JSpecify:** Padrão de anotações utilizado para declarar a nulidade de APIs, melhorando a integração com Kotlin [4, 17].

### Prompts Reutilizáveis para Revisão
1. "Explique como o arranjo de pacotes Java influencia a detecção de módulos no Spring Modulith" [13, 14].
2. "Quais são as propriedades necessárias para configurar o Actuator em um ambiente de produção?" [22, 23].
3. "Como utilizar o DynamicPropertyRegistry para integrar containers dinâmicos nos testes de integração?" [21].
4. "Liste as principais mudanças no baseline de Servlet e JPA no Spring Framework 7.0" [16].
