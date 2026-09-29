# 🕒 World Clock Java

<p align="center">
  <img src="https://img.shields.io/badge/Java-17%2B-orange?style=for-the-badge&logo=openjdk" alt="Java Version" />
  <img src="https://img.shields.io/badge/POO-Avançada-blue?style=for-the-badge" alt="POO" />
  <img src="https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge" alt="Status" />
</p>

<p align="center">
  Sistema simples, elegante e moderno em Java para manipulação e conversão de formatos de horários mundiais (padrão <b>24 horas / BRL</b> e padrão <b>12 horas AM/PM / US</b>), explorando recursos modernos de Programação Orientada a Objetos da linguagem.
</p>

---

## 🎯 Sobre o Projeto

O **World Clock** foi desenvolvido para demonstrar a modelagem orientada a objetos na prática, utilizando conceitos modernos do Java como **Sealed Classes**, **Pattern Matching for Switch**, polimorfismo e encapsulamento para converter formatos de horas de maneira segura e extensível.

### ✨ Funcionalidades

- 🇧🇷 **BRLClock (Padrão 24h)**: Exibição de horários no formato `HH : mm : ss` (00 a 23h).
- 🇺🇸 **USClock (Padrão 12h AM/PM)**: Exibição de horários no formato `hh : mm : ss AM/PM`.
- 🔄 **Conversão Bidirecional**: Converte horários entre os padrões BRL e US de forma fluida (`convert()`).
- 🛡️ **Validação de Entrada**: Tratamento automático de limites para horas, minutos e segundos.

---

## 🏗️ Arquitetura e Recursos Utilizados

```
src/
├── Clock.java      # Classe abstrata selada base (sealed class)
├── BRLClock.java   # Implementação do relógio brasileiro (24h)
├── USClock.java    # Implementação do relógio americano (12h AM/PM)
└── App.java        # Ponto de entrada (Main) com exemplos de uso
```

### 💡 Destaques de Implementação:
- **`sealed abstract class Clock permits BRLClock, USClock`**: Controle estrito sobre a hierarquia de herança.
- **Pattern Matching (`switch (clock)`)**: Conversão inteligente baseada no tipo do relógio fornecido em tempo de execução sem necessidade de *casts* manuais redundantes.

---

## 🚀 Como Executar

### Pré-requisitos
- **Java JDK 17+** instalado em sua máquina.
- Terminal / PowerShell ou uma IDE de sua preferência (VS Code, IntelliJ IDEA, Eclipse).

### Passo a passo

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/Hudson390/world-clock-java.git
   cd world-clock-java
   ```

2. **Compile as classes:**
   ```bash
   javac -d bin src/*.java
   ```

3. **Execute o programa:**
   ```bash
   java -cp bin App
   ```

---

## 💻 Exemplo de Uso

No arquivo [`App.java`](src/App.java):

```java
public class App {
    public static void main(String[] args) {
        // Criando e configurando um relógio no padrão brasileiro
        Clock brlClock = new BRLClock();
        brlClock.setHour(15);
        brlClock.setMinute(30);
        brlClock.setSecond(45);

        System.out.println("Horário BRL: " + brlClock.getTime());
        // Saída: 15 : 30 : 45

        // Convertendo para o formato americano (AM/PM)
        Clock usClock = new USClock().convert(brlClock);
        System.out.println("Horário US:  " + usClock.getTime());
        // Saída: 03 : 30 : 45 PM
    }
}
```

---

## 👨‍💻 Autor

Desenvolvido por **[Hudson](https://github.com/Hudson390)**.

---
<p align="center">Feito com ☕ e Java!</p>
