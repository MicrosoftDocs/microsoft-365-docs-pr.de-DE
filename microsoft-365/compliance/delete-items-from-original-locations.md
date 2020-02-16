---
title: Löschen von Elementen am ursprünglichen Speicherort
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In diesem Artikel wird beschrieben, wie Sie mithilfe des Tools für neue Daten Untersuchungen (Vorschau) im Security & Compliance Center Elemente aus ihren ursprünglichen Speicherorten löschen.
ms.openlocfilehash: 0232a822af0427fcfa669fa1e86558ca54996202
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42075846"
---
# <a name="delete-items-from-their-original-location-preview"></a>Löschen von Elementen aus dem ursprünglichen Speicherort (Vorschau)

Das Feature zum Löschen von Elementen aus dem ursprünglichen Speicherort befindet sich in der Vorschau.

Mithilfe von Daten Untersuchungen können Sie Elemente aus ihren ursprünglichen Speicherorten löschen. Dies bedeutet, dass Sie Elemente aus Exchange-Postfächern, SharePoint-Websites und OneDrive-Konten in Ihrer Organisation löschen können. Da Sie Elemente als Beweismaterial gesammelt haben, haben Sie Kopien der Elemente, die im Beweissatz aufbewahrt werden, zur weiteren Untersuchung oder als Referenz aufzubewahren.

## <a name="before-you-begin"></a>Vorabinformationen

- Um Elemente zu löschen, müssen Sie die **Such-und Lösch** Rolle im Security & Compliance Center zugewiesen haben. Diese Rolle wird standardmäßig der integrierten Data Investigator-Rollengruppe zugewiesen.

- Bei dem Verfahren in diesem Thema wird davon ausgegangen, dass Sie eine mit einer Untersuchung verknüpfte Suche ausgeführt und die Suchergebnisse einem Beweissatz hinzugefügt haben. Nachdem die Suchergebnisse in Evidenz angezeigt wurden, können Sie ein oder mehrere Elemente zum Löschen auswählen. Weitere Informationen finden Sie unter [Suchen nach Daten in einer Untersuchung](search-for-data.md).

- Beachten Sie, dass nur die Elemente in den ursprünglichen Inhaltsspeicherorten (wie Exchange-Postfächer, SharePoint-Websites und OneDrive-Konten) gelöscht werden. Diese Elemente werden nicht aus dem Beweissatz gelöscht. Das liegt daran, dass es sich bei den Elementen in einem Beweis Sätze um Kopien des Originals handelt. Diese Elemente werden kopiert, wenn Sie die Ergebnisse einer Suche zu einem Beweissatz hinzugefügt haben.

## <a name="delete-items"></a>Löschen von Elementen

Führen Sie die folgenden Schritte aus, um Elemente von Ihrem ursprünglichen Speicherort zu löschen:

1. Öffnen Sie im Tool **Daten Untersuchungen** die Datenermittlung, die die Elemente enthält, die Sie löschen möchten, und klicken Sie dann auf die Registerkarte **Beweise** .

2. Wählen Sie die Elemente aus, die Sie löschen möchten. Sie können alle Elemente im Beweissatz auswählen oder nur eine Teilmenge der Elemente auswählen.

   > [!NOTE]
   > Wenn Sie die Anlagen einer e-Mail oder einer an ein Dokument angeschlossenen Datei in SharePoint und OneDrive auswählen, wird das übergeordnete Element ebenfalls ausgewählt und gelöscht, wenn das Element von seinem ursprünglichen Speicherort gelöscht wird. Wenn Sie ein Element mit Anlagen auswählen, wird entsprechend das übergeordnete Element Element und alle Anlagen gelöscht.
 
2. Klicken Sie auf **Aktion** und dann auf **Elemente aus ursprünglichen Speicherorten löschen**.

   ![Klicken Sie auf Aktion und dann auf Elemente aus ursprünglichen Speicherorten löschen.](../media/DataInvestigationsDeleteItems1.png)

