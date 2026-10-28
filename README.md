# Plataforma Inteligente AI

API responsável por disponibilizar o modelo preditivo de Inteligência Artificial utilizado na plataforma inteligente de gestão de emergências urbanas.

## Tecnologias

- Python
- Flask
- Scikit-learn (Random Forest)
- Pandas
- NumPy
- Joblib

## Estrutura

- `app.py` — aplicação Flask e rotas da API
- `modelo/` — modelo Random Forest treinado (`random_forest_ai4i_obd2.pkl`)
- `services/` — serviços de pré-processamento, validação e previsão

## Passo a Passo para Execução

### 1. Criar o ambiente virtual (`venv`)

Se ainda não tiver o ambiente virtual criado na pasta do projeto:

- **macOS / Linux:**
  ```bash
  python3 -m venv venv
  ```
- **Windows:**
  ```bash
  python -m venv venv
  ```

### 2. Ativar o ambiente virtual

- **macOS / Linux:**
  ```bash
  source venv/bin/activate
  ```
- **Windows:**
  ```bash
  venv\Scripts\activate
  ```

### 3. Instalar as dependências

Com o ambiente ativado (você verá `(venv)` no terminal):

```bash
pip install -r requirements.txt
```

### 4. Executar o servidor

```bash
python app.py
```

A API estará disponível por padrão em `http://localhost:5001`.

---

> **Dica:** Para desativar o ambiente virtual quando terminar, execute:
> ```bash
> deactivate
> ```
