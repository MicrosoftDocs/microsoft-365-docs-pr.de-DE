---
title: Verwalten von Verträgen mithilfe einer Microsoft 365-Lösung
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Erfahren Sie, wie Sie Verträge mithilfe einer Microsoft 365 Lösung von SharePoint Syntex, SharePoint Lists, Microsoft Teams und Power Automate verwalten.
ms.openlocfilehash: d12ccd2d4bc777b05489556f0d96ce9de80954a8
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770817"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>Verwalten von Verträgen mithilfe einer Microsoft 365-Lösung

In diesem Artikel wird beschrieben, wie Sie mithilfe von SharePoint Syntex und Komponenten von Microsoft 365 eine Vertragsverwaltungslösung für Ihre Organisation erstellen. Es bietet Ihnen ein Framework, das Sie bei der Planung und Erstellung einer Lösung unterstützt, die Ihren individuellen Geschäftlichen Anforderungen entspricht. Auch wenn diese Lösung nicht ihren geschäftlichen Anforderungen als Ganzes entspricht, können Teile davon in Ihre Planung übernommen werden, um eine benutzerdefinierte Vertragsverwaltungslösung zu erstellen.

*Dieser Inhaltssatz dokumentiert eine Microsoft 365 Lösung, die von Einem Mol über das Team für moderne Arbeitslösungsstrategie von Microsoft entwickelt wurde.*

## <a name="identify-the-business-problem"></a>Identifizieren des Geschäftsproblems

Der erste Schritt bei der Planung Ihres Vertragsverwaltungssystems besteht darin, das Problem zu verstehen, das Sie lösen möchten. Für diese Lösung müssen vier wichtige Probleme behoben werden:

- **Identifizieren von Verträgen.** Ihre Organisation arbeitet mit vielen Dokumenten, z. B. Rechnungen, Verträgen, Arbeitsanweisungen usw.  Einige sind digitale Objekte, die per E-Mail gesendet werden, und einige sind Papierobjekte, die über herkömmliche E-Mails gesendet werden. Sie benötigen eine Möglichkeit, alle Kundenverträge aus allen anderen Dokumenten zu identifizieren und diese dann als solche zu klassifizieren.

- **Nachverfolgen des Verlaufs von Vertragsgenehmigungen.** Ihre Organisation benötigt eine zuverlässige Möglichkeit, um zu ermitteln, ob Verträge genehmigt oder abgelehnt wurden und ob die Zahlung verarbeitet wurde. 

- **Website zum Verwalten von Vertragsgenehmigungen.** Ihre Organisation muss eine Website für die Zusammenarbeit einrichten, auf der alle erforderlichen Beteiligten Verträge einfach überprüfen können. Projektbeteiligten sollten bei Bedarf den gesamten Vertrag überprüfen können, aber hauptsächlich möchten sie mehrere Schlüsselfelder aus jedem Vertrag sehen (z. B. Kundenname, Auftragsnummer und Gesamtkosten). Projektbeteiligten sollten in der Lage sein, eingehende Verträge einfach zu genehmigen oder abzulehnen.

- **Weitergeleitet überprüfte Verträge.** Genehmigte und abgelehnte Verträge müssen über einen bestimmten Workflow weitergeleitet werden. Genehmigte Verträge müssen zur Zahlungsverarbeitung an eine Drittanbieteranwendung weitergeleitet werden. Abgelehnte Verträge müssen zur weiteren Überprüfung weitergeleitet werden.