3. Überprüfen Sie auf der Seite Flyout die Anzahl der Elemente und zugehörigen untergeordneten Dokumente, die gelöscht werden sollen, und klicken Sie dann auf **Löschen**.

   ![Auf der Flyout-Seite wird die Anzahl der Elemente und der angefügten Dokumente angezeigt, die zum Löschen ausgewählt sind.](../media/DataInvestigationsDeleteItems2.png)

   > [!NOTE]
   > Im vorherigen Screenshot gibt die Anzahl der Elemente die Anzahl der Elemente an, die zum Löschen ausgewählt wurden. Die Anzahl der Dokumente gibt die Gesamtzahl der Elemente einschließlich aller Dateien an, die an ein übergeordnetes Element angefügt sind. Wenn Sie beispielsweise eine e-Mail-Nachricht auswählen und diese Nachricht ein angefügtes Word-Dokument enthält, würde die Anzahl der Elemente und Dokumente, die unter **Ausgewählte Dokumente** angezeigt werden, nur **1 Elemente sein (2 Dokumente)**.

Sie können den Fortschritt des Auftrags zum **Löschen von Elementen von ursprünglichen Speicherorten** auf der Registerkarte **Aufträge** nachverfolgen. Klicken Sie auf den Auftrag, um die Flyout-Seite anzuzeigen.

![Flyout-Seite für den Auftrag Elemente aus ursprünglichen Speicherorten löschen](../media/DataInvestigationsDeleteItems3.png)

Wenn die Elemente im Auftrag gelöscht werden, wird der Auftragsstatus auf " **erfolgreich**" festgelegt. Die Uhrzeit und das Datum des abgeschlossenen Auftrags werden ebenfalls angezeigt.

![Auftrag zum Löschen von Elementen abgeschlossen](../media/DataInvestigationsDeleteItems4.png)

> [!NOTE]
> Sie erhalten möglicherweise den Status **teilweise erfolgreich** für den Auftrag **Elemente aus ursprünglicher Position löschen** . Es gibt eine Reihe von Situationen, die zu diesem Auftragsstatus führen. Weitere Informationen finden Sie im Abschnitt [teilweise erfolgreiche Löschvorgänge](#partially-successful-deletions) in diesem Artikel.

## <a name="what-happens-when-you-delete-items"></a>Was geschieht, wenn Sie Elemente löschen

Wenn Sie jetzt Elemente aus Ihrem ursprünglichen Inhaltsspeicherort löschen, werden die Elemente *vorläufig gelöscht*. Dies bedeutet, dass Elemente an einen speziellen Speicherort verschoben und so lange aufbewahrt werden, bis der Aufbewahrungszeitraum für gelöschte Elemente abläuft und ein Element für das dauerhafte löschen aus Office 365 markiert wird. Das Löschen von Elementen bedeutet, dass Benutzer diese Elemente bis zum Ablauf des Aufbewahrungszeitraums noch wiederherstellen können. Hier finden Sie Beschreibungen darüber, was passiert, wenn Elemente aus Exchange-Postfächern und SharePoint-und OneDrive für Unternehmen-Websites gelöscht werden und welche Aktionen Benutzer ausführen können, nachdem Elemente aus ihren ursprünglichen Speicherorten gelöscht wurden.

- **Postfächer:** Wenn ein Postfachelement vorläufig gelöscht wird, wird es in den Ordner "refundable Items" im Postfach verschoben. Dieses Verhalten ähnelt dem, wenn ein Benutzer ein Element aus dem Ordner "Gelöschte Elemente" löscht oder ein Element dauerhaft durch Drücken von UMSCHALT + ENTF löscht. An diesem Punkt kann der Benutzer das Element bis zum Ablauf des Aufbewahrungszeitraums für gelöschte Elemente wiederherstellen. In Office 365 ist der Aufbewahrungszeitraum für gelöschte Elemente standardmäßig 14 Tage, aber ein Administrator kann den Aufbewahrungszeitraum auf 30 Tage verlängern. Nach Ablauf des Aufbewahrungszeitraums wird das Element in einen verborgenen Ordner verschoben (als *Lösch* Ordner bezeichnet). Das Element wird beim nächsten verarbeiten des Postfachs dauerhaft aus Office 365 entfernt. Postfächer werden einmal alle sieben Tage verarbeitet).

