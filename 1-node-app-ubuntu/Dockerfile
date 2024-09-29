# Ubuntu tabanlı bir image kullanarak başlıyoruz
FROM ubuntu:latest

# Zaman dilimi ayarını etkileşimli moddan çıkarıyoruz
ENV DEBIAN_FRONTEND=noninteractive

# Gerekli bağımlılıkları yüklemek ve Node.js'i kurmak
RUN apt-get update && apt-get install -y curl \
    && curl -sL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get install -y nodejs \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Uygulama dosyalarını kopyalıyoruz
COPY . /opt/node-app/

# Çalışma dizinini ayarlıyoruz
WORKDIR /opt/node-app/

#ENV
ENV channel=kablosuzkedi

# Uygulamayı başlatıyoruz
CMD ["node", "index.js"]
