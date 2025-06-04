
# 🚗 Sistema de Detecção Automática de Placas Veiculares

Este projeto implementa uma solução baseada em visão computacional para **detecção e leitura de placas de veículos**, com integração à **API Brasil** para consulta de dados veiculares. O sistema utiliza **redes neurais treinadas com YOLO**, técnicas de OCR e backend web com Django para gerenciamento e visualização dos resultados.

---

## 📌 Funcionalidades

- 📷 Detecção de placas em imagens com YOLOv5
- 🔠 Reconhecimento dos caracteres da placa via OCR
- 🌐 Consulta de dados da placa usando a API Brasil
- 🖥️ Interface web com Django
- 🧠 Scripts de treino e teste de IA
- 🗃️ Dataset customizado para placas e caracteres

---

## 🛠️ Tecnologias Utilizadas

- **Backend**: Django + Python
- **Visão Computacional**: OpenCV, YOLOv5, PyTorch
- **OCR**: EasyOCR
- **API externa**: [API Brasil](https://app.apibrasil.io/)
- **Banco de Dados**: SQLite
- **Frontend**: HTML + Templates Django
- **Outros**: Pandas, Numpy

---

## 📂 Estrutura do Projeto

```
ProjetoIOT/
├── placas/
│   ├── api_brasil.py           # Integração com a API Brasil
│   ├── detector/               # Lógica de IA e OCR
│   │   ├── detector.py
│   │   ├── ocr.py
│   │   ├── utils.py
│   │   └── ia/
│   │       ├── license_plate_detector.pt
│   │       ├── placa_stage1.pt
│   │       ├── train_yolo.py
│   │       ├── dataset/
│   ├── models.py               # Modelos Django
│   ├── views.py                # Views e lógica de controle
│   ├── urls.py                 # Rotas
│   ├── templates/              # Páginas HTML
│   └── static/                 # CSS, JS e imagens
├── manage.py
└── requirements.txt
```

---

## ▶️ Como Executar o Projeto

### 1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/projeto-iot-placas.git
cd projeto-iot-placas
```

### 2. Criar ambiente virtual e instalar dependências

```bash
python -m venv venv
source venv/bin/activate  # ou venv\Scripts\activate no Windows
pip install -r requirements.txt
```

### 3. Aplicar migrações e rodar o servidor

```bash
python manage.py migrate
python manage.py runserver
```

### 4. Acessar no navegador

```
http://127.0.0.1:8000/
```

---

## 🤖 Pipeline de IA

O sistema utiliza dois estágios de detecção com modelos YOLO:

- **Stage 1** – `license_plate_detector.pt`: detecta a placa no veículo.
- **Stage 2** – `placa_stage1.pt` / `placa_stage2.pt`: detectam e segmentam os caracteres da placa.

Após a detecção, o módulo `ocr.py` faz o reconhecimento dos caracteres da placa.

---

## 🔌 Integração com API Brasil

- O arquivo `placas/api_brasil.py` realiza requisições à [API Brasil](https://app.apibrasil.io/) para consultar dados de um veículo a partir da placa.
- É necessário fornecer uma chave de API válida para autenticação (configurada diretamente no script ou via `.env`).

---

## 📜 Licença

Este é um projeto acadêmico de código aberto. Consulte o arquivo `LICENSE` para mais informações.

---

## 👥 Desenvolvedores

- **Aderval Santiago Leite**  
- **Robert Santos Santana**   
- **Anderson Teixeira Leal de Jesus**
- **Everton Santana da Silva** 
- **Hugo Gabriel de Oliveira Marcelo** 

---

## 📚 Documentação Complementar

Além deste resumo técnico, você pode acessar o documento completo com todos os detalhes do projeto, incluindo arquitetura, inteligência artificial, testes e anexos, no arquivo abaixo:

📄 [Documentação Técnica Completa (PDF)](documentacao/Documento%20Sistema%20de%20Captura%20de%20Placas.pdf)


