---
title: Gérer les programmes et les contrôles pour les révisions d’accès Azure AD | Microsoft Docs
description: Vous pouvez créer des programmes supplémentaires pour chaque gouvernance, la gestion des risques et l’initiative de conformité dans votre organisation afin de collecter et d’organiser des révisions d’accès Azure Active Directory comme contrôles.
services: active-directory
documentationcenter: ''
author: markwahl-msft
manager: mtillman
editor: ''
ms.service: active-directory
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 05/14/2018
ms.author: billmath
ms.openlocfilehash: a3fb812623b490e27907f63c1f7c6610ae754fb8
ms.sourcegitcommit: eb75f177fc59d90b1b667afcfe64ac51936e2638
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2018
ms.locfileid: "34192878"
---
# <a name="manage-programs-and-their-controls"></a>Gérer des programmes et leurs contrôles 

Azure Active Directory (Azure AD) inclut des révisions d’accès des membres du groupe et d’accès à l’application. Ces contrôles permettent de savoir qui a accès aux applications et aux groupes de votre organisation. Ils permettent aux organisations de gérer efficacement leur gouvernance, la gestion des risques et les exigences de conformité.

## <a name="create-and-manage-programs-and-their-controls"></a>Créer et gérer des programmes et leurs contrôles
Vous pouvez simplifier le suivi et la collecte des révisions d’accès à des fins différentes en les organisant dans des programmes. Chaque révision d’accès peut être liée à un programme. Ainsi, lorsque vous préparez des rapports pour un auditeur, vous pouvez vous concentrer sur les révisions d’accès qui sont associées à une certaine initiative.  Les programmes et les résultats des révisions d’accès sont visibles par les utilisateurs disposant du rôle Administrateur général, Administrateur de la sécurité ou Lecteur Sécurité.

Pour voir la liste des programmes, accédez à la [page des révisions d’accès](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade/) et sélectionnez **Programmes**.

L’option **Programme par défaut** est toujours présente. Si vous disposez d’un rôle d’administrateur global, vous pouvez créer des programmes supplémentaires. Par exemple, vous pouvez choisir de disposer d’un programme pour chaque initiative de conformité ou objectif de l’entreprise.

Si vous n’avez plus besoin d’un programme et qu’il n’est lié à aucun contrôle, vous pouvez le supprimer.

## <a name="next-steps"></a>Étapes suivantes

- [Create an access review for members of a group or access to an application](active-directory-azure-ad-controls-create-access-review.md) (Créer une révision de l’accès des membres d’un groupe ou de l’accès à une application)
- [Récupérer les résultats d’une révision d’accès](active-directory-azure-ad-controls-retrieve-access-review.md)
