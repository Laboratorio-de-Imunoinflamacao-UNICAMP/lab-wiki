# Guia para organização e publicação de projetos no GitHub

**Laboratório de Imunoinflamação — UNICAMP**

Este guia apresenta orientações para organizar, documentar e compartilhar códigos, análises e materiais computacionais associados a projetos científicos desenvolvidos no laboratório.

O objetivo é facilitar a colaboração entre pesquisadores, preservar o histórico das análises e contribuir para a **transparência e reprodutibilidade científica**.

Não é necessário ter experiência prévia com Git ou GitHub para seguir estas instruções.

---

## 1. Antes de começar: Git e GitHub

**Git** é uma ferramenta de controle de versões. Ele registra as modificações realizadas em arquivos ao longo do tempo, permitindo recuperar versões anteriores.

**GitHub** é uma plataforma que hospeda repositórios Git e facilita o compartilhamento e a colaboração.

Um **repositório (repository)** é o espaço que reúne os arquivos e o histórico de versões de um projeto.

Os principais comandos são:

| Comando | Função |
|---|---|
| `git status` | Verifica alterações nos arquivos |
| `git add` | Seleciona alterações para o próximo registro |
| `git commit` | Salva uma versão no histórico local |
| `git push` | Envia os commits para o GitHub |
| `git pull` | Atualiza a cópia local com alterações do GitHub |
| `git log --oneline` | Mostra o histórico de commits |

**Importante:** salvar um arquivo no computador não atualiza automaticamente o GitHub. É necessário registrar as alterações e enviá-las.

---

## 2. Organização dos repositórios

Recomendamos criar **um repositório para cada projeto científico ou publicação**, agrupando os materiais necessários para compreender e reproduzir as análises.

Utilize nomes curtos, descritivos e relacionados ao estudo.

Exemplos:

- `scRNA-seq_Neutrophils_Ffar2`
- `scRNA-seq_IEC_Hcar2`
- `RNA-seq_Inflammation_Project`

### Estrutura sugerida

```text
project/
├── README.md
├── .gitignore
├── LICENSE
├── environment.yml
├── scripts/
├── notebooks/
├── figures/
├── tables/
├── reports/
└── data/
    └── README.md
```

| Arquivo/pasta | Conteúdo |
|---|---|
| `README.md` | Descrição do projeto e instruções para reproduzir as análises |
| `.gitignore` | Arquivos que não devem ser monitorados pelo Git |
| `LICENSE` | Condições de uso e reutilização, quando definidas |
| `environment.yml` | Dependências e versões dos programas |
| `scripts/` | Scripts Python, R, Bash e funções reutilizáveis |
| `notebooks/` | Notebooks Jupyter contendo análises e explicações |
| `figures/` | Figuras relevantes para o estudo |
| `tables/` | Tabelas pequenas com resultados processados |
| `reports/` | Relatórios de análise, HTML ou PDF |
| `data/README.md` | Descrição dos dados e indicação de onde obtê-los |

Essa estrutura é uma sugestão, não uma exigência. Os diretórios devem ser adaptados às necessidades de cada projeto.

### Recomendações de organização

- Utilize nomes de arquivos claros e informativos.
- Organize notebooks na sequência das análises, por exemplo, `01_quality_control.ipynb`, `02_clustering.ipynb`.
- Separe funções reutilizáveis em scripts quando apropriado.
- Evite arquivos duplicados ou versões como `final_v2_final_corrigido.py`.
- Mantenha somente resultados necessários à documentação e reprodução do estudo.

---

## 3. O que deve ser disponibilizado?

Para projetos associados a publicações científicas, recomendamos incluir:

- Códigos utilizados nas análises apresentadas no manuscrito.
- Notebooks ou scripts que documentem as principais etapas de processamento.
- Parâmetros e critérios adotados nas análises.
- Scripts para geração das figuras e tabelas.
- Versões de bibliotecas e softwares utilizados.
- Identificadores públicos dos dados, quando disponíveis (GEO, SRA, ENA, Zenodo etc.).
- Instruções para executar ou reproduzir as análises.
- Referência do artigo, DOI ou preprint, quando disponível.

**Não é necessário disponibilizar os dados brutos diretamente no GitHub.** Eles podem ser depositados em repositórios científicos apropriados, com seus respectivos identificadores documentados no README.

### O que não deve ser enviado

- Dados brutos de sequenciamento, como FASTQ e BAM.
- Objetos grandes de análise, como H5AD, quando não forem necessários no repositório.
- Arquivos temporários e intermediários volumosos.
- Senhas, tokens e credenciais.
- Dados confidenciais ou identificáveis.
- Resultados não autorizados para compartilhamento.

