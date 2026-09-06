# ☕ Projetos em Java — Rafael Costa

Repositório com os projetos que venho construindo enquanto aprendo Java na prática — depois de já ter mexido com C, quis ver como a linguagem resolve os mesmos problemas usando Programação Orientada a Objetos, coleções prontas e uma JVM cuidando da memória pra mim.

A ideia aqui é a mesma do repositório de C: nada de curso pronto ou tutorial copiado, cada pasta é um projeto fechado e funcional, resolvendo um problema específico do começo ao fim.

---

## 📂 Projetos

| Projeto | Nível | O que tem dentro |
|---|---|---|
| [`Calculadora_Swing`](./Calculadora_Swing) | 🟢 Iniciante/Intermediário | Calculadora com interface gráfica em Swing puro (`JFrame`, `JButton`, `GridLayout`), quatro operações básicas e tratamento de divisão por zero |
| [`Sistema_Estoque`](./Sistema_Estoque) | 🔴 Avançado | Sistema de controle de estoque orientado a objetos: produtos, movimentações de entrada/saída, regra de estoque nunca ficar negativo, relatórios e persistência em arquivo |

Cada pasta tem seu próprio `README.md` com detalhes, estrutura de classes e instruções de compilação específicas.

---

## 🚀 Como compilar e rodar

Precisa ter o **JDK** instalado (`javac` e `java` disponíveis no terminal). Nenhum projeto usa Maven, Gradle ou biblioteca externa — só a biblioteca padrão do Java.

```bash
cd <nome-do-projeto>
javac *.java
java NomeDaClassePrincipal
```

Cada README de projeto especifica exatamente qual é o arquivo/classe principal a rodar.

---

## 🛠️ Tecnologias e conceitos

- **Java puro** (sem frameworks), compilado com `javac`
- Swing (`javax.swing`, `java.awt`) pra interface gráfica
- Programação Orientada a Objetos: classes, interfaces, classes abstratas, herança e polimorfismo
- Coleções do `java.util` (`ArrayList`, `HashMap`, `LinkedHashMap`)
- Tratamento de exceções, inclusive exceções customizadas
- Persistência simples em arquivo (`java.io`)
- `java.time` pra datas e horários

---

## 👤 Autor

**Rafael Costa**
GitHub: [github.com/rafscorp](https://github.com/rafscorp)
