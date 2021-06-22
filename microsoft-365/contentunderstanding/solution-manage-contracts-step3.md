---
title: 'SCHRITT 3: Verwenden sie Power Automate, um Ihren Flow zur Verarbeitung Ihrer Verträge zu erstellen'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Erfahren Sie, wie Sie Power Automate verwenden, um Ihren Flow zu erstellen, um Ihre Verträge mithilfe einer Microsoft 365 Lösung zu verarbeiten.
ms.openlocfilehash: e6c1d1e53363f996241efb2394189853d840c6c2
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054461"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a>Schritt 3: Verwenden sie Power Automate, um Ihren Flow zur Verarbeitung Ihrer Verträge zu erstellen

Sie haben Ihren Vertragsverwaltungskanal erstellt und Ihre SharePoint Dokumentbibliothek angefügt. Der nächste Schritt besteht darin, einen Power Automate Ablauf zu erstellen, um Ihre Verträge zu verarbeiten, die ihr SharePoint Syntex-Modell identifiziert und klassifiziert. Sie können diesen Schritt ausführen, indem [Sie einen Power Automate Fluss in Ihrer SharePoint Dokumentbibliothek erstellen.](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)

Für Ihre Vertragsverwaltungslösung möchten Sie einen Power Automate Ablauf erstellen, um die folgenden Aktionen auszuführen:

-  Nachdem ein Vertrag von Ihrem SharePoint Syntex-Modell klassifiziert wurde, ändern Sie den Vertragsstatus in **"In Review".**
- Der Vertrag wird dann überprüft und entweder genehmigt oder abgelehnt.
- Bei genehmigten Verträgen werden die Vertragsinformationen auf einer Registerkarte für die Zahlungsverarbeitung bereitgestellt.
- Bei abgelehnten Verträgen wird das Team zur weiteren Analyse benachrichtigt. 

Das folgende Diagramm zeigt den Power Automate Ablauf für die Vertragsverwaltungslösung.

