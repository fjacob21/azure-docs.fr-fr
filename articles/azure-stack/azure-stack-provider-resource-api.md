---
title: API d’utilisation des ressources de fournisseur | Microsoft Docs
description: Informations de référence sur l’utilisation de ressources API, lesquelles récupèrent des informations relatives à l’utilisation d’Azure Stack
services: azure-stack
documentationcenter: ''
author: mattbriggs
manager: femila
editor: ''
ms.service: azure-stack
ms.workload: na
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 02/22/2018
ms.author: mabrigg
ms.reviewer: alfredop
ms.openlocfilehash: 763b0af9c258a70392e8c7ebbb4c107e94fce5b2
ms.sourcegitcommit: a0be2dc237d30b7f79914e8adfb85299571374ec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2018
---
# <a name="provider-resource-usage-api"></a>API Utilisation des ressources de fournisseur
Le terme *fournisseur* s’applique à l’administrateur de services et à tous les fournisseurs délégués. Les opérateurs et fournisseurs délégués Azure Stack peuvent utiliser l’API d’utilisation du fournisseur pour consulter l’utilisation de leurs locataires directs. Par exemple, comme indiqué dans le diagramme, P0 peut appeler l’API du fournisseur pour obtenir des informations sur l’utilisation directe de P1 et de P2, et P1 peut effectuer un appel pour obtenir des informations relatives à l’utilisation de P3 et P4.

![Modèle conceptuel de la hiérarchie des fournisseurs](media/azure-stack-provider-resource-api/image1.png)

## <a name="api-call-reference"></a>Référence de l’appel d’API
### <a name="request"></a>Requête
La requête obtient les détails de la consommation pour les abonnements demandés et pour la période demandée. Il n’existe aucun corps de demande.

Cette API d’utilisation est une API de fournisseur. Un rôle Propriétaire, Collaborateur ou Lecteur doit donc être affecté à l’appelant dans l’abonnement du fournisseur.

| **Méthode** | **URI de la requête** |
| --- | --- |
| GET |https://{armendpoint}/subscriptions/{subId}/providers/Microsoft.Commerce/subscriberUsageAggregates?reportedStartTime={reportedStartTime}&reportedEndTime={reportedEndTime}&aggregationGranularity={granularity}&subscriberId={sub1.1}&api-version=2015-06-01-preview&continuationToken={token-value} |

### <a name="arguments"></a>Arguments
| **Argument** | **Description** |
| --- | --- |
| *armendpoint* |Point de terminaison Azure Resource Manager de votre environnement Azure Stack. La convention Azure Stack est que le nom du point de terminaison Azure Resource Manager soit au format `https://adminmanagement.{domain-name}`. Par exemple, pour le kit de développement, si le nom du domaine est *local.azurestack.external*, le point de terminaison Resource Manager est `https://adminmanagement.local.azurestack.external`. |
| *subId* |ID d’abonnement de l’utilisateur qui effectue l’appel. |
| *reportedStartTime* |Heure de début de la requête. La valeur de *DateTime* doit être au format Coordinated Universal Time (UTC) et indiquer le début de l’heure ; par exemple, 13:00. Pour l’agrégation quotidienne, définissez cette valeur sur minuit au format UTC. Le format est l’ISO 8601 *échappé*. Par exemple *2015-06-16T18%3a53%3a11%2b00%3a00Z*, où les deux-points sont échappés avec*%3a* et le signe plus est échappé avec *%2b* afin qu’il soit adapté aux URI. |
| *reportedEndTime* |Heure de fin de la requête. Les contraintes qui s’appliquent à *reportedStartTime* s’appliquent également à cet argument. La valeur de *reportedEndTime* ne peut pas être la date actuelle ou ultérieure à la date actuelle. Dans ce cas, le résultat a la valeur « traitement non terminé ». |
| *aggregationGranularity* |Paramètre facultatif qui a deux valeurs potentielles discrètes : quotidienne et horaire. Comme le suggèrent les valeurs, l’une retourne les données avec une granularité journalière, et l’autre est une résolution horaire. L’option quotidienne est la valeur par défaut. |
| *subscriberId* |l'ID d'abonnement. Pour obtenir des données filtrées, l’ID d’abonnement d’un locataire direct du fournisseur est exigé. Si aucun paramètre d’ID d’abonnement n’est spécifié, l’appel retourne les données d’utilisation pour tous les locataires directs du fournisseur. |
| *api-version* |Version du protocole utilisé pour effectuer cette requête. Cette valeur est définie sur *2015-06-01-preview*. |
| *continuationToken* |Jeton récupéré à partir du dernier appel au fournisseur d’API d’utilisation. Ce jeton est nécessaire quand une réponse comprend plus de 1 000 lignes. Il joue alors le rôle de signet pour la progression. En l'absence du jeton, les données sont récupérées à partir du début de la journée ou de l’heure, en fonction de la granularité transmise. |

