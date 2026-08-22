# Especificação de Caso de Uso

## UC-01 — Gerar Rotina com IA

### 1. Visão Geral

**ID do Caso de Uso:** UC-01
**Nome:** Gerar Rotina com IA
**Atores:** Usuário, Inteligência Artificial (IA)

**Descrição:**

Este caso de uso permite que o usuário informe suas atividades, compromissos, horários disponíveis e prioridades para que o sistema, utilizando inteligência artificial, gere uma rotina personalizada.

O objetivo é auxiliar o usuário na organização de suas atividades, distribuindo as tarefas de acordo com os horários disponíveis e as prioridades informadas. Ao final, o usuário poderá visualizar a rotina gerada e utilizá-la para organizar seu dia.

---

## 2. Condições

### Pré-condições

O que obrigatoriamente precisa ser verdade para que este caso de uso possa começar:

1. O usuário deve estar autenticado no sistema.
2. O sistema deve estar disponível.
3. O sistema deve possuir acesso ao serviço de inteligência artificial.
4. O usuário deve fornecer as informações necessárias para a geração da rotina.

### Pós-condições

Após a conclusão do caso de uso:

1. Uma rotina personalizada é gerada pela IA.
2. A rotina é apresentada ao usuário.
3. A rotina gerada pode ser armazenada no sistema.
4. O usuário pode consultar posteriormente a rotina criada.

---

## 3. Fluxos de Eventos

### Fluxo Principal — Caminho Feliz

| Passo | Ação                                                                                                                                      |
| ----- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | O Usuário acessa a funcionalidade de geração de rotina.                                                                                   |
| 2     | O Sistema apresenta o formulário para informar as atividades, compromissos, horários disponíveis e prioridades.                           |
| 3     | O Usuário informa suas atividades e preferências.                                                                                         |
| 4     | O Usuário solicita a geração da rotina.                                                                                                   |
| 5     | O Sistema valida as informações fornecidas pelo Usuário.                                                                                  |
| 6     | O Sistema envia as informações para o serviço de Inteligência Artificial.                                                                 |
| 7     | A Inteligência Artificial analisa as informações recebidas e organiza as atividades de acordo com as preferências e horários disponíveis. |
| 8     | A Inteligência Artificial retorna uma sugestão de rotina para o Sistema.                                                                  |
| 9     | O Sistema apresenta a rotina gerada ao Usuário.                                                                                           |
| 10    | O Usuário visualiza a rotina e confirma a utilização da sugestão.                                                                         |
| 11    | O Sistema salva a rotina no cadastro do Usuário.                                                                                          |
| 12    | O Sistema informa ao Usuário que a rotina foi criada com sucesso.                                                                         |

---

### Fluxos Alternativos

#### FA-01 — Usuário deseja alterar a rotina

No passo 9 do Fluxo Principal, caso o Usuário não esteja satisfeito com a rotina gerada:

1. O Usuário solicita alterações na rotina.
2. O Sistema apresenta as opções disponíveis para alteração.
3. O Usuário informa quais alterações deseja realizar.
4. O Sistema envia as novas informações para a Inteligência Artificial.
5. A Inteligência Artificial gera uma nova sugestão de rotina.
6. O Sistema apresenta a nova rotina ao Usuário.
7. O Usuário confirma a rotina.
8. O Sistema salva a rotina atualizada.

---

#### FA-02 — Usuário não informa todas as atividades

No passo 5 do Fluxo Principal, caso o Usuário não informe alguma informação obrigatória:

1. O Sistema identifica que existem informações necessárias não preenchidas.
2. O Sistema informa ao Usuário quais informações precisam ser preenchidas.
3. O Usuário fornece as informações solicitadas.
4. O Sistema continua o Fluxo Principal a partir da validação das informações.

---

#### FA-03 — Usuário solicita uma nova rotina

Após a geração da rotina:

1. O Usuário seleciona a opção para gerar uma nova rotina.
2. O Sistema solicita as informações necessárias.
3. O Usuário informa ou altera suas atividades e preferências.
4. O Sistema solicita uma nova sugestão à Inteligência Artificial.
5. A IA gera uma nova rotina.
6. O Sistema apresenta a nova rotina ao Usuário.

---

## Fluxos de Exceção

### FE-01 — Serviço de IA indisponível

No passo 6 do Fluxo Principal, caso o Sistema não consiga acessar o serviço de Inteligência Artificial:

1. O Sistema identifica que o serviço de IA está indisponível.
2. O Sistema informa ao Usuário que não foi possível gerar a rotina naquele momento.
3. O Sistema orienta o Usuário a tentar novamente posteriormente.
4. O caso de uso é encerrado.

---

### FE-02 — Erro ao salvar a rotina

No passo 11 do Fluxo Principal, caso ocorra um erro ao salvar a rotina:

1. O Sistema identifica que não foi possível armazenar a rotina.
2. O Sistema informa ao Usuário que ocorreu um erro ao salvar a rotina.
3. O Sistema mantém a rotina apresentada para que o Usuário possa tentar salvá-la novamente.
4. O caso de uso permanece disponível para uma nova tentativa.

---

### FE-03 — Falha na comunicação com a IA

No passo 7 do Fluxo Principal, caso ocorra uma falha durante a comunicação com a Inteligência Artificial:

1. O Sistema identifica a falha na comunicação.
2. O Sistema informa ao Usuário que não foi possível processar a solicitação.
3. O Sistema oferece a opção de tentar novamente.
4. Caso o Usuário tente novamente, o Sistema realiza uma nova solicitação à IA.
5. Caso o Usuário não tente novamente, o caso de uso é encerrado.

---

## 4. Requisitos Especiais

* A geração da rotina deve ocorrer em um tempo adequado para proporcionar uma boa experiência ao usuário.
* As informações fornecidas pelo Usuário devem ser armazenadas de forma segura.
* O Sistema deve proteger os dados pessoais e as informações utilizadas para gerar a rotina.
* As comunicações entre o Sistema e o serviço de Inteligência Artificial devem ser realizadas de forma segura.
* As rotinas geradas devem ficar disponíveis para consulta posterior.
* O Sistema deve informar claramente ao Usuário quando uma rotina for gerada ou quando ocorrer algum problema durante o processo.
* As informações utilizadas pela IA devem ser organizadas de forma que possibilitem a geração de uma rotina coerente com os horários e prioridades informados pelo Usuário.