![Flow Diagramm, das die gesamte Lösung zeigt.](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a>Vorbereiten Ihres Vertrags für die Überprüfung

Wenn ein Vertrag durch Ihr SharePoint Syntex Dokumentverständnismodell identifiziert und klassifiziert wird, ändert der Power Automate Fluss zuerst den Status **in "In review".**

![Status aktualisieren.](../media/content-understanding/flow-overview.png)

Ändern Sie nach dem Auschecken der Datei den Statuswert in **"In review".**

![Im Überprüfungsstatus.](../media/content-understanding/in-review.png)

Der nächste Schritt besteht darin, eine adaptive Karte zu erstellen, die besagt, dass der Vertrag auf die Überprüfung wartet und sie im Vertragsverwaltungskanal veröffentlicht.

![Beitrag zur Vertragsüberprüfung.](../media/content-understanding/contract-approval-post.png)


![Erstellen Sie eine adaptive Karte zur Überprüfung.](../media/content-understanding/adaptive-card.png)

Der folgende Code ist der JSON-Code, der für diesen Schritt im Power Automate-Fluss verwendet wird.

```JSON
{
"$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
"type": "AdaptiveCard",
"version": "1.0",
"body": [
    {
    "type": "TextBlock",
    "text": "Contract approval request",
    "size": "large",
    "weight": "bolder",
     "wrap": true
    },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Date created",
                            "value": "@{triggerOutputs()?['body/Modified']} "
                        },
                        {
                            "title": "Link",
                            "value": "[@{triggerOutputs()?['body/{FilenameWithExtension}']}](@{triggerOutputs()?['body/{Link}']})"
                        }
                    ]
                }
            ]
         },
    {
    "type": "TextBlock",
    "text": "Comment:"
    },
        {
            "type": "Input.Text",
            "placeholder": "Enter comments",
            "id": "acComments"
        }
],
"actions": [
    {
    "type": "Action.Submit",
    "title": "Approve",
    "data": {
        "x": "Approve"
    }
    },
    {
    "type": "Action.Submit",
    "title": "Reject",
    "data": {
        "x": "Reject"
    }
    }
]
}
```


## <a name="conditional-context"></a>Bedingter Kontext

Als Nächstes müssen Sie in Ihrem Flow eine Bedingung erstellen, in der Ihr Vertrag entweder  [genehmigt](#if-the-contract-is-approved) oder [abgelehnt](#if-the-contract-is-rejected)wird.

![Bedingte.](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a>Wenn der Vertrag genehmigt wurde

Wenn ein Vertrag genehmigt wurde, geschieht Folgendes:

- Auf der Registerkarte **"Verträge"** ändert sich der Status in der Vertragskarte in **"Genehmigt".**

   ![Kartenstatus genehmigt.](../media/content-understanding/approved-contracts-tab.png)

- In Ihrem Flow wird der Status in **Genehmigt** geändert.

   ![Flow Status genehmigt.](../media/content-understanding/status-approved.png)

- In dieser Lösung werden die Vertragsdaten der Registerkarte **"Für Auszahlung"** hinzugefügt, damit die Auszahlungen verwaltet werden können. Dieser Prozess kann erweitert werden, damit der Fluss die Verträge zur Zahlung durch eine Drittanbieter-Finanzanwendung (z. B. Dynamics CRM) übermitteln kann.

   ![Der Vertrag wurde auf "Auszahlung" verschoben.](../media/content-understanding/for-payout.png)

- Im Fluss erstellen Sie das folgende Element, um genehmigte Verträge auf die Registerkarte **"Für Auszahlung"** zu verschieben.

   ![Flow Zu zahlenden Element.](../media/content-understanding/ready-for-payout.png)

    Verwenden Sie die in der folgenden Tabelle aufgeführten Werte, um die Ausdrücke für die von der Teams Karte benötigten Informationen abzurufen.
 
    |Name     |Expression |
    |---------|-----------|
    | Genehmigungsstatus  | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')? ['submitActionId']         |
    | Genehmigt von     | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')? ['responder'] ['displayName']        |
    | Genehmigungsdatum     | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')? ['responseTime']         |
    | Kommentar     | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')? ['data'] ['acComments']         |
    
    Das folgende Beispiel zeigt, wie Sie das Formelfeld in Power Automate verwenden, um einen Ausdruck zu schreiben.

   ![Screenshot in Power Automate mit einer Ausdrucksformel.](../media/content-understanding/expression-formula-power-automate.png)    

- Eine adaptive Karte, die besagt, dass der Vertrag genehmigt wurde, wird erstellt und im Vertragsverwaltungskanal veröffentlicht.

   ![Vertragsgenehmigung veröffentlicht.](../media/content-understanding/adaptive-card-approval.png)

   ![Genehmigung adaptiver Karten.](../media/content-understanding/adaptive-card.png)


   Der folgende Code ist der JSON-Code, der für diesen Schritt im Power Automate-Fluss verwendet wird.

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "emphasis",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT APPROVED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Approval by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Approved date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Approval comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Ready for payout"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

## <a name="if-the-contract-is-rejected"></a>Wenn der Vertrag abgelehnt wird

Wenn ein Vertrag abgelehnt wurde, geschieht Folgendes:

- Auf der Registerkarte **"Verträge"** ändert sich der Status in der Vertragskarte in **"Abgelehnt".**

   ![Kartenstatus abgelehnt.](../media/content-understanding/rejected-contracts-tab.png)

- In Ihrem Flow checken Sie die Vertragsdatei aus, ändern den Status in **"Abgelehnt",** und checken dann die Datei wieder ein.

   ![Flow in der Vertragsdatei abgelehnter Status.](../media/content-understanding/reject-flow.png)

- In Ihrem Flow erstellen Sie eine adaptive Karte, die besagt, dass der Vertrag abgelehnt wurde.

   ![Flow Status wird auf adaptiver Karte als abgelehnt angezeigt.](../media/content-understanding/reject-flow-item.png)

Der folgende Code ist der JSON-Code, der für diesen Schritt im Power Automate-Fluss verwendet wird.

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "attention",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT REJECTED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Rejected by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Rejected date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Needs review"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

- Die Karte wird im Vertragsverwaltungskanal bereitgestellt.

   ![Flow adaptive Karte, die abgelehnt werden soll.](../media/content-understanding/rejected.png)