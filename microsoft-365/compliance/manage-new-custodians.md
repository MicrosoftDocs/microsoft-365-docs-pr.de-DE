---
title: Verwalten von Verwahrern in einem Advanced eDiscovery Fall
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
description: Erfahren Sie, wie Sie Details anzeigen, bearbeiten und die Liste der Verwahrer in einem Advanced eDiscovery bearbeiten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739868"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>Verwalten von Verwahrern in einem Advanced eDiscovery Fall

Die Seite Custodians auf der Registerkarte **Quellen** in einem Advanced eDiscovery enthält eine Liste aller Verwahrer, die dem Fall hinzugefügt wurden. Nachdem Sie einem Fall Custodians hinzugefügt haben, werden Details zu jedem Custodian automatisch von Azure Active Directory erfasst und in der Advanced eDiscovery.

![Verwalten von Verwahrern](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>Anzeigen von Verwahrerdetails

Klicken Sie auf der Registerkarte Verwahrer auf der Liste auf den Custodian, um die Details zu einem **Custodian anzuzeigen.** Eine Flyoutseite wird angezeigt und enthält die folgenden Informationen zum Verwahrer:

- Kontaktinformationen

  - **Anzeigename** – Der Name, der im Adressbuch für den Verwahrer angezeigt wird. Dies ist in der Regel die Kombination aus Vorname, Vorname und Nachname des Verwahrers.
  
   - **Mail/SMTP** – Die primäre SMTP-Adresse für den Verwahrer, z. B. brianj@contoso.onmicrosoft.com. Der Benutzerprinzipalname (User Principal Name, UPN) des Custodians wird ebenfalls aufgeführt.

  - **Titel** – Der Auftragstitel des Verwahrers.

  - **Abteilung** – Der Name der Abteilung, in der der Verwahrer arbeitet.

  - **Manager** – Der Vorgesetzte des Verwalters. Der designierte Manager erhält jegliche Eskalationskommunikation für diesen Verwalter.
  
- Standortinformationen

  - **City** – Die Stadt, in der sich der Custodian befindet.

  - **Bundesland** – Das Bundesland oder die Provinz in der Adresse des Verwahrers.

  - **Land/Region** – Das Land/die Region, in dem sich der Custodian befindet.

  - **Office** – Der Bürostandort am Geschäftssitz des Verwahrers.

- Fallinformationen

  - **Haltestatus** – Gibt an, ob der Custodian in der Warteschleife platziert wurde. 

  - **Kommunikationsstatus**: Gibt an, ob der Custodian eine Haltebenachrichtigung erhalten hat. Wenn der Verwahrer eine Benachrichtigung erhalten hat, wird dieser Wert dieser Eigenschaft **veröffentlicht**. Wenn der Verwahrer keine Benachrichtigung erhalten hat, ist der Status **Un-published**. 

  - **Status** – Der Status des Verwahrers innerhalb des Falls. Der Status **Active** gibt an, dass der Verwahrer Teil des Falls ist. Wenn ein Verwahrer aus einem Fall freigelassen wird, wird der Status in **Freigegeben geändert.** 

- Datenquellen und Indizierungsinformationen

    - **Datenquellen** – Zeigt die Anzahl und den Typ der Datenquellen (Postfächer, Websites und Teams) an, die dem Custodian zugeordnet sind und Teil des Falls sind.

    - **Index updated time** – Gibt die Uhrzeit und das Datum an, an dem der erweiterte Indizierungsauftrag zuletzt ausgelöst wurde. Diese Eigenschaft gibt auch an, wann der erweiterte Indizierungsprozess gerade ausgeführt wird.


## <a name="edit-a-custodian"></a>Bearbeiten eines Verwahrers

Wenn Ihr Fall fortschreitet, stellen Sie möglicherweise fest, dass es zusätzliche Datenquellen gibt, die für einen bestimmten Verwahrer & fall relevant sind. In anderen Szenarien möchten Sie möglicherweise bestimmte Datenquellen entfernen, die überprüft wurden und als nicht relevant eingestuft wurden.

So aktualisieren Sie die Datenquellen, die einem Custodian zugeordnet sind:

1. Wechseln Sie **zu eDiscovery > Advanced eDiscovery,** und öffnen Sie den Fall.
  
2. Klicken Sie auf **die Registerkarte** Quellen.
  
3. Wählen Sie **auf der Seite** Verwahrer in der Liste einen Custodian aus, und klicken Sie auf der Flyoutseite auf Bearbeiten. 

    ![Bearbeiten von Datenquellen](../media/EditCustodianDataSource.PNG)
  
4. Klicken **Sie auf** Die Registerkarte Datenquellen auswählen, um die Einstellungen für das Exchange und OneDrive zu ändern, klicken Sie auf **Datenquellen auswählen**.
  
5. Klicken Sie auf die Registerkarte Zusätzliche **Datenquellen** auswählen, um dem Custodian zugeordnete Teams, SharePoint oder Exchange hinzuzufügen oder zu entfernen. 

    Weitere Informationen zu Datenquellen, die einem Verwahrer zugeordnet sind, finden Sie unter [Hinzufügen von Verwahrern zu einem Fall](add-custodians-to-case.md). 
  
6. Klicken **Sie auf Verwahrer platzieren,** um den Halteraum für den Verwahrer zu aktivieren oder zu deaktivieren.

## <a name="re-index-custodian-data"></a>Erneutes Indizieren von Daten des Verwahrers

In den meisten eDiscovery-Workflows für juristische Untersuchungen wird eine Teilmenge der Daten eines Verwahrers durchsucht, nachdem der Custodian einem Rechtsstreit hinzugefügt wurde. Aufgrund sehr großer Dateigrößen oder möglicher Datenbeschädigungen können einige Elemente in den einem Custodian zugeordneten Datenquellen teilweise indiziert werden. Mithilfe der [erweiterten](indexing-custodian-data.md) Indizierungsfunktion im Advanced eDiscovery können die meisten teilweise indizierten Elemente automatisch behoben werden, indem diese Elemente bei Bedarf erneut indiziert werden.

Wenn einem Fall ein Verwahrer hinzugefügt wird, werden die Daten in den datenquellen, die dem Custodian zugeordnet sind, automatisch neu indiziert (durch den erweiterten Indizierungsprozess). Dies bedeutet, dass Sie die Daten direkt lassen können, anstatt sie herunterzuladen und zu repakieren und dann offline zu durchsuchen). Während des Lebenszyklus eines Rechtsstreits können jedoch neue Datenquellen einem Verwahrer zugeordnet werden. In diesem Fall können Sie die Daten des Verwahrers neu indizieren, indem Sie den erweiterten Indizierungsprozess erneut ausführen, um teilweise indizierte Elemente zu re-indizieren und den Index für die Daten des Custodians zu aktualisieren.

