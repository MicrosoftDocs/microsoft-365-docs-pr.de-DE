---
title: Suchen nach und Löschen von E-Mail-Nachrichten in der Organisation
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Verwenden Sie im Microsoft 365 Compliance Center die Funktion zum Suchen und Löschen, um eine E-Mail-Nachricht in allen Postfächern in Ihrer Organisation zu suchen und daraus zu löschen.
ms.openlocfilehash: 95683ed5dc6cce8ff109976ebb0d13215593f046
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770709"
---
# <a name="search-for-and-delete-email-messages"></a>Suchen nach und Löschen von E-Mail-Nachrichten

**Dieser Artikel richtet sich an Administratoren. Versuchen Sie, in Ihrem Postfach Elemente zu finden, die Sie löschen möchten? Dann lesen Sie [Suchen einer Nachricht oder eines Elements mit der Sofortsuche](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**.

Mit dem Inhaltssuche-Feature können Sie nach E-Mail-Nachrichten in allen Postfächern Ihrer Organisation suchen und diese löschen. Auf diese Weise können Sie möglicherweise schädliche E-Mail-Nachrichten oder Nachrichten mit hohem Risiko suchen und löschen. Hierzu zählen zum Beispiel:

- Nachrichten, die gefährliche Anhänge oder Viren enthalten.

- Phishing-Nachrichten

- Nachrichten, die vertrauliche Daten enthalten.

> [!CAUTION]
> Die Such- und Löschfunktion ist ein leistungsfähiges Feature. Sie ermöglicht es jedem mit den erforderlichen Berechtigungen, E-Mail-Nachrichten aus den Postfächern Ihrer Organisation zu löschen.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Zum Erstellen und Ausführen einer Inhaltssuche müssen Sie Mitglied der Rollengruppe für **eDiscovery-Manager** sein, oder Ihnen muss die **Compliancesuche**-Rolle im Security & Compliance Center zugewiesen sein. Um Nachrichten löschen zu können, müssen Sie Mitglied der Rollengruppe **Organisationsverwaltung** sein, oder Ihnen muss die Rolle zum **Suchen und Löschen** im Security & Compliance Center zugewiesen sein. Informationen zum Hinzufügen von Benutzern zu einer Rollengruppe finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center](assign-ediscovery-permissions.md).

  > [!NOTE]
  > Die **Organisationsverwaltung**-Rollengruppe ist sowohl in Exchange Online als auch im Security & Compliance Center vorhanden. Hierbei handelt es sich um separate Rollengruppen, die unterschiedliche Berechtigungen umfassen. Wenn Sie Mitglied der **Organisationsverwaltung** in Exchange Online sind, erhalten Sie nicht die erforderlichen Berechtigungen zum Löschen von E-Mail-Nachrichten. Wenn Ihnen die Rolle **Suchen und Löschen** im Security & Compliance Center nicht zugewiesen wurde (entweder direkt oder über eine Rollengruppe wie **Organisationsverwaltung**), wird in Schritt 3 eine Fehlermeldung angezeigt, wenn Sie das dmdlet **New-ComplianceSearchAction** ausführen, mit der Meldung "Es kann kein Parameter gefunden werden, der dem Parameternamen "Löschen" entspricht“.

