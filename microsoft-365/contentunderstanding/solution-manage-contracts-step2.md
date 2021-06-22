---
title: 'Schritt 2: Verwenden Microsoft Teams zum Erstellen Ihres Vertragsverwaltungskanals'
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
description: Erfahren Sie, wie Sie Microsoft Teams verwenden, um Ihren Vertragsverwaltungskanal mithilfe einer Microsoft 365-Lösung zu erstellen.
ms.openlocfilehash: 099487279482385760e05d9b166ae80c665d931e
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054753"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>Schritt 2. Verwenden Microsoft Teams zum Erstellen Ihres Vertragsverwaltungskanals

Wenn Ihre Organisation eine Lösung für die Vertragsverwaltung einrichtet, benötigen Sie einen zentralen Ort, an dem Projektbeteiligten Verträge überprüfen und verwalten können. Zu diesem Zweck können Sie [Microsoft Teams](/microsoftteams/) verwenden, um einen Teams Kanal einzurichten und die Features in Teams für Folgendes zu verwenden:

- **Erstellen Sie einen Ort für Projektbeteiligten, um alle Verträge anzuzeigen, die Maßnahmen erfordern.** In Teams können Sie beispielsweise eine Registerkarte **"Verträge"** im Kanal "Vertragsverwaltung" erstellen, in der Mitglieder eine nützliche Kachelansicht aller Verträge sehen können, die genehmigt werden müssen. Sie können die Ansicht auch so konfigurieren, dass jede "Karte" die wichtigen Daten auflistet, die Ihnen wichtig sind (z. B. *Client,* *Auftragnehmer* und *Gebührenbetrag).*

     ![Registerkarte "Verträge".](../media/content-understanding/tile-view.png)

- **Haben Sie einen Ort, an dem Mitglieder miteinander interagieren und wichtige Ereignisse sehen können.** Beispielsweise kann in Teams die Registerkarte **"Beiträge"** verwendet werden, um Unterhaltungen zu führen, Updates abzurufen und Aktionen anzuzeigen (z. B. ein Mitglied, das einen Vertrag ablehnt). Wenn etwas passiert ist (z. B. ein neuer Vertrag, der zur Genehmigung übermittelt wurde), kann die Registerkarte **"Beiträge"** nicht nur verwendet werden, um ihn anzukündigen, sondern auch, um einen Datensatz darüber zu führen. Und wenn Mitglieder Benachrichtigungen abonnieren, werden sie benachrichtigt, wenn ein Update vorhanden ist.

     ![Registerkarte "Beiträge".](../media/content-understanding/posts.png)

- **Haben Sie einen Ort, an dem Mitglieder genehmigte Verträge sehen können, um zu wissen, wann sie zur Zahlung eingereicht werden können.** In SharePoint müssen Sie eine **"For Payout"-Liste** erstellen und Spalten für **den Betrag "Client",** **"Auszahlung"** und **"Gebühr"** einschließen, wobei **"Einzelne Textzeile"** als Spaltentyp ausgewählt wird. Sie müssen die For **Payout-Liste** als Teams Registerkarte im Vertragsverwaltungskanal hinzufügen, ähnlich wie [bei der Registerkarte **"Verträge".**](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab) Auf der Registerkarte **"Für Auszahlung"** werden alle Verträge aufgeführt, die zur Zahlung übermittelt werden müssen. Sie können diese Lösung einfach erweitern, um diese Informationen stattdessen direkt in eine Finanzanwendung eines Drittanbieters (z. B. Dynamics CRM) zu schreiben. 


## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>Fügen Sie Ihre SharePoint Dokumentbibliothek an die Registerkarte "Verträge" an.

Nachdem Sie im Kanal "Vertragsverwaltung" eine Registerkarte **"Verträge"** erstellt haben, müssen Sie [ihre SharePoint Dokumentbibliothek an diese anfügen.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b) Die SharePoint Dokumentbibliothek, die Sie anfügen möchten, ist diejenige, in der Sie ihr SharePoint Syntex Dokumentverständnismodell im vorherigen Abschnitt angewendet haben.

