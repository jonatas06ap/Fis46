# Prompt para relatório de laboratório FIS-46

Cole este prompt (ajustando o nome da pasta do experimento, ex. `E03`) no início de uma
nova conversa para gerar o relatório daquele experimento, seguindo exatamente as regras
já validadas com o professor Argemiro Soares da Silva Sobrinho (Turma 2).

---

## Prompt

Faça o relatório do experimento cujo roteiro está em `Documents/` (arquivo PDF
"EXX - <nome do experimento>.pdf"). Os dados coletados estão em `Data/`
(ou em `Documents/dados.txt ou similar`, se não existir pasta `Data`). As imagens (capturas de
tela do osciloscópio) estão em `Images/`.

Use `library.bib` de `Documents/` (ou de um `build_example/` anterior) como base de
referências. Relatórios anteriores em `build_example/` (E02/E03) servem só de
referência de **conteúdo/qualidade de discussão**, não de layout visual — eles usam
`revtex4-2`, que foi **substituído** pelo template oficial descrito em "Layout
obrigatório" abaixo (Times New Roman, espaço duplo, seções numeradas manualmente).
Gere o novo relatório numa pasta `build/` dentro deste experimento, pronta para
exportar para o Overleaf.

Regras obrigatórias (definidas pelo professor, mais rígidas que o `templete.tex`
genérico da disciplina):

### Estrutura do relatório
- **NÃO incluir seções de Introdução nem Metodologia.** A estrutura final deve ser
  exatamente: título/autores/afiliação → **Resumo** → **Resultados
  e Discussão** → **Conclusão** → **Referências Bibliográficas**.
- **Sem capa separada com logo/página de rosto.** O template oficial da disciplina
  (slides "Lab FIS46 – Aula 01", confirmado pelo professor) não usa página de capa:
  o documento começa direto no bloco título/autores/afiliação da primeira página.
  Ver "Layout obrigatório" abaixo para o formato exato desse bloco.
- Qualquer contexto teórico (equações, dedução de fórmulas usadas) e qualquer
  descrição do circuito/procedimento experimental deve ser incorporado como
  parágrafo(s) introdutório(s) da própria seção "Resultados e Discussão" — sem
  subtítulo próprio — e não como seção separada.
- **Resumo**: máximo 15 linhas, sem citações numéricas de referências (só citação
  explícita se for essencial).
