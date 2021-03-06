---
title: Schémas de suivi X12 pour la surveillance B2B - Azure Logic Apps | Microsoft Docs
description: Utilisez des schémas de suivi X12 pour surveiller les messages B2B des transactions de votre compte d’intégration Azure.
author: padmavc
manager: anneta
editor: ''
services: logic-apps
documentationcenter: ''
ms.assetid: a5413f80-eaad-4bcf-b371-2ad0ef629c3d
ms.service: logic-apps
ms.workload: integration
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 01/27/2017
ms.author: LADocs; padmavc
ms.custom: H1Hack27Feb2017
ms.openlocfilehash: e5a43b9bdf522b6b26f27c082f5cb623f7a76a8b
ms.sourcegitcommit: 9cdd83256b82e664bd36991d78f87ea1e56827cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="start-or-enable-tracking-of-x12-messages-to-monitor-success-errors-and-message-properties"></a>Démarrage ou activation du suivi des messages X12 pour surveiller la réussite, les erreurs et les propriétés de message
Vous pouvez utiliser ces schémas de suivi X12 dans votre compte d’intégration Azure pour surveiller les transactions B2B :

* Schéma de suivi de document informatisé X12
* Schéma de suivi d’accusé de réception de document informatisé X12
* Schéma de suivi d’échange X12
* Schéma de suivi d’accusé de réception d’échange X12
* Schéma de suivi de groupe fonctionnel X12
* Schéma de suivi d’accusé de réception de groupe fonctionnel X12

## <a name="x12-transaction-set-tracking-schema"></a>Schéma de suivi de document informatisé X12
````java

    {
            "agreementProperties": {
                "senderPartnerName": "",
                "receiverPartnerName": "",
                "senderQualifier": "",
                "senderIdentifier": "",
                "receiverQualifier": "",
                "receiverIdentifier": "",
                "agreementName": ""
            },
            "messageProperties": {
                "direction": "",
                "interchangeControlNumber": "",
                "functionalGroupControlNumber": "",
                "transactionSetControlNumber": "",
                "CorrelationMessageId": "",
                "messageType": "",
                "isMessageFailed": "",
                "isTechnicalAcknowledgmentExpected": "",
                "isFunctionalAcknowledgmentExpected": "",
                "needAk2LoopForValidMessages":  "",
                "segmentsCount": ""
            }
    }
````

| Propriété | type | Description |
| --- | --- | --- |
| senderPartnerName | Chaîne | Nom de partenaire de l’expéditeur du message X12. (facultatif) |
| receiverPartnerName | Chaîne | Nom de partenaire du destinataire du message X12. (facultatif) |
| senderQualifier | Chaîne | Qualificateur du partenaire d’envoi. (obligatoire) |
| senderIdentifier | Chaîne | Identificateur du partenaire d’envoi. (obligatoire) |
| receiverQualifier | Chaîne | Qualificateur du partenaire de réception. (obligatoire) |
| receiverIdentifier | Chaîne | Identificateur du partenaire de réception. (obligatoire) |
| agreementName | Chaîne | Nom du contrat X12 dans lequel les messages sont résolus. (facultatif) |
| direction | Enum | Direction du flux de messages (envoi ou réception). (obligatoire) |
| interchangeControlNumber | Chaîne | Numéro de contrôle de l’échange. (facultatif) |
| functionalGroupControlNumber | Chaîne | Numéro de contrôle fonctionnel. (facultatif) |
| transactionSetControlNumber | Chaîne | Numéro de contrôle de document informatisé. (facultatif) |
| CorrelationMessageId | Chaîne | ID de message de corrélation. Correspond à {AgreementName}*{GroupControlNumber}*{TransactionSetControlNumber}. (facultatif) |
| messageType | Chaîne | Type de document ou de document informatisé. (facultatif) |
| isMessageFailed | Booléen | Indique si le message X12 a échoué. (obligatoire) |
| isTechnicalAcknowledgmentExpected | Booléen | Indique si l’accusé de réception technique est configuré dans le contrat X12. (obligatoire) |
| isFunctionalAcknowledgmentExpected | Booléen | Indique si l’accusé de réception fonctionnel est configuré dans le contrat X12. (obligatoire) |
| needAk2LoopForValidMessages | Booléen | Indique si la boucle AK2 est nécessaire pour un message valide. (obligatoire) |
| segmentsCount | Entier  | Nombre de segments dans le document informatisé X12. (facultatif) |

