### Cenário do Projeto

## Agente de IA para Rotinas# Especificações de Caso de Uso

## UC-01 - Gerador de Rotina com IA
**Nome:** NextIA
 
## Ator
- Usuário
- Inteligência Artificial (IA)
## Descrição
 
Esse caso de uso mostra como o usuário pode criar uma rotina personalizada usando uma IA. O usuário informa suas atividades, horários livres e prioridades, e a IA organiza tudo em uma rotina.
 
## Pré-condições
 
- O usuário precisa estar logado no sistema.
- O sistema precisa estar funcionando.
- O usuário precisa preencher as informações pedidas.
## Pós-condições
 
- A rotina é criada e mostrada para o usuário.
- A rotina fica salva e pode ser vista depois.
## Fluxo Principal
 
1. O usuário entra na tela de criar rotina.
2. O sistema mostra o formulário (atividades, horários, prioridades).
3. O usuário preenche e envia.
4. O sistema confere se os dados estão certos.
5. O sistema manda os dados para a IA.
6. A IA organiza as atividades e monta a rotina.
7. O sistema mostra a rotina para o usuário.
8. O usuário confirma que quer usar essa rotina.
9. O sistema salva a rotina.
## Fluxos Alternativos
 
**A1 - Usuário quer mudar a rotina**
1. No passo 7, o usuário pede pra alterar algo.
2. O sistema deixa editar.
3. O usuário confirma a mudança.
4. O sistema salva a nova versão.
**A2 - Usuário quer gerar de novo**
1. O usuário não gostou da rotina e pede outra.
2. O sistema manda os dados de novo para a IA.
3. A IA gera uma nova rotina.
4. O sistema mostra a nova rotina.
## Fluxos de Exceção
 
**E1 - IA fora do ar**
1. O sistema não consegue falar com a IA.
2. O sistema avisa o usuário que deu erro.
3. Pede pra tentar de novo mais tarde.
**E2 - Faltou preencher algum campo**
1. O sistema vê que falta informação.
2. Avisa o usuário o que falta preencher.
3. O usuário completa e envia de novo.
**E3 - Rotina veio com horário repetido**
1. O sistema percebe que tem duas atividades no mesmo horário.
2. O sistema pede pra IA gerar de novo.
3. Se continuar dando erro, avisa o usuário pra ajustar as informações.
## Regras
 
- Não pode ter duas atividades no mesmo horário.
- O sistema tem que respeitar os compromissos fixos que o usuário colocou.
## Requisitos Especiais
 
- A rotina deve ser gerada rápido, sem o usuário esperar muito.
- Os dados do usuário devem ficar salvos de forma segura.