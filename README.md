<h1>Simulação - Análise de ataque de rede</h1>

 ### You can also read this in: [English](https://github.com/GLMello/Sim-Atk-Anl)

<h2>Descrição</h2>
Este projeto consiste em analisar uma simulação de um ataque de rede, identificar o tipo de ataque e explicar de que maneira ele afetou o funcionamento da página alvo. 
<br />


<h2>Cenário</h2>
Você trabalha como analista de segurança para uma agência de viagens que anuncia vendas e promoções no site da empresa. Os funcionários da empresa acessam frequentemente a página de vendas da empresa para procurar pacotes de férias que possam interessar seus clientes.

Uma tarde, você recebe um alerta automático do seu sistema de monitoramento indicando um problema com o servidor web. Você tenta visitar o site da empresa, mas recebe uma mensagem de erro de tempo limite de conexão no seu navegador.

Você usa um "packet sniffer" para capturar pacotes de dados em trânsito vindo para ou saindo do servidor. Você observa um grande número de solicitações do tipo TCP SYN vindas de um endereço de IP desconhecido. O servidor aparenta estar sobrecarregado pelo volume de tráfego e está perdendo a capacidade de responder ao número anormal de solicitações de conexão. Você suspeita que o servidor esteja sendo atacado por um ator malicioso.

Você desconecta o servidor temporariamente para que ele possa se recuperar e voltar a operar normalmente. Você também configura o firewall da empresa para bloquear o endereço de IP que estava enviando o número anormal de solicitações de conexão. Você sabe que esta solução não vai durar muito tempo, pois um atacante pode falsificar seu endereços de IP para fugir desse bloqueio. Você precisa alertar seu gerente sobre esse problema rapidamente e discutir os próximos passos para interromper esse atacante e evitar que esse problema ocorra novamente. Você precisará estar preparado para informar ao seu chefe sobre o tipo de ataque que você descobriu e como ele estava afetando o servidor e os funcionários.

<h2>Recursos </h2>

 ### [Registro TCP/HTTP](https://docs.google.com/spreadsheets/d/1PGqx7XkiAq2m5147FqyZ06JhLyrprZ0mQvwBBk8vJ_I/template/preview)

<h2>Passo a passo</h2>

<p align="left">
Ao analisar o registro me deparei com as seguintes tentativas de conexão: <br/><br />
<img src="https://i.imgur.com/mb3ijXT.png" height="55%" width="55%" alt="Registros anormais"/>
<br /><br />
Este comportamento se mantém, até o ponto no qual o servidor fica sobrecarregado e acaba por não conseguir responder a mais nenhuma conexão:
<br /><br />
<img src="https://i.imgur.com/GbTdY1T.png" height="55%" width="55%" alt="Agravação"/>
<br /><br />
Em seguida, decidi analisar estes registros anormais individualmente.
Pude então notar dois fatores em comum, o ip de origem e o tipo de pacote enviado por ele.  <br/><br />
<img src="https://i.imgur.com/4EzNKAl.png" height="55%" width="55%" alt="Padrão"/>
<br /><br />
Logo, pude concluir que o ataque sofrido foi do tipo DoS SYN, já que o ponto de origem foi único e abusou do pedido de sincronização.  <br/><br />
O passo final foi elaborar um relatório utilizando a informação deduzida em conjunto com a fornecida no cenário.
<br /><br />
<img src="https://i.imgur.com/yL6gp3p.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h2>Nota</h2>

 Este projeto faz parte do curso [Google Cybersecurity Professional Certificate.](https://www.coursera.org/professional-certificates/google-cybersecurity) <br />
