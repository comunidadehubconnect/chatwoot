<p align="center">
	<img src="https://www.chatwoot.com/docs/img/logo.png" alt="Chatwoot-logo" width="100" />	
	<p align="center">O Chatwoot oferece todas as ferramentas para gerenciar conversas, construir relacionamentos e encantar seus clientes em um só lugar.</p>
</p>
<hr />
<p align="left">
	<img src="https://telegram.org/favicon.ico" alt="Telegram-logo" width="32" />
	<span>Grupo e Canal Telegram: </span>
	<a href="[https://t.me/quepasa_api](https://t.me/chatwootbrasil)" target="_blank">Grupo</a>
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

**Manual de Instalação Portainer**

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

**Alterando Idioma e atiavando sua tela de cadastro**

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

**Trocando LOGO E NOMES CHATWOOT TERMOS E POLITICA DE PRIVACIDADE**

</p>
LOGO:
</p>
Acesse seu FTP
</p>
/home/chatwoot/chatwoot/public/brand-assets
</p>
Suba dois arquivos com esse nome
</p>
brand-assets/logo.png
</p>
logo.png

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
mkdir chatwoot
</p>
cd chatwoot
</p>
https://github.com/EngajamentoFlow/chatwoot/blob/main/.env
</p>
https://github.com/EngajamentoFlow/chatwoot/blob/main/docker-compose.yaml
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
</p>
server {
</p>
  server_name <yourdomain.com>;
  </p>
  # Point upstream to Chatwoot App Server
  </p>
  set $upstream 127.0.0.1:3000;
</p>
  # Nginx strips out underscore in headers by default
  </p>
  # Chatwoot relies on underscore in headers for API
  </p>
  # Make sure that the config is set to on.
  </p>
  underscores_in_headers on;
  </p>
  location /.well-known {
  </p>
    alias /var/www/ssl-proof/chatwoot/.well-known;
    </p>
  }
</p>
  location / {
  </p>
    proxy_pass_header Authorization;
    </p>
    proxy_pass http://$upstream;
    </p>
    proxy_set_header Upgrade $http_upgrade;
    </p>
    proxy_set_header Connection "upgrade";
    </p>
    proxy_set_header Host $host;
    </p>
    proxy_set_header X-Forwarded-Proto $scheme;
    </p>
    proxy_set_header X-Forwarded-Ssl on; # Optional
    </p>
    proxy_set_header X-Real-IP $remote_addr;
    </p>
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
</p>
    proxy_http_version 1.1;
    </p>
    proxy_set_header Connection “”;
    </p>
    proxy_buffering off;
</p>
    client_max_body_size 0;
    </p>
    proxy_read_timeout 36000s;
    </p>
    proxy_redirect off;
    </p>
  }
  </p>
  listen 80;
  </p>
}
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

Acesse:

http://IP:3003

Login: admin@admin.com.br
Senha: pgadmin

<img src="https://github.com/EngajamentoFlow/chatwoot/blob/main/Registrar.png" alt="Chatwoot-logo" width="100" />

<img src="https://github.com/EngajamentoFlow/chatwoot/blob/main/Acessando.png" alt="Chatwoot-logo" width="100" />

<img src="https://github.com/EngajamentoFlow/chatwoot/blob/main/Registrar.png" alt="Chatwoot-logo" width="100" />

<img src="https://github.com/EngajamentoFlow/chatwoot/blob/main/Server.png" alt="Chatwoot-logo" width="100" />















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

**Trocando LOGO E NOMES CHATWOOT TERMOS E POLITICA DE PRIVACIDADE**

</p>
LOGO:
</p>
Acesse seu FTP
</p>
/home/chatwoot/chatwoot/public/brand-assets
</p>
Suba dois arquivos com esse nome
</p>
brand-assets/logo.png
</p>
logo.png

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

**Recopile**

cd pastainstalada

docker compose up -d

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="Quepasa-logo" width="200" />
</p>
----------------------------------------------------------------------------
