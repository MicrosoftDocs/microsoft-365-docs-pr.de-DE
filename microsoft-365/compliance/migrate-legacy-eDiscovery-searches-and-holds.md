---
title: Migrieren von Legacy-eDiscovery-suchen und-Archiven zum Microsoft 365 Compliance Center
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: eacbb5577c070ce463ad8e17ba6d0d19a1d8736c
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971345"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a>Migrieren von Legacy-eDiscovery-suchen und-Archiven zum Microsoft 365 Compliance Center

Das Microsoft 365 Compliance Center bietet eine verbesserte Erfahrung für die eDiscovery-Verwendung, einschließlich: höhere Zuverlässigkeit, bessere Leistung und viele Features, die auf eDiscovery-Workflows zugeschnitten sind, einschließlich Fällen zum Organisieren Ihrer Inhalte nach Materie, Überprüfen der Sätze auf Überprüfen Sie Inhalte und Analysen zur Unterstützung von culldaten zur Überprüfung, beispielsweise in einer fast doppelten Gruppierung, in e-Mail-Threading, in der Design Analyse und in der Vorhersage Codierung.

Damit Kunden die neuen und verbesserten Funktionen nutzen können, bietet dieser Artikel grundlegende Anleitungen zur Migration von in-Place-eDiscovery-suchen und-Archiven vom Exchange Admin Center zum Microsoft 365 Compliance Center.

> [!NOTE]
> Da es viele unterschiedliche Szenarien gibt, finden Sie in diesem Artikel Allgemeine Anleitungen für Übergangs suchen und-Aufbewahrungen in einem zentralen eDiscovery-Fall im Microsoft 365 Compliance Center. Die Verwendung von eDiscovery-Fällen ist nicht immer erforderlich, aber Sie fügen eine zusätzliche Sicherheitsebene hinzu, indem Sie Berechtigungen zuweisen, um zu steuern, wer Zugriff auf die eDiscovery-Fälle in Ihrer Organisation hat.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Office 365 Security #a0 Compliance Center sein, um die in diesem Artikel beschriebenen PowerShell-Befehle auszuführen. Außerdem müssen Sie Mitglied der Rollengruppe "Discoveryverwaltung" in der Exchange-Verwaltungskonsole sein.

- Dieser Artikel enthält Anleitungen zum Erstellen eines eDiscovery-Haltestatus. Die Aufbewahrungsrichtlinie wird über einen asynchronen Prozess auf Postfächer angewendet. Wenn Sie einen eDiscovery-Speicher erstellen, müssen Sie sowohl eine CaseHoldPolicy als auch eine CaseHoldRule erstellen, andernfalls wird der Haltebereich nicht erstellt, und es werden keine inhaltsspeicherorte gespeichert.

## <a name="step-1-connect-to-exchange-online-powershell-and-office-365-security--compliance-center-powershell"></a>Schritt 1: Herstellen einer Verbindung mit Exchange Online PowerShell und Office 365 Security #a0 Compliance Center PowerShell

Der erste Schritt besteht darin, eine Verbindung mit Exchange Online PowerShell und Office 365 Security #a0 Compliance Center PowerShell herzustellen. Sie können das folgende Skript kopieren, in ein PowerShell-Fenster einfügen und dann ausführen. Sie werden zur Eingabe von Anmeldeinformationen für die Organisation aufgefordert, mit der Sie eine Verbindung herstellen möchten. 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session -AllowClobber -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

Sie müssen die Befehle in den folgenden Schritten in dieser PowerShell-Sitzung ausführen.

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a>Schritt 2: Abrufen einer Liste von in-Place-eDiscovery-suchen mithilfe von Get-MailboxSearch

Nachdem Sie sich authentifiziert haben, können Sie eine Liste der Compliance-eDiscovery-suchen erhalten, indem Sie das Cmdlet **Get-MailboxSearch** ausführen. Kopieren Sie den folgenden Befehl, und fügen Sie ihn in PowerShell ein, und führen Sie ihn aus. Eine Liste der Suchvorgänge wird mit ihren Namen und dem Status einer in-Place-Aufbewahrungs Liste aufgelistet.

```powershell
Get-MailboxSearch
```

Die Ausgabe des Cmdlets ist wie folgt:

