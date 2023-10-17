# Projeto Conversão de Temperatura

O Projeto Conversão de Temperatura é uma aplicação desenvolvida em Node.js, que serve como um exemplo prático para a criação de ambientes com containers utilizando Docker.

## Sobre o Projeto

Neste projeto, apresentamos uma introdução ao Docker Daemon, imagens, containers e o repositório de imagens, o Docker Registry. Abaixo está o conteúdo do Dockerfile utilizado para criar a imagem do projeto:

    Dockerfile
    FROM node:18.16.0
    WORKDIR /app
    COPY package*.json ./
    RUN npm install
    COPY . .
    EXPOSE 8080
    CMD ["node", "server.js"]

1.  **Criação da imagem:** A base deste projeto é a criação de uma imagem Docker. Utilizamos o Dockerfile para descrever como a imagem deve ser construída, incluindo as dependências e configurações necessárias. O comando a seguir é utilizado para criar a imagem, considerando as instruções contidas no Dockerfile:
    
    
    `docker build -t conversao-temperatura .` 
    
2.  **Tags da imagem:** Em seguida, criamos duas tags para a imagem: uma versão "v1" e outra "latest" com os seguintes comandos:
    
    -   Para a versão "v1":
        
      
        
        `docker tag conversao-temperatura belarminoneto/conversao-temperatura:v1` 
        
    -   Para a versão "latest":
        
   
        
        `docker tag conversao-temperatura belarminoneto/conversao-temperatura:latest` 
        
3.  **Envio para o repositório:** Após a criação das tags, as imagens são enviadas para o repositório com os comandos:
    
    -   Para a versão "v1":
        
        
        `docker push belarminoneto/conversao-temperatura:v1` 
        
    -   Para a versão "latest":
        
        
        `docker push belarminoneto/conversao-temperatura:latest` 
        
4.  **Verificação das imagens:** Para verificar as imagens disponíveis, você pode realizar o pull das imagens com os comandos:
    
    -   Para a versão "latest":
        
        
        `docker pull belarminoneto/conversao-temperatura:latest` 
        
    -   Para a versão "v1":
        
   
        
        `docker pull belarminoneto/conversao-temperatura:v1` 
        

## Observações do Projeto

A aplicação é exposta na porta 8080. Esta documentação fornece uma visão geral do projeto Conversão de Temperatura e das etapas necessárias para gerenciar imagens e containers Docker associados a ele. 
