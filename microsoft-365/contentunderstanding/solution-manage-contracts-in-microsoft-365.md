---
title: Verwalten von Verträgen mithilfe einer Microsoft 365 Lösung
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie, wie Sie Verträge mithilfe Microsoft 365 Lösung SharePoint Syntex, Microsoft Teams und Power Automate.
ms.openlocfilehash: 806ea9fd048dec198a19fa79f3b60f3f3cb81018
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281184"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>Verwalten von Verträgen mithilfe einer Microsoft 365 Lösung

In diesem Artikel wird beschrieben, wie Sie eine Vertragsverwaltungslösung für Ihre Organisation mithilfe von SharePoint Syntex und Komponenten von Microsoft 365. Es bietet Ihnen ein Framework, mit dem Sie eine Lösung planen und erstellen können, die Ihren individuellen Geschäftsanforderungen entspricht. Auch wenn diese Lösung nicht ihren geschäftlichen Anforderungen insgesamt entspricht, können Teile davon in Ihre Planung übernommen werden, um eine benutzerdefinierte Vertragsverwaltungslösung zu erstellen.

## <a name="identify-the-business-problem"></a>Identifizieren des Geschäftsproblems

Der erste Schritt bei der Planung Ihres Vertragsverwaltungssystems besteht im Verständnis des Problems, das Sie lösen möchten. Für diese Lösung müssen vier wichtige Probleme behoben werden:

- **Identifizieren von Verträgen**. Ihre Organisation arbeitet mit vielen Dokumenten wie Rechnungen, Verträgen, Arbeitsanweisungen und so weiter.  Bei einigen handelt es sich um digitale Objekte, die per E-Mail gesendet werden, andere um Papierressourcen, die über herkömmliche E-Mails gesendet werden. Sie benötigen eine Möglichkeit, alle Kundenverträge aus allen anderen Dokumenten zu identifizieren und sie dann als solche zu klassifizieren.

- **Verfolgen Sie den Verlauf von Vertragsgenehmigungen**. Ihre Organisation benötigt eine zuverlässige Möglichkeit, um festzustellen, ob Verträge genehmigt oder abgelehnt wurden und ob die Zahlung verarbeitet wurde. 

- **Website zum Verwalten von Vertragsgenehmigungen**. Ihre Organisation muss eine Gemeinsame Website einrichten, auf der alle erforderlichen Beteiligten Verträge problemlos überprüfen können. Die Beteiligten sollten bei Bedarf den gesamten Vertrag überprüfen können, aber es ist ihnen am wichtigsten, mehrere Schlüsselfelder aus jedem Vertrag zu sehen (z. B. Kundenname, Po-Nummer und Gesamtkosten). Interessengruppen sollten in der Lage sein, eingehende Verträge problemlos zu genehmigen oder abzulehnen.

- **Route überprüfter Verträge**. Genehmigte und abgelehnte Verträge müssen über einen bestimmten Workflow geroutet werden. Genehmigte Verträge müssen zur Zahlungsverarbeitung an eine Drittanbieteranwendung geroutet werden. Abgelehnte Verträge müssen zur weiteren Überprüfung geroutet werden.

## <a name="overview-of-the-solution"></a>Übersicht über die Lösung

  ![Diagramm der Lösung mit SharePoint Syntex, SharePoint Listen, Teams und Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

Diese Anleitung zur Vertragsverwaltungslösung umfasst vier Komponenten von Microsoft 365:

- **Microsoft SharePoint Syntex**: Erstellen Sie Modelle, um Ihre Vertragsdateien zu identifizieren und zu klassifizieren und anschließend die entsprechenden Daten aus ihnen zu extrahieren.

- **Microsoft SharePoint:** Verwenden Sie die in modernen SharePoint verfügbaren Formatierungen, um Verträge in einem unternehmensfreundlichen Format zu präsentieren.

- **Microsoft Teams**: Verwenden Sie die Funktionalität eines Teams Kanals und der zugehörigen Registerkarten, um es Ihren Beteiligten zu ermöglichen, Verträge zu überprüfen und zu verwalten.

- **Power Automate**: Verwenden Sie Flüsse, um Verträge durch den Genehmigungsprozess und dann an eine Drittanbieteranwendung zur Zahlung zu leiten.

### <a name="how-it-all-works"></a>Funktionsweise

  ![Diagramm der Lösung mit dem Workflow zum Hochladen von Dokumenten, Extrahieren von Daten, Benachrichtigen von Beteiligten und Genehmigen oder Ablehnen des Vertrags.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. Dokumente werden in eine SharePoint hochgeladen. Ein SharePoint Syntex-Dokumentverständnismodell wurde auf die Dokumentbibliothek angewendet. Es überprüft jede Datei, um zu überprüfen, ob eine Datei mit einem "Vertrag"-Inhaltstyp übereinstimmen kann, nach dem sie geschult ist. Wenn eine Übereinstimmung gefunden wird, wird die Datei als "Vertrag" klassifizisiert und der Inhaltstyp für das Dokument aktualisiert.

2. Das Modell zieht auch bestimmte Daten aus jeder Vertragsdatei heraus, an der die Beteiligten interessiert sind, z. B. *den Kunden,* den Auftragnehmer *und* den *Gebührenbetrag.*

    Die folgende Seite ist ein Beispiel für einen Vertrag, für den das Modell geschult ist.

      ![Beispiel für einen Vertrag.](../media/content-understanding/contract.png)

3. In Microsoft Teams sind alle Beteiligten Mitglieder eines sicheren Teams, in dem alle Verträge in der Dokumentbibliothek zur Genehmigung oder Ablehnung angezeigt werden. Durch die Teams werden alle Beteiligten benachrichtigt, wenn neue Verträge überprüft werden müssen.
 
4. Mithilfe Power Automate werden Verträge über den Genehmigungsprozess im Kanal Teams verschoben. Wenn ein Mitglied einen Vertrag genehmigt, wird der Vertragsstatus so geändert, dass er genehmigt wird, alle Mitglieder werden über einen Teams-Beitrag benachrichtigt, und ein Zeilenelement wird erstellt, um zu zeigen, dass der Vertrag auszahlungsbereit ist. Dieser Prozess kann so erweitert werden, dass er zur Zahlung direkt in eine Finanzanwendung eines Drittanbieters geschrieben wird.

5.  Wenn ein Mitglied einen Vertrag ablehnt, wird der Status in abgelehnt geändert, und alle Mitglieder werden über eine Teams benachrichtigt.

## <a name="create-the-solution"></a>Erstellen der Lösung

In den nächsten Abschnitten wird ausführlich erläutert, wie Sie Ihre Vertragsverwaltungslösung konfigurieren. Sie ist in drei Schritte unterteilt:

- [Schritt 1. Verwenden SharePoint Syntex zum Identifizieren von Vertragsdateien und Extrahieren von Daten](solution-manage-contracts-step1.md)
- [Schritt 2. Erstellen Microsoft Teams Vertragsverwaltungskanals mithilfe von Microsoft Teams](solution-manage-contracts-step2.md)
- [Schritt 3. Verwenden Power Automate, um Ihren Fluss zum Verarbeiten Ihrer Verträge zu erstellen](solution-manage-contracts-step3.md)