## <a name="x12-transaction-set-acknowledgement-tracking-schema"></a>Schéma de suivi d’accusé de réception de document informatisé X12
````java

    {
            "agreementProperties": {
                "senderPartnerName": "",
                "receiverPartnerName": "",
                "senderQualifier": "",
                "senderIdentifier": "",
                "receiverQualifier": "",
                "receiverIdentifier": "",
                "agreementName": ""
            },
            "messageProperties": {
                "direction": "",
                "interchangeControlNumber": "",
                "functionalGroupControlNumber": "",
                "isaSegment": "",
                "gsSegment": "",
                "respondingfunctionalGroupControlNumber": "",
                "respondingFunctionalGroupId": "",
                "respondingtransactionSetControlNumber": "",
                "respondingTransactionSetId": "",
                "statusCode": "",
                "processingStatus": "",
                "CorrelationMessageId": ""
                "isMessageFailed": "",
                "ak2Segment": "",
                "ak3Segment": "",
                "ak5Segment": ""
            }
    }
````

| Propriété | type | Description |
| --- | --- | --- |
| senderPartnerName | Chaîne | Nom de partenaire de l’expéditeur du message X12. (facultatif) |
| receiverPartnerName | Chaîne | Nom de partenaire du destinataire du message X12. (facultatif) |
| senderQualifier | Chaîne | Qualificateur du partenaire d’envoi. (obligatoire) |
| senderIdentifier | Chaîne | Identificateur du partenaire d’envoi. (obligatoire) |
| receiverQualifier | Chaîne | Qualificateur du partenaire de réception. (obligatoire) |
| receiverIdentifier | Chaîne | Identificateur du partenaire de réception. (obligatoire) |
| agreementName | Chaîne | Nom du contrat X12 dans lequel les messages sont résolus. (facultatif) |
| direction | Enum | Direction du flux de messages (envoi ou réception). (obligatoire) |
| interchangeControlNumber | Chaîne | Numéro de contrôle de l’échange de l’accusé de réception fonctionnel. Valeur renseignée uniquement pour l’envoi si un accusé de réception fonctionnel a été reçu pour les messages envoyés au partenaire. (facultatif) |
| functionalGroupControlNumber | Chaîne | Numéro de contrôle de groupe fonctionnel de l’accusé de réception fonctionnel. Valeur renseignée uniquement pour l’envoi si un accusé de réception fonctionnel a été reçu pour les messages envoyés au partenaire. (facultatif) |
| isaSegment | Chaîne | Segment ISA du message. Valeur renseignée uniquement pour l’envoi si un accusé de réception fonctionnel a été reçu pour les messages envoyés au partenaire. (facultatif) |
| gsSegment | Chaîne | Segment GS du message. Valeur renseignée uniquement pour l’envoi si un accusé de réception fonctionnel a été reçu pour les messages envoyés au partenaire. (facultatif) |
| respondingfunctionalGroupControlNumber | Chaîne | Numéro de contrôle de l’échange de réponse. (facultatif) |
| respondingFunctionalGroupId | Chaîne | ID du groupe fonctionnel de réponse qui est mappé à AK101 dans l’accusé de réception. (facultatif) |
| respondingtransactionSetControlNumber | Chaîne | Numéro de contrôle de document informatisé de réponse. (facultatif) |
| respondingTransactionSetId | Chaîne | ID du document informatisé de réponse, qui est mappé à AK201 dans l’accusé de réception. (facultatif) |
| statusCode | Booléen | Code d’état de l’accusé de réception du document informatisé. (obligatoire) |
| segmentsCount | Enum | Code d’état de l’accusé de réception. Les valeurs autorisées sont **Accepted**, **Rejected** et **AcceptedWithErrors**. (obligatoire) |
| processingStatus | Enum | État de traitement de l’accusé de réception. Les valeurs autorisées sont **Received**, **Generated** ou **Sent**. (obligatoire) |
| CorrelationMessageId | Chaîne | ID de message de corrélation. Correspond à {AgreementName}*{GroupControlNumber}*{TransactionSetControlNumber}. (facultatif) |
| isMessageFailed | Booléen | Indique si le message X12 a échoué. (obligatoire) |
| ak2Segment | Chaîne | Accusé de réception pour un document informatisé dans le groupe fonctionnel reçu. (facultatif) |
| ak3Segment | Chaîne | Signale les erreurs dans un segment de données. (facultatif) |
| ak5Segment | Chaîne | Signale si le document informatisé identifié dans le segment AK2 est accepté ou rejeté et pourquoi. (facultatif) |

