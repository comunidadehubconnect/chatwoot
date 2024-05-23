<p align="center">
<img src="https://cwmkt.com.br/wp-content/uploads/2024/04/logo_github.png" width="240" />
<p align="center">Seja bem-vindo ao Guia de Instalação Chatwoot 🚀</p>
</p>
  
<p align="center"> 
<a href="https://hubconnect.top" target="_blank">👉 Participe da Comunidade HubConnect 👈</a>
</p>

<hr />
<hr />

<details>
<summary>Manual de Instalação ChatWoot</summary>

```bash
sudo apt update && apt upgrade -y
```

```bash
wget https://get.chatwoot.app/linux/install.sh
```

```bash
chmod +x install.sh
```

```bash
./install.sh --install
```

Use as opções abaixo

yes

app.dominio.com.br

contato@dominio.com.br

yes para todos
</details>

### Alterando Idioma e ativando sua tela de cadastro

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

### Habilitando configurações ocultas do Chatwoot

```bash
sudo -i -u postgres psql
\c chatwoot_production
update installation_configs set locked = false;
\q
```

### NOMES CHATWOOT TERMOS E POLITICA DE PRIVACIDADE

Acesse super Admin

https://seudominio.com.br/super_admin

Opção>installation_configs

LOGO

LOGO_THUMBNAIL

NOMES CHATWOOT:

Alterando nomes na plataforma

INSTALLATION_NAME

BRAND_NAME

TERMOS E POLITICA DE PRIVACIDADE

TERMS_URL

PRIVACY_URL

BRAND_URL

WIDGET_BRAND_URL

<details>
<summary>Downgrade versão do Chatwoot</summary>

### Como fazer downgrade no seu Chatwwoot

```bash
sudo -i -u chatwoot

cd chatwoot

git checkout tag/commit (pega o commit ou tag da versão em https://github.com/chatwoot/chatwoot/releases)

bundle

yarn

rake assets:precompile RAILS_ENV=production

RAILS_ENV=production bundle exec rake db:migrate

exit
```

```bash
systemctl daemon-reload

systemctl restart chatwoot.target
```

Pronto! Downgrade realizado com sucesso ✅😎

</details>
