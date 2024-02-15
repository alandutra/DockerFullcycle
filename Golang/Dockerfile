# Imagem oficial do Golang com base no Alpine
FROM golang:alpine AS builder

# Definição do diretório de trabalho dentro do contêiner
WORKDIR /app

# Copiando o código fonte para o contêiner
COPY . .

# Criando o módulo go
RUN go mod init fullcycle/app

# Compilando o código Go, tornando em binário
RUN go build -o main .

# Criaando uma nova imagem mínima
FROM scratch

# Copiando a aplicação compilada para a imagem mínima criada
COPY --from=builder /app/main /app/

# Printando a aplicação
CMD ["/app/main"]