### <a name="response"></a>response
GET /subscriptions/sub1/providers/Microsoft.Commerce/subscriberUsageAggregates?reportedStartTime=reportedStartTime=2014-05-01T00%3a00%3a00%2b00%3a00&reportedEndTime=2015-06-01T00%3a00%3a00%2b00%3a00&aggregationGranularity=Daily&subscriberId=sub1.1&api-version=1.0

```json
{
"value": [
{

"id":
"/subscriptions/sub1.1/providers/Microsoft.Commerce/UsageAggregate/sub1.1-

meterID1",
"name": "sub1.1-meterID1",
"type": "Microsoft.Commerce/UsageAggregate",

"properties": {
"subscriptionId":"sub1.1",
"usageStartTime": "2015-03-03T00:00:00+00:00",
"usageEndTime": "2015-03-04T00:00:00+00:00",
"instanceData":"{\"Microsoft.Resources\":{\"resourceUri\":\"resourceUri1\",\"location\":\"Alaska\",\"tags\":null,\"additionalInfo\":null}}",
"quantity":2.4000000000,
"meterId":"meterID1"

}
},

…
```

### <a name="response-details"></a>Détails de la réponse
| **Argument** | **Description** |
| --- | --- |
| *id* |ID unique de l’agrégat d’utilisation. |
| *name* |Nom de l’agrégat d’utilisation. |
| *type* |Définition de la ressource. |
| *subscriptionId* |Identificateur d’abonnement de l’utilisateur Azure Stack. |
| *usageStartTime* |Heure de début, au format UTC, du compartiment d’utilisation auquel appartient cet agrégat d’utilisation.|
| *usageEndTime* |Heure de fin, au format UTC, du compartiment d’utilisation auquel appartient cet agrégat d’utilisation. |
| *instanceData* |Paires clé-valeur des détails de l’instance (dans un nouveau format) :<br> *resourceUri* : ID de ressource complet, qui inclut les groupes de ressources et le nom de l’instance. <br> *location* : région dans laquelle ce service a été exécuté. <br> *tags* : balises de ressources spécifiées par l’utilisateur. <br> *additionalInfo* : informations supplémentaires sur la ressource consommée, par exemple, la version du système d’exploitation ou le type d’image. |
| *quantity* |Quantité de ressources consommées au cours de cette période. |
| *meterId* |ID unique de la ressource consommée (également appelé *ResourceID*). |


## <a name="retrieve-usage-information"></a>Récupérer les informations sur l’utilisation

Pour générer les données d’utilisation, vous devez disposer de ressources en cours d’exécution qui utilisent activement le système, comme une machine virtuelle active ou un compte de stockage contenant des données. Si vous ne savez pas si vous avez des ressources en cours d’exécution dans la Place de marché Azure Stack, déployez une machine virtuelle et consultez le panneau d’analyse de la machine virtuelle pour vous assurer qu’elle est en cours d’exécution. Pour afficher les données d’utilisation, utilisez les cmdlets PowerShell suivantes :

1. [Installer PowerShell pour Azure Stack.](azure-stack-powershell-install.md)
2. [Configurer l’environnement PowerShell de l’utilisateur Azure Stack](user/azure-stack-powershell-configure-user.md) ou [Configurer l’environnement PowerShell de l’opérateur Azure Stack](azure-stack-powershell-configure-admin.md) 
3. Pour récupérer les données d’utilisation, utilisez la cmdlet PowerShell [Get-UsageAggregates](/powershell/module/azurerm.usageaggregates/get-usageaggregates) :
```powershell
Get-UsageAggregates -ReportedStartTime "<Start time for usage reporting>" -ReportedEndTime "<end time for usage reporting>" -AggregationGranularity <Hourly or Daily>
```

## <a name="next-steps"></a>Étapes suivantes
[Informations de référence sur l’API d’utilisation des ressources de locataire](azure-stack-tenant-resource-usage-api.md)

[Questions fréquentes (FAQ) relatives à l’utilisation](azure-stack-usage-related-faq.md)
