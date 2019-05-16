---
title: Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Verwenden Sie dieses Test Labor Handbuch, um die privilegierte Zugriffsverwaltung Ihrer Microsoft 365 Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: 306cd8d3cb574fd18a3d184898ead765936bf431
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073015"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung

Mit den Anweisungen in diesem Artikel Konfigurieren Sie die privilegierte Zugriffsverwaltung, um die Sicherheit in Ihrer Microsoft 365 Enterprise-Testumgebung zu verbessern.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie die Verwaltung von privilegierten Zugriffen nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die Verwaltung privilegierter Zugriffsrechte in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen der privilegierten Zugriffsverwaltung erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine AD DS-Gesamtstruktur verbunden ist. Sie wird hier als Option bereitgestellt, damit Sie die privilegierte Zugriffsverwaltung testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 

## <a name="phase-2-configure-privileged-access-management"></a>Phase 2: Konfigurieren der Verwaltung privilegierter Zugriffsrechte

In dieser Phase konfigurieren Sie eine genehmigende Gruppe und aktivieren die privilegierte Zugriffsverwaltung für Ihre Microsoft 365 Enterprise-Testumgebung. Weitere Details und eine Übersicht über die Verwaltung privilegierter Zugriffsrechte finden Sie unter [privilegierte Zugriffsverwaltung in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

Führen Sie die folgenden Schritte aus, um den privilegierten Zugriff in Ihrer Office 365-Organisation einzurichten und zu verwenden:

- [Schritt 1: Erstellen der Gruppe einer genehmigenden Person](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    Bevor Sie mit dem Verwenden von Berechtigungszugriff beginnen, bestimmen Sie, wer über Genehmigungsautorität für eingehende Anforderungen für den Zugriff auf erhöhte und privilegierte Aufgaben verfügt. Jeder Benutzer, der Teil der Gruppe der genehmigenden Personen ist, kann Zugriffsanforderungen genehmigen. Dies wird durch das Erstellen einer e-Mail-aktivierten Sicherheitsgruppe in Office 365 aktiviert. Erstellen Sie in Ihrer Testumgebung eine neue Sicherheitsgruppe mit dem Namen "privilegierte Zugriffs genehmigende Personen", und fügen Sie den zuvor in den Schritten "Test Lab Guide" erstellten Benutzer 3 hinzu.

- [Schritt 2: Aktivieren des privilegierten Zugriffs](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    Privilegierter Zugriff muss explizit in Office 365 mit der standardmäßigen genehmigenden Gruppe aktiviert werden und eine Reihe von Systemkonten enthalten, die Sie aus der Zugriffssteuerung für die privilegierte Zugriffsverwaltung ausschließen möchten. Stellen Sie sicher, dass Sie den privilegierten Zugriff in Ihrer Office 365-Organisation aktivieren, bevor Sie mit Phase 3 dieses Handbuchs beginnen.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Phase 3: überprüfen, ob die Genehmigung für erhöhte und privilegierte Aufgaben erforderlich ist
In dieser Phase stellen Sie sicher, dass die Richtlinie für den privilegierten Zugriff funktioniert, und die Benutzer benötigen die Genehmigung zum Ausführen definierter erhöhter und privilegierter Aufgaben.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testen der Fähigkeit zum Ausführen einer Aufgabe, die nicht in einer privilegierten Zugriffsrichtlinie definiert ist

Stellen Sie zunächst eine Verbindung mit Exchange Management PowerShell mit den Anmeldeinformationen eines in der Testumgebung als globaler Administrator konfigurierten Benutzers her, und versuchen Sie, eine neue Journal Regel zu erstellen. Die [New-JournalRule-](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) Aufgabe ist derzeit nicht in einer privilegierten Zugriffsrichtlinie für Ihre Organisation definiert.

1. Öffnen Sie auf Ihrem lokalen Computer das Exchange Online-Remote-PowerShell-Modul bei **Microsoft** > **Exchange Online-Remote-PowerShell-Modul** unter Verwendung des globalen Administratorkontos für Ihre Testumgebung, und melden Sie sich an.

2. Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. Zeigen Sie an, dass die neue Journal Regel erfolgreich in Exchange Management PowerShell erstellt wurde.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Erstellen einer neuen privilegierten Zugriffsrichtlinie für die Aufgabe "New-JournalRule"

> [!NOTE]
> Wenn Sie die Schritte 1 und 2 aus Phase 2 dieses Handbuchs noch nicht abgeschlossen haben, führen Sie die Schritte zum Erstellen einer genehmigenden Gruppe mit dem Namen "Berechtigungen für den Zugriff Genehmiger" aus, und aktivieren Sie den privilegierten Zugriff in Ihrer Testumgebung.

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen das globale Administratorkonto für Ihre Testumgebung an.

2. Navigieren Sie im Admin Center zu **Einstellungen** > **Security & Privacy** > **privileged Access**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie **Richtlinien konfigurieren** aus, und wählen Sie **Richtlinie hinzufügen**aus.

5. Wählen Sie in den Dropdownfeldern die folgenden Werte aus, oder geben Sie Sie ein:
    
    **Richtlinientyp**: Aufgabe

    **Richtlinienbereich**: Exchange

    **Richtlinienname**: neue Journal Regel

    **** Genehmigungs: manual

    **Genehmigungsgruppe**: Berechtigungen für privilegierten Zugriff

6. Klicken Sie auf **Erstellen** und dann auf **Schließen**. Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist. Stellen Sie sicher, dass die vollständige Aktivierung der Richtlinie vor dem Testen der Genehmigungsanforderung im nächsten Schritt aktiviert ist.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Test Genehmigungsanforderung für den New-JournalRule-Task, der in einer privilegierten Zugriffsrichtlinie definiert ist

1. Öffnen Sie auf Ihrem lokalen Computer das Exchange Online-Remote-PowerShell-Modul bei **Microsoft** > **Exchange Online-Remote-PowerShell-Modul** unter Verwendung des globalen Administratorkontos für Ihren Test, und melden Sie sich an. Umgebung.

2. Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Anzeigen des Fehlers "Insuffient-Berechtigungen" in Exchange Management PowerShell:

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Anfordern des Zugriffs zum Erstellen einer neuen Journal Regel mithilfe der New-JournalRule-Aufgabe

1. Melden Sie sich im [Microsoft 365 Admin Center](https://admin.microsoft.com) unter Verwendung des globalen Administratorkontos für Ihre Testumgebung an.

2. Navigieren Sie im Admin Center zu **Einstellungen** > **Security & Privacy** > **privileged Access**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie **neue Anforderung**aus. Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:

    **Anforderungstyp**: Aufgabe

    **Anforderungsbereich**: Exchange

    **Anforderung für**: neue Journal Regel

    **Dauer (Stunden)**: 2

    **Kommentare**: Anfordern der Berechtigung zum Erstellen einer neuen Journal Regel

5. Klicken Sie auf **Speichern** und dann auf **Schließen**. Ihre Anfrage wird per e-Mail an die Gruppe der genehmigenden Person gesendet.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Genehmigen einer privilegierten Zugriffsanforderung für die Erstellung einer neuen Journal Regel

1. Melden Sie sich im [Microsoft 365 Admin Center](https://admin.microsoft.com) mithilfe der Anmeldeinformationen für Benutzer 3 in Ihrer Testumgebung an (Mitglied der Sicherheitsgruppe "privilegierte Zugriffs-genehmigende Personen" in Ihrer Testumgebung).

2. Navigieren Sie im Admin Center zu **Einstellungen** > **Security & Privacy** > **privileged Access**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie die ausstehende **** Anforderung aus, und wählen Sie genehmigen aus, um Zugriff auf das globale Administratorkonto zu gewähren, um eine neue Journal Regel zu erstellen. Eine Benachrichtigungs-e-Mail, die bestätigt, dass die Genehmigung erteilt wurde, wird an das globale Administratorkonto (der anfordernde Benutzer) gesendet.  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testen des Erstellens einer neuen Journal Regel mit genehmigtem privilegiertem Zugriff für die Aufgabe "New-JournalRule"

1. Öffnen Sie auf Ihrem lokalen Computer das Exchange Online-Remote-PowerShell-Modul bei **Microsoft** > **Exchange Online-Remote-PowerShell-Modul** unter Verwendung des globalen Administratorkontos für Ihre Testumgebung, und melden Sie sich an.

2. Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Zeigen Sie an, dass die neue Journal Regel erfolgreich in Exchange Management PowerShell erstellt wurde.

## <a name="next-step"></a>Nächster Schritt

Erkunden Sie zusätzliche Features und Funktionen zum [Schutz von Informationen](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)