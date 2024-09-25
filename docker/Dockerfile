FROM python:3.9.20-slim-bullseye

WORKDIR /app

RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    git \
    && rm -rf /var/lib/apt/lists/*

# RUN git config --global user.name ${GITHUB_USERNAME}
# RUN git config --global user.email ${GITHUB_EMAIL}

RUN git clone https://github.com/Z3r0c0k3/dukyoung-film-server.git
WORKDIR /app/dukyoung-film-server
# RUN git remote remove origin
# RUN git remote add origin https://${GITHUB_TOKEN}@github.com/Z3r0c0k3/dukyoung-film-server.git
# COPY requirements.txt requirements.txt
RUN pip3 install --no-cache-dir -r requirements.txt
RUN chmod 777 /app/dukyoung-film-server/start.sh

EXPOSE 10000
ENTRYPOINT [ "start.sh" ]