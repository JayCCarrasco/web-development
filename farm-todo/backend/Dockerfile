FROM python:3.11-slim

WORKDIR /usr/src/app

# Instalar dependencias del sistema para compilar paquetes
RUN apt-get update && apt-get install -y \
    build-essential \
    gcc \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

# Copiar requirements
COPY requirements.txt ./

# Actualizar herramientas de pip
RUN pip install --upgrade pip setuptools wheel

# Instalar dependencias de Python
RUN pip install --no-cache-dir -r requirements.txt

# Copiar el código
COPY . .

EXPOSE 3001

CMD ["python", "./src/server.py"]