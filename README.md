# Conhecendo o JUnit 5

Este projeto foi criado para apresentar e compartilhar meu aprendizado sobre o **JUnit 5**, a versão mais recente do principal framework de testes para Java. Testes automatizados são essenciais para garantir a qualidade do software, e o JUnit tornou-se padrão na indústria para escrever e executar testes unitários de maneira eficiente e estruturada.

---

## 🔍 O que é o JUnit 5?

O **JUnit 5** trouxe diversas melhorias em relação às versões anteriores, incluindo:

- **Suporte ao Java 8+**
- **Arquitetura modularizada**
- **Maior extensibilidade**

Ele é composto por três partes principais:

- **JUnit Platform**: Infraestrutura que permite a execução de testes em diferentes engines.
- **JUnit Jupiter**: API que traz suporte a novas anotações e funcionalidades modernas para testes no JUnit 5.
- **JUnit Vintage**: Suporte para execução de testes escritos em versões anteriores do JUnit (JUnit 3 e 4).

Na minha experiência, essa nova arquitetura tornou o JUnit 5 muito mais flexível e poderoso, possibilitando criar testes mais organizados e eficientes.

---

## 🔄 Ciclo de Vida de um Teste

O JUnit 5 introduz um conjunto de anotações que controlam o ciclo de vida dos testes, garantindo que a configuração e a limpeza dos recursos ocorram na ordem correta. As principais anotações são:

- `@BeforeAll` → Executa um trecho de código antes de todos os testes da classe.
- `@BeforeEach` → Executa um trecho antes de cada teste individual.
- `@Test` → Define um método de teste, contendo a lógica de verificação (asserts).
- `@AfterEach` → Executa um trecho após cada teste.
- `@AfterAll` → Executa um trecho após todos os testes da classe.

Esse ciclo de vida me permite configurar um ambiente adequado antes da execução dos testes e limpar recursos após sua finalização.

---

## 🛠 Exemplo de Estrutura de Teste com JUnit 5

Abaixo está um exemplo de teste unitário utilizando o JUnit 5 para uma classe `Calculadora`:

```java
import org.junit.jupiter.api.BeforeAll;
import org.junit.jupiter.api.AfterAll;
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

class CalculadoraTest {

    @BeforeAll
    static void beforeAll() {
        System.out.println("Antes de tudo!");
    }

    @Test
    void testSoma() {
        int resultado = 2 + 3;
        assertEquals(5, resultado, "A soma deve ser 5");
    }

    @AfterAll
    static void afterAll() {
        System.out.println("Depois de tudo!");
    }
}
```

**Explicação do código:**
- Antes de todos os testes, a mensagem `"Antes de tudo!"` será impressa (`@BeforeAll`).
- O método `testSoma()` valida se a soma `2 + 3` resulta em `5`, usando `assertEquals()`.
- Após a execução de todos os testes, a mensagem `"Depois de tudo!"` será impressa (`@AfterAll`).

---

## ✅ Conclusão

O **JUnit 5** trouxe grandes melhorias para a escrita e execução de testes em Java, tornando-os mais organizados e flexíveis. Com suas novas APIs, ciclo de vida bem definido e maior modularização, ele se tornou minha escolha ideal para testes unitários modernos.

**Dominar o JUnit 5 é fundamental para qualquer desenvolvedor que deseja garantir a qualidade do código e evitar problemas em produção.**

---

> Projeto criado para fins educacionais e para consolidar meu aprendizado sobre testes automatizados com JUnit 5.
