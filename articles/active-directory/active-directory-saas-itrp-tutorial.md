---
title: 'Didacticiel : Intégration d’Azure Active Directory avec ITRP | Microsoft Docs'
description: Découvrez comment configurer l’authentification unique entre Azure Active Directory et ITRP.
services: active-directory
documentationCenter: na
author: jeevansd
manager: mtillman
ms.assetid: e09716a3-4200-4853-9414-2390e6c10d98
ms.service: active-directory
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 06/29/2017
ms.author: jeedes
ms.openlocfilehash: 6f81d203d4ada286169054b35286dbbc4f9526ae
ms.sourcegitcommit: b6319f1a87d9316122f96769aab0d92b46a6879a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2018
---
# <a name="tutorial-azure-active-directory-integration-with-itrp"></a>Didacticiel : Intégration d’Azure Active Directory avec ITRP

Dans ce didacticiel, vous allez apprendre à intégrer ITRP à Azure Active Directory (Azure AD).

L’intégration d’ITRP dans Azure AD vous offre les avantages suivants :

- Dans Azure AD, vous pouvez contrôler qui a accès à ITRP.
- Vous pouvez autoriser vos utilisateurs à se connecter automatiquement à ITRP (par authentification unique) avec leur compte Azure AD.
- Vous pouvez gérer vos comptes à partir d’un emplacement central : le portail Azure.

Pour en savoir plus sur l’intégration des applications SaaS avec Azure AD, consultez [Qu’est-ce que l’accès aux applications et l’authentification unique avec Azure Active Directory ?](manage-apps/what-is-single-sign-on.md).

## <a name="prerequisites"></a>Prérequis


Pour configurer l’intégration d’Azure AD avec ITRP, vous avez besoin des éléments suivants :

- Un abonnement Azure AD
- Un abonnement ITRP pour lequel l’authentification unique est activée

> [!NOTE]
> Pour tester les étapes de ce didacticiel, nous déconseillons l’utilisation d’un environnement de production.

Vous devez en outre suivre les recommandations ci-dessous :

