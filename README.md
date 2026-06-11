# Uso de IA para geração de cenários de teste

## Função escolhida

```python
def potencia(a, b):
    return a ** b
```

## Prompt utilizado

```text
Atue como um professor de Teste de Software.

Tenho a seguinte função Python:

def potencia(a, b):
    return a ** b

Quero criar testes unitários usando unittest.

Liste pelo menos 6 cenários de teste para essa função.

Para cada cenário, informe:

- nome do cenário;
- entrada;
- resultado esperado;
- tipo do cenário: caso normal, caso de borda ou caso de erro.

Não gere código ainda.
```

## Cenários sugeridos pela IA

| ID  | Cenário                      | Entrada          | Resultado Esperado | Tipo   |
| --- | ---------------------------- | ---------------- | ------------------ | ------ |
| T01 | Potência positiva            | `potencia(2,3)`  | `8`                | Normal |
| T02 | Expoente zero                | `potencia(5,0)`  | `1`                | Borda  |
| T03 | Expoente um                  | `potencia(10,1)` | `10`               | Borda  |
| T04 | Base zero                    | `potencia(0,5)`  | `0`                | Borda  |
| T05 | Expoente negativo            | `potencia(2,-1)` | `0.5`              | Normal |
| T06 | Base negativa e expoente par | `potencia(-2,2)` | `4`                | Normal |

## Análise dos cenários

Todos os cenários sugeridos foram aceitos.

Os cenários T02, T03 e T04 foram considerados casos de borda por envolverem valores especiais que podem causar comportamentos diferentes em algumas implementações.

Os cenários T05 e T06 foram mantidos para verificar se a função lida corretamente com expoentes negativos e bases negativas.

Nenhum cenário precisou ser removido, pois todos contribuem para aumentar a cobertura dos testes.

## Código final dos testes

```python
def test_potencia(self):
    self.assertEqual(potencia(2, 3), 8)
    self.assertEqual(potencia(5, 0), 1)
    self.assertEqual(potencia(10, 1), 10)
    self.assertEqual(potencia(0, 5), 0)
    self.assertEqual(potencia(2, -1), 0.5)
    self.assertEqual(potencia(-2, 2), 4)
```

## Resultado da execução

Comando executado:

```bash
python -m unittest discover
```

Saída obtida:

```text
......
----------------------------------------------------------------------
Ran 6 tests in 0.001s

OK
```

## Conclusão

A utilização da Inteligência Artificial auxiliou na identificação de diferentes cenários de teste para a função `potencia(a, b)`. Após analisar os cenários sugeridos, foi possível criar testes mais completos, incluindo casos normais e casos de borda. Os testes foram executados com sucesso utilizando o framework `unittest`, contribuindo para aumentar a confiabilidade da função implementada.
