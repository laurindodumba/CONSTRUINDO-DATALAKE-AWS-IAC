[datalake.drawio](https://github.com/user-attachments/files/24554736/datalake.drawio)# 🚀 AWS Data Engineering Pipeline

Este repositório contém um **pipeline de engenharia de dados na AWS**, seguindo boas práticas de **Data Lake**, **arquitetura em camadas (Bronze / Silver / Gold)** e automação para ingestão, transformação e disponibilização de dados para análise e também uma bordagem sobre infrastrutura como código (Iac).

---

## Visão Geral

O objetivo deste projeto é demonstrar a construção de um pipeline de dados escalável e confiável utilizando serviços da AWS, desde a extração de dados de fontes externas até a disponibilização para consumo analítico.

**Principais características:**
- Ingestão de dados via API / arquivos
- Armazenamento em Data Lake (Amazon S3)
- Processamento e transformação de dados
- Organização em camadas (Bronze, Silver e Gold)
- Código modular e reutilizável

---

##  Arquitetura do Pipeline

```text
┌──────────────┐
│ Data Source  │  (API / CSV / JSON)
└──────┬───────┘
       │
       ▼
┌────────────────────┐
│ S3 - Bronze Layer  │  (Raw data)
└──────┬─────────────┘
       │
       ▼
┌────────────────────┐
│ S3 - Silver Layer  │  (Cleaned & standardized)
└──────┬─────────────┘
       │
       ▼
┌────────────────────┐
│ S3 - Gold Layer    │  (Business-ready data)
└────────────────────┘
```

---

##  Data Lake Layers

### 🥉 Bronze (Raw)
- Dados brutos
- Sem transformações
- Fonte original preservada

### 🥈 Silver (Trusted)
- Limpeza de dados
- Padronização de tipos
- Tratamento de valores nulos

### 🥇 Gold (Analytics)
- Dados agregados
- Métricas de negócio
- Prontos para consumo (BI / ML)

---

##  Tecnologias Utilizadas

- **AWS S3** – Data Lake
- **AWS IAM** – Controle de acesso
- **Python 3** – Linguagem principal
- **Boto3** – Integração com AWS
- **Pandas / PySpark** – Transformações de dados
- **Git & GitHub** – Versionamento
- **Terraform - Iac

---

##  Estrutura do Projeto

```text
├── data/
│   ├── bronze/
│   ├── silver/
│   └── gold/
├── src/
│   ├── extract.py
│   ├── transform.py
│   ├── load.py
│   └── main.py
├── config/
│   └── settings.yaml
├── requirements.txt
├── README.md
└── .gitignore
```

##  ARQUITETURA DOS DADOS

<img width="1487" height="1013" alt="Datalake drawio" src="https://github.com/user-attachments/assets/490adb27-8d6c-4b83-b6bb-233743117895" />


## ⚙️ Configuração do Ambiente

###  Clonar o repositório

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

###  Criar ambiente virtual

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\\Scripts\\activate     # Windows
```

###  Instalar dependências

```bash
pip install -r requirements.txt
```

###  Configurar credenciais AWS

```bash
aws configure
```

---

##  Execução do Pipeline

```bash
python src/main.py
```

Fluxo executado:
1. Extração dos dados
2. Upload para camada Bronze
3. Transformações (Silver)
4. Agregações finais (Gold)

---

##  Segurança e Boas Práticas

- Princípio do menor privilégio (IAM)
- Separação de permissões por camada
- Não versionar credenciais
- Uso de variáveis de ambiente

---

##  Possíveis Evoluções

- Orquestração com Apache Airflow
- Processamento distribuído com AWS Glue / Spark
- Catálogo de dados com AWS Glue Data Catalog
- Monitoramento com CloudWatch
- CI/CD com GitHub Actions

---

##  Contribuição

Contribuições são bem-vindas!

1. Faça um fork do projeto
2. Crie uma branch (`feature/nova-feature`)
3. Commit suas alterações
4. Abra um Pull Request



## Autor

**Laurindo Dumba**  
Engenheiro de Dados 

🔗 LinkedIn: https://www.linkedin.com

---

⭐ Se este projeto te ajudou, deixe uma estrela no repositório!