- N’utilisez pas votre environnement de production, sauf si cela est nécessaire.
- Si vous n’avez pas d’environnement d’essai Azure AD, vous pouvez obtenir un essai d’un mois [ici](https://azure.microsoft.com/pricing/free-trial/).

## <a name="scenario-description"></a>Description du scénario
Dans ce didacticiel, vous testez l’authentification unique Azure AD dans un environnement de test. Le scénario décrit dans ce didacticiel se compose des deux sections principales suivantes :

1. Ajout d’ITRP depuis la galerie
2. Configuration et test de l’authentification unique Azure AD

## <a name="adding-itrp-from-the-gallery"></a>Ajout d’ITRP depuis la galerie
Pour configurer l’intégration d’ITRP avec Azure AD, vous devez ajouter ITRP à votre liste d’applications SaaS gérées, à partir de la galerie.

**Pour ajouter ITRP à partir de la galerie, procédez comme suit :**

1. Dans le volet de navigation gauche du **[portail Azure](https://portal.azure.com)**, cliquez sur l’icône **Azure Active Directory**. 

    ![Active Directory][1]

2. Accédez à **Applications d’entreprise**. Accédez ensuite à **Toutes les applications**.

    ![APPLICATIONS][2]
    
3. Pour ajouter l’application, cliquez sur le bouton **Nouvelle application** en haut de la boîte de dialogue.

    ![APPLICATIONS][3]

4. Dans la zone de recherche, entrez **ITRP**.

    ![Création d’un utilisateur de test Azure AD](./media/active-directory-saas-itrp-tutorial/tutorial_itrp_search.png)

5. Dans le panneau des résultats, sélectionnez **ITRP**, puis cliquez sur **Ajouter** pour ajouter l’application.

    ![Création d’un utilisateur de test Azure AD](./media/active-directory-saas-itrp-tutorial/tutorial_itrp_addfromgallery.png)

##  <a name="configuring-and-testing-azure-ad-single-sign-on"></a>Configuration et test de l’authentification unique Azure AD

Dans cette section, vous allez configurer et tester l’authentification unique Azure AD avec ITRP, avec un utilisateur de test appelé « Britta Simon ».

Pour que l’authentification unique fonctionne, Azure AD doit savoir qui est l’utilisateur ITRP équivalent dans Azure AD. En d’autres termes, une relation entre un utilisateur Azure AD et un utilisateur ITRP associé doit être établie.

Dans ITRP, affectez la valeur du **nom d’utilisateur** d’Azure AD comme valeur du **nom d’utilisateur** pour établir la relation.

Pour configurer et tester l’authentification unique Azure AD avec ITRP, vous devez suivre les indications des sections suivantes :

1. **[Configuration de l’authentification unique Azure AD](#configuring-azure-ad-single-sign-on)** pour permettre à vos utilisateurs d’utiliser cette fonctionnalité.
2. **[Création d’un utilisateur de test Azure AD](#creating-an-azure-ad-test-user)** pour tester l’authentification unique Azure AD avec Britta Simon.
3. **[Création d’un utilisateur de test ITRP](#creating-an-itrp-test-user)** pour obtenir un équivalent de Britta Simon dans ITRP lié à la représentation Azure AD associée.
4. **[Affectation de l’utilisateur de test Azure AD](#assigning-the-azure-ad-test-user)** : permet à Britta Simon d’utiliser l’authentification unique Azure AD.
5. **[Testing Single Sign-On](#testing-single-sign-on)** pour vérifier si la configuration fonctionne.

### <a name="configuring-azure-ad-single-sign-on"></a>Configuration de l’authentification unique Azure AD

Dans cette section, vous activez l’authentification unique Azure AD dans le portail Azure et configurez l’authentification unique dans votre application ITRP.

**Pour configurer l’authentification unique Azure AD avec ITRP, procédez comme suit :**

1. Dans le portail Azure, sur la page d’intégration de l’application **ITRP**, cliquez sur **Authentification unique**.

    ![Configure Single Sign-On][4]

2. Dans la boîte de dialogue **Authentification unique**, pour le **Mode**, sélectionnez **Authentification basée sur SAML** pour activer l’authentification unique.
 
    ![Configure Single Sign-On](./media/active-directory-saas-itrp-tutorial/tutorial_itrp_samlbase.png)

3. Dans la section **Domaine et URL ITRP**, procédez comme suit :

    ![Configure Single Sign-On](./media/active-directory-saas-itrp-tutorial/tutorial_itrp_url.png)

    a. Dans la zone de texte **URL de connexion**, tapez une URL au format suivant : `https://<tenant-name>.itrp.com`

    b. Dans la zone de texte **Identificateur**, tapez une URL au format suivant : `https://<tenant-name>.itrp.com`

    > [!NOTE] 
    > Il ne s’agit pas de valeurs réelles. Mettez à jour ces valeurs avec l’URL de connexion et l’identificateur réels. Pour obtenir ces valeurs, contactez l’[équipe de support technique ITRP](https://www.itrp.com/support). 
 
4. Dans la section **Certificat de signature SAML**, copiez la valeur **EMPREINTE** du certificat.

    ![Configure Single Sign-On](./media/active-directory-saas-itrp-tutorial/tutorial_itrp_certificate.png) 

5. Cliquez sur le bouton **Enregistrer** .

    ![Configure Single Sign-On](./media/active-directory-saas-itrp-tutorial/tutorial_general_400.png)

6. Dans la section **Configuration d’ITRP**, cliquez sur **Configurer ITRP** pour ouvrir la fenêtre **Configurer l’authentification**. Copiez l’**URL du service d’authentification unique SAML et l’URL de déconnexion** à partir de la **section Référence rapide**.

    ![Configure Single Sign-On](./media/active-directory-saas-itrp-tutorial/tutorial_itrp_configure.png) 

7. Dans une autre fenêtre de navigateur web, connectez-vous à votre site d’entreprise ITRP en tant qu’administrateur.

8. Dans la barre d’outils située en haut, cliquez sur **Settings**.
   
    ![ITRP](./media/active-directory-saas-itrp-tutorial/ic775570.png "ITRP")

8. Dans le volet de navigation de gauche, sélectionnez **Single Sign-On**.
   
    ![Authentification unique](./media/active-directory-saas-itrp-tutorial/ic775571.png "Authentification unique")

9. Dans la section de configuration Single Sign-On, procédez comme suit :
   
    ![Authentification unique](./media/active-directory-saas-itrp-tutorial/ic775572.png "Authentification unique")
    
    ![Authentification unique](./media/active-directory-saas-itrp-tutorial/ic775573.png "Authentification unique")   

    a. Cliquez sur **Enable**.

    b. Dans la zone de texte **URL de déconnexion à distance**, collez la valeur de **URL de déconnexion** que vous avez copiée sur le portail Azure.

    c. Dans la zone de texte **URL SAML SSO**, collez la valeur de l’**URL du service d’authentification unique SAML** que vous avez copiée sur le portail Azure.

    d. Dans la zone de texte **Empreinte digitale du certificat**, collez la valeur **Empreinte** du certificat que vous avez copiée sur le portail Azure. 
      
10. Cliquez sur **Enregistrer**.

> [!TIP]
> Vous pouvez maintenant lire une version concise de ces instructions dans le [portail Azure](https://portal.azure.com), pendant que vous configurez l’application.  Après avoir ajouté cette application à partir de la section **Active Directory > Applications d’entreprise**, cliquez simplement sur l’onglet **Authentification unique** et accédez à la documentation incorporée par le biais de la section **Configuration** en bas. Vous pouvez en savoir plus sur la fonctionnalité de documentation incorporée ici : [Documentation incorporée Azure AD]( https://go.microsoft.com/fwlink/?linkid=845985)
> 

### <a name="creating-an-azure-ad-test-user"></a>Création d’un utilisateur de test Azure AD
L’objectif de cette section est de créer un utilisateur de test appelé Britta Simon dans le portail Azure.

![Créer un utilisateur Azure AD][100]

**Pour créer un utilisateur de test dans Azure AD, procédez comme suit :**

1. Dans le panneau de navigation gauche du **portail Azure**, cliquez sur l’icône **Azure Active Directory**.

    ![Création d’un utilisateur de test Azure AD](./media/active-directory-saas-itrp-tutorial/create_aaduser_01.png) 

2. Pour afficher la liste des utilisateurs, accédez à **Utilisateurs et groupes**, puis cliquez sur **Tous les utilisateurs**.
    
    ![Création d’un utilisateur de test Azure AD](./media/active-directory-saas-itrp-tutorial/create_aaduser_02.png) 

3. Pour ouvrir la boîte de dialogue **Utilisateur**, cliquez sur **Ajouter** en haut de la boîte de dialogue.
 
    ![Création d’un utilisateur de test Azure AD](./media/active-directory-saas-itrp-tutorial/create_aaduser_03.png) 

4. Dans la boîte de dialogue **Utilisateur**, procédez comme suit :
 
    ![Création d’un utilisateur de test Azure AD](./media/active-directory-saas-itrp-tutorial/create_aaduser_04.png) 

    a. Dans la zone de texte **Nom**, entrez **BrittaSimon**.

    b. Dans la zone de texte **Nom d’utilisateur**, tapez **l’adresse e-mail** de Britta Simon.

    c. Sélectionnez **Afficher le mot de passe** et notez la valeur du **mot de passe**.

    d. Cliquez sur **Créer**.
 
### <a name="creating-an-itrp-test-user"></a>Création d’un utilisateur de test ITRP

Pour pouvoir se connecter à ITRP, les utilisateurs d’Azure Active Directory doivent être configurés dans ITRP.  

Dans le cas d’ITRP, l’approvisionnement est une tâche manuelle.

**Pour approvisionner un compte d’utilisateur, procédez comme suit :**

1. Connectez-vous à votre locataire **ITRP** .

2. Dans la barre d’outils située en haut, cliquez sur **Records**.
   
    ![Administrateur](./media/active-directory-saas-itrp-tutorial/ic775575.png "Administrateur")

3. Dans le menu contextuel, sélectionnez **People**.
   
    ![Personnes](./media/active-directory-saas-itrp-tutorial/ic775587.png "Personnes")

4. Cliquez sur **Add New Person** (« + »).
   
    ![Administrateur](./media/active-directory-saas-itrp-tutorial/ic775576.png "Administrateur")

5. Dans la boîte de dialogue Add New Person, procédez comme suit :
   
    ![Utilisateur](./media/active-directory-saas-itrp-tutorial/ic775577.png "Utilisateur") 
      
    a. Entrez le **nom**, et **l’adresse de messagerie** d’un compte AAD valide que vous voulez approvisionner.

    b. Cliquez sur **Enregistrer**.

>[!NOTE]
>Vous pouvez utiliser tout autre outil ou n’importe quelle API de création de compte d’utilisateur fournis par ITRP pour approvisionner des comptes d’utilisateurs Azure Active Directory. 
> 

### <a name="assigning-the-azure-ad-test-user"></a>Affectation de l’utilisateur de test Azure AD

Dans cette section, vous allez autoriser Britta Simon à utiliser l’authentification unique Azure en lui accordant l’accès à ITRP.

![Affecter des utilisateurs][200] 

**Pour affecter Britta Simon à ITRP, procédez comme suit :**

1. Dans le portail Azure, ouvrez la vue des applications, accédez à la vue des répertoires, accédez à **Applications d’entreprise**, puis cliquez sur **Toutes les applications**.

    ![Affecter des utilisateurs][201] 

2. Dans la liste des applications, sélectionnez **ITRP**.

    ![Configure Single Sign-On](./media/active-directory-saas-itrp-tutorial/tutorial_itrp_app.png) 

3. Dans le menu de gauche, cliquez sur **Utilisateurs et groupes**.

    ![Affecter des utilisateurs][202] 

4. Cliquez sur le bouton **Ajouter**. Ensuite, sélectionnez **Utilisateurs et groupes** dans la boîte de dialogue **Ajouter une affectation**.

    ![Affecter des utilisateurs][203]

5. Dans la boîte de dialogue **Utilisateurs et groupes**, sélectionnez **Britta Simon** dans la liste des utilisateurs.

6. Cliquez sur le bouton **Sélectionner** dans la boîte de dialogue **Utilisateurs et groupes**.

7. Cliquez sur le bouton **Affecter** dans la boîte de dialogue **Ajouter une affectation**.
    
### <a name="testing-single-sign-on"></a>Test de l’authentification unique

Dans cette section, vous allez tester la configuration de l’authentification unique Azure AD à l’aide du volet d’accès.

Lorsque vous cliquez sur la vignette ITRP dans le panneau d’accès, vous êtes automatiquement connecté à votre application ITRP.
Pour plus d’informations sur le panneau d’accès, consultez [Présentation du panneau d’accès](active-directory-saas-access-panel-introduction.md).

## <a name="additional-resources"></a>Ressources supplémentaires

* [Liste de didacticiels sur l’intégration d’applications SaaS avec Azure Active Directory](active-directory-saas-tutorial-list.md)
* [Qu’est-ce que l’accès aux applications et l’authentification unique avec Azure Active Directory ?](manage-apps/what-is-single-sign-on.md)

<!--Image references-->

[1]: ./media/active-directory-saas-itrp-tutorial/tutorial_general_01.png
[2]: ./media/active-directory-saas-itrp-tutorial/tutorial_general_02.png
[3]: ./media/active-directory-saas-itrp-tutorial/tutorial_general_03.png
[4]: ./media/active-directory-saas-itrp-tutorial/tutorial_general_04.png

[100]: ./media/active-directory-saas-itrp-tutorial/tutorial_general_100.png

[200]: ./media/active-directory-saas-itrp-tutorial/tutorial_general_200.png
[201]: ./media/active-directory-saas-itrp-tutorial/tutorial_general_201.png
[202]: ./media/active-directory-saas-itrp-tutorial/tutorial_general_202.png
[203]: ./media/active-directory-saas-itrp-tutorial/tutorial_general_203.png

