---
title: Prise en main d’Azure AD dans les projets Visual Studio WebApi
description: Comment prendre en main Azure Active Directory dans les projets WebApi après s’être connecté à un annuaire Azure AD ou avoir créé un annuaire Azure AD à l’aide des services connectés de Visual Studio
services: active-directory
author: ghogen
manager: douge
ms.assetid: bf1eb32d-25cd-4abf-8679-2ead299fedaa
ms.prod: visual-studio-dev15
ms.technology: vs-azure
ms.workload: azure
ms.topic: conceptual
ms.date: 03/12/2018
ms.author: ghogen
ms.custom: aaddev
ms.openlocfilehash: 109de9fb78ae3abfc09a37c6b8cb38c554f7613c
ms.sourcegitcommit: fa493b66552af11260db48d89e3ddfcdcb5e3152
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2018
---
# <a name="get-started-with-azure-active-directory-webapi-projects"></a>Prise en main avec Azure Active Directory (projets WebApi)

> [!div class="op_single_selector"]
> - [Prise en main](vs-active-directory-webapi-getting-started.md)
> - [Que s'est-il passé ?](vs-active-directory-webapi-what-happened.md)

Cet article fournit des conseils supplémentaires une fois que vous avez ajouté Active Directory à un projet ASP.NET WebAPI via la commande **Projet > Services connectés** de Visual Studio. Si vous n’avez pas déjà ajouté le service à votre projet, vous pouvez le faire à tout moment.

Consultez [Qu’est-il arrivé à mon projet WebAPI ?](vs-active-directory-webapi-what-happened.md) pour connaitre les modifications apportées à votre projet lorsque vous ajoutez le service connecté.

## <a name="requiring-authentication-to-access-controllers"></a>Demander une authentification pour l'accès aux contrôleurs

Tous les contrôleurs de votre projet ont été ornés de l’attribut `[Authorize]`. Cet attribut permet de demander à l’utilisateur de s’authentifier avant d’accéder aux API définies par ces contrôleurs. Pour autoriser un accès anonyme au contrôleur, cet attribut doit être supprimé du contrôleur. Pour définir plus précisément les autorisations, appliquez cet attribut à chaque méthode nécessitant une autorisation, au lieu de l’appliquer à la classe de contrôleur.

## <a name="next-steps"></a>Étapes suivantes

- [Scénarios d’authentification pour Azure Active Directory](active-directory-authentication-scenarios.md)
- [Ajouter la connexion avec Microsoft à une application web ASP.NET](guidedsetups/active-directory-aspnetwebapp-v1.md)
