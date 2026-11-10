# LEIdle

Wordle da praxe de Engenharia Informática da UMinho. Tem dois modos:

- **Clássico** ("Quem é a besta de hoje?"): 5 tentativas que comparam a primeira letra do nome, ano, número e género. Antes da última tentativa podes ver a foto desfocada.
- **Triggers** ("De quem caralho é este trigger?"): 8 tentativas, e cada erro mostra mais um trigger.

## Correr localmente

O `index.html` vai buscar o `leidle.json` com `fetch`, e isso não funciona se abrires o ficheiro com duplo clique. Corre um servidor na pasta:

```bash
python3 -m http.server
# abre http://localhost:8000
```

(ou `npx serve`, ou a extensão Live Server do VS Code)

## Adicionar pessoas

Edita o `leidle.json`:

```json
{ "ano": 2022, "numero": 21, "nome": "Scar", "genero": "M", "foto": null, "triggers": ["..."] }
```

- `numero` e `ano` são números, sem aspas.
- `genero` é `"M"` ou `"F"`.
- `foto` é o caminho para uma imagem (ex. `"fotos/scar.jpg"`) ou `null`.
- Quem não tem triggers fica fora do modo Triggers.

Adicionar ou remover pessoas muda a ordem das bestas a partir desse dia, por isso é melhor carregar os anos todos antes do lançamento.

## Configuração (topo do script no `index.html`)

- `MODO_TREINO`: pôr a `false` no lançamento.
- `LANCAMENTO`: o dia 0 do calendário de bestas.
- `CFG`: o número de tentativas de cada modo.

## Publicar

Settings → Pages no GitHub, branch `main`, pasta raiz. O GitHub Pages serve o JSON sem problemas.
