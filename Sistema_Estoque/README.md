# 📦 Sistema de Controle de Estoque (Java)

## Visão Geral

Sistema de controle de estoque em Java, orientado a objetos, rodando por menu no terminal (`Scanner`). É o projeto "avançado" desse repositório: em vez de um arquivo único, o sistema é dividido em várias classes, cada uma com uma responsabilidade clara — produto, movimentação, exceção de negócio, persistência e relatórios ficam todos separados.

A ideia central é simples: todo produto tem uma quantidade em estoque, e toda mudança nessa quantidade (entrada ou saída) vira um registro de `Movimentacao`, guardado num histórico que nunca é apagado. As regras de negócio (não deixar o estoque ficar negativo, avisar quando tá baixo) ficam concentradas na classe `GerenciadorEstoque`, então o menu (`Main`) só chama métodos prontos e nunca decide nada sozinho.

---

## ✨ Funcionalidades

- Cadastro de produtos (nome, categoria, quantidade inicial, estoque mínimo, preço)
- Registro de entrada e saída de estoque, com histórico completo de movimentações
- **Regra de negócio principal:** o sistema não deixa registrar uma saída maior do que o estoque disponível — lança uma exceção própria (`EstoqueException`) em vez de deixar o número ficar negativo
- Alerta automático de estoque baixo (quando a quantidade fica igual ou abaixo do mínimo cadastrado)
- Relatório de produtos com estoque baixo
- Relatório de produtos mais movimentados (soma entradas + saídas e ordena do maior pro menor)
- Persistência simples em arquivo de texto (`produtos.txt` e `movimentacoes.txt`) — os dados são carregados automaticamente ao abrir o programa e salvos ao sair

---

## 🧱 Estrutura do Projeto

```text
.
├── Main.java                       # menu interativo (Scanner) — só chama os métodos, não decide regra nenhuma
├── GerenciadorEstoque.java         # o "banco de dados" em memória + todas as regras de negócio
├── Produto.java                    # modela um produto do estoque
├── Movimentacao.java               # modela um registro de entrada/saída (histórico)
├── TipoMovimentacao.java           # enum ENTRADA / SAIDA
├── EstoqueException.java           # exceção própria pra violação de regra de negócio
├── Persistivel.java                # interface comum pra Produto e Movimentacao saberem virar linha de texto
├── Relatorio.java                  # classe abstrata: define a "forma" de um relatório
├── RelatorioEstoqueBaixo.java      # relatório concreto: produtos abaixo do mínimo
└── RelatorioMaisMovimentados.java  # relatório concreto: ranking de movimentação
```

---

## 🚀 Como Compilar e Rodar

Precisa ter o JDK instalado (`javac` e `java` no PATH). Sem dependências externas — só biblioteca padrão do Java (`java.util`, `java.io`, `java.time`).

```bash
cd Sistema_Estoque
javac *.java
java Main
```

Os arquivos `produtos.txt` e `movimentacoes.txt` são criados automaticamente na primeira vez que você sair do programa pela opção "Salvar e sair" — e recarregados sozinhos da próxima vez que o programa abrir.

---

## 📋 Menu do Sistema

```text
1 - Cadastrar produto
2 - Listar produtos
3 - Registrar entrada de estoque
4 - Registrar saida de estoque
5 - Ver historico de movimentacoes
6 - Relatorio: estoque baixo
7 - Relatorio: produtos mais movimentados
0 - Salvar e sair
```

---

## 🧠 Conceitos Aplicados

- Programação Orientada a Objetos: encapsulamento (getters/setters, campo pacote-privado em `Produto`), herança (`Relatorio` abstrata) e polimorfismo (`Persistivel`)
- Interface (`Persistivel`) pra permitir salvar `Produto` e `Movimentacao` com o mesmo código, sem duplicar lógica de arquivo
- Classe abstrata (`Relatorio`) com dois relatórios concretos que reaproveitam um método comum
- Exceção customizada (`EstoqueException`) pra regra de negócio, em vez de deixar o programa quebrar ou retornar `false` sem explicação
- Coleções: `HashMap`/`LinkedHashMap` (busca de produto por ID em tempo constante) e `ArrayList` (histórico ordenado por chegada)
- `enum` (`TipoMovimentacao`) em vez de `String` solta pra representar entrada/saída
- Persistência simples com `BufferedReader`/`BufferedWriter` (arquivo texto), sem banco de dados
- `java.time.LocalDateTime` pra registrar quando cada movimentação aconteceu

---

## 📈 Melhorias Futuras

- Migrar persistência de arquivo texto pra um banco de dados real (SQLite, por exemplo)
- Busca de produto por nome/categoria, não só por ID
- Relatório de valor total em estoque (quantidade × preço)
- Múltiplos usuários com login
- Testes automatizados (JUnit)
- Interface gráfica (Swing ou JavaFX) no lugar do menu de terminal

---

## 👤 Autor

**Rafael Costa**
GitHub: [github.com/rafscorp](https://github.com/rafscorp)
