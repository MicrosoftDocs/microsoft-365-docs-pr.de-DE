---
title: Verwalten von Depotbanken in einem erweiterten eDiscovery-Fall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In diesem Artikel erfahren Sie, wie Sie die Liste der depotverwalter in einem erweiterten eDiscovery-Fall anzeigen, bearbeiten und Massen bearbeiten können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739868"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>Verwalten von Depotbanken in einem erweiterten eDiscovery-Fall

Die Seite depotverwalter auf der Registerkarte **Quellen** in einem erweiterten eDiscovery-Fall enthält eine Liste aller depotverwalter, die dem Fall hinzugefügt wurden. Nachdem Sie einem Fall Verwalter hinzugefügt haben, werden Details zu jeder Depotbank automatisch aus Azure Active Directory gesammelt und in Advanced eDiscovery angezeigt.

![Verwalten von Depotbanken](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>Anzeigen von Depot Details

Um die Details zu einer Depotbank anzuzeigen, klicken Sie in der Liste auf der Registerkarte **depotverwalter** auf die Depotbank. Eine Flyout-Seite wird angezeigt und enthält die folgenden Informationen zur Depotbank:

- Kontaktinformationen

  - **Anzeigename** : der Name, der im Adressbuch für die Depotbank angezeigt wird. Dies ist in der Regel die Kombination aus Vorname, Vornamen und Nachname des Depotbank.
  
   - **Mail/SMTP** – die primäre SMTP-Adresse für die Depotstelle, beispielsweise brianj@contoso.onmicrosoft.com. Der Benutzerprinzipalname (UPN) der Depotbank wird ebenfalls aufgeführt.

  - **Title** – die Position des Verwalters.

  - **Department** -der Name für die Abteilung, in der die Depotbank arbeitet.

  - **Manager** -Verwalter des Depotbank. Der designierte Manager erhält eine Eskalations Kommunikation für diese Depotbank.
  
- Standortinformationen

  - **City** – die Stadt, in der sich die Depotbank befindet.

  - **State** -der Staat oder die Provinz in der Depotbank-Adresse.

  - **Land/Region** – das Land/die Region, in dem sich die Depotbank befindet.

  - **Office** – der Office-Standort im Geschäftssitz der Depotbank.

- Fallinformationen

  - **Haltestatus** -gibt an, ob die Depotstelle in die Warteschleife gestellt wurde. 

  - **Kommunikationsstatus**: gibt an, ob der Depotbank ein Aufbewahrungs Vermerk ausgestellt wurde. Wenn der Depotbank eine Benachrichtigung ausgestellt wurde, wird dieser Wert dieser Eigenschaft **veröffentlicht**. Wenn der Depotbank kein Hinweis erteilt wurde, wird der Status nicht **veröffentlicht**. 

  - **Status** -der Status der Depotbank in der Anfrage. Der Status **aktiv** gibt an, dass die Depotbank Teil des Falles ist. Wenn ein depotverwalter von einem Fall freigegeben wird, wird der Status in " **freigegeben**" geändert. 

- Datenquellen und Indizierungsinformationen

    - **Datenquellen** : zeigt die Anzahl und den Typ der Datenquellen (Postfächer, Websites und Teams) an, die der Depotbank zugeordnet sind und Teil des Falles sind.

    - **Index updated Time** -gibt die Uhrzeit und das Datum für den Zeitpunkt an, zu dem der erweiterte Indizierungs Auftrag zuletzt ausgelöst wurde. Diese Eigenschaft gibt auch an, wann der erweiterte Indizierungsprozess derzeit ausgeführt wird.


## <a name="edit-a-custodian"></a>Bearbeiten einer Depotstelle

Wenn Ihr Fall fortschreitet, stellen Sie möglicherweise fest, dass für eine bestimmte Depotbank & Ihrem Fall möglicherweise zusätzliche Datenquellen relevant sind. In anderen Szenarien möchten Sie möglicherweise bestimmte Datenquellen entfernen, die überprüft und als nicht relevant erachtet wurden.

So aktualisieren Sie die Datenquellen, die einer Depotbank zugeordnet sind:

1. Wechseln Sie zu  **eDiscovery > Advanced eDiscovery** , und öffnen Sie die Anfrage.
  
2. Klicken Sie auf die Registerkarte **Quellen** .
  
3. Wählen Sie auf der Seite **depotverwalter** eine Depotbank aus der Liste aus, und klicken Sie auf der Flyout-Seite auf **Bearbeiten** .

    ![Bearbeiten von Datenquellen](../media/EditCustodianDataSource.PNG)
  
4. Klicken Sie auf **Datenquellen** Registerkarte auswählen, um die Einstellungen für das Exchange-Postfach und das OneDrive-Konto der Depotbank zu ändern, indem Sie auf **Datenquellen auswählen** klicken.
  
5. Klicken Sie auf die Registerkarte **Weitere Datenquellen auswählen** , um Teams, SharePoint-oder Exchange-Postfächer hinzuzufügen oder zu entfernen, die der Depotbank zugeordnet sind. 

    Weitere Informationen zu Datenquellen, die einer Depotbank zugeordnet sind, finden Sie unter [Add depotbanks to a Case](add-custodians-to-case.md). 
  
6. Klicken Sie auf **Depot Platz** Halter, um den Haltebereich für die Depotbank zu aktivieren oder zu deaktivieren.

## <a name="re-index-custodian-data"></a>Erneutes Indizieren von Depotdaten

In den meisten eDiscovery-Workflows für rechtliche Untersuchungen wird eine Teilmenge der Daten eines Depotinhabers durchsucht, nachdem die Depotbank einem Rechtsfall hinzugefügt wurde. Aufgrund sehr großer Dateigrößen oder möglicher Datenbeschädigungen können einige Elemente in den Datenquellen, die einer Depotbank zugeordnet sind, teilweise indiziert werden. Mithilfe der [erweiterten Indizierungs](indexing-custodian-data.md) Funktion in der erweiterten eDiscovery können die meisten teilweise indizierten Elemente automatisch durch Erneutes Indizieren dieser Elemente bei Bedarf behoben werden.

Wenn eine Depotstelle einem Fall hinzugefügt wird, werden die Daten, die sich in den Datenquellen befinden, die der Depotbank zugeordnet sind, automatisch erneut indiziert (durch den erweiterten Indizierungsprozess). Dies bedeutet, dass Sie die Daten in einem Ort lassen können, anstatt Sie herunterladen und korrigieren und dann offline durchsuchen zu müssen. Während des Lebenszyklus eines Rechts Falls können neue Datenquellen jedoch einer Depotbank zugeordnet werden. In diesem Fall können Sie die Daten der Depotbank erneut indizieren, indem Sie den erweiterten Indizierungsprozess erneut durchführen, um teilweise indizierte Elemente zu korrigieren und den Index für die Daten der Depotbank zu aktualisieren.

So lösen Sie den erneuten Indizierungsprozess zum Adressieren von teilweise indizierten Elementen aus:

1. Wechseln Sie zu  **eDiscovery > Advanced eDiscovery** , und öffnen Sie die Anfrage.

2. Klicken Sie auf die Registerkarte **Quellen** .

3. Wählen Sie auf der Seite **depotverwalter** eine Depotbank aus, deren Daten neu indiziert werden müssen.

4. Klicken Sie auf der Seite Flyout auf **Index aktualisieren**.

   Es wird ein Dialogfeld angezeigt, das besagt, dass der Index Auftrag erstellt wurde.

Das erneute Indizieren von Depotdaten ist ein langwieriger Prozess; der entsprechende Auftrag, der erstellt wird, wird als **erneute Indizierung von Depotdaten** bezeichnet. Sie können den Fortschritt auf der Registerkarte **Aufträge** oder auf der Registerkarte **depotverwalter** verfolgen, indem Sie den Status in der Spalte **Indizierungs Auftragsstatus** überwachen.

Weitere Informationen finden Sie unter:

- [Arbeiten mit Verarbeitungsfehlern](processing-data-for-case.md)

- [Verwalten von Aufträgen](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>Freigeben einer Depotbank aus einem Fall

Eine Depotbank wird in Situationen, in denen ein Fall geschlossen wird, freigegeben, die Depotbank ist nicht mehr verpflichtet, Inhalte für einen Fall aufzubewahren oder wenn die Depotbank für den Fall nicht mehr relevant erachtet wird. 

Wenn Sie einen depotverwalter freigeben, nachdem ein Aufbewahrungs Bescheid veröffentlicht wurde, wird eine Veröffentlichungs Benachrichtigung an die Depotbank gesendet. Darüber hinaus werden alle in Datenquellen, die mit der Depotbank verknüpft sind, aufgenommenen Haltestatus entfernt. Wenn die Depotbank in einem *stillen* Speicherplatz genommen wurde und keine Benachrichtigungen über den rechtlichen Aufbewahrungsplatz ausgestellt wurden, wird keine Veröffentlichungs Benachrichtigung gesendet, aber alle auf Datenquellen, die dieser Depotbank zugeordnet sind, bereitgestellten Haltestatus werden entfernt.

So veröffentlichen Sie eine Depotstelle: 

1. Wechseln Sie zu  **eDiscovery > Advanced eDiscovery** , und öffnen Sie die Anfrage.

2. Klicken Sie auf die Registerkarte **Quellen** .

3. Wählen Sie auf der Seite **depotverwalter** die Depotbank aus, die für den Fall freigegeben wird.

4. Klicken Sie auf der Seite Flyout auf **Versionsverwalter**.

   Eine Warn Seite wird angezeigt, in der erläutert wird, dass der Haltebereich entfernt wird, wenn ein Haltebereich in einer Datenquelle gespeichert wird, die mit der Depotbank verknüpft ist, und dass alle anderen Halterungen, die einem anderen erweiterten eDiscovery-Fall zugeordnet sind, weiterhin zutreffen. Dies umfasst andere Arten von Aufbewahrungs-und Aufbewahrungsfunktionen (beispielsweise eine Microsoft 365-Aufbewahrungsrichtlinie).

5. Klicken Sie auf **Ja** , um zu bestätigen, dass Sie die Depotbank freigeben möchten. 

    Der Status für diesen Benutzer auf der Registerkarte " **Verwalter** " wird auf " **freigegeben** " festgelegt, und der **Aufbewahrungs Status** auf der Flyout-Seite wird auf " **false**" geändert. 

> [!NOTE]
> Eine Depotbank kann gleichzeitig in mehreren Rechtsfällen beteiligt sein. Wenn ein depotverwalter von einem Fall freigegeben wird, werden die Aufbewahrungs-und Benachrichtigungen in anderen Bereichen nicht beeinträchtigt.

## <a name="bulk-edit-custodians"></a>Massenbearbeitung von Depot Betreuern

Sie können den Massen-Editor verwenden, um mehrere Verwalter gleichzeitig zu bearbeiten. Wählen Sie dazu einfach mindestens zwei Verwalter auf der Registerkarte **depotverwalter** aus, um den Massen Editor anzuzeigen, und klicken Sie dann auf eine der Aufgaben.

![Flyout-Seite zum Bearbeiten von Einstellungen mehrerer depotverwalter](../media/AeDBulkEditCustodians.png)
