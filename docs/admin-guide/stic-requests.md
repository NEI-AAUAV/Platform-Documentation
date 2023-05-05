# STIC Requests

- [Balcão Único Digital da UA](https://bud.ua.pt)
- [Sharepoint - Formulários](https://sharepoint.ua.pt/formularios/Requests/Forms/thumbnails1.aspx)

Pode ser preciso estar conectado à VPN da UA para aceder aos links acima.

Breve descrição da necessidade  : maquina virtual para o site nei.web.ua.pt

Descrição adicional Q129  : Solicitar Alojamento de Servidores Virtuais

Sistema Operativo do servidor  : Windows Server 2019

## <small>S221004_0021</small><br> maquina virtual para o site nei.web.ua.pt 

**Tópico:** Alojar (Housing) servidor Virtual no Datacenter da UA <br>
**Beneficiário:** Leandro Silva <br>
**Requisitante:** Nautília Maia <br>
**Data:** 04/10/2022 - 11/10/2022 <br>
**Documentos:**

- nei_web_ua_pt.pfx

**Histórico:**

???+ call-made "04/10/2022"
    O NEI, pretende solicitar uma maquina virtual para o site nei.web.ua.pt

    O que pretendem, uma vez que o seu alojamento é Windows com IIS, precisam de uma VM Linux com SSH.

    As especificações da máquina são 4 cores, com 8gb de RAM e 20GB para a base de dados. Expor os portos 80, 443 e 587.

    Obrigada


??? call-received "06/10/2022"
    Bom dia Leandro,

    Do que sabemos, o site tem estado no hosting.

    As tecnologias que o hosting suporta deixaram de ser suficientes para os requisitos da vossa aplicação?

    Obrigado.

    José Ramalho


??? call-made "06/10/2022"
    Boa tarde, José Ramalho,

    Sim, como alteramos as tecnologias, precisamos agora de requisitos diferentes. Posso tentar enquadrar mais especificamente o nosso ponto de situação.

    O NEI esteve a fazer alterações à stack do website para automatizar e facilitar o desenvolvimento e manutenção do website em futuros mandatos do NEI. Para isso, colocamos tudo em dockers e modernizamos algumas tecnologias - convertemos, por exemplo, a API de PHP para FastAPI e alteramos a BD para PostgreSQL. Contudo, ao tentar requisitar outra máquina nos STIC para colocar a nossa nova stack, não conseguimos obter o que queríamos. Os vossos serviços limitavam-nos a uma máquina Windows com IIS, com uma BD pré-criada em MySQL, e acesso por FTP, e o essencial seria mesmo uma máquina Linux com acesso por SSH por onde poderíamos correr a nossa stack em docker com Continuous Deployment por Github Actions.

    Caso seja importante, deixo já definido que o responsável administrativo / técnico para esta nova VM seria eu, Leandro Silva, ou seja, o mesmo responsável do atual hosting.

    Obrigado pela atenção,

    Leandro Silva


??? call-received "06/10/2022"
    Bom dia Leandro,

    O NEI já tem uma VM com Ubuntu, aauav-nei.ua.pt. A esta VM têm acesso os UUs:

    danielteixeira31@ua.pt
    joaosilva9@ua.pt
    miguel.fradinho@ua.pt
    ruicoelho@ua.pt

    Têm algum problema em usar esta VM?


??? call-made "10/10/2022"
    Boa tarde,

    O NEI sofreu mudanças extremas na equipa, pelo que não houve knowledge sharing do que foi feito ou do que está nessa VM.
    Como não estamos mais em contacto com esses 4 utilizadores, teríamos preferência por uma VM nova. Nós já temos inclusive outro DNS preparado para a nova VM, nei-aauav.pt, uma vez que não temos acesso à administração do anterior.
    No entanto, assumo que atualmente essa VM está em desuso, e que, portanto, pode ser eliminada com segurança. Agora percebo que não possa vir da minha decisão eliminar a VM, mas se conseguir entrar em contacto com algum desses utilizadores, tenho a certeza que eles dirão que a podem apagar.

    Obrigado pela compreensão,

    Leandro Silva


??? call-received "10/10/2022"
    Do nosso lado, só precisamos que nos informem que a VM é para repor da raíz e entregamos a VM limpa. Esta é a VM que foi atribuída ao NEI para o que entenderem.


??? call-made "10/10/2022"
    Nesse caso, agradecíamos que repusessem a VM de raiz.
    Consegue nos indicar quais são as especificações dessa VM?

    Obrigado


??? call-received "10/10/2022"
    1 VCPU, 2GB RAM e 20GB disco. O pedido apenas será retomado quando alguém no DETI confirme a constituição dos atuais membros do NEI (já fizemos o pedido).


??? call-received "10/10/2022"
    A VM foi recriada.
    Aumentei os recursos para 2vCPUs, 4GB de RAM e 20GB.
    Podes aceder por ssh com o teu UU.


??? call-made "21/11/2022"
    Boa tarde, na necessidade de continuar este pedido, acabei por criar um pedido diferente quando talvez teria sido melhor dar continuidade a este mesmo.

    Por essa razão, e seguindo o indicação do STIP Helpdesk, envio a referência do pedido novo que criei para garantir de que fica ao encargo da mesma pessoa: **S221118_0033**

    De reforçar que este pedido tem um caráter **urgente**, uma vez que se avizinha um evento que depende da existência do website.

    Obrigado por toda a atenção dispendida.


??? call-received "22/11/2022"
    Boa tarde,

    Este pedido diz respeito à disponibilização de uma VM, que vocês já tinham, e que foi recriada. Há algum problema com a VM? Não conseguem aceder?


??? call-made "22/11/2022"
    Boa tarde,

    Neste pedido pedi para que abrissem as portas 80, 443 e 587 para o exterior da UA, o qual foi recusado por a máquina se encontrar numa rede interna que não tem acessos abertos para o exterior.

    Por essa razão, abri outro pedido que pedisse que a máquina fosse então movida para uma rede com acesso ao exterior.

    Como não obtive resposta, foi-me recomendado pelo Helpdesk dos STIC para reabrir este pedido e referenciar o pedido que tinha aberto, S221118_0033, uma vez que estão relacionados e seria mais simples se a mesma pessoa que estava anteriormente responsável resolvesse o pedido.

    Peço desculpa pela confusão, mas agradecia que tratassem este pedido com cariz urgente, uma vez que se avizinha um evento que depende da existência da máquina.

    Obrigado

    No pedido anterior estava escrito o seguinte:

    ...


??? call-received "23/11/2022"
    A VM mudou de rede e manteve o mesmo nome dns: aauav-nei.ua.pt. Falta abrir os portos solicitados.


??? call-made "25/11/2022"
    Boa tarde, Hermano Pereira,

    Não querendo causar obstinação, encontro-me a reabrir o pedido só para me assegurar de que estas questões colocadas no pedido **S221118_0033** também eram resolvidas, uma vez que neste ficou apenas resolvido a eliminação do site nei.web.ua.pt:

    "Seria possível depois mudar o domínio da nova máquina aauav-nei.ua.pt para o mesmo domínio, nei.web.ua.pt?"

    "E seria possível manter também o atual certificado com CN *.web.ua.pt?"

    Obrigado pela atenção,

    Leandro Silva


??? call-made "27/11/2022 (email)"
    Boa tarde, Hermano Pereira,
 
    Estou a enviar esta mensagem devido à urgência em que tempos em ter o pedido S221004_0021 resolvido, isto é, ter as portas abertas ao exterior da UA e com o certificado da UA. Obtive a informação de que estava responsável pelo nosso pedido através do Helpdesk dos STIC.
    
    Como precisávamos de ter o pedido resolvido até terça, seria fundamental que nos avisasse se esta data é suficiente para o conseguirem resolver.
    
    Cumprimentos,
    Leandro Silva


??? call-received "28/11/2022 (email)"
    Olá Leandro,
    
    Os acessos estão configurados e a criação do certificado está a ser tratada pelo colega responsável.
    
    Temos uma dúvida: foi pedido a abertura do porto 587 em direção à máquina do nei a partir da Internet. Foi equívoco e é ao contrario ou pretendem instalar um serviço de correio electrónico.
    
    Cumprimentos,
    Hermano Filipe D. Pereira


??? call-made "28/11/2022 (email)"
    Olá Hermano,
    
    Obrigado pela resposta.

    Não, apenas pretendíamos comunicar com outro servidor de correio eletronico externo à UA, não instaltar. Haveria algum problema?

    Cumprimentos,
    
    Leandro Silva


??? call-received "28/11/2022 (email)"
    Olá,
 
    E qual é o destino? Gmail?


??? call-made "28/11/2022 (email)"
    Sim, para um SMTP Gmail.


??? call-received "29/11/2022"
    Bom dia Leandro,

    A fim de esclarecer de forma mais rápida o que ainda está pendente, pode facultar-me um contato telefónico ou ligar para o meu número (964XXXXXX)?

    Cumprimentos,

    José Ramalho


??? call-made "29/11/2022"
    O meu contacto telefónico: +351 912 XXX XXX


??? call-received "30/11/2022"
    Bom dia Leandro,

    Segue em anexo o certificado. A password de acesso é:

    xxxxxxxxxxxxxxx

    O endereço nei.web.ua.pt já se encontra a apontar para a máquina aauav-nei.ua.pt.

    Como o registo foi efetuado recentemente, é possível que a alteração não seja visivel de imediato.

    Relativamente às restantes regras, os colegas do firewall entrarão em contato quando estiver concluído.

    Obrigado.

    José Ramalho


??? call-received "30/11/2022 (email)"
    Boa tarde Leandro,
 
    Acabei de encerrar o pedido por já ter tudo concluído, a mudança de DNS e o certificado.
    Entretanto falei com o colega Hermano que me indicou já ter aberto os portos solicitados mas estando ainda a aguardar pela vossa resposta em relação ao porto 587.
    Podem contatá-lo diretamente respondendo ao email que vos foi enviado a 28/11.
    
    Cumprimentos,
    Hermano Filipe D. Pereira


??? call-made "01/12/2022 (email)"
    Boa noite, Hermano Pereira,

    Estou a enviar este email por indicação do José Ramalho.

    Não sei se seria a pessoa responsável pela questão da abertura das portas para o exterior da UA, mas ainda não confirmei a abertura das portas 80 e 443 na máquina aauav-nei.ua.pt, apesar do que foi dito pelo José Ramalho.

    Sobre a questão da porta 587, seria para comunicar com o SMTP Gmail. Haveria algum problema com este ponto?
    
    Obrigado,
    Leandro Silva


??? call-made "05/12/2022"
    Boa dia,

    Estou a reabrir o pedido para comunicar que ainda não confirmei a **abertura das portas 80 e 443** na máquina aauav-nei.ua.pt.

    Tinha também pedido a abertura da porta 587, para comunicar com o SMTP Gmail, mas caso esta porta requeira mais tempo para certas averiguações, pedia que abrissem primeiramente a 80 e 443 o mais breve possível.

    Estamos seriamente dependentes da abertura dessas portas **até o dia 7, quarta-feira**.

    Obrigado pela compreensão,

    Leandro Silva


??? call-received "05/12/2022 (email)"
    Olá,
 
    Não há problema, acessos já estão configurados no firewall da UA. Se tiverem problemas de conectividade quando testarem, poderei ajudar a diagnosticar .
    
    Cumprimentos,
    Hermano Filipe D. Pereira


??? call-received "05/12/2022"
    Boa tarde,

    Os portos 80 e 443 já se encontravam configurados mas apenas estavam a funcionar dentro da UA porque o registo DNS da máquina só estava visível para o interior da UA. Testem por favor.

    Relativamente ao porto 587, chegaram a responder ao mail e às questões colocadas pelo colega Hermano?

    Obrigado.


??? call-made "05/12/2022 (email)"
    Muito obrigado, Hermano Pereira,

    Já confirmei a conectividade!

    Sobre a porta 587, não haveria maneira de a abrir também?

    Cumprimentos,
    Leandro Silva


??? call-received "05/12/2022 (email)"
    Olá,
 
    Supostamente o 587 está aberto para o gmail! Testaram e não funciona? Não encontro tentativas de acesso ao porto 587 a partir de aauav-nei.ua.pt.
    
    HF


??? call-made "05/12/2022 (email)"
    Olá, Hermano Pereira,

    Sim, já confirmei também a existência da porta 587.

    Muito obrigado,
    Leandro Silva



## <small>S221118_0033</small><br> Alteração da rede da máquina do NEI 

**Tópico:** Solicitar Operações em Sites Web Genéricos <br>
**Beneficiário:** Leandro Silva <br>
**Requisitante:** Leandro Silva <br>
**Data:** 18/11/2022 - 23/11/2022 <br>
**Histórico:**


??? call-received "09/11/2022 (email)"
    Caro utilizador,
    
    O seu pedido nº 348 de criação de regras no foi recusado.
    
    Motivo da recusa:
    
    A máquina aauav-nei.ua.pt encontra-se numa rede interna que nao tem acessos abertos para o exterior.
    Para a abertura de acessos para a internet a máquina terá que mudar de rede.
    
    O pedido terá que ser feito em https://bud.ua.pt .


??? call-made "18/11/2022"
    Boa tarde,

    No pedido nº 348 de criação de regras foi nos recusado a abertura das portas 80, 443 e 587 para o exterior da UA por termos a máquina numa rede interna sem acessos abertos para o exterior.
    Entretanto, tivemos a preparar-nos para mudar completamente a nossa stack para a nova máquina, a aauav-nei.ua.pt, e descartar a atual, a nei.web.ua.pt.

    Presumindo que a única rede com acesso ao exterior seja dentro do domínio web.ua.pt, seria possível mudar o domínio da nova máquina para nei.web.ua.pt, e descartar a que tem esse domínio de momento?
    Acerca do certificado, seria possível manter também o atual com CN *.web.ua.pt?

    Obrigado pela atenção.
    

??? call-received "22/11/2022"
    Bom dia,

    Quando tiverem migrado o site nei.web.ua.pt para a nova máquina devem fazer um pedido para a eliminação do site da plataforma de alojamento de sites web de projectos da UA em https://bud.ua.pt -> Preciso Algo -> Comunicação e colaboração -> Alojamento de conteúdos web -> Solicitar Operações em Sites Web Genéricos.

    Damos este pedido como terminado pois o assunto que refere já se encontra em tratamento no pedido S221004_0021.

    Bom trabalho!

    Alex Angélico


??? call-made "22/11/2022"
    Boa tarde,

    Neste pedido pedi para que abrissem as portas 80, 443 e 587 para o exterior da UA, o qual foi recusado por a máquina se encontrar numa rede interna que nao tem acessos abertos para o exterior.

    Por essa razão, abri outro pedido que pedisse que a máquina fosse então movida para uma rede com acesso ao exterior.

    Como não obtive resposta, foi me recomendado pelo Helpdesk dos STIC para reabrir este pedido e referenciar o pedido que tinha aberto, **S221118_0033**, uma vez que estão relacionados e seria mais simples se a mesma pessoa que estava anteriormente responsável resolvesse o pedido.

    Obrigado


??? call-received "23/11/2022"
    Bom dia,

    As questões que coloca já estão a ser respondidas no pedido S221004_0021, por esse motivo este pedido é encerrado.

    Quando tiverem migrado o site nei.web.ua.pt para a nova máquina devem fazer um pedido para a eliminação do site da plataforma de alojamento de sites web de projectos da UA em https://bud.ua.pt -> Preciso Algo -> Comunicação e colaboração -> Alojamento de conteúdos web -> Solicitar Operações em Sites Web Genéricos.

    Bom trabalho!

    Alex Angélico


??? call-made "24/11/2022"
    Boa tarde,

    Já confirmei a existência da máquina na nova rede. Falta então só **abrir as portas 80, 443 e 587** para o exterior da UA.

    Estamos preparados para a migração da nossa stack para a nova máquina, portanto solicito então aqui a **eliminação da máquina** nei.web.ua.pt.

    Seria possível depois **mudar o domínio** da nova máquina aauav-nei.ua.pt para o mesmo domínio, nei.web.ua.pt? 

    E seria possível **manter também o atual certificado** com CN *.web.ua.pt?

    Obrigado


??? call-received "25/11/2022"
    Boa tarde,

    De acordo com o solicitado o site nei.web.ua.pt foi eliminado.

    As restantes questões estão a ser tratadas pelos colegas no pedido S221004_0021.

    Bom trabalho!

    Alex Angélico


??? call-made "27/11/2022 (email)"
    Boa tarde, Hermano Pereira,
 
    Estou a enviar esta mensagem devido à urgência em que tempos em ter o pedido S221004_0021 resolvido, isto é, ter as portas abertas ao exterior da UA e com o certificado da UA. Obtive a informação de que estava responsável pelo nosso pedido através do Helpdesk dos STIC.
    
    Como precisávamos de ter o pedido resolvido até terça, seria fundamental que nos avisasse se esta data é suficiente para o conseguirem resolver.
    
    Cumprimentos,
    Leandro Silva


??? call-received "28/11/2022 (email)"
    Olá Leandro,
    
    Os acessos estão configurados e a criação do certificado está a ser tratada pelo colega responsável.
    
    Temos uma dúvida: foi pedido a abertura do porto 587 em direção à máquina do nei a partir da Internet. Foi equívoco e é ao contrario ou pretendem instalar um serviço de correio electrónico.
    
    Cumprimentos,
    Hermano Filipe D. Pereira


??? call-made "28/11/2022 (email)"
    Olá Hermano,
    
    Obrigado pela resposta.

    Não, apenas pretendíamos comunicar com outro servidor de correio eletronico externo à UA, não instaltar. Haveria algum problema?

    Cumprimentos,
    
    Leandro Silva


??? call-received "28/11/2022 (email)"
    Olá,
 
    E qual é o destino? Gmail?


??? call-made "28/11/2022 (email)"
    Sim, para um SMTP Gmail.


??? call-received "30/11/2022 (email)"
    Boa tarde Leandro,
 
    Acabei de encerrar o pedido por já ter tudo concluído, a mudança de DNS e o certificado.
    Entretanto falei com o colega Hermano que me indicou já ter aberto os portos solicitados mas estando ainda a aguardar pela vossa resposta em relação ao porto 587.
    Podem contatá-lo diretamente respondendo ao email que vos foi enviado a 28/11.
    
    Cumprimentos,
    Hermano Filipe D. Pereira


??? call-made "01/12/2022 (email)"
    Boa noite, Hermano Pereira,

    Estou a enviar este email por indicação do José Ramalho.

    Não sei se seria a pessoa responsável pela questão da abertura das portas para o exterior da UA, mas ainda não confirmei a abertura das portas 80 e 443 na máquina aauav-nei.ua.pt, apesar do que foi dito pelo José Ramalho.

    Sobre a questão da porta 587, seria para comunicar com o SMTP Gmail. Haveria algum problema com este ponto?
    
    Obrigado,
    Leandro Silva


??? call-received "05/12/2022 (email)"
    Olá,
 
    Não há problema, acessos já estão configurados no firewall da UA. Se tiverem problemas de conectividade quando testarem, poderei ajudar a diagnosticar .
    
    Cumprimentos,
    Hermano Filipe D. Pereira


??? call-made "05/12/2022 (email)"
    Muito obrigado, Hermano Pereira,

    Já confirmei a conectividade!

    Sobre a porta 587, não haveria maneira de a abrir também?

    Cumprimentos,
    Leandro Silva


??? call-received "05/12/2022 (email)"
    Olá,
 
    Supostamente o 587 está aberto para o gmail! Testaram e não funciona? Não encontro tentativas de acesso ao porto 587 a partir de aauav-nei.ua.pt.
    
    HF


??? call-made "05/12/2022 (email)"
    Olá, Hermano Pereira,

    Sim, já confirmei também a existência da porta 587.

    Muito obrigado,
    Leandro Silva



## <small>S221220_0003</small><br> Autenticação com o IDP da UA 

**Título:** Solicitar Operações em Sites Web Genéricos <br>
**Beneficiário:** Leandro Silva <br>
**Requisitante:** Leandro Silva <br>
**Data:** 20/12/2022 - 23/12/2022 <br>
**Histórico:**

???+ call-made "20/12/2022"
    Boa dia,

    Há 11 dias atrás realizei um pedido no https://identity.ua.pt/oauth/apps para integração no website do Núcleo de Estudantes de Informática, mas continua Sob aprovação. Desta maneira, e sob orientação do Helpdesk dos STIC, tento procurar feedback por este meio para saber se preciso de acrescentar alguma informação. 

    Não sabendo como identificar o pedido, envio o nome da aplicação e a key que me foi fornecida:
    
    **Nome:** Núcleo de Estudantes de Informática

    **Chave:** _82e3318ee5c5cf2c7d7f7a1367fd4b3ea40858f08a

    Obrigado pela atenção,

    Leandro Silva, Vogal da Administração Interna do NEI
    912XXXXXX


??? call-received "03/01/2023"
    Boa tarde, o pedido foi agora aprovado, pedimos desculpa pela demora na resposta.



## <small>S230405_0015</small><br> Bloqueio da conexão SMTP GMAIL 

**Tópico:** Criar|alterar regras de acesso no firewall <br>
**Beneficiário:** Leandro Silva <br>
**Requisitante:** Leandro Silva <br>
**Data:** 05/04/2023 - 12/04/2023 <br>
**Histórico:**

???+ call-made "05/04/2023"
    Boa tarde, no seguimento dos pedidos:

    Nº: **S221004_0021** 

    Data: 04/10/2022 12:24:03

    Nº: **S221118_0033** 

    Data: 18/11/2022 14:56:18

    Nº: **S221220_0003** 

    Data: 20/12/2022 09:51:53

    quero solicitar mais uma vez a abertura da porta **587/tcp** da máquina **nei.web.ua.pt** (aauav-nei.ua.pt) para o exterior da UA.

    Na altura, quando dei o pedido por concluído, penso que tinha verificado com o **Hermano Pereira** que a conexão existia.
    Supostamente a porta **587** estava aberta para o **smtp.gmail.com**.

    No entanto, deixamos de verificar isso no dia anterior. Tentamos perceber a origem do problema, e após corrermos o telnet dentro da máquina:
    telnet smtp.gmail.com 587
    verificamos que não conseguiamos estabeler uma conexão TCP.

    Haverá alguma regra na firewall que esteja a bloquear a conexão?

    Obrigado pela atenção.

    Leandro Silva,
    Vogal do Núcleo de Estudantes de Informática


??? call-received "05/04/2023"
    Boa tarde,

    Este pedido foi colocado no tópico errado.

    nslookup nei.web.ua.pt
    Server: dns3.ua.pt
    Address: 192.168.227.20

    Name: aauav-nei.ua.pt
    Address: 193.137.172.78
    Aliases: nei.web.ua.pt

    Bom trabalho!
    Alex Angélico


??? call-received "12/04/2023"
    Acesso configurado. Pedimos que testem.




## <small>S230424_0026</small><br> Aumento do espaço em disco


**Tópico:** Solicitar Operações em Sites Web Genéricos <br>
**Beneficiário:** Leandro Silva <br>
**Requisitante:** Leandro Silva <br>
**Data:** 24/04/2023 - 28/04/2023 <br>
**Histórico:**


???+ call-made "24/04/2023"
    Boa tarde,

    Gostaria de solicitar um aumento de espaço de armazenamento. Estou usando este espaço para armazenar materiais educacionais que, atualmente, está cheio de anotações, arquivos e zips usados para ajudar os alunos a estudar para as unidades curriculares. 

    Com o tempo, este acúmulo de materiais tem crescido e atingido o limite do espaço atualmente disponível. Isso impede o correto funcionamento dos serviços ativos e de continuar a adicionar novos recursos e materiais.

    Por este motivo, peço que seja considerada a alocação de espaço adicional de armazenamento na máquina. Neste momento, **temos 20GB de memória disco, e gostariamos de duplicar este valor para 40GB**. Qualquer quantidade de espaço adicional fornecida seria muito apreciada.

    Agradeço antecipadamente pela atenção e ajuda.

    Cumprimentos,
    Leandro Silva, Vogal do Núcleo de Estudantes de Informática


??? call-received "28/04/2023"
    O disco da VM foi aumentado para 40GB. Podem estender no mesmo no SO.