- **SharePoint-und OneDrive-Websites:** Wenn eine Datei oder ein Dokument auf einer Website vorläufig gelöscht wird, wird Sie in den Papierkorb der Website verschoben (auch als *erst stufiger* Papierkorb bezeichnet). Das Element verbleibt 93 Tage im Papierkorb (dies ist der Aufbewahrungszeitraum für Websites in Office 365). Während des Zeitraums von 93 Tagen können gelöschte Elemente weiterhin von einem Websitesammlungsadministrator in SharePoint oder vom Benutzer oder Administrator in OneDrive wiederhergestellt werden. Elemente können auch aus dem Papierkorb der ersten Stufe gelöscht werden. In diesem Fall werden die Elemente in den Papierkorb für die Websitesammlung verschoben, die als *endgültigen* Papierkorb bezeichnet wird. Der Aufbewahrungszeitraum beträgt 93 Tage für Papierkörbe der ersten und der endgültigen Phase. Das bedeutet, dass die Beibehaltung des endgültigen Papierkorbs beginnt, wenn das Element anfänglich gelöscht wird. Das bedeutet, dass die maximale Aufbewahrungszeit für beide Papierkörbe 93 Tage beträgt. Wenn ein Element aus dem endgültigen Papierkorb gelöscht wird (entweder manuell durch einen Administrator oder automatisch, wenn der Aufbewahrungszeitraum abläuft), ist der Zugriff durch einen Administrator nicht mehr möglich.

## <a name="what-happens-if-a-content-location-is-on-hold"></a>Was geschieht, wenn ein Inhaltsspeicherort gespeichert ist

In Office 365 können Postfächer und Websites gespeichert oder einer Aufbewahrungsrichtlinie zugewiesen werden. Dies bedeutet, dass nichts dauerhaft entfernt wird, bis der Aufbewahrungszeitraum für ein Element abläuft oder bis der Haltebereich entfernt wird. Selbst wenn Sie ein Element von seinem ursprünglichen Speicherort löschen, wird das Element möglicherweise nicht dauerhaft aus Office 365 entfernt. Wenn ein Postfach beispielsweise in der Warteschleife gespeichert ist, werden im Ordner "Wiederherstellbare Elemente" endgültig gelöschte Elemente in "purges"-oder "DiscoveryHold"-Unterordner verschoben und bis zum Ablauf der Haltedauer oder Aufbewahrungszeit beibehalten. Bei Websites wird eine Kopie des Elements, das in den Papierkorb verschoben wurde, in die Aufbewahrungs Archiv Bibliothek kopiert, die erstellt wird, wenn eine Aufbewahrungs-oder Aufbewahrungsrichtlinie auf einer Website gespeichert wird.

## <a name="partially-successful-deletions"></a>Teilweise erfolgreiche Löschungen

Nachdem der Auftrag zum **Löschen von Elementen von Original Standorten** ausgeführt wurde, erhalten Sie möglicherweise den Auftragsstatus **teilweise erfolgreich**. Im Allgemeinen gibt dieser Status an, dass der Auftrag erfolgreich ausgeführt wurde, aber nicht alle Elemente wurden vorläufig gelöscht. Im folgenden finden Sie eine Liste der Gründe, die zu teilweise erfolgreichen Löschungen führen:

- Ein Postfachelement befindet sich bereits im Ordner "refundable Items" im Quellpostfach.

- Ein Postfachelement wurde aus dem Ordner "refundable Items" im Quellpostfach gelöscht.

- Ein Dokument befindet sich bereits im ersten Papierkorb einer SharePoint-oder OneDrive-Website.

- Ein Dokument wurde in eine andere SharePoint-Website verschoben, nachdem es dem Beweis Sätze hinzugefügt wurde. In diesem Fall wird das Dokument nicht in den Papierkorb der Website verschoben, in die es verschoben wurde.

- Ein Dokument wurde endgültig in SharePoint oder OneDrive (in den endgültigen Papierkorb verschoben) gelöscht, nachdem es dem Beweissatzes hinzugefügt wurde.
