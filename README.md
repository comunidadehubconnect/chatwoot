<p align="center">
	<img src="https://www.chatwoot.com/docs/img/logo.png" alt="Chatwoot-logo" width="100" />	
	<p align="center">O Chatwoot oferece todas as ferramentas para gerenciar conversas, construir relacionamentos e encantar seus clientes em um só lugar.</p>
</p>
<hr />
<p align="left">
	<img src="https://telegram.org/favicon.ico" alt="Telegram-logo" width="32" />
	<span>Grupo e Canal Telegram: </span>
	<a href="https://t.me/chatwootbrasil" target="_blank">Grupo</a>
	<span> </span>
</p>
<hr />
<p align="left">
	<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
	<span>Grupo WhatsaAPP: </span>
	<a href="https://chat.whatsapp.com/CLKge3hmHmmBcIL04mBzmT" target="_blank">Grupo</a>
</p>
----------------------------------------------------------------------------
</p>

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="Quepasa-logo" width="200" />
</p>

**PIX CNPJ**

```
45959142000119	
```

----------------------------------------------------------------------------

**Manual de Instalação ChatWoot**

sudo apt update && apt upgrade -y
</p>
wget https://get.chatwoot.app/linux/install.sh
</p>
chmod +x install.sh
</p>
./install.sh --install
</p>
Use as opções abaixo
</p>
yes
</p>
chatwoot.dominio.com.br
</p>
contato@dominio.com.br
</p>
yes
</p>
yes
</p>

----------------------------------------------------------------------------

**Alterando Idioma e ativando sua tela de cadastro**

</p>
cd /home/chatwoot/chatwoot
</p>
nano .env
</p>
Altere a linha
</p>
DEFAULT_LOCALE=pt_BR
</p>
ENABLE_ACCOUNT_SIGNUP=true
</p>
sudo systemctl restart chatwoot.target
</p>
Acesse: seudominio.com.br
</p>
Faça seu cadastro
</p>

----------------------------------------------------------------------------

**Habilitando configurações ocultas do Chatwoot**

</p>
No banco de dados PostgreSQL
</p>
sudo -u postgres psql
</p>
\c chatwoot_production
</p>
update installation_configs set locked = false;
</p>
\q
</p>

----------------------------------------------------------------------------

**NOMES CHATWOOT TERMOS E POLITICA DE PRIVACIDADE**

**Acesse super Admin**
</p>
https://seudominio.com.br/super_admin
</p>
Opção>installation_configs
</p>
LOGO
</p>
LOGO_THUMBNAIL
</p>
NOMES CHATWOOT:
</p>
Alterando nomes na plataforma
</p>
INSTALLATION_NAME
</p>
BRAND_NAME
</p>
TERMOS E POLITICA DE PRIVACIDADE
</p>
TERMS_URL
</p>
PRIVACY_URL
</p>
BRAND_URL
</p>
WIDGET_BRAND_URL
</p>

----------------------------------------------------------------------------

----------------------------------------------------------------------------

**Versão Docker**

**Manual de Instalação ChatWoot via Docker**

sudo apt update && apt upgrade -y
</p>
curl -L https://get.docker.com | sh
</p>
git clone https://github.com/EngajamentoFlow/chatwoot
</p>
cd chatwoot
</p>
nano docker-compose.yaml
</p>
nano .env
</p>
Colocar mesma senha usuário e banco de dados nos dois arquivos postgres
</p>
Altere as linhas .env
</p>
FRONTEND_URL=SeuDominio
</p>
DEFAULT_LOCALE=pt_BR
</p>
ENABLE_ACCOUNT_SIGNUP=true
</p>

**Prepare o banco de dados executando as migrações**

</p>
docker compose run --rm rails bundle exec rails db:chatwoot_prepare
</p>

**Coloque o serviço em funcionamento**

</p>
docker compose up -d
</p>

**Configure o Nginx para servir como um proxy de front-end**

