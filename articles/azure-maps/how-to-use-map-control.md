---
title: Guide pratique d’utilisation de la bibliothèque Azure Maps Map Control | Microsoft Docs
description: Découvrez comment utiliser la bibliothèque JavaScript côté client Azure Maps Map Control.
services: azure-maps
author: kgremban
ms.author: kgremban
ms.date: 05/07/2018
ms.topic: article
ms.service: azure-maps
manager: timlt
ms.openlocfilehash: bbd06aad9052d2a775c35dd08f80462f8ea505a9
ms.sourcegitcommit: e221d1a2e0fb245610a6dd886e7e74c362f06467
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-the-azure-maps-map-control"></a>Guide pratique d’utilisation de la bibliothèque Azure Maps Map Control
La bibliothèque Javascript côté client Map Control vous permet d’effectuer le rendu de cartes et des fonctionnalités Azure Maps intégrées dans votre application web ou mobile. 

## <a name="create-a-new-map-in-a-web-page"></a>Créer une carte dans une page web

Vous pouvez intégrer une carte dans une page web à l’aide de la bibliothèque JavaScript côté client Map Control.

1. Créez un fichier et nommez-le MapSearch.html.

2. Ajoutez la feuille de styles Azure Maps et les références de la source du script à l’élément `<head>` du fichier :

    ```html
    <link rel="stylesheet" href="https://atlas.microsoft.com/sdk/css/atlas.min.css?api-version=1.0" type="text/css" />
    <script src="https://atlas.microsoft.com/sdk/js/atlas.min.js?api-version=1.0"></script>
    ```
    
3. Afin d’effectuer le rendu d’une nouvelle carte dans votre navigateur, ajoutez une référence **#map** dans l’élément `<style>`.

    ```html
    #map {
                width: 100%;
                height: 100%;
            }
    ``` 
    
4. Afin d’initialiser le contrôle de la carte, définissez une nouvelle section dans le corps HTML et créez un script. Utilisez votre propre clé de compte Azure Maps dans le script. Si vous devez créer un compte ou rechercher votre clé, consultez la section [How to manage your Azure Maps account and keys](how-to-manage-account-keys.md) (Guide de gestion de votre compte et de vos clés Azure Maps).

    ```html
    <div id="map">
        <script>
            var MapsAccountKey = "<_your account key_>";
            var map = new atlas.Map("map", {
                "subscription-key": MapsAccountKey,
                center: [47.59093,-122.33263],
                zoom: 12
            });
        </script>
    </div>
    ```
    
5. Ouvrez le fichier dans votre navigateur web et consultez la carte ayant fait l’objet du rendu.

## <a name="next-steps"></a>Étapes suivantes

Cet article vous a expliqué comment créer une carte de base avec votre clé Azure Maps. Pour consulter plus d’exemples de code à ajouter à vos cartes, consultez les articles suivants : 

* [Créer une carte](map-create.md)
* [Ajouter un repère](map-add-pin.md)