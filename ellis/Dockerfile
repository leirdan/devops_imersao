FROM python:3.13-alpine3.22

# Define o diretório de trabalho no container
WORKDIR /app

# Copia os arquivos de dependências
COPY requirements.txt .

# Instala as dependências Python sem cache
RUN pip install --no-cache-dir -r requirements.txt

# Copia o código inteiro da aplicação
COPY . .

# Expõe a porta que a aplicação vai usar
EXPOSE 8000

# Define variáveis de ambiente
#ENV PYTHONPATH=/app
#ENV PYTHONUNBUFFERED=1

# Comando para executar a aplicação
# Especificar o host 0.0.0.0, se não ocorrem problemas
CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