## <a name="overview-of-the-solution"></a>Übersicht über die Lösung

  ![Diagramm der Lösung mit SharePoint Syntex, SharePoint Listen, Teams und Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

Dieser Leitfaden zur Vertragsverwaltungslösung umfasst vier Komponenten von Microsoft 365:

- **Microsoft SharePoint Syntex:** Erstellen Sie Modelle, um Ihre Vertragsdateien zu identifizieren und zu klassifizieren und dann die entsprechenden Daten daraus zu extrahieren.

- **Microsoft SharePoint-Listen:** Verwenden Sie die in modernen SharePoint-Listen verfügbaren Formatierungen, um Verträge in einem unternehmensfreundlichen Format darzustellen.

- **Microsoft Teams:** Verwenden Sie die Funktionalität eines Teams Kanals und zugehöriger Registerkarten, um Ihren Projektbeteiligten die Überprüfung und Verwaltung von Verträgen zu ermöglichen.

- **Power Automate:** Verwenden Sie Flüsse, um Verträge durch den Genehmigungsprozess und dann zu einer Drittanbieteranwendung für die Zahlung zu führen.

### <a name="how-it-all-works"></a>Funktionsweise

  ![Diagramm der Lösung mit dem Workflow zum Hochladen von Dokumenten, Extrahieren von Daten, Benachrichtigen der Projektbeteiligten und Genehmigen oder Ablehnen des Vertrags.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. Dokumente werden in eine SharePoint Dokumentbibliothek hochgeladen. Ein SharePoint Syntex-Dokumentverständnismodell wurde auf die Dokumentbibliothek angewendet. Es überprüft jede Datei, um festzustellen, ob sie einem "Vertrags"-Inhaltstyp entspricht, nach dem gesucht wird. Wenn eine Übereinstimmung gefunden wird, klassifiziert sie die Datei als "Vertrag" und aktualisiert den Inhaltstyp für das Dokument.

2. Das Modell ruft auch bestimmte Daten aus jeder Vertragsdatei ab, die projektbezogene Interessenvertreter sehen möchten, z. B. *den Betrag für Client,* *Auftragnehmer* und *Gebühren.*

    Die folgende Seite ist ein Beispiel für einen Vertrag, für den das Modell zur Identifizierung geschult ist.

      ![Beispiel für einen Vertrag.](../media/content-understanding/contract.png)

3. In Microsoft Teams sind alle Beteiligten Mitglieder eines sicheren Teams Kanals, in dem alle Verträge in der Dokumentbibliothek zur Genehmigung oder Ablehnung sichtbar sind. Durch die Verwendung Teams Funktionalität werden alle Beteiligten benachrichtigt, wenn neue Verträge überprüft werden müssen.
 
4. Mithilfe von Power Automate werden Verträge über den Genehmigungsprozess im Teams Kanal verschoben. Wenn ein Mitglied einen Vertrag genehmigt, wird der Vertragsstatus geändert, sodass er genehmigt wird, alle Mitglieder über einen Teams Beitrag benachrichtigt werden und ein Positionselement erstellt wird, um anzuzeigen, dass der Vertrag zur Auszahlung bereit ist. Dieser Prozess kann erweitert werden, um direkt auf eine Finanzanwendung eines Drittanbieters zur Zahlung zu schreiben.

5.  Wenn ein Mitglied einen Vertrag ablehnt, wird der Status in "Abgelehnt" geändert, und alle Mitglieder werden über einen Teams Beitrag benachrichtigt.

6. Das Endergebnis dieser Lösung ist ein automatisierter Geschäftsprozess für Ihre Organisation. Mitarbeiter können die benutzerdefinierte Kachelansicht ganz einfach in Teams verwenden, um den Genehmigungsworkflow Ihrer Dokumente zu initiieren und zu überwachen. 

     ![Registerkarte "Verträge".](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Diese Lösung basiert auf den folgenden Funktionen, die alle als Teil einer Microsoft 365 Enterprise (E1, E3, E5, F3) oder Business-Lizenz (Basic, Standard oder Premium) verfügbar sind:

-   Microsoft SharePoint Syntex
-   Microsoft Teams
-   Power Automate

## <a name="create-the-solution"></a>Erstellen der Lösung

In den nächsten Abschnitten wird ausführlich erläutert, wie Sie Ihre Vertragsverwaltungslösung konfigurieren. Es ist in drei Schritte unterteilt:

- [Schritt 1. Verwenden von SharePoint Syntex zum Identifizieren von Vertragsdateien und Extrahieren von Daten](solution-manage-contracts-step1.md)
- [Schritt 2. Verwenden Microsoft Teams zum Erstellen Ihres Vertragsverwaltungskanals](solution-manage-contracts-step2.md)
- [Schritt 3. Verwenden sie Power Automate, um Ihren Flow zur Verarbeitung Ihrer Verträge zu erstellen.](solution-manage-contracts-step3.md)
