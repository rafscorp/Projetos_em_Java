# 🧮 Calculadora Swing (Java)

## Visão Geral

Calculadora com interface gráfica feita em **Java Swing puro** — sem nenhuma lib externa de UI, só `javax.swing` e `java.awt` mesmo. É o projeto "interface" desse repositório: depois de mexer só com terminal, quis ver como é trabalhar com janela, botão e evento de clique de verdade.

O layout é o clássico: um visor (`JTextField`) em cima, mostrando o que tá sendo digitado, e uma grade de botões embaixo (`GridLayout`). Cada clique de botão dispara o mesmo `actionPerformed`, e o programa decide o que fazer olhando o texto do botão que foi clicado.

---

## ✨ Funcionalidades

- Quatro operações básicas: soma, subtração, multiplicação e divisão
- Encadeamento de contas (`5 + 3 + 2 =`) igual calculadora de bolso, sem respeitar precedência matemática — é o comportamento clássico desse tipo de interface
- Tratamento de divisão por zero (mostra uma mensagem de erro no visor em vez de travar ou de mostrar `Infinity`)
- Botão `C` pra limpar tudo e começar de novo
- Suporte a números decimais (`.`)
- Interface criada dentro da Event Dispatch Thread (`SwingUtilities.invokeLater`), do jeito que o Swing espera

---

## 🚀 Como Compilar e Rodar

Precisa ter o JDK instalado (`javac` e `java` no PATH). Sem dependências externas.

```bash
cd Calculadora_Swing
javac Calculadora.java
java Calculadora
```

Uma janela deve abrir na tela — não é um programa de terminal.

---

## 🧠 Conceitos Aplicados

- Swing: `JFrame`, `JTextField`, `JButton`, `JPanel`
- Layouts: `BorderLayout` (visor em cima, botões no meio, limpar embaixo) e `GridLayout` (grade dos botões numéricos)
- `ActionListener` e `ActionEvent` pra reagir a clique
- Event Dispatch Thread do Swing
- Controle de estado (valor acumulado, operador pendente, se deve "começar um número novo") pra fazer contas encadeadas funcionarem
- Tratamento de erro (divisão por zero) sem deixar exceção não tratada estourar

---

## 📈 Melhorias Futuras

- Suporte a teclado (digitar sem clicar nos botões)
- Precedência matemática de verdade (multiplicação antes da soma)
- Histórico de operações na tela
- Botão de porcentagem e raiz quadrada
- Tema escuro / troca de cores

---

## 👤 Autor

**Rafael Costa**
GitHub: [github.com/rafscorp](https://github.com/rafscorp)
