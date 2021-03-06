---
title: 'Didacticiel : Intégration d’Azure Active Directory avec Agiloft | Microsoft Docs'
description: Découvrez comment configurer l’authentification unique entre Azure Active Directory et Agiloft.
services: active-directory
documentationCenter: na
author: jeevansd
manager: mtillman
ms.reviewer: joflore
ms.assetid: aca13814-cdbd-46b8-93dc-1578099c5ee4
ms.service: active-directory
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 10/09/2017
ms.author: jeedes
ms.openlocfilehash: 296b972eced0bfb54435489d727270cc22c75798
ms.sourcegitcommit: b6319f1a87d9316122f96769aab0d92b46a6879a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2018
---
# <a name="tutorial-azure-active-directory-integration-with-agiloft"></a>Didacticiel : Intégration d’Azure Active Directory avec Agiloft

Dans ce didacticiel, vous allez apprendre à intégrer Agiloft dans Azure Active Directory (Azure AD).

L’intégration d’Agiloft dans Azure AD vous offre les avantages suivants :

- Dans Azure AD, vous pouvez déterminer qui a accès à Agiloft.
- Vous pouvez autoriser les utilisateurs à se connecter automatiquement à Agiloft (via l’authentification unique) avec leur compte Azure AD.
- Vous pouvez gérer vos comptes dans un emplacement central : le portail Azure

Pour en savoir plus sur l’intégration des applications SaaS avec Azure AD, consultez [Qu’est-ce que l’accès aux applications et l’authentification unique avec Azure Active Directory ?](manage-apps/what-is-single-sign-on.md).

## <a name="prerequisites"></a>Prérequis


Pour configurer l’intégration d’Azure AD à Agiloft, vous avez besoin des éléments suivants :

- Un abonnement Azure AD
- Un abonnement Agiloft pour lequel l’authentification unique est activée

> [!NOTE]
> Pour tester les étapes de ce didacticiel, nous déconseillons l’utilisation d’un environnement de production.

Vous devez en outre suivre les recommandations ci-dessous :