Nachdem Sie die SharePoint Dokumentbibliothek angefügt haben, können Sie alle klassifizierten Verträge über eine Standardlistenansicht anzeigen.

   ![Listenansicht SharePoint Bibliothek.](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a>Anpassen der Kachelansicht der Registerkarte "Verträge"

> [!NOTE]
> In diesem Abschnitt wird auf [ Codebeispiele](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) verwiesen, die in derContractTileFormatting.js-Datei enthalten sind, die im [Repository "Contracts Management Solution Assets"](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)enthalten ist.

Während Sie mit Teams Ihre Verträge in einer Kachelansicht anzeigen können, können Sie sie anpassen, um die Vertragsdaten anzuzeigen, die Sie auf der Vertragskarte sichtbar machen möchten. Für die Registerkarte **"Verträge"** ist es beispielsweise wichtig, dass Mitglieder den Client, den Vertragsnehmer und den Gebührenbetrag auf der Vertragskarte sehen. Alle diese Felder wurden aus jedem Vertrag über Ihr SharePoint Syntex Modell extrahiert, das auf Ihre Dokumentbibliothek angewendet wurde. Sie möchten auch in der Lage sein, die Kachelkopfleiste für jeden Status in unterschiedliche Farben zu ändern, damit mitglieder leicht sehen können, wo sich der Vertrag im Genehmigungsprozess befindet. Beispielsweise verfügen alle genehmigten Verträge über eine blaue Kopfzeile.

   ![Kachelansicht SharePoint Bibliothek.](../media/content-understanding/tile.png)

Für die von Ihnen verwendete benutzerdefinierte Kachelansicht müssen Sie Änderungen an der JSON-Datei vornehmen, die zum Formatieren der aktuellen Kachelansicht verwendet wird. Sie können auf die JSON-Datei verweisen, die zum Erstellen der Kartenansicht verwendet wird, indem Sie sich die [ContractTileFormatting.json-Datei](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) ansehen. In den folgenden Abschnitten sehen Sie bestimmte Abschnitte des Codes für Features, die in den Vertragskarten enthalten sind.

Wenn Sie den JSON-Code für Ihre Ansicht in Ihrem Teams Kanal anzeigen oder ändern möchten, wählen Sie im Teams Kanal das Dropdownmenü "Ansicht" und dann **"Aktuelle Ansicht formatieren"** aus.

   ![Screenshot des JSON-Formats in Teams Kanal.](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a>Kartengröße und -form

Sehen [ Sie](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) sich imContractTileFormatting.json-Datei den folgenden Abschnitt an, um den Code für die Formatierung der Größe und Form der Karte anzuzeigen.

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

Mit dem folgenden Code können Sie den Status jeder Titelkarte definieren. Beachten Sie, dass jeder Statuswert (*Neu*, *In Rezension,* *Genehmigt* und *Abgelehnt*) jeweils einen anderen Farbcode anzeigt. In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the section that defines the status.

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

Jede Vertragskarte zeigt drei Felder an, die für jeden Vertrag extrahiert wurden (*Client,* *Auftragnehmer* und *Gebührenbetrag).* Darüber hinaus möchten Sie die Uhrzeit/das Datum anzeigen, zu dem die Datei vom SharePoint Syntex Modell klassifiziert wurde, mit dem sie identifiziert wurde.

In der [ContractTileFormatting.json-Datei](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) definieren die folgenden Abschnitte diese.

### <a name="client"></a>Client

In diesem Abschnitt wird definiert, wie "Client" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag wird verwendet.

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

In diesem Abschnitt wird definiert, wie die "Benachrichtigung" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag wird verwendet.

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

In diesem Abschnitt wird definiert, wie der "Gebührenbetrag" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag wird verwendet.

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

In diesem Abschnitt wird definiert, wie "Klassifizierung" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag wird verwendet.

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

[Schritt 3. Verwenden sie Power Automate, um Ihren Flow zur Verarbeitung Ihrer Verträge zu erstellen](solution-manage-contracts-step3.md)