![PowerShell-Beispiel Get-MailboxSearch](media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a>Schritt 3: Abrufen von Informationen zu den Compliance-eDiscovery-suchen und in-Place-Archiven, die Sie migrieren möchten

Wieder verwenden Sie das Cmdlet **Get-MailboxSearch** , dieses Mal jedoch, um die Eigenschaften der Suche abzurufen. Sie können diese Eigenschaften in einer Variablen speichern, um Sie später zu verwenden. Im folgenden Beispiel werden die Ergebnisse des Cmdlets **Get-MailboxSearch** in einer Variablen gespeichert, und anschließend werden die Eigenschaften der Suche angezeigt.

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

Die Ausgabe dieser beiden Befehle ist wie folgt:

![Beispiel für eine PowerShell-Ausgabe mit Get-MailboxSearch für eine individuelle Suche](media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> Die Dauer des in-situ-Speichers in diesem Beispiel ist unbestimmt (*ItemHoldPeriod: Unlimited*). Dies ist typisch für eDiscovery-und rechtliche Ermittlungs Szenarien. Wenn die Aufbewahrungsdauer einen anderen Wert als unbegrenzt hat, liegt der Grund wahrscheinlich daran, dass der Haltebereich zum Beibehalten von Inhalt in einem Aufbewahrungs Szenario verwendet wird. Anstatt die eDiscovery-Cmdlets in Office 365 Security #a0 Compliance Center PowerShell für Aufbewahrungs Szenarien zu verwenden, empfehlen wir die Verwendung von [New-HoldCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-holdcompliancepolicy) und [New-HoldComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-holdcompliancerule) , um Inhalte beizubehalten. Das Ergebnis der Verwendung dieser Cmdlets ähnelt der Verwendung von **New-CaseHoldPolicy** und **New-CaseHoldRule**, aber Sie können einen Aufbewahrungszeitraum und eine Aufbewahrungsaktion angeben, beispielsweise das Löschen von Inhalten nach Ablauf des Aufbewahrungszeitraums. Darüber hinaus ist es für die Verwendung der Aufbewahrungs-Cmdlets nicht erforderlich, die Aufbewahrungszeiträume einem eDiscovery-Fall zuzuordnen.

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a>Schritt 4: Erstellen eines Falls im Microsoft 365 Compliance Center

Um einen eDiscovery-Speicher zu erstellen, müssen Sie einen eDiscovery-Fall erstellen, dem der Haltestatus zugeordnet werden soll. Im folgenden Beispiel wird ein eDiscovery-Fall mithilfe eines Namens Ihrer Wahl erstellt. Die Eigenschaften des neuen Falls werden in einer Variablen gespeichert, um Sie später zu verwenden. Sie können diese Eigenschaften anzeigen, indem Sie `$case | FL` den Befehl ausführen, nachdem Sie die Anfrage erstellt haben.

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```

![Beispiel für das Ausführen des Befehls "New-ComplianceCase"](media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a>Schritt 5: Erstellen des eDiscovery-Haltestatus

Nachdem der Fall erstellt wurde, können Sie den Haltebereich erstellen und ihn der Groß-/Kleinschreibung zuordnen, die Sie im vorherigen Schritt erstellt haben. Es ist wichtig zu beachten, dass Sie sowohl eine Case Hold-Richtlinie als auch eine Case Hold-Regel erstellen müssen. Wenn die Case Hold-Regel nicht erstellt wird, nachdem Sie die Case Hold-Richtlinie erstellt haben, wird der eDiscovery-Speicher nicht erstellt, und alle Inhalte werden nicht gespeichert.

Führen Sie die folgenden Befehle aus, um die eDiscovery-Aufbewahrung neu zu erstellen, die Sie migrieren möchten. In diesen Beispielen werden die Eigenschaften von in-situ-Speicher aus Schritt 3 verwendet, den Sie migrieren möchten.

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
$rule = New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Beispiel für die Verwendung von NewCaseHoldPolicy-und NewCaseHoldRule-Cmdlets](media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a>Schritt 6: Überprüfen des eDiscovery-Haltestatus

Um sicherzustellen, dass beim Erstellen des Haltestatus keine Probleme aufgetreten sind, sollten Sie überprüfen, ob der halte Verteilungsstatus erfolgreich verläuft. Verteilung bedeutet, dass der Haltebereich auf alle im *ExchangeLocation* -Parameter im vorherigen Schritt angegebenen inhaltsspeicherorte angewendet wurde. Dazu können Sie das Cmdlet **Get-CaseHoldPolicy** ausführen. Da die Eigenschaften, die in der *$Policy* Variablen gespeichert wurden, die Sie im vorherigen Schritt erstellt haben, nicht automatisch in der Variablen aktualisiert werden, müssen Sie das Cmdlet erneut ausführen, um zu überprüfen, ob die Verteilung erfolgreich verläuft. Es kann zwischen 5 Minuten und 24 Stunden dauern, bis die Fall Aufbewahrungsrichtlinien erfolgreich verteilt wurden.

Führen Sie den folgenden Befehl aus, um zu überprüfen, ob die eDiscovery-Aufbewahrung erfolgreich verteilt wurde.

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

Der Wert von **Success** für die *Eigenschaften distributionstatus* -Eigenschaft gibt an, dass der Haltebereich erfolgreich an den Inhaltsspeicherorten positioniert wurde. Wenn die Verteilung noch nicht abgeschlossen ist, wird der Wert **Ausstehend** angezeigt.

![PowerShell-Get-CaseHoldPolicy-Beispiel](media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a>Schritt 7: Erstellen der Suche

Der letzte Schritt besteht darin, die Suche neu zu erstellen, die Sie in Schritt 3 identifiziert haben, und Sie der Groß-/Kleinschreibung zuzuordnen. Nachdem Sie die Suche erstellt haben, können Sie Sie mit dem Cmdlet **Start-ComplianceSearch** ausführen oder zu einem späteren Zeitpunkt ausführen.

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell New-ComplianceSearch-Beispiel](media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a>Schritt 8: Überprüfen der Groß-/Kleinschreibung, des Haltestatus und der Suche im Microsoft 365 Compliance Center

Um sicherzustellen, dass alles ordnungsgemäß eingerichtet ist, wechseln Sie zum Microsoft 365 Compliance [https://compliance.microsoft.com](https://compliance.microsoft.com)Center unter, und klicken Sie auf **eDiscovery #a0 Core**.

![Microsoft 365 Compliance Center eDiscovery](media/MigrateLegacyeDiscovery7.png)

Der in Schritt 3 erstellte Fall wird auf der **zentralen eDiscovery** -Seite aufgeführt. Öffnen Sie den Fall, und beachten Sie dann die in Schritt 4 erstellte Aufbewahrungszeit auf der Registerkarte halte **Status** . Sie können auf den Haltebereich klicken, um Details anzuzeigen, einschließlich der Anzahl der Postfächer, auf die der Haltebereich angewendet wird, und des Verteilungsstatus.

![eDiscovery hält im Microsoft 365 Compliance Center](media/MigrateLegacyeDiscovery8.png)

Die Suche, die Sie in Schritt 7 erstellt haben, wird auf der Registerkarte **Suchen** im eDiscovery-Fall aufgeführt.

![eDiscovery-Fall Suche im Microsoft 365 Compliance Center](media/MigrateLegacyeDiscovery9.png)

Wenn Sie eine Compliance-eDiscovery-Suche migrieren, diese aber keinem eDiscovery-Fall zuordnen, wird Sie auf der Seite "Inhaltssuche" im Microsoft 365 Compliance Center aufgeführt.

## <a name="more-information"></a>Weitere Informationen

- Weitere Informationen zum Compliance-eDiscovery #a0 im Exchange Admin Center finden Sie unter:
  
  - [Compliance-eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [In-Situ-Speicher und Beweissicherungsverfahren](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- Weitere Informationen zu den im Artikel verwendeten PowerShell-Cmdlets finden Sie unter:

  - [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)
  
  - [New-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-compliancecase)

  - [New-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdpolicy)
  
  - [New-CaseHoldRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdrule)

  - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)
  
  - [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

  - [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

- Weitere Informationen zum Microsoft 365 Compliance Center finden Sie unter [Overview of the Microsoft 365 Compliance Center](microsoft-365-compliance-center.md).