## <a name="x12-interchange-tracking-schema"></a>Schéma de suivi d’échange X12
````java

    {
            "agreementProperties": {
                "senderPartnerName": "",
                "receiverPartnerName": "",
                "senderQualifier": "",
                "senderIdentifier": "",
                "receiverQualifier": "",
                "receiverIdentifier": "",
                "agreementName": ""
            },
            "messageProperties": {
                "direction": "",
                "interchangeControlNumber": "",
                "isaSegment": "",
                "isTechnicalAcknowledgmentExpected": "",
                "isMessageFailed": "",
                "isa09": "",
                "isa10": "",
                "isa11": "",
                "isa12": "",
                "isa14": "",
                "isa15": "",
                "isa16": ""
            }
    }
````

| Propriété | type | Description |
| --- | --- | --- |
| senderPartnerName | Chaîne | Nom de partenaire de l’expéditeur du message X12. (facultatif) |
| receiverPartnerName | Chaîne | Nom de partenaire du destinataire du message X12. (facultatif) |
| senderQualifier | Chaîne | Qualificateur du partenaire d’envoi. (obligatoire) |
| senderIdentifier | Chaîne | Identificateur du partenaire d’envoi. (obligatoire) |
| receiverQualifier | Chaîne | Qualificateur du partenaire de réception. (obligatoire) |
| receiverIdentifier | Chaîne | Identificateur du partenaire de réception. (obligatoire) |
| agreementName | Chaîne | Nom du contrat X12 dans lequel les messages sont résolus. (facultatif) |
| direction | Enum | Direction du flux de messages (envoi ou réception). (obligatoire) |
| interchangeControlNumber | Chaîne | Numéro de contrôle de l’échange. (facultatif) |
| isaSegment | Chaîne | Segment ISA du message. (facultatif) |
| isTechnicalAcknowledgmentExpected | Booléen | Indique si l’accusé de réception technique est configuré dans le contrat X12. (obligatoire) |
| isMessageFailed | Booléen | Indique si le message X12 a échoué. (obligatoire) |
| isa09 | Chaîne | Date d’échange du document X12. (facultatif) |
| isa10 | Chaîne | Heure d’échange du document X12. (facultatif) |
| isa11 | Chaîne | Identificateur des normes de contrôle d’échange X12. (facultatif) |
| isa12 | Chaîne | Numéro de version du contrôle d’échange X12. (facultatif) |
| isa14 | Chaîne | Un accusé de réception X12 est exigé. (facultatif) |
| isa15 | Chaîne | Indicateur de test ou de production. (facultatif) |
| isa16 | Chaîne | Séparateur d'éléments. (facultatif) |

## <a name="x12-interchange-acknowledgement-tracking-schema"></a>Schéma de suivi d’accusé de réception d’échange X12
````java
    {
            "agreementProperties": {
                "senderPartnerName": "",
                "receiverPartnerName": "",
                "senderQualifier": "",
                "senderIdentifier": "",
                "receiverQualifier": "",
                "receiverIdentifier": "",
                "agreementName": ""
            },
            "messageProperties": {
                "direction": "",
                "interchangeControlNumber": "",
                "isaSegment": "",
                "respondingInterchangeControlNumber": "",
                "isMessageFailed": "",
                "statusCode": "",
                "processingStatus": "",
                "ta102": "",
                "ta103": "",
                "ta105": ""
            }
    }
````

