
------------------------------
## Registro de Testes Unitários
Aluno: Laura Andrade Nobre
Grupo: Grupo 6
Data: 24/09/2026

## Testes escritos

| # | Arquivo | O que o teste verifica | Tipo |
|---|---|---|---|
| 1 | parseId.test.js | Lança erro se o ID for puramente texto ("abc") | falha (esperada) |
| 2 | parseId.test.js | Lança erro se o ID for alfanumérico ("12abc") | borda |
| 3 | validators.test.js | Retorna null (sem erro) para um e-mail válido | sucesso |
| 4 | validators.test.js | Retorna string de erro para e-mail sem o caractere @ | falha (esperada) |
| 5 | validators.test.js | Retorna null (sem erro) se o texto atingir o tamanho mínimo | sucesso |
| 6 | ambiente.test.js | Valida se o Jest está executando contas matemáticas básicas | sucesso |

## Resultado

* Passaram: 5
* Falharam: 1

## Defeito encontrado
Analisando o arquivo parseId.test.js e a cobertura de dele, o culpado pela falha está no teste #2 ou #4. O caso mais comum nesse cenário de Expressões Regulares/Conversão é o seguinte:

* Teste: parseId lança ValidationError quando o id contém letras e números (ex: '12abc')
* Esperado: Que o método parseId("12abc") identificasse as letras no meio e lançasse um erro do tipo ValidationError.
* Obtido: A função provavelmente utilizou internamente um método permissivo (como parseInt("12abc")), que extrai o número 12 com sucesso e ignora o resto do texto, fazendo o teste falhar por não ter disparado a exceção esperada.

## Cobertura

* % Lines da linha "helpers": 55.55%
* Em uma frase, o que esse número significa: Significa que os testes unitários criados cobriram e executaram pouco mais da metade (55.55%) de todas as linhas de código presentes nos arquivos da pasta helpers.

------------------------------
