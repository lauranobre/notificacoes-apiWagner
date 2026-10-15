# Registro de Testes de Integração

Aluno: Laura Nobre
Grupo: Grupo 6 
Data: 15/10/2026

## Banco de teste

Nome do banco de teste: notificacoes_teste
Por que ele é separado do banco da API (uma frase): porque os testes de integração apagam todos os dados antes de cada teste, então o banco original não deve ser utilizado

## Testes escritos

| #   |         Arquivo                  |    O que o teste verifica    | Verde ou vermelho? |
| --- | -------------------------------- | ---------------------------- | ------------------ |
| 1   | evento.integration.test js       |    grava um evento           |       Verde        |
| 2   | participante.integration.test.js |e-mail inválido não é gravado |       Verde        |
| 3   | participante.integration.test.js |           Desafio            |      Vermelho      |

## Resultado

Linha "Tests:" da saída do npm run test:integration:

* Tests:       2 failed, 4 passed, 6 total 

## Defeito encontrado

Teste: ParticipanteService.atualizar (integração) > grava o nome novo no banco
Esperado: "Ana Maria"
Obtido: "Ana"
O que o usuário da API veria (a rota responde 200, mas...): O usuário iria ver uma mensagem de sucesso (starus 200), dando a falsa impressão que o nome foi alterado, mas ao verificar ele iria ver que o nome antigo continuou