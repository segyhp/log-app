FROM python:3-slim-buster

WORKDIR /app

COPY requirements.txt .

# Install tools for debugging (using vi/vim/nano)
RUN apt update && apt install -y \
    vim \
    iputils-ping \
    && rm -rf /var/lib/apt/lists/*

RUN pip install -r requirements.txt

COPY . .

CMD ["python3", "-m", "flask", "run", "--host=0.0.0.0"]