- **Resultados e Discussão**: 3–5 páginas. Apresentar tabelas e gráficos/figuras
  (com dados brutos, não só resultados finais). Resultado e discussão são
  apresentados juntos, nunca em subseções separadas ("apresenta-se e discute-se
  simultaneamente").
- **Conclusão**: máximo 15 linhas, retomando os resultados quantitativos principais.
- **Referências**: reais e verificáveis (nunca inventar autores/DOIs). Usar
  `library.bib` existente como base (ex. Vuolo para teoria de erros) e adicionar
  referências de livro-texto pertinentes ao fenômeno físico do experimento.

### Layout obrigatório (slides "Lab FIS46 – Aula 01", confirmado pelo professor)
Este template é literal — segue exatamente a formatação exigida, não o estilo
`revtex4-2` usado em relatórios anteriores (E02/E03), que **não deve mais ser usado**
a partir daqui.
- Fonte **Times New Roman**, corpo tamanho 12, **alinhamento justificado**,
  **espaçamento duplo** (documento inteiro, do título às referências).
- Sem página de capa (ver seção "Estrutura do relatório" acima); primeira página
  começa direto neste bloco:
  1. **Título do experimento**: tamanho 14, negrito, centralizado. Espaço duplo
     depois.
  2. **Autores**: tamanho 12, nomes completos, centralizados, na ordem alfabética
     já definida; usar marcador numérico sobrescrito (¹²³...) por autor apenas se
     houver lista de e-mails (ver item 4).
  3. **Afiliação**: tamanho 10, centralizada — instituição, laboratório/disciplina
     (ex. "Instituto Tecnológico de Aeronáutica, Laboratório de Física
     Experimental (FIS-46)"), professor responsável, cidade/UF, data.
  4. **E-mails dos autores** (opcional): uma linha por autor, formato
     "¹E-eletrônico: endereço@dominio", tamanho 10, alinhado à esquerda, logo
     abaixo da afiliação. **Nunca inventar e-mail de colega** — só incluir se o
     usuário fornecer; caso contrário omitir este item inteiro (mantendo os
     marcadores numéricos nos autores só se algum e-mail for dado).
  5. Espaço duplo antes do resumo.
- **"RESUMO"**: cabeçalho em negrito, maiúsculo, tamanho 12, sem numeração, sem
  citação numérica.
- Seções seguintes **numeradas** (negrito, tamanho igual ao corpo, alinhadas à
  esquerda — não centralizadas), exatamente: "1. RESULTADOS E DISCUSSÃO",
  "2. CONCLUSÃO", "3. REFERÊNCIAS BIBLIOGRÁFICAS" (título em maiúsculo).
- Tabelas muito grandes: reduzir a fonte da tabela para tamanho 10 se necessário
  para caber na página.
- Implementação sugerida em LaTeX: `\documentclass[12pt]{article}` +
  `\usepackage{newtxtext,newtxmath}` (substitui Computer Modern por Times) +
  `\usepackage{setspace}` com `\doublespacing` + `\usepackage{titlesec}` para
  forçar `\section` a renderizar "N. TÍTULO EM MAIÚSCULO" negrito sem mudar de
  tamanho de fonte. Bibliografia numérica: `\bibliographystyle{plain}` (ou
  equivalente numérico) com `\bibliography{library}`, seção
  "Referências Bibliográficas" como `\section` normal (numerada, não `\section*`).

### Regras gerais de conteúdo (do PDF de instruções da Aula 01)
- Texto justificado, sem tópicos/itens na descrição do experimento.
- Toda grandeza experimental deve vir acompanhada de incerteza, inclusive em
  tabelas; não misturar erro sistemático com estatístico; propagar erros
  corretamente (citar Vuolo1996) sempre que uma grandeza for calculada a partir de
  outras.
- Incluir tabela com **dados brutos** (não só resultados finais) para conferência.
- Legendas de tabela ficam **acima** da tabela; legendas de figura ficam **abaixo**.
- Evitar muitas figuras/tabelas soltas — agrupar em uma única figura multi-painel
  com legenda única e painéis identificados por letras (a), (b), (c)... sempre que
  fizer sentido.
- Toda figura/tabela deve ser citada pelo número e comentada no texto.
- Nenhuma seção começa com tabela ou figura — sempre com texto antes.
- Incluir análise de resíduos (não pular esse ponto).
- Se houver erro experimental (ex. inversão de sinal, discrepância sistemática),
  **discutir abertamente a causa provável**, nunca esconder ou ignorar — isso vale
  nota, não tira nota.
- Gráficos precisam de eixo, unidade e legenda.

### Autoria e capa
- **Perguntar ao usuário** (nunca inventar): nomes completos dos integrantes
  presentes (ordem alfabética pelo primeiro nome), número do grupo/bancada, e se
  quer um título específico (padrão: usar o mesmo título do roteiro do experimento).
- Grupo padrão desta disciplina (confirmar se mudou): Turma 2, Grupo 5 — Gael
  Vinícius Maia Sampaio, Jônatas Augusto de Paula, José Guilherme Correia de
  Menezes. Professor: Argemiro Soares da Silva Sobrinho.
- Nome do arquivo final: `EXX_Nome1_Nome2_Nome3.pdf` (primeiro nome de cada autor,
  ordem alfabética; usar nome+sobrenome só se houver conflito de primeiro nome).

### Processamento das imagens
- Converter `.bmp` → `.png` (ImageMagick `convert`).
- Cortar a barra de menu lateral (não é dado, é interface) e o rodapé com
  data/modelo do aparelho, mantendo a área do gráfico e a barra de leituras
  (escalas V/div, tempo/div, modo) — **conferir visualmente o corte antes de
  aplicar em lote**, pois a geometria pode variar entre experimentos.
- Antes de usar qualquer imagem em uma figura, **verificar a ordem/rotulagem**:
  cruzar o nome do arquivo com os dados numéricos da tabela correspondente
  (recontar tangências/picos na imagem quando o valor determinar uma conclusão
  importante, especialmente se algo parecer inconsistente visualmente).
- Atenção à convenção de contagem de tangências em figuras de Lissajous: conta-se
  o toque em **uma única linha tangente** (só o topo OU só a base — dá o mesmo
  valor por simetria), nunca topo+base somados.
- Se uma captura estiver visivelmente degradada (traço muito pontilhado/serrilhado
  por alta razão de frequência ou baixa densidade de amostragem), isso é inerente
  à captura original, não um problema do pipeline de conversão — verificar por
  checksum/comparação antes de supor que uma nova imagem enviada é diferente.
  Só aplicar pós-processamento cosmético (ex. `-morphology Dilate Disk:1` do
  ImageMagick) **mediante confirmação do usuário**, deixando claro que é só
  estético, sem alterar o conteúdo científico.

### Pasta `build/`
- Deve ser autossuficiente para abrir direto no Overleaf: `.tex` principal,
  `capa.tex`, `library.bib`, `LogoITA.jpg`, e `figs/` com todas as imagens
  usadas (já cortadas/processadas). **Não** incluir PDFs do roteiro, dados brutos,
  ou slides de instrução dentro de `build/`.
- Compilar (`pdflatex` → `bibtex` → `pdflatex` ×2) **de dentro da própria pasta
  `build/`** para garantir que ela compila sozinha, sem depender de arquivos fora
  dela.
- Checar o log de compilação por `Warning`/`undefined`/`Overfull`/`Underfull`
  antes de considerar concluído.
- Renderizar as páginas finais (`pdftoppm`) e revisar visualmente antes de
  reportar como pronto.
- Limpar arquivos auxiliares de compilação (`.aux`, `.log`, `.bbl`, `.blg`) ao
  final, tanto na pasta de trabalho quanto em `build/`.

### Avaliação e entrega (slides "Lab FIS46 – Aula 01")
- Nota do relatório = 2,0 (Resumo) + 6,0 (Resultados e Discussão, 3–5 páginas) +
  2,0 (Conclusão) = 10,0 pontos.
- Entrega pelo Google Classroom (turma FIS46-T2), até 23:59h da semana seguinte à
  realização do experimento — **após o prazo, nota é ZERO**, sem exceção.
- Só é preciso um integrante do grupo enviar o relatório.
- Nome do arquivo: `EXX_Aluno1_Aluno2_..._AlunoN.pdf` (XX = número do experimento
  com dois dígitos, nomes em ordem alfabética; usar nome + um sobrenome só para
  desambiguar autores com o mesmo primeiro nome).

### Coisas a **perguntar** em vez de assumir
- Nomes dos autores presentes e número do grupo (se puder ter mudado).
- Título do relatório, se não for para usar o do roteiro.
- Qualquer valor de componente/tolerância não fornecido nos dados nem no roteiro
  (ex. tolerância de resistores/capacitores) — pode adotar um valor nominal
  típico do componente, mas deixe explícito no texto que é uma suposição.
- E-mails dos autores para o bloco de afiliação (ver "Layout obrigatório") — nunca
  inventar; se não fornecidos, omitir o item inteiro do template.

### Cálculos e geração de imagens
 - Deixe os calculos salvos em um arquivo .ipynb na raiz
 - Use o mesmo notebook para processar possiveis imagens

---

*Este prompt resume as decisões tomadas ao longo do relatório do experimento E02
("Medida de Defasagem entre Duas Ondas"). Ajuste o nome do experimento e da pasta
conforme necessário; as regras de estrutura, formatação e processo valem para
todos os experimentos da disciplina.*
