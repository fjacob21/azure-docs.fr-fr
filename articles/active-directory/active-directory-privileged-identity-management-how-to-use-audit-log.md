---
title: Comment utiliser le journal d’audit dans Azure AD Privileged Identity Management | Microsoft Docs
description: Découvrez comment utiliser le journal d’audit dans l’extension Azure Privileged Identity Management.
services: active-directory
documentationcenter: ''
author: curtand
manager: mtillman
editor: ''
ms.service: active-directory
ms.topic: article
ms.workload: identity
ms.component: users-groups-roles
ms.date: 02/14/2017
ms.author: curtand
ms.custom: pim
ms.openlocfilehash: 20fd9c5ee90947cc2d3816a0590d4780408baa2f
ms.sourcegitcommit: e221d1a2e0fb245610a6dd886e7e74c362f06467
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="using-the-audit-log-in-pim"></a>Utilisation du journal d’audit dans PIM
Vous pouvez utiliser le journal d’audit Privileged Identity Management (PIM) pour voir toutes les activations et affectations d’utilisateur dans un laps de temps donné. Si vous souhaitez consulter l’historique d’audit complet de l’activité dans votre client, notamment l’activité de l’administrateur, de l’utilisateur final et de la synchronisation, vous pouvez utiliser les [rapports d’accès et d’utilisation d’Azure Active Directory.](active-directory-view-access-usage-reports.md)

## <a name="navigate-to-the-audit-log"></a>Accéder au journal d’audit
À partir du [portail Azure](https://portal.azure.com) et du tableau de bord, sélectionnez l’application **Azure AD Privileged Identity Management** . À partir de là, accédez au journal d’audit en cliquant sur **Gérer les rôles privilégiés** > **Historique d’audit** dans le tableau de bord PIM.

## <a name="the-audit-log-graph"></a>Graphique du journal d’audit
Le journal d’audit indique le nombre total d’activations, le nombre maximal d’activations par jour et la moyenne d’activations par jour dans un graphique linéaire.  Vous pouvez également filtrer les données par rôle s’il existe plusieurs rôles dans l’historique d’audit.

Utilisez les boutons **temps**, **action** et **rôle** pour trier le journal.

## <a name="the-audit-log-list"></a>Liste du journal d’audit
Les colonnes dans la liste du journal d’audit sont les suivantes :

* **Demandeur** : personne qui a demandé l’activation de rôle ou la modification.  Si la valeur est « Système Azure », consultez le journal d'audit Azure pour plus d'informations.
* **Utilisateur** : l’utilisateur qui active un rôle ou y est affecté.
* **Rôle** : le rôle affecté ou activé par l’utilisateur.
* **Action** : les mesures prises par le demandeur. Ceci peut inclure l'attribution, la non-attribution, l’activation ou la désactivation.
* **Heure** : heure à laquelle l’action s’est produite.
* **Motif** : tout texte éventuellement entré dans le champ de motif pendant l’activation.
* **Expiration** : concerne uniquement l’activation de rôles.

## <a name="filter-the-audit-log"></a>Filtrer le journal d’audit
Vous pouvez filtrer les informations qui s’affichent dans le journal d’audit en cliquant sur le bouton **Filtre** .  Le panneau **Mettre à jour les paramètres du graphique** s’affiche.

Après avoir défini les filtres, cliquez sur **Mettre à jour** pour filtrer les données dans le journal.  Si les données ne s’affichent pas immédiatement, actualisez la page.

### <a name="change-the-date-range"></a>Modifier la plage de dates
Utilisez les boutons **Aujourd’hui**, **Semaine passée**, **Mois Dernier** ou **Personnalisé**.

Si vous choisissez le bouton **Personnalisé**, les champs de date **De** et **À** s’affichent pour que vous puissiez spécifier une plage de dates pour le journal.  Vous pouvez entrer les dates au format JJ/MM/AAAA ou cliquer sur l’icône de **calendrier** et sélectionner une date dans un calendrier.

### <a name="change-the-roles-included-in-the-log"></a>Modifier les rôles inclus dans le journal
Cochez (ou décochez) la case **Rôle** en regard de chaque rôle à inclure dans le journal (ou à exclure de ce dernier).

<!--Every topic should have next steps and links to the next logical set of content to keep the customer engaged-->
## <a name="next-steps"></a>Étapes suivantes
[!INCLUDE [active-directory-privileged-identity-management-toc](../../includes/active-directory-privileged-identity-management-toc.md)]

