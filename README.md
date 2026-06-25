# 📋 Relatório de Validação e Testes Manuais - AgendaLab

**Analista de Qualidade:** Talison Vieira Brito  
**Ambiente:** [AgendaLab QA](https://agendalabqa.vercel.app/)  
**Data da Execução:** 24/06/2026  
**Navegador Utilizado:** Google Chrome (Versão 149.0.7827.197 - 64 bits)

### 🎯 Objetivo
Validar o correto funcionamento do fluxo de Novo Agendamento na plataforma AgendaLab, garantindo a conformidade com as regras de negócio estabelecidas e mitigando riscos antes do lançamento em produção.

### 🧠 O que é BDD?
O BDD (*Behavior-Driven Development*) é uma prática de desenvolvimento de software que visa integrar as regras de negócio com a especificação técnica e os testes. Ele utiliza uma linguagem natural, simples e estruturada para descrever como o sistema deve se comportar do ponto de vista do usuário final.

### 🔑 Massa de Teste
* **Usuário:** `usuario_normal`
* **Senha:** `secret123`

---

## 🧪 Cenários de Teste (CT)

### 👤 Campo: Nome

**CT-01: Validar campo Nome sendo obrigatório**
* **Status:** 🟢 Aprovado
* **Evidência:** `ayihl-ktju1.jpg`
* **Dado** que o usuário está na tela de agendamento
* **Quando** ele tenta confirmar o agendamento deixando o campo "Nome" vazio
* **Então** o sistema deve exibir uma mensagem de erro informando que o campo "Nome" é obrigatório
* **E** o agendamento não deve ser processado
* **Resultado esperado:** O sistema deve impedir o envio do formulário e exibir a mensagem de alerta correspondente à obrigatoriedade do campo.
* **Resultado obtido:** O formulário foi bloqueado e a mensagem "O campo Nome é obrigatório" foi exibida corretamente.

**CT-02: Validar campo Nome aceitando apenas letras e espaço (exceto primeiro caractere)**
* **Status:** 🔴 Reprovado
* **Evidência:** `aot3h-xcow2.jpg` , `adi9j-ottsf.jpg`
* **Dado** que o usuário está na tela de agendamento
* **Quando** ele insere no campo "Nome" números, caracteres especiais (#$%) e inicia com espaço
* **Então** campo não deve aceitar a digitação dos mesmos
* **Resultado esperado:** O campo deve rejeitar caracteres inválidos (números/símbolos) e impedir espaços em branco no início da entrada.
* **Resultado obtido:** O sistema permitiu a inserção de caracteres numéricos, especiais e espaço no início do campo, sem apresentar validações.

### 📞 Campo: Telefone

**CT-03: Validar campo Telefone sendo obrigatório**
* **Status:** 🟢 Aprovado
* **Evidência:** `aekag-un3mk.jpg`
* **Dado** que o usuário está na tela de agendamento
* **Quando** ele tenta confirmar o agendamento deixando o campo "Telefone" vazio
* **Então** o sistema deve exibir uma mensagem de erro informando que o campo "Telefone" é obrigatório
* **Resultado esperado:** Exibição de um alerta indicando a obrigatoriedade do preenchimento para avançar com o agendamento.
* **Resultado obtido:** O preenchimento foi validado como obrigatório através da exibição do alerta em tela.

**CT-04: Validar campo Telefone aceitando apenas números e caracteres da máscara**
* **Status:** 🔴 Reprovado
* **Evidência:** `a7gse-hbblf.jpg`
* **Dado** que o usuário está digitando no campo "Telefone"
* **Quando** ele digita letras ou caracteres especiais (fora os caracteres da máscara)
* **Então** o campo deve ignorar esses caracteres, mantendo apenas os números
* **Resultado esperado:** A entrada de texto deve ser restrita a dígitos numéricos, formatando automaticamente o texto de acordo com a máscara telefônica estabelecida.
* **Resultado obtido:** A máscara falhou em restringir a entrada, permitindo a digitação livre de caracteres alfabéticos e símbolos especiais.

### 🩺 Campos: Serviço e Profissional

**CT-05: Validar campo Serviço sendo obrigatório**
* **Status:** 🟢 Aprovado
* **Evidência:** `ab2gq-w82xb.jpg`
* **Dado** que