| Propriété | type | Description |
| --- | --- | --- |
| senderPartnerName | Chaîne | Nom de partenaire de l’expéditeur du message X12. (facultatif) |
| receiverPartnerName | Chaîne | Nom de partenaire du destinataire du message X12. (facultatif) |
| senderQualifier | Chaîne | Qualificateur du partenaire d’envoi. (obligatoire) |
| senderIdentifier | Chaîne | Identificateur du partenaire d’envoi. (obligatoire) |
| receiverQualifier | Chaîne | Qualificateur du partenaire de réception. (obligatoire) |
| receiverIdentifier | Chaîne | Identificateur du partenaire de réception. (obligatoire) |
| agreementName | Chaîne | Nom du contrat X12 dans lequel les messages sont résolus. (facultatif) |
| direction | Enum | Direction du flux de messages (envoi ou réception). (obligatoire) |
| interchangeControlNumber | Chaîne | Numéro de contrôle de l’échange de l’accusé de réception technique reçu de partenaires. (facultatif) |
| isaSegment | Chaîne | Segment ISA de l’accusé de réception technique reçu de partenaires. (facultatif) |
| respondingInterchangeControlNumber |Chaîne | Numéro de contrôle de l’échange pour l’accusé de réception technique reçu de partenaires. (facultatif) |
| isMessageFailed | Booléen | Indique si le message X12 a échoué. (obligatoire) |
| statusCode | Enum | Code d’état de l’accusé de réception de l’échange. Les valeurs autorisées sont **Accepted**, **Rejected** et **AcceptedWithErrors**. (obligatoire) |
| processingStatus | Enum | État de l’accusé de réception. Les valeurs autorisées sont **Received**, **Generated** ou **Sent**. (obligatoire) |
| ta102 | Chaîne | Date de l’échange. (facultatif) |
| ta103 | Chaîne | Heure de l’échange. (facultatif) |
| ta105 | Chaîne | Code de note de l’échange. (facultatif) |

## <a name="x12-functional-group-tracking-schema"></a>Schéma de suivi de groupe fonctionnel X12
````java

    {
            "agreementProperties": {
                "senderPartnerName": "",
                "receiverPartnerName": "",
                "senderQualifier": "",
                "senderIdentifier": "",
                "receiverQualifier": "",
                "receiverIdentifier": "",
                "agreementName": ""
            },
            "messageProperties": {
                "direction": "",
                "interchangeControlNumber": "",
                "functionalGroupControlNumber": "",
                "gsSegment": "",
                "isTechnicalAcknowledgmentExpected": "",
                "isFunctionalAcknowledgmentExpected": "",
                "isMessageFailed": "",
                "gs01": "",
                "gs02": "",
                "gs03": "",
                "gs04": "",
                "gs05": "",
                "gs07": "",
                "gs08": ""
            }
    }
````

| Propriété | type | Description |
| --- | --- | --- |
| senderPartnerName | Chaîne | Nom de partenaire de l’expéditeur du message X12. (facultatif) |
| receiverPartnerName | Chaîne | Nom de partenaire du destinataire du message X12. (facultatif) |
| senderQualifier | Chaîne | Qualificateur du partenaire d’envoi. (obligatoire) |
| senderIdentifier | Chaîne | Identificateur du partenaire d’envoi. (obligatoire) |
| receiverQualifier | Chaîne | Qualificateur du partenaire de réception. (obligatoire) |
| receiverIdentifier | Chaîne | Identificateur du partenaire de réception. (obligatoire) |
| agreementName | Chaîne | Nom du contrat X12 dans lequel les messages sont résolus. (facultatif) |
| direction | Enum | Direction du flux de messages (envoi ou réception). (obligatoire) |
| interchangeControlNumber | Chaîne | Numéro de contrôle de l’échange. (facultatif) |
| functionalGroupControlNumber | Chaîne | Numéro de contrôle fonctionnel. (facultatif) |
| gsSegment | Chaîne | Segment GS de message. (facultatif) |
| isTechnicalAcknowledgmentExpected | Booléen | Indique si l’accusé de réception technique est configuré dans le contrat X12. (obligatoire) |
| isFunctionalAcknowledgmentExpected | Booléen | Indique si l’accusé de réception fonctionnel est configuré dans le contrat X12. (obligatoire) |
| isMessageFailed | Booléen | Indique si le message X12 a échoué. (obligatoire)|
| gs01 | Chaîne | Code d’identificateur fonctionnel. (facultatif) |
| gs02 | Chaîne | Code de l’expéditeur de l’application. (facultatif) |
| gs03 | Chaîne | Code du destinataire de l’application. (facultatif) |
| gs04 | Chaîne | Date du groupe fonctionnel. (facultatif) |
| gs05 | Chaîne | Heure du groupe fonctionnel. (facultatif) |
| gs07 | Chaîne | Code de l’agence responsable. (facultatif) |
| gs08 | Chaîne | Code identificateur de version/du secteur. (facultatif) |

