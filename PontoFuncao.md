# Parte 5: Análise de Pontos de Função (APF) - Livraria Resolve

A contagem de pontos de função abaixo foi realizada com base nos Requisitos e Casos de Uso levantados anteriormente. O objetivo é estimar o tamanho funcional do projeto "Livraria Resolve".

## 1. Funções de Dados (Armazenamento)

Aqui listamos os dados que o sistema precisa manter (**ALI**) e os dados que ele apenas consulta de fora (**AIE**).

| Tipo | Descrição (Arquivo) | Justificativa | Complexidade Estimada | Peso (PF) |
| :--- | :--- | :--- | :--- | :--- |
| **ALI** | **Cadastro de Clientes** | Dados dos clientes (nome, endereço, contatos). | Baixa | 7 |
| **ALI** | **Catálogo de Livros** | Dados dos livros, autores, preços e ISBN. | Média | 10 |
| **ALI** | **Pedidos de Venda** | O "coração" do sistema. Guarda itens, valores, datas e status. | Alta | 15 |
| **ALI** | **Fornecedores** | Dados de contato das editoras e sebos parceiros. | Baixa | 7 |
| **AIE** | **Status Financeiro (ERP)** | O sistema consulta no ERP se o cliente está inadimplente (apenas leitura). | Baixa | 5 |
| **AIE** | **Base de CEP (Correios)** | Consulta externa para preenchimento de endereço e cálculo de frete. | Baixa | 5 |
| **TOTAL** | **DADOS** | | | **49 PF** |

---

## 2. Funções de Transação (Processos)

Aqui listamos as funcionalidades que os usuários utilizam para interagir com os dados (Entradas, Saídas e Consultas).

| Tipo | Descrição (Funcionalidade) | Relacionado ao UC | Complexidade Estimada | Peso (PF) |
| :--- | :--- | :--- | :--- | :--- |
| **EE** | **Registrar Pedido de Venda** | UC01 | Alta (Atualiza pedido, estoque e cliente) | 6 |
| **EE** | **Cadastrar/Atualizar Cliente** | UC01 | Baixa | 3 |
| **EE** | **Receber Livros (Dar Entrada)** | UC02 | Média (Atualiza estoque e status do pedido) | 4 |
| **SE** | **Relatório de Vendas** | UC03 | Média (Cálculos e agrupamentos) | 5 |
| **SE** | **Relatório de Fornecedores/Gastos** | UC03 | Média | 5 |
| **SE** | **Notificação de Envio (E-mail)** | UC02 | Baixa | 4 |
| **CE** | **Consultar Histórico do Cliente** | UC01 | Média | 4 |
| **CE** | **Buscar Livro no Catálogo** | UC01 | Baixa | 3 |
| **TOTAL** | **TRANSAÇÕES** | | | **34 PF** |

---

## 3. Resumo da Contagem (Tamanho Funcional)

Abaixo apresentamos o total de Pontos de Função Não Ajustados (PFNA).

| Componente | Total de Pontos |
| :--- | :--- |
| Funções de Dados (ALI + AIE) | 49 |
| Funções de Transação (EE + SE + CE) | 34 |
| **TOTAL GERAL (PF)** | **83 Pontos de Função** |

---

### Legenda:
* **ALI:** Arquivo Lógico Interno (Dados mantidos pelo sistema).
* **AIE:** Arquivo de Interface Externa (Dados de outros sistemas).
* **EE:** Entrada Externa (Usuário insere dados).
* **SE:** Saída Externa (Relatórios ou dados derivados enviados para fora).
* **CE:** Consulta Externa (Busca simples de dados).
