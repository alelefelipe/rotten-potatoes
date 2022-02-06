# Definir a imagem base
FROM python:3.8-slim-buster

# Definir o diretorio de trabalho
WORKDIR /app

# Copiar o arquivo requirements para instalar os pacotes necessários no projeto
COPY requirements.txt .

# Instalar os pacotes
RUN python -m pip install -r requirements.txt

# Copiar os arquivos do projetos para a pasta da imagem
COPY . /app

# Expor a porta da aplicação
EXPOSE 5000

# Executar os comandos de inicialização
CMD ["gunicorn", "--workers=3", "--bind", "0.0.0.0:5000", "-c", "config.py", "app:app"]