# Parte 4: Casos de Uso - Livraria Resolve

Abaixo estão descritos os Casos de Uso essenciais identificados na fase de levantamento de requisitos. [cite_start]A modelagem segue o padrão de **Narrativa Expandida**, focando em uma tarefa concluída em uma sessão que produz resultado mensurável[cite: 1187].

## 1. Diagrama de Casos de Uso (Visualização)

```mermaid
usecaseDiagram
    actor "Vendedor" as V
    actor "Gerente Geral" as G
    actor "Diretor" as D
    actor "Sistema ERP" as ERP

    package "Sistema Livraria Resolve" {
        usecase "UC01: Realizar Pedido de Venda" as UC1
        usecase "UC02: Receber e Identificar Livros" as UC2
        usecase "UC03: Gerar Relatórios Gerenciais" as UC3
        usecase "UC04: Autorizar Desconto Especial" as UC4
    }

    V --> UC1
    V --> UC2
    G --> UC2
    D --> UC3
    
    UC1 ..> UC4 : <<extend>>
    UC1 ..> ERP : <<include>>
