---
title: 'Schritt 2: Erstellen Microsoft Teams Vertragsverwaltungskanals mithilfe von Microsoft Teams'
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
description: Erfahren Sie, wie Sie Microsoft Teams zum Erstellen Ihres Vertragsverwaltungskanals mithilfe einer Microsoft 365 verwenden.
ms.openlocfilehash: 81d5fe34383453b187363b13c21ef47844948193
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636182"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>Schritt 2. Erstellen Microsoft Teams Vertragsverwaltungskanals mithilfe von Microsoft Teams

Wenn Ihre Organisation eine Lösung für die Vertragsverwaltung eingerichtet hat, benötigen Sie einen zentralen Ort, an dem Beteiligte Verträge überprüfen und verwalten können. Zu diesem Zweck können Sie [Microsoft Teams](https://docs.microsoft.com/microsoftteams/) verwenden, um einen Teams einrichten und die Features in Teams verwenden:

- **Erstellen Sie einen Ort für Beteiligte, um alle Verträge, die Aktionen erfordern, einfach zu sehen.** In der Teams Sie beispielsweise eine  Registerkarte Verträge im Kanal Vertragsverwaltung erstellen, in der Mitgliedern eine nützliche Kachelansicht aller Verträge angezeigt wird, die genehmigt werden müssen. Sie können die Ansicht auch so konfigurieren, dass jede "Karte" die wichtigen Daten auflistet, die Ihnen wichtig sind (z. B. *Client,* *Auftragnehmer* und *Gebührenbetrag).*

     ![Registerkarte Verträge.](../media/content-understanding/tile-view.png)

- **Verfügen Sie über einen Ort, an dem Mitglieder miteinander interagieren und wichtige Ereignisse sehen können.** Beispielsweise kann in Teams die  Registerkarte Beiträge verwendet werden, um Unterhaltungen zu führen, Updates zu erhalten und Aktionen zu sehen (z. B. ein Mitglied, das einen Vertrag ablehnt). Wenn etwas passiert ist (z. B. ein neuer Vertrag, der zur Genehmigung eingereicht wurde), kann die Registerkarte **Beiträge** nicht nur zum Ankündigen, sondern auch zum Aufzeichnen verwendet werden. Und wenn Mitglieder Benachrichtigungen abonnieren, werden sie benachrichtigt, wenn ein Update vorkommt. 

     ![Registerkarte Beiträge.](../media/content-understanding/posts.png)</br> 

- **Haben Sie einen Ort, an dem Mitglieder genehmigte Verträge sehen können, um zu wissen, wann sie zur Zahlung eingereicht werden können.** In Teams können Sie einen <b>For Payment-Kanal</b> erstellen, der alle Verträge auflistet, die zur Zahlung übermittelt werden müssen. Sie können diese Lösung problemlos erweitern, um diese Informationen stattdessen direkt in eine Finanzanwendung eines Drittanbieters (z. B. Dynamics CRM) zu schreiben.

## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>Anfügen SharePoint Dokumentbibliothek an die Registerkarte Verträge 

Nachdem Sie im **Kanal** Vertragsverwaltung eine Registerkarte Verträge erstellt haben, müssen Sie die SharePoint [Dokumentbibliothek anfügen.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b) Die SharePoint Dokumentbibliothek, die Sie anfügen möchten, ist die Dokumentbibliothek, auf die Sie ihr SharePoint Syntex-Dokumentverständnismodell im vorherigen Abschnitt angewendet haben.

Nachdem Sie die SharePoint hinzugefügt haben, können Sie alle klassifizierten Verträge über eine Standardlistenansicht anzeigen.

   ![Listenansicht.](../media/content-understanding/list-view.png) 

## <a name="customize-your-contracts-tab-tile-view"></a>Anpassen der Kachelansicht der Registerkarte Verträge

> [!NOTE]
> In diesem Abschnitt werden Codebeispiele referenziert, die in der [ContractTileFormatting.json-Datei](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) enthalten sind, die im [Repository "Contracts Management Solution Assets" enthalten ist.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)

Während Teams Sie Ihre Verträge in einer Kachelansicht anzeigen können, möchten Sie sie möglicherweise so anpassen, dass die Vertragsdaten angezeigt werden, die Sie auf der Vertragskarte sichtbar machen möchten. Für die Registerkarte  Verträge ist es z. B. wichtig, dass Mitglieder den Client, den Auftragnehmer und den Gebührenbetrag auf der Vertragskarte sehen. Alle diese Felder wurden aus jedem Vertrag über Ihr SharePoint Syntex-Modell extrahiert, das auf Ihre Dokumentbibliothek angewendet wurde. Sie möchten auch in der Lage sein, die Kachelkopfleiste für jeden Status in unterschiedliche Farben zu ändern, damit Mitglieder leicht sehen können, wo sich der Vertrag im Genehmigungsprozess befindet. Beispielsweise verfügen alle genehmigten Verträge über eine blaue Kopfzeile.

   ![Listenansicht.](../media/content-understanding/tile.png)

Für die von Ihnen verwendete benutzerdefinierte Kachelansicht müssen Sie Änderungen an der JSON-Datei vornehmen, die zum Formatieren der aktuellen Kachelansicht verwendet wird. Sie können auf die JSON-Datei verweisen, die zum Erstellen der Kartenansicht verwendet wird, indem Sie sich die Datei [ContractTileFormatting.js](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) ansehen. In den folgenden Abschnitten werden bestimmte Abschnitte des Codes für Features in den Vertragskarten beschrieben.

Wenn Sie den JSON-Code für Ihre Ansicht in Ihrem Teams-Kanal anzeigen oder ändern möchten, wählen Sie im Teams-Kanal das Dropdownmenü Ansicht aus, und wählen Sie dann Aktuelle Ansicht **formatieren aus.**

   ![json-Format.](../media/content-understanding/jason-format.png) 

## <a name="card-size-and-shape"></a>Kartengröße und -form

In der [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) sehen Sie sich den folgenden Abschnitt an, um den Code für die Formatierung der Größe und Form der Karte zu sehen.

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```


## <a name="contract-status"></a>Vertragsstatus

Mit dem folgenden Code können Sie den Status jeder Titelkarte definieren. Beachten Sie, dass für jeden Statuswert (*Neu*, *In Review*, *Approved* und *Rejected*) jeweils ein anderer Farbcode angezeigt wird. Sehen SieContractTileFormatting.jsin der Datei [ "on"](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) den Abschnitt an, in dem der Status definiert ist.

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```


## <a name="extracted-fields"></a>Extrahierte Felder

Jede Vertragskarte zeigt drei Felder an, die für jeden Vertrag extrahiert wurden (*Client,* *Auftragnehmer* und *Gebührenbetrag*). Darüber hinaus möchten Sie auch die Uhrzeit/das Datum anzeigen, an dem die Datei vom SharePoint syntex-Modell klassifiziert wurde, mit dem sie identifiziert wurde. 

In der [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) werden diese in den folgenden Abschnitten definiert.

### <a name="client"></a>Client

In diesem Abschnitt wird definiert, wie "Client" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag verwendet.

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a>Auftragnehmer

In diesem Abschnitt wird definiert, wie der "Auftragnehmer" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag verwendet.

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
},
```


### <a name="fee-amount"></a>Gebührenbetrag

In diesem Abschnitt wird definiert, wie der "Gebührenbetrag" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag verwendet.

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```



### <a name="classification-date"></a>Klassifizierungsdatum

In diesem Abschnitt wird definiert, wie "Klassifizierung" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag verwendet.

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a>Nächster Schritt

[Schritt 3. Verwenden Power Automate, um Ihren Fluss zum Verarbeiten Ihrer Verträge zu erstellen](solution-manage-contracts-step3.md)
