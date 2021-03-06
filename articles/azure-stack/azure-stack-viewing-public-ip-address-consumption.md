---
title: "Afficher la consommation d’adresses IP publiques dans Azure Stack | Microsoft Docs"
description: "Les administrateurs peuvent afficher la consommation d’adresses IP publiques dans une région"
services: azure-stack
documentationcenter: 
author: mattbriggs
manager: femila
editor: 
ms.assetid: 0f77be49-eafe-4886-8c58-a17061e8120f
ms.service: azure-stack
ms.workload: na
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: get-started-article
ms.date: 02/28/2018
ms.author: mabrigg
ms.openlocfilehash: 50bf01d6de6105d3041c6bb88e803f3d110f751d
ms.sourcegitcommit: 782d5955e1bec50a17d9366a8e2bf583559dca9e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2018
---
# <a name="view-public-ip-address-consumption-in-azure-stack"></a>Afficher la consommation d’adresses IP publiques dans Azure Stack

*S’applique à : systèmes intégrés Azure Stack et Kit de développement Azure Stack*

En tant qu’administrateur, vous pouvez afficher les éléments suivants :
 - Le nombre d’adresses IP publiques qui ont été attribuées à des locataires.
 - Le nombre d’adresses IP publiques encore disponibles.
 - Le pourcentage d’adresses IP publiques qui ont été attribuées à cet emplacement.

La vignette **Utilisation des pools d’adresses IP publiques** indique le nombre d’adresses IP publiques consommées sur les pools d’adresses IP publiques. Pour chaque adresse IP, la vignette affiche l’utilisation du locataire des instances de machine virtuelle IaaS, des services d’infrastructure fabric et des ressources d’adresses IP publiques créées explicitement par les locataires.

L’objectif de la vignette est de donner aux opérateurs Azure Stack une idée du nombre d’adresses IP publiques utilisées à cet emplacement. Ce nombre permet aux administrateurs de déterminer si cette ressource est insuffisante.

L’élément de menu **Adresses IP publiques** sous **Ressources de locataire** répertorie uniquement les adresses IP publiques qui ont été *explicitement créées par les locataires*. L’élément de menu se trouve sur le volet **Fournisseurs de ressources**, **Réseau**. Le nombre d’adresses IP publiques **Utilisées** dans la vignette **Utilisation des pools d’adresses IP publiques** est toujours différent (supérieur) par rapport au nombre de la vignette **Adresses IP publiques** sous **Ressources de locataire**.

## <a name="view-the-public-ip-address-usage-information"></a>Afficher les informations d’utilisation d’adresses IP publiques
Pour afficher le nombre total d’adresses IP publiques qui ont été consommées dans la région :

1. Dans le portail d’administration Azure Stack, sélectionnez **Autres services**, sous **Ressources administratives**, sélectionnez **Fournisseurs de ressources**.
2. Dans la liste des **Fournisseurs de ressources**, sélectionnez **Réseau**.
3. Le volet **Réseau** affiche la vignette **Utilisation des pools d’adresses IP publiques** dans la section **Vue d’ensemble**.

![Volet Fournisseur de ressources réseau](media/azure-stack-viewing-public-ip-address-consumption/image01.png)

Le nombre**Utilisé** représente le nombre d’adresses IP publiques affectées à partir de pools d’adresses IP publiques. Le nombre sous **Libres** représente le nombre d’adresses IP publiques de pools d’adresses IP publiques qui n’ont pas été affectées et sont encore disponibles. Le nombre sous **% utilisé** représente le nombre d’adresses utilisées ou affectées en pourcentage du nombre d’adresses IP publiques dans tous les pools d’adresses IP publiques de cet emplacement.

## <a name="view-the-public-ip-addresses-that-were-created-by-tenant-subscriptions"></a>Afficher les adresses IP publiques créées par des abonnements de locataire
Sélectionnez **Adresses IP publiques** sous **Ressources de locataire**. Passez en revue la liste d’adresses IP publiques explicitement créées par des abonnements de locataire dans une région donnée.

![Adresses IP publiques de locataire](media/azure-stack-viewing-public-ip-address-consumption/image02.png)

Notez que certaines adresses IP publiques qui ont été allouées dynamiquement apparaissent dans la liste. Toutefois, elles n’ont pas encore d’adresse associée. La ressource d’adresse a été créée dans le Fournisseur de ressources réseau, mais pas encore dans le contrôleur de réseau.

Le contrôleur de réseau n’affecte pas d’adresse à la ressource tant qu’elle n’est pas liée à une interface, une carte d’interface réseau, un équilibreur de charge ou une passerelle de réseau virtuel. Quand l’adresse IP publique est liée à une interface, le contrôleur de réseau lui alloue une adresse IP. L’adresse s’affiche dans le champ **Adresse**.

## <a name="view-the-public-ip-address-information-summary-table"></a>Afficher le tableau récapitulatif des informations d’adresses IP publiques
Quand une adresse IP publique est affectée, elle apparaît dans une liste ou dans l’autre selon les cas.

| **Cas d’affectation d’adresses IP publiques** | **Apparaît dans le récapitulatif d’utilisation** | **Apparaît dans la liste d’adresses IP publiques du locataire** |
| --- | --- | --- |
| Adresse IP publique dynamique non encore affectée à une carte réseau ou un équilibreur de charge (temporaire) |Non  |OUI |
| Adresse IP publique dynamique affectée à une carte réseau ou un équilibreur de charge. |OUI |OUI |
| Adresse IP publique statique affectée à une carte réseau ou un équilibreur de charge du locataire. |OUI |OUI |
| Adresse IP publique statique affectée à un point de terminaison de service d’infrastructure fabric. |OUI |Non  |
| Adresse IP publique implicitement créée pour des instances de machine virtuelle IaaS et utilisée pour les règles NAT de trafic sortant sur le réseau virtuel. Ces adresses IP sont créées en arrière-plan chaque fois qu’un locataire crée une instance de machine virtuelle pour que les machines virtuelles puissent envoyer des informations sur Internet. |OUI |Non  |

## <a name="next-steps"></a>Étapes suivantes
[Gérer les comptes de stockage dans Azure Stack](azure-stack-manage-storage-accounts.md)