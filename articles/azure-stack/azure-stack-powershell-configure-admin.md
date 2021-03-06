---
title: Configurer l’environnement PowerShell d’Azure Stack | Microsoft Docs
description: Découvrez comment configurer l’environnement PowerShell d’Azure Stack.
services: azure-stack
documentationcenter: ''
author: mattbriggs
manager: femila
editor: ''
ms.service: azure-stack
ms.workload: na
pms.tgt_pltfrm: na
ms.devlang: PowerShell
ms.topic: article
ms.date: 05/10/2018
ms.author: mabrigg
ms.reviewer: thoroet
ms.openlocfilehash: 86608ef8b3623682bd10498605f8b7b62c377ff1
ms.sourcegitcommit: fc64acba9d9b9784e3662327414e5fe7bd3e972e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2018
ms.locfileid: "34076468"
---
# <a name="configure-the-azure-stack-powershell-environment"></a>Configurez l’environnement PowerShell d’Azure Stack

*S’applique à : systèmes intégrés Azure Stack et Kit de développement Azure Stack*

Vous pouvez configurer Azure Stack pour utiliser PowerShell en vue de gérer les ressources Azure Stack, par exemple créer des offres, des plans, des quotas et des alertes. Cette rubrique vous permet de configurer l’environnement de l’opérateur.

## <a name="prerequisites"></a>Prérequis


Effectuez les étapes prérequises suivantes à partir du [Kit de développement](azure-stack-connect-azure-stack.md#connect-to-azure-stack-with-remote-desktop) ou à partir d’un client externe Windows si vous êtes [connecté par le biais d’un VPN](azure-stack-connect-azure-stack.md#connect-to-azure-stack-with-vpn) : 

 - Installez les [modules Azure PowerShell compatibles avec Azure Stack](azure-stack-powershell-install.md).  
 - Téléchargez les [outils nécessaires pour utiliser Azure Stack](azure-stack-powershell-download.md).  

## <a name="configure-the-operator-environment-and-sign-in-to-azure-stack"></a>Configurer l’environnement de l’opérateur et se connecter à Azure Stack

Configurez l’environnement de l’opérateur Azure Stack avec PowerShell. En fonction du type de déploiement (Azure AD ou AD FS), exécutez l’un des scripts suivants (remplacez les valeurs tenantName Azure AD, le point de terminaison GraphAudience et la valeur ArmEndpoint par la configuration de votre propre environnement) :

### <a name="azure-active-directory-azure-ad-based-deployments"></a>Déploiements basés sur Azure Active Directory (Azure AD)

````PowerShell  
#  Create an administrator environment
Add-AzureRMEnvironment -Name AzureStackAdmin -ArmEndpoint "https://adminmanagement.local.azurestack.external"

# After registering the AzureRM environment, cmdlets can be 
# easily targeted at your Azure Stack instance.
Add-AzureRmAccount -EnvironmentName "AzureStackAdmin" -TenantId $TenantID
````


### <a name="active-directory-federation-services-ad-fs-based-deployments"></a>Déploiements basés sur Active Directory Federation Services (AD FS)

````PowerShell  
#  Create an administrator environment
Add-AzureRMEnvironment -Name AzureStackAdmin -ArmEndpoint "https://adminmanagement.local.azurestack.external"

# After registering the AzureRM environment, cmdlets can be 
# easily targeted at your Azure Stack instance.
Add-AzureRmAccount -EnvironmentName "AzureStackAdmin" -TenantId $TenantID
````

## <a name="test-the-connectivity"></a>Tester la connectivité

Vous avez terminé l’installation. Nous allons maintenant utiliser PowerShell pour créer des ressources dans Azure Stack. Par exemple, vous pouvez créer un groupe de ressources pour une application et ajouter une machine virtuelle. Utilisez la commande suivante pour créer le groupe de ressources nommé « myResourceGroup » :

```powershell
New-AzureRmResourceGroup -Name "MyResourceGroup" -Location "Local"
```

## <a name="next-steps"></a>Étapes suivantes
 - [Développer des modèles pour Azure Stack](user/azure-stack-develop-templates.md)
 - [Déployer des modèles avec PowerShell](user/azure-stack-deploy-template-powershell.md)