- Sie müssen Security & Compliance Center PowerShell verwenden, um Nachrichten zu löschen. Anweisungen zum Herstellen einer Verbindung finden Sie unter [Schritt 1](#step-1-connect-to-security--compliance-center-powershell).

- Aus jedem Postfach können maximal 10 Elemente gleichzeitig entfernt werden. Da das Tool zum Suchen und Entfernen von Nachrichten die Möglichkeit bieten soll, auf Vorfälle zu reagieren, stellt dieser Grenzwert sicher, dass Nachrichten schnell aus Postfächern entfernt werden. Das Feature ist nicht zum Bereinigen von Benutzerpostfächern vorgesehen.

- Die maximale Anzahl von Postfächern in einer Inhaltssuche, die Sie verwenden können, um Elemente zu löschen, indem Sie eine „Suchen und löschen“-Aktion ausführen, beträgt 50.000. Wenn die Suche (die Sie in [Schritt 2](#step-2-create-a-content-search-to-find-the-message-to-delete) erstellen) mehr als 50.000 Postfächer durchsucht, schlägt die Bereinigungsaktion (die Sie in Schritt 3 erstellen) fehl. Zum Durchsuchen von mehr als 50.000 Postfächern in einer einzigen Suche kann es typischerweise kommen, wenn Sie die Suche so konfigurieren, dass alle Postfächer in Ihrer Organisation durchsucht werden. Diese Einschränkung gilt auch dann, wenn weniger als 50.000 Postfächer Elemente enthalten, die der Suchabfrage entsprechen. Im Abschnitt [Weitere Informationen](#more-information) finden Sie eine Anleitung zur Verwendung von Filtern für Suchberechtigungen zum Suchen und Bereinigen von Elementen in mehr als 50.000 Postfächern.

- Das in diesem Artikel beschriebene Verfahren kann nur zum Löschen von Elementen aus Exchange Online-Postfächern und öffentlichen Ordnern verwendet werden. Sie können es nicht verwenden, um Inhalte von SharePoint- oder OneDrive for Business-Websites zu löschen.

- E-Mail-Elemente in einer Überprüfung in einem erweiterten eDiscovery-Fall können nicht mithilfe der in diesem Artikel beschriebenen Verfahren gelöscht werden. Der Grund dafür ist, dass Elemente in einer Überprüfungsgruppe in einem Azure-Speicherort und nicht im Live Dienst gespeichert sind. Dies bedeutet, dass Sie nicht von der Inhaltssuche zurückgegeben werden, die Sie in Schritt 1 erstellt haben. Wenn Sie Elemente in einem Überprüfungssatz löschen möchten, müssen Sie den erweiterten eDiscovery-Fall löschen, der den Überprüfungssatz enthält. Weitere Informationen finden Sie unter [Schließen oder Löschen eines erweiterten eDiscovery-Falls](close-or-delete-case.md).

## <a name="step-1-connect-to-security--compliance-center-powershell"></a>Schritt 1: Herstellen einer Verbindung mit Security & Compliance Center PowerShell

Der erste Schritt besteht darin, eine Verbindung mit der Security & Compliance Center PowerShell für Ihre Organisation herzustellen. Schrittweise Anleitungen erhalten Sie unter [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).

## <a name="step-2-create-a-content-search-to-find-the-message-to-delete"></a>Schritt 2: Erstellen Sie eine Inhaltssuche, um die zu löschende Nachricht zu suchen

Im zweiten Schritt wird eine Inhaltssuche erstellt und ausgeführt, um die Nachricht zu suchen, die Sie aus den Postfächern Ihrer Organisation entfernen möchten. Sie können die Suche mithilfe des Microsoft 365 Compliance Centers oder durch Ausführen der Cmdlets **New-ComplianceSearch** und **Start-ComplianceSearch** in Security & Compliance PowerShell erstellen. Nachrichten, die der Abfrage dieser Suche entsprechen, werden gelöscht, indem Sie den Befehl **New-ComplianceSearchAction -Purge** in [Schritt 3](#step-3-delete-the-message) ausführen. Informationen zum Erstellen einer Inhaltssuche und zum Konfigurieren von Suchabfragen finden Sie unter den folgenden Themen:

- [Inhaltssuche in Office 365](content-search.md)

- [Stichwortabfragen für die Inhaltssuche](keyword-queries-and-search-conditions.md)

- [New-ComplianceSearch](/powershell/module/exchange/New-ComplianceSearch)

- [Start-ComplianceSearch](/powershell/module/exchange/Start-ComplianceSearch)

> [!NOTE]
> Die Speicherorte für Inhalte, die im Rahmen der in diesem Schritt erstellten Inhaltssuche durchsucht werden, dürfen keine SharePoint- oder OneDrive for Business-Websites enthalten. Sie können nur Postfächer und öffentliche Ordner in eine Inhaltssuche einbeziehen, die zum Suchen von E-Mail-Nachrichten verwendet wird. Wenn die Inhaltssuche Websites umfasst, wird in Schritt 3 beim Ausführen des Cmdlets **New-ComplianceSearchAction** eine Fehlermeldung angezeigt.

### <a name="tips-for-finding-messages-to-remove"></a>Tipps zum Suchen nach zu löschenden Nachrichten

Das Ziel der Suchabfrage ist es, die Ergebnisse der Suche auf die Nachricht oder Nachrichten einzuschränken, die Sie entfernen möchten. Hier finden Sie einige Tipps:

- Wenn Sie den genauen Text oder einen Ausdruck kennen, der in der Betreffzeile der Nachricht aufgeführt ist, verwenden Sie die **Betreff**-Eigenschaft in der Suchabfrage.

- Wenn Sie das genaue Datum (oder den Datumsbereich) der Nachricht kennen, nehmen Sie die Eigenschaft **Empfangen** in die Suchabfrage auf.

- Wenn Sie wissen, wer die Nachricht gesendet hat, nehmen Sie die Eigenschaft **Von** in die Suchabfrage auf.

- Zeigen Sie eine Vorschau der Suchergebnisse an, um sicherzustellen, dass die Suche nur die Nachricht(en) zurückgegeben hat, die Sie löschen möchten.

- Verwenden Sie die (im Detailbereich der Suche im Microsoft 365 Compliance Center oder bei Verwendung des Cmdlets [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch) angezeigten) statistischen Daten der Suchschätzung, um die Gesamtanzahl der Ergebnisse zu ermitteln.

Nachfolgend finden Sie zwei Beispiele für Abfragen, um verdächtige E-Mail-Nachrichten zu suchen.

- Diese Abfrage gibt Nachrichten zurück, die von Benutzern zwischen dem 13. April 2016 und dem 14. April 2016 empfangen wurden und die Wörter „action“ und „required“ in der Betreffzeile enthalten.

  ```powershell
  (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
  ```

- Diese Abfrage gibt Nachrichten zurück, die von chatsuwloginsset12345@outlook.com gesendet wurden und die den exakten Ausdruck „Update your account information“ in der Betreffzeile enthalten.

  ```powershell
  (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
  ```

Nachfolgend finden Sie ein Beispiel für die Verwendung einer Abfrage zum Erstellen und Starten einer Suche, indem Sie die Cmdlets **New-ComplianceSearch** und **Start-ComplianceSearch** ausführen, um alle Postfächer in der Organisation zu durchsuchen:

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-3-delete-the-message"></a>Schritt 3: Löschen der Nachricht

Nachdem Sie eine Inhaltssuche zum Zurückgeben der Nachricht, die Sie löschen möchten, erstellt und verfeinert sowie eine Verbindung mit Security & Compliance Center PowerShell hergestellt haben, führen Sie als letzten Schritt das Cmdlet **New-ComplianceSearchAction** aus, um die Nachricht zu löschen. Sie können die Nachricht vorläufig oder endgültig löschen. Eine vorläufig gelöschte Nachricht wird in den Benutzerordner „Wiederherstellbare Elemente“ verschoben und bis zum Ablauf des Aufbewahrungszeitraums für gelöschte Elemente gespeichert. Endgültig gelöschte Nachrichten werden für die dauerhafte Entfernung aus dem Postfach markiert und dauerhaft entfernt, wenn das Postfach das nächste Mal vom Assistenten für verwaltete Ordner abgearbeitet wird. Wenn die Wiederherstellung einzelner Elemente für das Postfach aktiviert ist, werden endgültig gelöschte Elemente nach Ablauf des Aufbewahrungszeitraums für gelöschte Elemente dauerhaft entfernt. Wenn ein Postfach gesperrt wird, bleiben gelöschte Nachrichten erhalten, bis die Aufbewahrungsdauer für das Element abläuft oder bis die Sperre des Postfachs aufgehoben wird.

Im folgenden Beispiel löscht der Befehl die Suchergebnisse, die von einer Inhaltssuche des Begriffs „Phishingnachricht entfernen“ zurückgegeben wurden, vorläufig.

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

Um die Elemente, die von der Inhaltssuche „Phishing-Nachricht entfernen“ zurückgegeben werden, endgültig zu löschen, führen Sie folgenden Befehl aus:

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

Wenn Sie den vorherigen Befehl ausführen, um Nachrichten vorläufig oder endgültig zu löschen, ist die durch den Parameter *SearchName* bestimmte Suche die Inhaltssuche, die Sie in Schritt 1 erstellt haben.

Weitere Informationen finden Sie unter [New-ComplianceSearchAction](/powershell/module/exchange/New-ComplianceSearchAction).

## <a name="more-information"></a>Weitere Informationen

- **Wie wird der Status des Such- und Löschvorgangs abgerufen?**

  Führen Sie die **Get-ComplianceSearchAction** aus, um den Status des Löschvorgangs abzurufen. Das Objekt, das beim Ausführen des Cmdlets **New-ComplianceSearchAction** erstellt wird, wird im folgenden Format benannt: `<name of Content Search>_Purge`.

- **Was geschieht nach dem Löschen einer Nachricht?**

  Eine mit dem Befehl `New-ComplianceSearchAction -Purge -PurgeType HardDelete` gelöschte Nachricht wird in den Ordner „Endgültige Löschvorgänge“ verschoben, und der Benutzer kann nicht darauf zugreifen. Nachdem die Nachricht in den Ordner „Endgültige Löschvorgänge“ verschoben wurde, wird die Nachricht für die Dauer des Aufbewahrungszeitraums für gelöschte Elemente gespeichert, sofern die Wiederherstellung einzelner Elemente für das Postfach aktiviert ist. (In Microsoft 365 ist die Wiederherstellung einzelner Elemente standardmäßig aktiviert, wenn ein neues Postfach erstellt wird.) Nach Ablauf des Aufbewahrungszeitraums für gelöschte Elemente wird die Nachricht für die dauerhafte Löschung gekennzeichnet und aus Microsoft 365 gelöscht, sobald das Postfach das nächste Mal vom Assistenten für verwaltete Ordner abgearbeitet wird.

  Mit dem Befehl `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` werden Nachrichten in den Ordner „Löschvorgänge“ innerhalb des Benutzerordners „Wiederherstellbare Elemente“ verschoben. Sie wird nicht sofort endgültig aus Microsoft 365 gelöscht. Der Benutzer kann Nachrichten im Ordner "Gelöschte Elemente" so lange wiederherstellen, wie der für das Postfach konfigurierte Aufbewahrungszeitraum für gelöschte Elemente dauert. Nach Ablauf dieses Aufbewahrungszeitraums (oder wenn der Benutzer die Nachricht vor dem Ablauf löscht) wird die Nachricht in den Ordner "Löschungen" verschoben, und der Benutzer kann nicht mehr darauf zugreifen. Sobald sich die Nachricht im Ordner „Endgültige Löschvorgänge“ befindet, wird die Nachricht für die Dauer des Aufbewahrungszeitraums für gelöschte Elemente gespeichert, der für das Postfach konfiguriert wurde, sofern die Wiederherstellung einzelner Elemente für das Postfach aktiviert ist. (In Microsoft 365 ist die Wiederherstellung einzelner Elemente standardmäßig aktiviert, wenn ein neues Postfach erstellt wird.) Nach Ablauf des Aufbewahrungszeitraums für gelöschte Elemente wird die Nachricht für die dauerhafte Löschung gekennzeichnet und aus Microsoft 365 gelöscht, sobald das Postfach das nächste Mal vom Assistenten für verwaltete Ordner abgearbeitet wird.

- **Was ist zu tun, wenn Sie eine Nachricht aus mehr als 50.000 Postfächern löschen müssen?**

  Wie bereits erwähnt, können Sie einen Such- und Löschvorgang über höchstens 50.000 Postfächer ausführen (selbst wenn weniger als 50.000 Postfächer Elemente enthalten, die der Suchabfrage entsprechen). Wenn Sie einen Such- und Löschvorgang für mehr als 50.000 Postfächer durchführen müssen, erwägen Sie, temporäre Suchberechtigungsfilter zu erstellen, die die Anzahl der zu durchsuchenden Postfächer auf unter 50.000 verringern. Wenn Ihre Organisation z. B. über Postfächer in verschiedenen Gebieten, Staaten oder Ländern verfügt, können Sie einen Suchberechtigungsfilter für Postfächer auf Grundlage einer dieser Postfacheigenschaften erstellen, um eine Teilmenge der Postfächer in Ihrer Organisation zu durchsuchen. Nachdem Sie den Filter für Suchberechtigungen eingerichet haben, erstellen Sie die Suche (in Schritt 1 beschrieben), und anschließend löschen Sie die Nachricht (in Schritt 3 beschrieben). Dann können Sie den Filter bearbeiten, um Nachrichten in einer anderen Gruppe von Postfächern zu suchen und zu löschen. Weitere Informationen zur Erstellung von Suchberechtigungsfiltern finden Sie unter [Konfigurieren von Berechtigungsfiltern für die Inhaltssuche](permissions-filtering-for-content-search.md).

- **Werden in den Suchergebnissen enthaltene, nicht indizierte Elemente gelöscht?**

  Nein, der Befehl „New-ComplianceSearchAction -Purge“ löscht keine nicht indizierten Elemente.

- **Was geschieht, wenn eine Nachricht aus einem Postfach gelöscht wird, das durch In-Situ-Aufbewahrung oder die Aufbewahrung für juristische Zwecke gesperrt oder einer Microsoft 365-Aufbewahrungsrichtlinie zugewiesen wurde?**

  Nachdem die Nachricht gelöscht und in den Ordner „Endgültig gelöschte Elemente“ verschoben wurde, wird die Nachricht beibehalten, bis die Aufbewahrungsdauer abläuft. Wenn die Aufbewahrungsdauer unbegrenzt ist, werden die Elemente beibehalten, bis die Aufbewahrung entfernt oder die Aufbewahrungsdauer geändert wird.

- **Warum ist der Workflow zum Suchen und Löschen zwischen verschiedenen Security and Compliance Center-Rollengruppen aufgeteilt?**

  Wie bereits weiter oben erwähnt, muss ein Benutzer Mitglied der eDiscovery-Manager-Rollengruppe sein, oder ihm muss die Compliancesuche-Verwaltungsrolle zugewiesen sein, damit er Postfächer durchsuchen kann. Um Nachrichten löschen zu können, muss der Benutzer Mitglied der Rollengruppe „Organisationsverwaltung“ sein, oder ihm muss die Verwaltungsrolle zum Suchen und Löschen zugewiesen sein. Auf diese Weise kann geregelt werden, wer Postfächer in der Organisation durchsuchen und wer Nachrichten löschen kann.
