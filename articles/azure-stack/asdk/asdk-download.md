---
title: Télécharger et extraire le Kit de développement Azure Stack (ASDK) | Microsoft Docs
description: Explique comment télécharger et extraire le Kit de développement Azure Stack (ASDK).
services: azure-stack
documentationcenter: ''
author: jeffgilb
manager: femila
editor: ''
ms.assetid: ''
ms.service: azure-stack
ms.workload: na
pms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 03/16/2018
ms.author: jeffgilb
ms.reviewer: misainat
ms.openlocfilehash: 0cf389c9443a9cff477b884c277d72de27769afc
ms.sourcegitcommit: a36a1ae91968de3fd68ff2f0c1697effbb210ba8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2018
---
# <a name="download-and-extract-the-azure-stack-development-kit-asdk"></a>Télécharger et extraire le Kit de développement Azure Stack (ASDK)
Après avoir vérifié que l’ordinateur hôte du Kit de développement répond bien aux exigences de base pour l’installation du kit ASDK, vous devez télécharger puis extraire le package de déploiement du Kit de développement Azure Stack afin d’obtenir le fichier Cloudbuilder.vhdx.

## <a name="download-the-asdk"></a>Télécharger l’ASDK
1. Avant de commencer le téléchargement, vérifiez que votre ordinateur répond aux prérequis suivants :

  - L’ordinateur doit avoir au moins 60 Go d’espace disque disponible sur quatre disques durs logiques identiques et distincts en plus du disque de système d’exploitation.
  - [.NET Framework 4.6 (ou ultérieur)](https://aka.ms/r6mkiy) doit être installé.

2. [Accédez à la page de démarrage](https://azure.microsoft.com/overview/azure-stack/try/?v=try) sur laquelle vous pouvez télécharger le Kit de développement Azure Stack, renseignez vos informations, puis cliquez sur **Envoyer**.
3. Téléchargez et exécutez le script de vérification des conditions requises du [vérificateur de déploiement pour le Kit de développement Azure Stack](https://go.microsoft.com/fwlink/?LinkId=828735&clcid=0x409). Ce script autonome passe en revue les vérifications des conditions requises réalisées par la configuration pour le Kit de développement Azure Stack. Il vous permet de vous assurer que vous respectez les exigences matérielles et logicielles avant de télécharger le package plus volumineux du Kit de développement Azure Stack.
4. Sous **Télécharger le logiciel**, cliquez sur **Kit de développement Azure Stack**.

  > [!NOTE]
  > La taille du téléchargement du kit ASDK (AzureStackDevelopmentKit.exe) est d’environ 10 Go.

## <a name="extract-the-asdk"></a>Extraire le kit ASDK
1. Une fois le téléchargement terminé, cliquez sur **Exécuter** pour lancer l’auto-extracteur ASDK (AzureStackDevelopmentKit.exe).
2. Lisez et acceptez le contrat de licence de la page **Contrat de licence** de l’Assistant de l’auto-extracteur, plus cliquez sur **Suivant**.
3. Passez en revue la déclaration de confidentialité de la page **Avis important** de l’Assistant de l’auto-extracteur, puis cliquez sur **Suivant**.
4. Sélectionnez l’emplacement où les fichiers de configuration Azure Stack doivent être extraits sur la page **Sélectionner l’emplacement de destination** de l’Assistant de l’auto-extracteur, puis cliquez sur **Suivant**. L’emplacement par défaut est *dossier actuel*\Kit de développement Azure Stack. 
5. Passez en revue le résumé de l’emplacement de la page **Ready to Extract** (Prêt pour l’extraction) de l’Assistant de l’auto-extracteur, puis cliquez sur **Extraire** pour extraire les fichiers CloudBuilder.vhdx (environ 25 Go) et ThirdPartyLicenses.rtf. Ce processus prend un certain temps.
6. Copiez ou déplacez le fichier CloudBuilder.vhdx à la racine du lecteur C:\ (C:\CloudBuilder.vhdx) sur l’ordinateur hôte ASDK.

> [!NOTE]
> Après avoir extrait les fichiers, vous pouvez supprimer les fichiers .EXE et .BIN pour récupérer de l’espace sur le disque dur. Vous pouvez aussi sauvegarder ces fichiers pour ne pas avoir à les retélécharger en cas de redéploiement du kit ASDK.


## <a name="next-steps"></a>Étapes suivantes
[Préparer l’ordinateur hôte de l’ASDK](asdk-prepare-host.md)