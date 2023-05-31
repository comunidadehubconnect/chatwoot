<p align="center">
	<img src="https://www.chatwoot.com/docs/img/logo.png" alt="Chatwoot-logo" width="100" />	
	<p align="center">O Chatwoot oferece todas as ferramentas para gerenciar conversas, construir relacionamentos e encantar seus clientes em um só lugar.</p>
</p>
<hr />
</p>
<hr />
<p align="left">
	<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
	<span>Grupo WhatsaAPP: </span>
	<a href="https://chat.whatsapp.com/CLKge3hmHmmBcIL04mBzmT" target="_blank">Grupo</a>
</p>
<hr />
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
yes para todos
</p>

----------------------------------------------------------------------------

**Novos Comandos para atualizar Chatwoot com novas funções**

Atenção um por vez
</p>
sudo -i -u chatwoot
</p>
cd chatwoot
</p>
git checkout develop && git pull
</p>
Apenas se for primeira fez que esta atualizando Ruby
</p>
rvm reinstall ruby-3.2.2
</p>
rvm use 3.2.2 --default
</p>
bundle
</p>
yarn
</p>
rake assets:precompile RAILS_ENV=production
</p>
RAILS_ENV=production bundle exec rake db:migrate
</p>
exit
</p>
systemctl daemon-reload
</p>
systemctl restart chatwoot.target
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

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="Quepasa-logo" width="200" />
</p>

**PIX CNPJ**

```
45959142000119	
```
----------------------------------------------------------------------------
