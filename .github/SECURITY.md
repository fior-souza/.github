# Segurança

## Reportar uma vulnerabilidade

**Não abra issue pública.** Fale direto com os mantenedores da organização
([@carlosfior](https://github.com/carlosfior),
[@DevGabrielSouza](https://github.com/DevGabrielSouza)) descrevendo o que dá pra
reproduzir e o impacto que você enxerga. Respondemos em até 5 dias úteis.

## O que nunca entra num repo, issue ou PR

- **Segredo de qualquer tipo**: chave, token, senha, `.pem`, string de conexão.
  Nem em print, nem como exemplo. Segredo que apareceu num commit é segredo
  vazado: **rotacione primeiro**, limpe o histórico depois.
- **Dado de paciente**: nome, CPF, prontuário, leito identificado, print com
  paciente real. Nenhum repo nosso é ambiente tratado pra PHI.
- **Dado pessoal de cliente real** em fixture, seed ou teste. Use dado sintético.

## Gate de segredo na CI

Scan de segredo `skipped` ou ausente **não é aprovação de segurança**: fica
registrado no PR como gate pendente.

## Fronteiras que exigem teste negativo

Isolamento por tenant, autorização, link público, LGPD, concorrência, migration
e backfill. Nessas, o teste que prova que **não** dá pra atravessar vale mais
que o teste que prova que funciona.