- N’utilisez pas votre environnement de production, sauf si cela est nécessaire.
- Si vous n’avez pas d’environnement d’essai Azure AD, vous pouvez [obtenir un essai d’un mois](https://azure.microsoft.com/pricing/free-trial/).

## <a name="scenario-description"></a>Description du scénario
Dans ce didacticiel, vous testez l’authentification unique Azure AD dans un environnement de test. Le scénario décrit dans ce didacticiel se compose des deux sections principales suivantes :

1. Ajout d’Agiloft à partir de la galerie
2. Configuration et test de l’authentification unique Azure AD

## <a name="adding-agiloft-from-the-gallery"></a>Ajout d’Agiloft à partir de la galerie
Pour configurer l’intégration d’Agiloft à Azure AD, vous devez ajouter Agiloft, disponible dans la galerie, à votre liste d’applications SaaS managées.

**Pour ajouter Agiloft à partir de la galerie, procédez comme suit :**

1. Dans le volet de navigation gauche du **[portail Azure](https://portal.azure.com)**, cliquez sur l’icône **Azure Active Directory**. 

    ![Bouton Azure Active Directory][1]

2. Accédez à **Applications d’entreprise**. Accédez ensuite à **Toutes les applications**.

    ![Panneau Applications d’entreprise][2]
    
3. Pour ajouter l’application, cliquez sur le bouton **Nouvelle application** en haut de la boîte de dialogue.

    ![Bouton Nouvelle application][3]

4. Dans la zone de recherche, saisissez **Agiloft**, sélectionnez **Agiloft** à nouveau dans le volet de résultats, puis cliquez sur le bouton **Ajouter** pour ajouter l’application.

    ![Agiloft dans la liste des résultats](./media/active-directory-saas-agiloft-tutorial/tutorial_agiloft_addfromgallery.png)

## <a name="configure-and-test-azure-ad-single-sign-on"></a>Configurer et tester l’authentification unique Azure AD

Dans cette section, vous allez configurer et tester l’authentification unique Azure AD avec Agiloft, avec un utilisateur de test appelé « Britta Simon ».

Pour que l’authentification unique fonctionne, Azure AD doit savoir qui est l’utilisateur Agiloft équivalent dans Azure AD. En d’autres termes, une relation entre un utilisateur Azure AD et l’utilisateur Agiloft associé doit être établie.

Dans Agiloft, assignez la valeur de **nom d’utilisateur** dans Azure AD en tant que valeur de **nom d’utilisateur** pour établir la relation.

Pour configurer et tester l’authentification unique Azure AD avec Agiloft, vous devez suivre les indications des sections suivantes :

1. **[Configurer l’authentification unique Azure AD](#configure-azure-ad-single-sign-on)** pour permettre à vos utilisateurs d’utiliser cette fonctionnalité.
2. **[Créer un utilisateur de test Azure AD](#create-an-azure-ad-test-user)** pour tester l’authentification unique Azure AD avec Britta Simon.
3. **[Créer un utilisateur de test Agiloft](#create-an-agiloft-test-user)** pour avoir un équivalent de Britta Simon dans Agiloft, associé à sa représentation dans Azure AD.
4. **[Affecter l’utilisateur de test Azure AD](#assign-the-azure-ad-test-user)** pour permettre à Britta Simon d’utiliser l’authentification unique Azure AD.
5. **[Tester l’authentification unique](#test-single-sign-on)** : pour vérifier si la configuration fonctionne.

### <a name="configure-azure-ad-single-sign-on"></a>Configurer l’authentification unique Azure AD

Dans cette section, vous activez l’authentification unique Azure AD dans le portail Azure et la configurez dans votre application Agiloft.

**Pour configurer l’authentification unique Azure AD avec Agiloft, procédez comme suit :**

1. Dans le portail Azure, sur la page d’intégration de l’application **Agiloft**, cliquez sur **Authentification unique**.

    ![Lien Configurer l’authentification unique][4]

2. Dans la boîte de dialogue **Authentification unique**, pour le **Mode**, sélectionnez **Authentification basée sur SAML** pour activer l’authentification unique.
 
    ![Boîte de dialogue Authentification unique](./media/active-directory-saas-agiloft-tutorial/tutorial_agiloft_samlbase.png)

3. Dans la section relative aux **domaine et URL Agiloft**, suivez les étapes ci-dessous si vous souhaitez configurer l’application en mode initié par IDP :

    ![Informations d’authentification unique dans les domaines et URL Agiloft](./media/active-directory-saas-agiloft-tutorial/tutorial_agiloft_url.png)

    a. Dans la zone de texte **Identificateur**, tapez une URL au format suivant : 
    | |
    |-|-|
    | `https://<subdomain>.saas.enterprisewizard.com/project/<KB_NAME>` |
    | `https://<subdomain>.agiloft.com/project/<KB_NAME>` |

    b. Dans la zone de texte **URL de réponse** , tapez une URL au format suivant :
    | |
    |-|-|
    | `https://<subdomain>.saas.enterprisewizard.com:443/gui2/spsamlsso?project=<KB_NAME>` |
    | `https://<subdomain>.agiloft.com:443/gui2/spsamlsso?project=<KB_NAME>` |

4. Si vous souhaitez configurer l’application en **mode démarré par le fournisseur de service**, cochez **Afficher les paramètres d’URL avancés**, puis effectuez les étapes suivantes :

    ![Informations d’authentification unique dans les domaines et URL Agiloft](./media/active-directory-saas-agiloft-tutorial/tutorial_agiloft_url1.png)

    Dans la zone de texte **URL de connexion**, tapez une URL au format suivant : 
    | |
    |-|-|
    | `https://<subdomain>.saas.enterprisewizard.com/gui2/samlssologin.jsp?project=<KB_NAME>` |
    | `https://<subdomain>.agiloft.com/gui2/samlssologin.jsp?project=<KB_NAME>` |
     
    > [!NOTE] 
    > Il ne s’agit pas de valeurs réelles. Mettez à jour ces valeurs avec l’identificateur, l’URL de réponse et l’URL de connexion réels. Pour obtenir ces valeurs, contactez [l’équipe de support technique Agiloft](https://www.agiloft.com/support-login.htm). 

5. Dans la section **Certificat de signature SAML**, cliquez sur **Téléchargez le certificat (Base64)** puis enregistrez le fichier du certificat sur votre ordinateur.

    ![Lien Téléchargement de certificat](./media/active-directory-saas-agiloft-tutorial/tutorial_agiloft_certificate.png) 

6. Cliquez sur le bouton **Enregistrer** .

    ![Bouton Enregistrer de la page Configurer l’authentification unique](./media/active-directory-saas-agiloft-tutorial/tutorial_general_400.png)
    
7. Dans la section relative à la **configuration Agiloft**, cliquez sur l’option de **configuration d’Agiloft** pour ouvrir la fenêtre **Configurer l’authentification**. Copiez **l’URL de déconnexion, l’ID d’entité SAML et l’URL du service d’authentification unique SAML** à partir de la **section Référence rapide.**

    ![Configuration d’Agiloft](./media/active-directory-saas-agiloft-tutorial/tutorial_agiloft_configure.png) 

8. Dans une autre fenêtre de navigateur web, connectez-vous à votre site d’entreprise Agiloft en tant qu’administrateur.

9. Cliquez sur **Configuration** (dans le volet gauche), puis sur **Accès**.

    ![Configuration d’Agiloft](./media/active-directory-saas-agiloft-tutorial/setup1.png) 

10. Cliquez sur le bouton permettant de **configurer l’authentification unique SAML 2.0**. 
    
    ![Configuration d’Agiloft](./media/active-directory-saas-agiloft-tutorial/setup2.png) 

11. Une boîte de dialogue d’assistant s’affiche. Dans la boîte de dialogue, cliquez sur l’onglet relatif aux **détails du fournisseur d’identité** et renseignez les champs suivants :  
    
    ![Configuration d’Agiloft](./media/active-directory-saas-agiloft-tutorial/setup4.png) 

    a. Dans la zone de texte **ID d’entité IdP/Émetteur**, collez la valeur **ID d’entité SAML** que vous avez copiée à partir du portail Azure.

    b. Dans la zone de texte relative à **l’URL de connexion de fournisseur d’identité**, collez la valeur de **l’URL du service d’authentification unique** copiée à partir du portail Azure.

    c. Dans la zone de texte **URL de déconnexion de fournisseur d’identité**, collez la valeur de **l’URL de déconnexion** que vous avez copiée à partir du portail Azure.

    d. Ouvrez dans le Bloc-notes votre **certificat codé en base 64** téléchargé à partir du portail Azure, copiez son contenu dans le Presse-papiers, puis collez-le dans la zone de texte du **contenu du certificat X.509 proposé par le fournisseur d’identité**.

    e. Cliquez sur **Terminer**.


> [!TIP]
> Vous pouvez maintenant lire une version concise de ces instructions dans le [portail Azure](https://portal.azure.com), pendant que vous configurez l’application.  Après avoir ajouté cette application à partir de la section **Active Directory > Applications d’entreprise**, cliquez simplement sur l’onglet **Authentification unique** et accédez à la documentation incorporée par le biais de la section **Configuration** en bas. Vous pouvez en savoir plus sur la fonctionnalité de documentation incorporée ici : [Documentation incorporée Azure AD]( https://go.microsoft.com/fwlink/?linkid=845985)

### <a name="create-an-azure-ad-test-user"></a>Créer un utilisateur de test Azure AD

L’objectif de cette section est de créer un utilisateur de test appelé Britta Simon dans le portail Azure.

   ![Créer un utilisateur de test Azure AD][100]

**Pour créer un utilisateur de test dans Azure AD, procédez comme suit :**

1. Dans le volet gauche du Portail Azure, cliquez sur le bouton **Azure Active Directory**.

    ![Bouton Azure Active Directory](./media/active-directory-saas-agiloft-tutorial/create_aaduser_01.png)

2. Pour afficher la liste des utilisateurs, accédez à **Utilisateurs et groupes**, puis cliquez sur **Tous les utilisateurs**.

    ![Liens « Utilisateurs et groupes » et « Tous les utilisateurs »](./media/active-directory-saas-agiloft-tutorial/create_aaduser_02.png)

3. Pour ouvrir la boîte de dialogue **Utilisateur**, cliquez sur **Ajouter** en haut de la boîte de dialogue **Tous les utilisateurs**.

    ![Bouton Ajouter](./media/active-directory-saas-agiloft-tutorial/create_aaduser_03.png)

4. Dans la boîte de dialogue **Utilisateur**, procédez comme suit :

    ![Boîte de dialogue Utilisateur](./media/active-directory-saas-agiloft-tutorial/create_aaduser_04.png)

    a. Dans la zone **Nom**, tapez **BrittaSimon**.

    b. Dans la zone **Nom d’utilisateur** , tapez l’adresse e-mail de l’utilisateur Britta Simon.

    c. Cochez la case **Afficher le mot de passe**, puis notez la valeur affichée dans le champ **Mot de passe**.

    d. Cliquez sur **Créer**.
 
### <a name="create-an-agiloft-test-user"></a>Créer un utilisateur de test Agiloft

L’application prend en charge la configuration d’utilisateur juste à temps, et après authentification, les utilisateurs sont créés automatiquement dans l’application. Vous n’avez aucune opération à effectuer dans cette section.

### <a name="assign-the-azure-ad-test-user"></a>Affecter l’utilisateur de test Azure AD

Dans cette section, vous allez autoriser Britta Simon à utiliser l’authentification unique Azure en lui accordant l’accès à Agiloft.

![Attribuer le rôle utilisateur][200] 

**Pour affecter Britta Simon à Agiloft, procédez comme suit :**

1. Dans le portail Azure, ouvrez la vue des applications, accédez à la vue des répertoires, accédez à **Applications d’entreprise**, puis cliquez sur **Toutes les applications**.

    ![Affecter des utilisateurs][201] 

2. Dans la liste des applications, sélectionnez **Agiloft**.

    ![Lien Agiloft dans la liste des applications](./media/active-directory-saas-agiloft-tutorial/tutorial_agiloft_app.png)  

3. Dans le menu de gauche, cliquez sur **Utilisateurs et groupes**.

    ![Lien « Utilisateurs et groupes »][202]

4. Cliquez sur le bouton **Ajouter**. Ensuite, sélectionnez **Utilisateurs et groupes** dans la boîte de dialogue **Ajouter une affectation**.

    ![Volet Ajouter une attribution][203]

5. Dans la boîte de dialogue **Utilisateurs et groupes**, sélectionnez **Britta Simon** dans la liste des utilisateurs.

6. Cliquez sur le bouton **Sélectionner** dans la boîte de dialogue **Utilisateurs et groupes**.

7. Cliquez sur le bouton **Affecter** dans la boîte de dialogue **Ajouter une affectation**.
    
### <a name="test-single-sign-on"></a>Tester l’authentification unique

Dans cette section, vous allez tester la configuration de l’authentification unique Azure AD à l’aide du volet d’accès.

Lorsque vous cliquez sur la vignette Agiloft dans le volet d’accès, vous devez être connecté automatiquement à votre application Agiloft.
Pour plus d’informations sur le panneau d’accès, consultez [Présentation du panneau d’accès](active-directory-saas-access-panel-introduction.md). 

## <a name="additional-resources"></a>Ressources supplémentaires

* [Liste de didacticiels sur l’intégration d’applications SaaS avec Azure Active Directory](active-directory-saas-tutorial-list.md)
* [Qu’est-ce que l’accès aux applications et l’authentification unique avec Azure Active Directory ?](manage-apps/what-is-single-sign-on.md)



<!--Image references-->

[1]: ./media/active-directory-saas-agiloft-tutorial/tutorial_general_01.png
[2]: ./media/active-directory-saas-agiloft-tutorial/tutorial_general_02.png
[3]: ./media/active-directory-saas-agiloft-tutorial/tutorial_general_03.png
[4]: ./media/active-directory-saas-agiloft-tutorial/tutorial_general_04.png

[100]: ./media/active-directory-saas-agiloft-tutorial/tutorial_general_100.png

[200]: ./media/active-directory-saas-agiloft-tutorial/tutorial_general_200.png
[201]: ./media/active-directory-saas-agiloft-tutorial/tutorial_general_201.png
[202]: ./media/active-directory-saas-agiloft-tutorial/tutorial_general_202.png
[203]: ./media/active-directory-saas-agiloft-tutorial/tutorial_general_203.png

