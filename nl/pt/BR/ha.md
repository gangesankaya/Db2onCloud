---

copyright:
  years: 2014, 2018
lastupdated: "2018-07-19"

---

<!-- Attribute definitions --> 
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}

# Alta disponibilidade (HA)
{: #ha}

Os planos de alta disponibilidade do {{site.data.keyword.Db2_on_Cloud_short}} têm excelentes características de
disponibilidade com um SLA de 99,99% . 
{: shortdesc}

Os planos de alta disponibilidade padrão sem um nó DR fornecem failover contínuo e atualizações contínuas. Eles são gerenciados para você usando nova rota do cliente automática (ACR) e IPs móveis.

Além disso, é possível incluir um Nó de recuperação de desastre geo-replicado. Essa opção de nó DR externo fornece a capacidade de sincronizar rapidamente seus dados em tempo real para um nó de banco de dados em um centro de dados externo do {{site.data.keyword.Bluemix_notm}} de sua escolha. 

[Lista de locais de datacenter nos quais os nós DR estão disponíveis. ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://developer.ibm.com/answers/questions/366888/what-locations-cities-or-countries-is-dashdb-avail.html){:new_window}

O {{site.data.keyword.Db2_on_Cloud_short}} usa a tecnologia Db2 High Availability Disaster Recovery (HADR) no modo `ASYNC` para alcançar o recurso do nó DR externo e fornece `Leitura em espera` no nó DR.

## Como incluir um nó de recuperação de desastre geo-replicado
{: #add_dr}

Para usuários existentes do {{site.data.keyword.Db2_on_Cloud_short}}:
 * É possível incluir um nó DR on demand em instâncias existentes do {{site.data.keyword.Db2_on_Cloud_short}}. Depois de clicar em sua instância no painel do {{site.data.keyword.Bluemix_notm}}, você verá uma opção chamada **Gerenciar recuperação de desastre**. É possível incluir um Nó de recuperação de desastre geo-replicado nesse local.
 * Se você comprou o {{site.data.keyword.Db2_on_Cloud_short}} em um contrato por meio de um representante de vendas e não tiver uma assinatura do {{site.data.keyword.Bluemix_notm}}, entre em contato com seu representante IBM para incluir um nó DR.

Se atualmente você não for um usuário do {{site.data.keyword.Db2_on_Cloud_short}}:
 * Solicite o {{site.data.keyword.Db2_on_Cloud_short}} por meio do {{site.data.keyword.Bluemix_notm}} ou fale com seu representante de vendas.
 * É possível então incluir um nó de DR usando **Gerenciar recuperação de desastre** no console.
<!--- Through the web console, you can also add a disaster recovery (DR) node located in a datacenter of your choice. -->

## Gerenciando nós de alta disponibilidade e de recuperação de desastre
{: #manage_ha_dr}

Para nós de alta disponibilidade padrão, que não são externos, o failover é gerenciado para você pela IBM. A IBM monitora o funcionamento de seu servidor, failover e failback, conforme necessário, incluindo atualizações contínuas e ajuste de escala para manter o maior tempo de atividade possível.

Para Geo-Replicated Disaster Recovery (HADR), deve-se executar failover manualmente usando **Gerenciar recuperação de desastre** no console. Além disso, é possível executar failover usando uma API, conforme descrito [aqui![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://developer.ibm.com/answers/questions/457901/where-can-i-find-api-documentation-for-db2-on-clou.html){:new_window}.

## FAQ
{: #faq}

### Quais são as mudanças requeridas para que um aplicativo use o Db2 para trabalhar com a recuperação de DR após o controle? O nome DNS ou o endereço IP mudam após o controle?

**R**: Não. Você tem dois nomes de host que podem ser resolvidos. Se seu app estiver configurado para usar o Db2 ACR (Active Connection Reroute), então, seu app será roteado novamente para o novo nó primário.

Para obter mais informações sobre o Nó de recuperação de desastre geo-replicado, clique [aqui![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://developer.ibm.com/answers/questions/458385/frequently-asked-questions-for-db2-on-cloud-hadr-g.html){:new_window}.