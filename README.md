# 🐍 Anaconda / Conda Environment Guide

Guia prático e profissional para **gestão de ambientes Python utilizando Anaconda/Conda**. Este documento descreve boas práticas utilizadas em projetos reais para evitar conflitos de dependências, manter ambientes reprodutíveis e facilitar a colaboração entre desenvolvedores.

---

# 📚 Índice

* Visão Geral
* Estrutura recomendada de ambientes
* Criação de ambientes
* Ativação e desativação
* Instalação de bibliotecas
* Manutenção do ambiente
* Integração com VS Code
* Exportação e reprodução de ambientes
* Boas práticas profissionais

---

# 🔎 Visão Geral

O **Conda** é um gerenciador de ambientes e pacotes amplamente utilizado no ecossistema Python. Ele permite criar ambientes isolados onde cada projeto possui:

* sua própria versão do Python
* suas próprias bibliotecas
* dependências controladas

Isso evita problemas comuns como:

* conflitos de versões
* atualizações que quebram projetos antigos
* dificuldade em reproduzir ambientes em outras máquinas

---

# 🧱 Estrutura Recomendada de Ambientes

Uma prática comum em projetos profissionais é:

```
python-projects
│
├── vision_project
│   └── environment.yml
│
├── robotics_simulation
│   └── environment.yml
│
└── data_analysis
    └── environment.yml
```

Cada projeto possui seu **próprio ambiente Conda**.

Nunca utilize o ambiente **base** para desenvolvimento de projetos.

---

# ⚙️ Criação de Ambientes

Criar um novo ambiente com uma versão específica do Python:

```bash
conda create --name meu_projeto python=3.10
```

Exemplo real:

```bash
conda create --name vision_env python=3.10
```

---

# ▶️ Ativação do Ambiente

```bash
conda activate meu_projeto
```

Após ativado, todos os pacotes instalados serão adicionados **somente neste ambiente**.

---

# ⏹️ Desativar Ambiente

```bash
conda deactivate
```

---

# 📋 Listar Ambientes Existentes

```bash
conda env list
```

ou

```bash
conda info --envs
```

Saída típica:

```
base                  *  /anaconda3
vision_env               /anaconda3/envs/vision_env
robotics_env             /anaconda3/envs/robotics_env
```

---

# 📦 Instalação de Bibliotecas

Após ativar o ambiente, você pode instalar pacotes.

### Instalar com Conda

```bash
conda install opencv
```

### Instalar múltiplos pacotes

```bash
conda install numpy scipy matplotlib
```

### Instalar via pip

Caso o pacote não esteja disponível no Conda:

```bash
pip install mediapipe
```

---

# ❌ Remover Pacotes

```bash
conda remove nome_do_pacote
```

Exemplo:

```bash
conda remove opencv
```

---

# 🛠️ Comandos de Manutenção

### Listar pacotes instalados

```bash
conda list
```

### Atualizar Conda

```bash
conda update conda
```

### Atualizar todos os pacotes do ambiente

```bash
conda update --all
```

---

# 🗑️ Remover um Ambiente

Se um ambiente não for mais necessário:

```bash
conda remove --name meu_projeto --all
```

---

# 🧑‍💻 Integração com VS Code

Para utilizar corretamente o ambiente dentro do VS Code:

1. Abra um arquivo `.py`
2. Clique na versão do **Python no canto inferior direito**
3. Selecione o interpretador correspondente ao ambiente Conda

Exemplo:

```
Python 3.10 (vision_env)
```

Isso garante que:

* o terminal use o ambiente correto
* as bibliotecas do projeto sejam reconhecidas
* o linting e autocomplete funcionem corretamente

---

# 📤 Exportar Ambiente

Para compartilhar ou versionar dependências do projeto:

```bash
conda env export > environment.yml
```

Isso gera um arquivo com todas as dependências instaladas.

---

# 📥 Recriar Ambiente em Outra Máquina

```bash
conda env create -f environment.yml
```

Esse comando recria **exatamente o mesmo ambiente**.

---

# 🧠 Boas Práticas Profissionais

✔ Nunca desenvolver no ambiente `base`

✔ Criar um ambiente por projeto

✔ Fixar versões críticas de bibliotecas

✔ Versionar `environment.yml` no repositório

✔ Evitar misturar `conda` e `pip` sem necessidade

✔ Documentar dependências no README

---

# 🚀 Exemplos de Áreas onde Conda é Muito Utilizado

* Visão Computacional
* Machine Learning
* Robótica
* Ciência de Dados
* Interfaces gráficas com PyQt

Bibliotecas comuns nesses ambientes:

* OpenCV
* MediaPipe
* PyQt
* NumPy
* SciPy

---

# 📄 Licença

Este guia pode ser utilizado livremente em projetos educacionais ou profissionais.

---

# 🤝 Contribuição

Sugestões e melhorias são bem-vindas. Abra uma **issue** ou **pull request**.
