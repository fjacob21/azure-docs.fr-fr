---
title: Désactiver les connexions utilisateur pour une application d’entreprise dans Azure Active Directory | Microsoft Docs
description: Comment désactiver une application d’entreprise afin qu’aucun utilisateur ne puisse s’y connecter dans Azure Active Directory
services: active-directory
documentationcenter: ''
author: barbkess
manager: mtillman
editor: ''
ms.service: active-directory
ms.component: app-mgmt
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 08/28/2017
ms.author: barbkess
ms.reviewer: asteen
ms.custom: it-pro
ms.openlocfilehash: be0c8ede4a99c532aecbfbb4ee0fc51657f96886
ms.sourcegitcommit: d98d99567d0383bb8d7cbe2d767ec15ebf2daeb2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2018
---
# <a name="disable-user-sign-ins-for-an-enterprise-app-in-azure-active-directory"></a>Désactiver les connexions utilisateur pour une application d’entreprise dans Azure Active Directory
Il est facile de désactiver une application d’entreprise afin qu’aucun utilisateur ne puisse s’y connecter dans Azure Active Directory (Azure AD). Vous devez disposer des autorisations nécessaires pour gérer l’application d’entreprise, et vous devez être l’administrateur général du répertoire.

## <a name="how-do-i-disable-user-sign-ins"></a>Comment désactiver les connexions des utilisateurs ?
1. Connectez-vous au [portail Azure](https://portal.azure.com) en utilisant un compte d’administrateur général pour le répertoire.
2. Sélectionnez **Tous les services**, entrez **Azure Active Directory** dans la zone de texte, puis sélectionnez **Entrée**.
3. Dans le volet **Azure Active Directory** -  ***NomRépertoire*** (autrement dit, le volet Azure AD du répertoire que vous gérez), sélectionnez **Applications d’entreprise**.

    ![Ouverture des applications d’entreprise](./media/active-directory-coreapps-disable-app-azure-portal/open-enterprise-apps.png)
4. Dans le volet **Applications d’entreprise**, sélectionnez **Toutes les applications**. Vous verrez une liste des applications que vous pouvez gérer.
5. Dans le volet **Applications d’entreprise - Toutes les applications**, sélectionnez une application.
6. Dans le volet ***NomApplication*** (autrement dit, le volet intitulé avec le nom de l’application sélectionnée), sélectionnez **Propriétés**.

    ![Sélection de la commande Toutes les applications](./media/active-directory-coreapps-disable-app-azure-portal/select-app.png)
7. Dans le volet ***NomApplication*** - **Propriétés**, sélectionnez **Non** pour **Activé pour que les utilisateurs se connectent ?**.
8. Sélectionnez la commande **Enregistrer** .

## <a name="next-steps"></a>Étapes suivantes
* [Voir tous mes groupes](active-directory-groups-view-azure-portal.md)
* [Affecter un utilisateur ou un groupe à une application d’entreprise](active-directory-coreapps-assign-user-azure-portal.md)
* [Supprimer l’affectation d’un utilisateur ou d’un groupe à une application d’entreprise dans la version préliminaire d’Azure Active Directory](active-directory-coreapps-remove-assignment-azure-portal.md)
* [Modifier le nom ou le logo d’une application d’entreprise dans la version préliminaire d’Azure Active Directory](active-directory-coreapps-change-app-logo-user-azure-portal.md)