Para dados humanos ou sensíveis, respeite as aprovações éticas, consentimentos, restrições de acesso e políticas institucionais aplicáveis.

---

## 4. Como escrever um bom README

Todo repositório deve ter um `README.md`.

Ele funciona como a página de apresentação do projeto e deve permitir que outro pesquisador compreenda sua finalidade e saiba como utilizar os arquivos.

### Informações recomendadas

1. **Título do projeto** — nome do estudo.
2. **Descrição** — objetivo e contexto científico.
3. **Desenho experimental** — grupos, amostras e principais comparações.
4. **Dados utilizados** — origem, identificadores e condições de acesso.
5. **Estrutura do repositório** — descrição das principais pastas.
6. **Métodos computacionais** — programas, pacotes e parâmetros relevantes.
7. **Como reproduzir** — ordem de execução e instruções básicas.
8. **Referência** — artigo, preprint ou DOI.
9. **Contato** — responsável pelas análises ou manutenção do código.

Para projetos em desenvolvimento, indique que o repositório ainda está sendo atualizado.

---

## 5. Primeiro acesso pelo terminal

Os comandos abaixo devem ser executados no terminal Linux.

É necessário ter o Git e o GitHub CLI (`gh`) instalados.

### 5.1. Verificar a instalação

```bash
git --version
gh --version
```

### 5.2. Entrar na conta GitHub

```bash
gh auth status
```

Se ainda não estiver autenticado:

```bash
gh auth login
```

Selecione `GitHub.com`, autenticação por `HTTPS` e a opção de login pelo navegador. Siga as instruções exibidas.

A autenticação é pessoal. Não compartilhe suas credenciais com outras pessoas.

---

## 6. Criar um novo repositório na organização

Antes de criar o repositório, confirme com os responsáveis pelo projeto se ele deve ficar privado ou público.

**Recomendação:** projetos em desenvolvimento devem começar como privados. A abertura pública deve ser autorizada pelos responsáveis pelo estudo.

### 6.1. Escolher onde guardar os repositórios no computador

```bash
mkdir -p ~/github
cd ~/github
```

### 6.2. Criar o repositório na organização

Substitua `NOME_DO_REPOSITORIO` pelo nome escolhido.

```bash
gh repo create Laboratorio-de-Imunoinflamacao-UNICAMP/NOME_DO_REPOSITORIO --private --add-readme --clone
```

Esse comando cria um repositório privado no GitHub, adiciona um README inicial e baixa uma cópia para o computador.

É necessário ter permissão para criar repositórios na organização.

### 6.3. Entrar na pasta do repositório

```bash
cd NOME_DO_REPOSITORIO
```

Se o repositório já existir no GitHub, não é necessário criá-lo novamente. Utilize:

```bash
gh repo clone Laboratorio-de-Imunoinflamacao-UNICAMP/NOME_DO_REPOSITORIO
cd NOME_DO_REPOSITORIO
```

**Atenção:** criar um repositório e copiar arquivos modifica o computador e/ou o GitHub. Antes de substituir arquivos existentes, mantenha uma cópia de segurança dos originais.

---

## 7. Adicionar arquivos ao repositório

Depois de criar ou clonar o repositório:

1. Abra a pasta correspondente no computador.
2. Crie as subpastas desejadas (`scripts`, `notebooks`, `figures` etc.).
3. Copie para dentro delas os arquivos que deseja compartilhar.
4. Mantenha os dados brutos e outros arquivos desnecessários fora do repositório, sempre que possível.

Antes de adicionar arquivos ao Git, configure o `.gitignore`.

### 7.1. Criar ou editar o `.gitignore`

```bash
nano .gitignore
```

Exemplo básico:

```gitignore
# Sequencing files
*.fastq
*.fastq.gz
*.fq.gz
*.bam
*.sam
*.cram

# Large analysis objects
*.h5ad
*.h5
*.loom
*.rds

# Python and Jupyter
__pycache__/
.ipynb_checkpoints/
*.pyc

# Temporary files
*.log
*.tmp

# Credentials
.env
.env.*
*.pem
*.key
```

Para salvar no `nano`, pressione `Ctrl + O`, `Enter` e `Ctrl + X`.

O `.gitignore` não remove automaticamente arquivos que já foram registrados anteriormente no Git.

### 7.2. Verificar as alterações

```bash
git status
```

### 7.3. Adicionar os arquivos

Para incluir todas as alterações não ignoradas:

```bash
git add -A
```

Ou para incluir somente um arquivo:

