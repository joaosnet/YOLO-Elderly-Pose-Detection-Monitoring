# Sistema de Monitoramento de Poses para Idosos 🤖👴

Sistema de monitoramento de poses baseado em YOLO para detecção de posturas de idosos, capaz de identificar se a pessoa está em pé, sentada ou deitada.

## ✨ Funcionalidades

- 📹 Suporte para câmera web ou arquivo de vídeo
- ⏱️ Monitoramento por tempo determinado
- 🎯 Detecção de 3 poses: em pé, sentado e deitado
- 📊 Relatório detalhado com duração de cada pose
- 🔄 Interface interativa via terminal
- 🐳 Suporte a Docker
- 💻 Executável standalone disponível

## 🚀 Como Usar

### Opção 1: Usando Python (Recomendado para Desenvolvedores)

#### Pré-requisitos
- Python 3.12 ou superior
- Git
- uv (recomendado para gerenciamento de dependências)

#### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/joaosnet/YOLO-Elderly-Pose-Detection-Monitoring.git
cd YOLO-Elderly-Pose-Detection-Monitoring
```

2. Instale o uv (opcional, mas recomendado):
```bash
# Windows (PowerShell)
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

# Linux/macOS
curl -LsSf https://astral.sh/uv/install.sh | sh
```

3. Instale as dependências:
```bash
# Usando uv (recomendado)
uv sync

# Ou usando pip tradicional
pip install -m requirements.txt
```

4. Para desenvolvimento, instale as dependências de desenvolvimento:
```bash
# Usando uv
uv sync --dev
```

#### Comandos Disponíveis

O projeto utiliza `taskipy` para automatizar comandos comuns. Aqui estão os comandos disponíveis:

```bash
# Executar o monitoramento (modo interativo)
task run_main

# Executar com vídeo específico
task run_main_video

# Executar com webcam
task run_main_camera

# Executar com parâmetros personalizados
task run_main_custom path=caminho/video.mp4 duration=5 weights=path/weights.pt

# Formatar e verificar código
task format
task lint

# Limpar arquivos cache
task clean

# Executar testes
task test

# Iniciar treinamento
task train

# Iniciar Jupyter Lab
task jupyter
```

### Opção 2: Usando Docker 🐳

1. Construa a imagem:
```bash
docker build -t elderly-monitoring .
```

2. Execute o container:
```bash
docker run elderly-monitoring
```

Para usar um vídeo específico, monte um volume:
```bash
docker run -v $(pwd):/app elderly-monitoring --video_path seu_video.mp4
```

### Opção 3: Executável Standalone 📦

1. Baixe o último release na seção "Releases"
2. Extraia o arquivo zip
3. Execute o arquivo `monitoring.exe` (Windows) ou `monitoring` (Linux/Mac)

## 📊 Estrutura do Projeto

```
YOLO-Elderly-Pose-Detection-Monitoring/
├── main.py           # Script principal
├── constants.py      # Constantes e configurações
├── best.pt          # Arquivo de pesos do modelo
├── pyproject.toml   # Configurações do projeto
├── Dockerfile       # Configuração Docker
└── README.md        # Este arquivo
```

## 🛠️ Configurações

O sistema possui várias configurações que podem ser ajustadas:

- `DURACAO_PADRAO`: 300 segundos (5 minutos)
- `FPS_PADRAO`: 30 fps
- Classes detectadas:
  - 0: Em pé
  - 1: Sentado
  - 2: Deitado

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

## 👥 Contribuindo

Contribuições são bem-vindas! Por favor, leia o arquivo CONTRIBUTING.md antes de enviar um Pull Request.

## 🐛 Problemas Conhecidos

Se encontrar algum problema, por favor [abra uma issue](https://github.com/seu-usuario/YOLO-Elderly-Pose-Detection-Monitoring/issues).

## 📞 Contato

Para dúvidas ou sugestões, entre em contato através das issues do GitHub.