## <a name="x12-functional-group-acknowledgement-tracking-schema"></a>Schéma de suivi d’accusé de réception de groupe fonctionnel X12
````java
    {
            "agreementProperties": {
                "senderPartnerName": "",
                "receiverPartnerName": "",
                "senderQualifier": "",
                "senderIdentifier": "",
                "receiverQualifier": "",
                "receiverIdentifier": "",
                "agreementName": ""
            },
            "messageProperties": {
                "direction": "",
                "interchangeControlNumber": "",
                "functionalGroupControlNumber": "",
                "isaSegment": "",
                "gsSegment": "",
                "respondingfunctionalGroupControlNumber": "",
                "respondingFunctionalGroupId": "",
                "isMessageFailed": "",
                "statusCode": "",
                "processingStatus": "",
                "ak903": "",
                "ak904": "",
                "ak9Segment": ""
            }
    }
````

| Propriété | type | Description |
| --- | --- | --- |
| senderPartnerName | Chaîne | Nom de partenaire de l’expéditeur du message X12. (facultatif) |
| receiverPartnerName | Chaîne | Nom de partenaire du destinataire du message X12. (facultatif) |
| senderQualifier | Chaîne | Qualificateur du partenaire d’envoi. (obligatoire) |
| senderIdentifier | Chaîne | Identificateur du partenaire d’envoi. (obligatoire) |
| receiverQualifier | Chaîne | Qualificateur du partenaire de réception. (obligatoire) |
| receiverIdentifier | Chaîne | Identificateur du partenaire de réception. (obligatoire) |
| agreementName | Chaîne | Nom du contrat X12 dans lequel les messages sont résolus. (facultatif) |
| direction | Enum | Direction du flux de messages (envoi ou réception). (obligatoire) |
| interchangeControlNumber | Chaîne | Numéro de contrôle de l’échange, qui renseigne le côté envoi lors de la réception d’un accusé de réception technique de partenaires. (facultatif) |
| functionalGroupControlNumber | Chaîne | Numéro de contrôle de groupe fonctionnel de l’accusé de réception technique, qui renseigne le côté envoi lors de la réception d’un accusé de réception technique de partenaires. (facultatif) |
| isaSegment | Chaîne | Identique au numéro de contrôle de l’échange, mais renseigné uniquement dans des cas spécifiques. (facultatif) |
| gsSegment | Chaîne | Identique au numéro de contrôle de groupe fonctionnel, mais renseigné uniquement dans des cas spécifiques. (facultatif) |
| respondingfunctionalGroupControlNumber | Chaîne | Numéro de contrôle du groupe fonctionnel d’origine. (facultatif) |
| respondingFunctionalGroupId | Chaîne | Mappé à AK101 dans l’ID de groupe fonctionnel de l’accusé de réception. (facultatif) |
| isMessageFailed | Booléen | Indique si le message X12 a échoué. (obligatoire) |
| statusCode | Enum | Code d’état de l’accusé de réception. Les valeurs autorisées sont **Accepted**, **Rejected** et **AcceptedWithErrors**. (obligatoire) |
| processingStatus | Enum | État de traitement de l’accusé de réception. Les valeurs autorisées sont **Received**, **Generated** ou **Sent**. (obligatoire) |
| ak903 | Chaîne | Nombre maximal de documents informatisés reçus. (facultatif) |
| ak904 | Chaîne | Nombre de documents informatisés acceptés dans le groupe fonctionnel identifié. (facultatif) |
| ak9Segment | Chaîne | Indique si le groupe fonctionnel identifié dans le segment AK1 est accepté ou rejeté et pourquoi. (facultatif) |

## <a name="next-steps"></a>Étapes suivantes
* En savoir plus sur le [suivi des messages B2B](logic-apps-monitor-b2b-message.md).
* En savoir plus sur les [schémas de suivi AS2](../logic-apps/logic-apps-track-integration-account-as2-tracking-schemas.md).
* En savoir plus sur les [schémas de suivi personnalisé B2B](../logic-apps/logic-apps-track-integration-account-custom-tracking-schema.md).
* En savoir plus sur [le suivi des messages B2B dans Log Analytics](../logic-apps/logic-apps-track-b2b-messages-omsportal.md).
* En savoir plus sur [Enterprise Integration Pack](../logic-apps/logic-apps-enterprise-integration-overview.md).  
