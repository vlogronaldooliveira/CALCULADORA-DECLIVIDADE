# Calculadora de Declividade

App para projeto e execução de redes de esgoto por gravidade: calcula as cotas de fundo (CF) e as inclinações de cada trecho a partir das cotas do terreno (CT), verifica a norma, desenha o perfil longitudinal e gera o memorial, a lista de materiais e as fichas de obra.

Funciona **offline**, no computador e no celular, sem login e sem servidor.

## O que ele faz

- **Rede principal e coletoras**: quantas redes quiser, cada coletora ligada na caixa onde deságua.
- **Ajuste automático das cotas**: distribui o desnível com inclinações uniformes, dentro da faixa definida (padrão 1% a 4,9%), da profundidade mínima da caixa (0,60 m), do recobrimento mínimo (0,30 m) e da profundidade de alerta (1,50 m) e máxima (2,00 m). Pode chegar **sem degrau** na caixa receptora ou no coletor público.
- **Tipos de caixa**: CI, TIL e PV. Pode nomear e tipar pela profundidade (CI até 1,00 m, PV acima), conforme a NBR 8160.
- **Verificações**: erros em vermelho, alertas em amarelo e uma tabela de avisos revistos pelo projetista.
- **Croqui** (perfil longitudinal com guitarra) de cada rede, com exportação em **DXF** para o AutoCAD.
- **Memorial descritivo** com critérios, fichas de execução (gabarito de cruzetas, escavação, "desce por metro"), croquis, procedimento executivo, quantitativos e checklist. Copia formatado para o Word.
- **Lista de materiais** no formato de tabela do CAD, em **Excel (.xlsx)** ou **DXF**.
- **Importação dos rótulos do CAD** (`CI 01 - REDE PRINCIPAL CT:... CF:...`) e exportação dos rótulos calculados.
- **Modo Obra**: um cartão por caixa, pensado para o celular, para registrar a CF executada e marcar o que foi feito.

## Como usar

1. Abra o app e clique em **+ Novo projeto em branco** (ou veja o **projeto de exemplo**).
2. Confira os **dados gerais** (sistema, faixa de inclinação, profundidades).
3. Lance a **rede principal**: caixa inicial (CT) e, para cada trecho, a caixa de chegada, o comprimento e o CT. Se ela termina num coletor público, informe a CF dele.
4. Use **+ Coletora** para cada rede coletora e escolha em **Deságua em** a caixa onde ela chega.
5. Clique em **Recalcular tudo**.

O guia "Como usar, em 5 passos" também está dentro do app.

### Levar um projeto para outro aparelho

Os projetos ficam salvos no próprio navegador de cada aparelho. Para passar um projeto adiante, use **Exportar projeto** (gera um arquivo `.json`) e, no outro aparelho, **Importar projeto**. O arquivo pode ir por WhatsApp, e-mail ou pendrive.

## Instalação

### No computador, sem instalar nada

Baixe o arquivo `calculadora-declividade-offline.html` e abra com dois cliques. Ele funciona sem internet.

### Publicar no GitHub Pages

1. Crie um repositório e envie todos os arquivos desta pasta (inclusive o `.nojekyll`).
2. No repositório, vá em **Settings → Pages**.
3. Em **Build and deployment**, escolha **Deploy from a branch**, a branch `main` e a pasta `/ (root)`. Salve.
4. Em um ou dois minutos, o endereço aparece na mesma página, no formato `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

### Instalar no celular (funciona offline depois)

Abra o endereço do GitHub Pages uma vez com internet e:

- **Android (Chrome)**: menu ⋮ → **Instalar app** (ou "Adicionar à tela inicial").
- **iPhone (Safari)**: botão Compartilhar → **Adicionar à Tela de Início**.

Depois disso, o app abre pelo ícone mesmo sem internet. Quando houver internet, ele busca sozinho a versão mais nova publicada no repositório.

## Arquivos

| Arquivo | Para quê |
|---|---|
| `index.html` | O app completo (página do GitHub Pages) |
| `calculadora-declividade-offline.html` | Cópia do app para abrir direto no computador |
| `sw.js` | Guarda o app no aparelho para funcionar offline |
| `manifest.webmanifest` | Nome e ícone para instalar no celular |
| `icon-*.png` | Ícones do app |
| `.nojekyll` | Faz o GitHub Pages publicar os arquivos como estão |

## Observações técnicas

- Normas de referência: ABNT NBR 8160 (esgoto) e NBR 10844 (águas pluviais). O app ajuda a verificar o projeto, mas não substitui a análise do responsável técnico nem o padrão da concessionária local.
- Usa a biblioteca SheetJS (Apache 2.0), embutida para gerar o Excel offline, e as fontes IBM Plex Mono e IBM Plex Sans Condensed (SIL Open Font License), também embutidas.