So lösen Sie den Erneutindizierungsprozess aus, um teilweise indizierte Elemente zu adressieren:

1. Wechseln Sie **zu eDiscovery > Advanced eDiscovery,** und öffnen Sie den Fall.

2. Klicken Sie auf **die Registerkarte** Quellen.

3. Wählen Sie **auf der Seite** Verwahrer einen Custodian aus, dessen Daten neu indiziert werden müssen.

4. Klicken Sie auf der Flyoutseite auf **Index aktualisieren.**

   Es wird ein Dialogfeld mit der Meldung angezeigt, dass der Indexauftrag erstellt wurde.

Die erneute Indizierung von Daten von Verwahrer ist ein langer Prozess. Der entsprechende auftrag, der erstellt wird, heißt **Re-indexing custodian data**. Sie können den Fortschritt auf der  Registerkarte **Aufträge** oder auf der Registerkarte Verwahrer nachverfolgen, indem Sie den Status in der Spalte **Auftragsstatus indizieren** überwachen.

Weitere Informationen finden Sie unter:

- [Arbeiten mit Verarbeitungsfehlern](processing-data-for-case.md)

- [Verwalten von Aufträgen](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>Freigabe eines Verwahrers aus einem Fall

Ein Verwahrer wird in Situationen freigelassen, in denen ein Fall geschlossen wird, der Custodian nicht mehr verpflichtet ist, Inhalte für einen Fall zu bewahren, oder wenn der Custodian als nicht mehr relevant für den Fall angesehen wird. 

Wenn Sie einen Verwahrer nach der Veröffentlichung einer Haltebenachrichtigung frei lassen, wird eine Veröffentlichungsbenachrichtigung an den Verwahrer gesendet. Darüber hinaus werden alle halte für Datenquellen, die dem Custodian zugeordnet waren, entfernt. Wenn der Verwahrer in einem stillen Halterecht platziert wurde *und* keine Benachrichtigungen über das gesetzliche Halterecht ausgestellt wurden, wird keine Veröffentlichungsbenachrichtigung gesendet, aber alle halte, die für Datenquellen, die diesem Custodian zugeordnet waren, platziert wurden, werden entfernt.

So lassen Sie einen Verwahrer frei: 

1. Wechseln Sie **zu eDiscovery > Advanced eDiscovery,** und öffnen Sie den Fall.

2. Klicken Sie auf **die Registerkarte** Quellen.

3. Wählen Sie **auf der Seite** Verwahrer den Custodian aus, der aus dem Fall freigelassen wird.

4. Klicken Sie auf der Flyoutseite auf **Custodian los.**

   Es wird eine Warnseite angezeigt, auf der erklärt wird, dass bei einem Halterecht für eine Datenquelle, die dem Custodian zugeordnet ist, der Halteraum entfernt wird und dass ein anderer Halteraum, der einem anderen Advanced eDiscovery-Fall zugeordnet ist, weiterhin gilt. Dies umfasst andere Arten von Erhaltungs- und Aufbewahrungsfeatures (z. B. Microsoft 365 Aufbewahrungsrichtlinie).

5. Klicken **Sie auf Ja,** um zu bestätigen, dass Sie den Custodian los lassen möchten. 

    Der Status für diesen  Benutzer auf der Registerkarte  Verwahrer ist auf **Freigegeben** festgelegt, und der Haltestatus auf der Flyoutseite wird in **False geändert.** 

> [!NOTE]
> Ein Verwahrer kann gleichzeitig an mehreren Rechtsfällen beteiligt sein. Wenn ein Verwahrer aus einem Fall freigelassen wird, werden die Halte- und Benachrichtigungen in anderen Fällen nicht betroffen sein.

## <a name="bulk-edit-custodians"></a>Massenbearbeitung von Verwahrern

Sie können den Masseneditor verwenden, um mehrere Custodians gleichzeitig zu bearbeiten. Wählen Sie dazu auf der Registerkarte Custodians nur zwei oder mehr **Custodians** aus, um den Masseneditor anzeigen zu können, und klicken Sie dann auf eine der Aufgaben.

![Flyoutseite zum Bearbeiten von Einstellungen mehrerer Custodians](../media/AeDBulkEditCustodians.png)