```bash
git add notebooks/01_quality_control.ipynb
```

Confira o que foi selecionado:

```bash
git status
git diff --cached --stat
```

**Importante:** `git add -A` também prepara exclusões de arquivos já monitorados. Verifique a lista antes de continuar.

Se adicionou algo por engano, pode retirar os arquivos da área de preparação, sem apagá-los:

```bash
git restore --staged .
```

### 7.4. Registrar a versão

```bash
git commit -m "Add initial analysis files"
```

### 7.5. Enviar para o GitHub

```bash
git push
```

O comando envia os commits locais para a branch remota configurada.

Depois, consulte o repositório na página da organização para conferir os arquivos.

---

## 8. Como atualizar o repositório posteriormente

Quando modificar scripts, notebooks ou documentos, não é necessário criar outro repositório.

Dentro da pasta do projeto:

```bash
git status
git add -A
git status
git commit -m "Update quality control analysis"
git push
```

### Quando fazer um commit?

Recomendamos registrar versões quando uma etapa ou alteração significativa estiver concluída, por exemplo:

- Adição de uma análise.
- Correção de uma função.
- Atualização de parâmetros.
- Revisão de um notebook.
- Inclusão de figuras ou relatórios.
- Atualização da documentação.

Utilize mensagens que descrevam o que foi alterado.

O commit guarda a versão localmente; o push a envia para o GitHub.

---

## 9. Trabalhando com colaboradores

Se diferentes pesquisadores utilizarem o mesmo repositório, recomenda-se trabalhar em branches próprias para alterações importantes.

Uma **branch** permite desenvolver mudanças sem modificar imediatamente a versão principal (`main`).

Exemplo:

```bash
git switch -c update-analysis
```

Depois de realizar as modificações:

```bash
git add -A
git commit -m "Update analysis pipeline"
git push -u origin update-analysis
```

Para solicitar que essas mudanças sejam incorporadas à `main`:

```bash
gh pr create --base main --head update-analysis
```

Isso cria um **Pull Request (PR)**, no qual as alterações podem ser revisadas antes de serem incorporadas.

Quando mais de uma pessoa modifica a mesma branch, atualize sua cópia local antes de começar novas alterações:

```bash
git pull --ff-only
```

Se o comando indicar divergência ou conflito, não force a atualização. Solicite ajuda ao responsável pelo repositório.

---

## 10. Preparação para publicação

Antes de disponibilizar publicamente um repositório associado a um manuscrito, confira:

- [ ] O README explica o projeto e as análises.
- [ ] Os scripts e notebooks relevantes estão presentes.
- [ ] As etapas de análise estão organizadas e documentadas.
- [ ] Parâmetros e versões de software estão registrados.
- [ ] Os dados possuem referências ou instruções de acesso.
- [ ] Os arquivos necessários para reproduzir os resultados foram identificados.
- [ ] Não existem dados confidenciais ou credenciais.
- [ ] Os responsáveis pelo estudo autorizaram a divulgação.
- [ ] As condições de reutilização e a licença foram definidas, quando apropriado.
- [ ] A versão correspondente ao manuscrito está identificada.

Após a publicação, recomenda-se criar uma **release** identificando a versão do código associada ao artigo.

Quando apropriado, o repositório pode ser integrado ao Zenodo para gerar um DOI de software e permitir a citação de uma versão específica do código.

---

## 11. Em caso de dúvidas ou erros

Alguns comandos úteis:

```bash
git status
git branch
git remote -v
git log --oneline
gh auth status
```

Se ocorrer um erro durante `pull`, `commit`, `push` ou `merge`, leia a mensagem e procure orientação antes de continuar.

**Evite utilizar `git push --force`, `git reset --hard` ou excluir arquivos da pasta `.git` sem compreender suas consequências.** Esses comandos podem causar perda de alterações ou modificar o histórico compartilhado.

Se informações sensíveis forem enviadas acidentalmente, informe imediatamente os responsáveis. Apagar o arquivo em um novo commit não elimina necessariamente o conteúdo do histórico.

---

## 12. Contatos

Para dúvidas sobre a organização dos repositórios, acesso ao GitHub ou documentação computacional:

**Tahila Andrighetti**  
Postdoctoral Researcher · Bioinformatician  
Laboratório de Imunoinflamação · UNICAMP

Email: [tahilaandrighetti@gmail.com](mailto:tahilaandrighetti@gmail.com)  
Email: [tahila@unicamp.br](mailto:tahila@unicamp.br)

---

*O objetivo não é apenas armazenar códigos, mas preservar análises científicas de maneira organizada, compreensível e reproduzível.*
