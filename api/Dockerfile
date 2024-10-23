# Use uma imagem oficial do Node.js como base
FROM node:21

# Defina o diretório de trabalho no container
WORKDIR /usr/src/app

# Copie apenas os arquivos de dependências primeiro (para cache eficiente)
COPY package*.json ./

# Instale as dependências do projeto
RUN npm install

# Instale o Angular CLI globalmente
RUN npm install -g @angular/cli

# Copie o restante dos arquivos da aplicação
COPY . .

# Exponha a porta 4200 para o Angular dev server
EXPOSE 4200

# Comando para iniciar a aplicação
CMD ["ng", "serve", "--host", "0.0.0.0"]

# (Opcional) Limpe os caches do npm para reduzir o tamanho da imagem
RUN npm cache clean --force