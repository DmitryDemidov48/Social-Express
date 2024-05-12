# Используем образ Node.js версии 21.6 на основе Alpine Linux
FROM --platform=linux/amd64 node:21.6-alpin

# Устанавливаем рабочую директорию контейнера
WORKDIR /app

# Копируем package.json и package-lock.json для установки зависимостей
COPY package.json package-lock.json ./

# Устанавливаем зависимости
RUN npm install

# Глобально устанавливаем Prisma
RUN npm install -g prisma

# Генерируем файлы Prisma
RUN prisma generate

# Копируем остальные файлы приложения
COPY .. .

# Открываем порт 3000
EXPOSE 3000

# Команда запуска приложения
CMD ["npm", "start"]
