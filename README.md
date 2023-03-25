<p align="center">
	<img src="https://www.portainer.io/hubfs/portainer-logo-black.svg" alt="Quepasa-logo" width="100" />	
	<p align="center">Implante, configure, solucione problemas e proteja contêineres em minutos no Kubernetes, Docker, Swarm e Nomad em qualquer data center, nuvem, borda de rede ou dispositivo IIOT</p>
</p>
<hr />
<p align="left">
	<img src="https://telegram.org/favicon.ico" alt="Telegram-logo" width="32" />
	<span>Grupo e Canal Telegram: </span>
	<a href="https://t.me/quepasa_api" target="_blank">Grupo</a>
	<span> || </span>
	<a href="https://t.me/quepasa_channel" target="_blank">Canal</a>
</p>
<hr />
<p align="left">
	<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
	<span>Grupo WhatsaAPP: </span>
	<a href="https://chat.whatsapp.com/Cv5WfmujRzE09yQ6hagYim" target="_blank">Grupo</a>
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

*Versão Docker*

**Manual de Instalação ChatWoot via Docker**

sudo apt update && apt upgrade -y
</p>
Baixe o contêiner do Chatwoot do Docker Hub usando o seguinte comando
</p>
sudo docker pull chatwoot/chatwoot
</p>
mkdir chatwoot
</p>
cd chatwoot
</p>
wget -O docker-compose.yaml https://raw.githubusercontent.com/chatwoot/chatwoot/develop/docker-compose.production.yaml
</p>
nano docker-compose.yaml
</p>
Prepare o banco de dados executando as migrações
</p>
docker compose run --rm rails bundle exec rails db:chatwoot_prepare
</p>
Coloque o serviço em funcionamento
</p>
docker compose up -d
</p>
</p>

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="Quepasa-logo" width="200" />
</p>
----------------------------------------------------------------------------
