# Diagrama de Classes – Sistema de Geração de Rotinas

```mermaid
classDiagram
    direction LR

    class Usuario {
        -int id
        -String nome
        -String email
        -String senhaHash
        +cadastrarAtividade(atividade) void
        +cadastrarCompromisso(compromisso) void
        +definirDisponibilidade(horario) void
        +solicitarRotina(periodo) Rotina
    }

    class Atividade {
        -int id
        -String titulo
        -String descricao
        -int duracaoEstimadaMin
        -Prioridade prioridade
        -Date prazo
        -StatusAtividade status
        +validar() boolean
        +editar() void
        +remover() void
    }

    class Compromisso {
        -int id
        -String titulo
        -DateTime inicio
        -DateTime fim
        -String local
        -boolean fixo
        +validar() boolean
        +conflitaCom(outro) boolean
    }

    class HorarioDisponivel {
        -int id
        -DiaSemana diaSemana
        -Time horaInicio
        -Time horaFim
        +duracaoMin() int
        +sobrepoe(outro) boolean
    }

    class Rotina {
        -int id
        -Date dataInicio
        -Date dataFim
        -DateTime geradaEm
        -StatusRotina status
        +adicionarBloco(bloco) void
        +ajustar() void
        +exportar() void
    }

    class BlocoRotina {
        -int id
        -DateTime inicio
        -DateTime fim
        -String justificativa
        -boolean concluido
        +marcarConcluido() void
    }

    class GeradorRotina {
        -ServicoIA servicoIA
        +gerar(usuario, periodo) Rotina
        -montarPrompt(atividades, compromissos, horarios) String
        -interpretarResposta(resposta) List~BlocoRotina~
        -validarConflitos(blocos) boolean
    }

    class ServicoIA {
        <<interface>>
        +enviarPrompt(prompt) String
    }

    class ServicoIAExterno {
        -String apiKey
        -String modelo
        +enviarPrompt(prompt) String
    }

    class Prioridade {
        <<enumeration>>
        BAIXA
        MEDIA
        ALTA
        URGENTE
    }

    class StatusAtividade {
        <<enumeration>>
        PENDENTE
        EM_ANDAMENTO
        CONCLUIDA
    }

    class StatusRotina {
        <<enumeration>>
        GERADA
        AJUSTADA
        ARQUIVADA
    }

    class DiaSemana {
        <<enumeration>>
        SEGUNDA
        TERCA
        QUARTA
        QUINTA
        SEXTA
        SABADO
        DOMINGO
    }

    Usuario "1" --> "0..*" Atividade : possui
    Usuario "1" --> "0..*" Compromisso : possui
    Usuario "1" --> "1..*" HorarioDisponivel : define
    Usuario "1" --> "0..*" Rotina : solicita

    Rotina "1" *-- "1..*" BlocoRotina : composta por
    BlocoRotina "0..*" --> "0..1" Atividade : referencia
    BlocoRotina "0..*" --> "0..1" Compromisso : referencia

    GeradorRotina ..> Usuario : usa dados de
    GeradorRotina ..> Rotina : cria
    GeradorRotina --> ServicoIA : depende de
    ServicoIAExterno ..|> ServicoIA : implementa

    Atividade --> Prioridade
    Atividade --> StatusAtividade
    Rotina --> StatusRotina
    HorarioDisponivel --> DiaSemana****