sudo apt-get install nginx
</p>
cd /etc/nginx/sites-enabled
</p>
sudo nano /etc/nginx/sites-available/chatwoot

```
server {
  server_name seudominio.com>;
  # Point upstream to Chatwoot App Server
  set $upstream 127.0.0.1:3000;
  # Nginx strips out underscore in headers by default
  # Chatwoot relies on underscore in headers for API
  # Make sure that the config is set to on.
  underscores_in_headers on;
  location /.well-known {
    alias /var/www/ssl-proof/chatwoot/.well-known;
  }
  location / {
    proxy_pass_header Authorization;
    proxy_pass http://$upstream;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
    proxy_set_header Host $host;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header X-Forwarded-Ssl on; # Optional
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_http_version 1.1;
    proxy_set_header Connection “”;
    proxy_buffering off;
    client_max_body_size 0;
    proxy_read_timeout 36000s;
    proxy_redirect off;
  }
  listen 80;
}
```

</p>
sudo ln -s /etc/nginx/sites-available/chatwoot /etc/nginx/sites-enabled
 </p>
sudo apt-get install snapd
 </p>
sudo snap install --classic certbot
 </p>
sudo certbot --nginx
 </p>
 Coloque Email: 
 </p>
 Y
 </p>
 Y
 </p>
sudo service nginx restart
</p>
Acesse: seudominio.com.br
</p>
Faça seu cadastro

----------------------------------------------------------------------------

**Habilitando configurações ocultas do Chatwoot**

sudo nano /etc/nginx/sites-available/pgadmin
</p>

```
server {
  server_name pgadmin.socialatendimento.com.br;
  location / {
    proxy_pass http://127.0.0.1:3003;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set</p>_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_cache_bypass $http_upgrade;
    proxy_buffering off;
    proxy_cache off;
  }
  }
```
  
</p>
sudo ln -s /etc/nginx/sites-available/pgadmin /etc/nginx/sites-enabled
 </p>
sudo certbot --nginx
</p>
sudo service nginx restart
</p>
</p>
Acesse:
</p>
http://pgadmin.socialatendimento.com.br
</p>
Login: admin@admin.com.br
Senha: pgadmin
</p>
Crie seu servidor
</p>

<img src="https://github.com/EngajamentoFlow/chatwoot/blob/main/Registrar.png" alt="Chatwoot-logo" width="1000" />

</p>
Adicionar nome do servidor
</p>

<img src="https://github.com/EngajamentoFlow/chatwoot/blob/main/Server.png" alt="Chatwoot-logo" width="1000" />

</p>
Coloque sua credeciais do banco de dados, a mesma do .env
</p>

<img src="https://github.com/EngajamentoFlow/chatwoot/blob/main/Acessando1.png" alt="Chatwoot-logo" width="1000" />

</p>
Habilitando configurações ocultas do Chatwoot
</p>
Adicione a linha
</p>
update installation_configs set locked = false;
</p>

<img src="https://github.com/EngajamentoFlow/chatwoot/blob/main/Acessando.png" width="1000" />

----------------------------------------------------------------------------

**NOMES CHATWOOT TERMOS E POLITICA DE PRIVACIDADE**

**Acesse super Admin**

</p>
https://seudominio.com.br/super_admin
</p>
Opção>installation_configs

LOGO
</p>
LOGO_THUMBNAIL
</p>
NOMES CHATWOOT:
</p>
Alterando nomes na plataforma
</p>
INSTALLATION_NAME
</p>
BRAND_NAME
</p>
TERMOS E POLITICA DE PRIVACIDADE
</p>
TERMS_URL
</p>
PRIVACY_URL
</p>
BRAND_URL
</p>
WIDGET_BRAND_URL
</p>

**Recopile**

cd chatwoot

docker compose up -d

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="Quepasa-logo" width="200" />
</p>

**PIX CNPJ**

```
45959142000119	
```
----------------------------------------------------------------------------
