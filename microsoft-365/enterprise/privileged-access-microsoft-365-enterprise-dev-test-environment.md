---
title: Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung
f1.keywords:
- NOCSH
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
description: Verwenden Sie diese Test Umgebungs Anleitung, um die Verwaltung privilegierten Zugriffs für Ihre Microsoft 365 Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: ce637b94333f088d25e479e61ad2a98176a2f7c6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085374"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung

*Diese Testumgebungsanleitung kann für Microsoft 365 Enterprise- und Office 365 Enterprise-Testumgebungen verwendet werden.*

Mit den Anweisungen in diesem Artikel Konfigurieren Sie die privilegierte Zugriffsverwaltung, um die Sicherheit in Ihrer Microsoft 365 Enterprise-Testumgebung zu verbessern.

![Testumgebungsanleitungen für die Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
>Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie die privilegierte Zugriffsverwaltung nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die privilegierte Zugriffsverwaltung in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>Für das Testen der privilegierten Zugriffsverwaltung ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine AD DS Gesamtstruktur umfasst. Sie wird hier als Option bereitgestellt, damit Sie die privilegierte Zugriffsverwaltung testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 

## <a name="phase-2-configure-privileged-access-management"></a>Phase 2: Konfigurieren der Verwaltung von privilegierten Zugriffsrechten

In dieser Phase konfigurieren Sie eine Gruppe Genehmigende Personen und aktivieren die Verwaltung privilegierter Zugriffsrechte für Ihre Microsoft 365 Enterprise-Testumgebung. Weitere Details und eine Übersicht über die Verwaltung privilegierten Zugriffs finden Sie unter [privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

Führen Sie die folgenden Schritte zum Einrichten und Verwenden von privilegiertem Zugriff in Ihrer Office 365 Organisation aus:

- [Schritt 1: Erstellen einer Gruppe einer genehmigenden Person](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    Bevor Sie mit dem Verwenden des Zugriffs auf Berechtigungen beginnen, müssen Sie ermitteln, wer über Genehmigungsautorität für eingehende Anforderungen für den Zugriff auf Erweiterte und privilegierte Aufgaben verfügt. Jeder Benutzer, der Teil der Gruppe der Genehmiger ist, kann Zugriffsanforderungen genehmigen. Dies wird durch Erstellen einer e-Mail-aktivierten Sicherheitsgruppe in Office 365 aktiviert. Erstellen Sie eine neue Sicherheitsgruppe mit dem Namen "privileged Access genehmigende Personen" in Ihrer Testumgebung, und fügen Sie den zuvor in den Schritten der Test Umgebungs Anleitung erstellten "Benutzer 3" hinzu.

- [Schritt 2: Aktivieren des privilegierten Zugriffs](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    Der privilegierte Zugriff muss in Office 365 explizit mit der standardmäßigen genehmigenden Gruppe aktiviert sein und eine Reihe von Systemkonten enthalten, die von der Zugriffssteuerung für privilegierte Zugriffsverwaltung ausgeschlossen werden sollen. Achten Sie darauf, den privilegierten Zugriff in Ihrer Office 365 Organisation zu aktivieren, bevor Sie Phase 3 dieses Handbuchs starten.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Phase 3: überprüfen, ob eine Genehmigung für erweiterte und privilegierte Aufgaben erforderlich ist

In dieser Phase stellen Sie sicher, dass die Richtlinie für privilegierten Zugriff funktioniert, und Benutzer benötigen eine Genehmigung zum Ausführen definierter erhöhter und privilegierter Aufgaben.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testen der Fähigkeit zum Ausführen einer Aufgabe, die nicht in einer privilegierten Zugriffsrichtlinie definiert ist

Stellen Sie zunächst eine Verbindung mit der Exchange-Verwaltungs-PowerShell mit den Anmeldeinformationen eines als globaler Administrator konfigurierten Benutzers in Ihrer Testumgebung her, und versuchen Sie, eine neue Journal Regel zu erstellen. Der [New-JournalRule-](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) Vorgang ist derzeit nicht in einer privilegierten Zugriffsrichtlinie für Ihre Organisation definiert.

1. Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation** > **Microsoft Exchange Online Remote-PowerShell-Modul** mit dem globalen Administratorkonto für Ihre Testumgebung an.

2. Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. Zeigt an, dass die neue Journal Regel in der Exchange-Verwaltungs-PowerShell erfolgreich erstellt wurde.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Erstellen einer neuen Richtlinie für den privilegierten Zugriff für den Task "New-JournalRule"

>[!NOTE]
>Wenn Sie die Schritte 1 und 2 aus Phase 2 dieses Handbuchs noch nicht abgeschlossen haben, müssen Sie sicherstellen, dass Sie die Schritte zum Erstellen einer genehmigenden Gruppe mit dem Namen "Berechtigungen für den genehmigenden Personen Zugriff" und zum Aktivieren des privilegierten Zugriffs in Ihrer Testumgebung ausführen.

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen des globalen Administratorkontos für Ihre Testumgebung an.

2. Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit & Zugriff auf Datenschutz** > **privilegiert**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie **Richtlinien konfigurieren** aus, und wählen Sie **Richtlinie hinzufügen**aus.

5. Wählen Sie in den Dropdownfeldern die folgenden Werte aus, oder geben Sie Sie ein:

    **Richtlinientyp**: Aufgabe

    **Richtlinienbereich**: Exchange

    **Richtlinienname**: neue Journal Regel

    **Genehmigungs**: manuell

    **Genehmigungsgruppe**: genehmigende Personen mit privilegiertem Zugriff

6. Klicken Sie auf **Erstellen** und dann auf **Schließen**. Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist. Achten Sie darauf, dass die Richtlinie erst vollständig aktiviert ist, bevor Sie die Genehmigungsanforderung im nächsten Schritt testen.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Testen der Genehmigungsanforderung für den in einer privilegierten Zugriffsrichtlinie definierten New-JournalRule-Vorgang

1. Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation** > **Microsoft Exchange Online-Remote-PowerShell-Modul** mithilfe eines globalen Administratorkontos für Ihre Testumgebung an.

2. Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Anzeigen des Fehlers "unzureichende Berechtigungen" in der Exchange-Verwaltungs-PowerShell:

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Anfordern von Zugriff zum Erstellen einer neuen Journal Regel mit dem Task "New-JournalRule"

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit dem globalen Administratorkonto für Ihre Testumgebung an.

2. Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit & Zugriff auf Datenschutz** > **privilegiert**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie **neue Anforderung**aus. Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:

    **Anforderungstyp**: Aufgabe

    **Anforderungsbereich**: Exchange

    **Anforderung für**: neue Journal Regel

    **Dauer (Stunden)**: 2

    **Kommentare**: Anfordern einer Berechtigung zum Erstellen einer neuen Journal Regel

5. Klicken Sie auf **Speichern** und dann auf **Schließen**. Ihre Anfrage wird per e-Mail an die Gruppe der genehmigenden Person gesendet.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Genehmigen einer privilegierten Zugriffsanforderung für die Erstellung einer neuen Journal Regel

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen für Benutzer 3 in Ihrer Testumgebung an (Mitglied der Sicherheitsgruppe "privilegierte Zugriffs genehmigende Personen" in Ihrer Testumgebung).

2. Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit & Zugriff auf Datenschutz** > **privilegiert**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie die ausstehende Anforderung aus, und wählen Sie **genehmigen** aus, um dem globalen Administratorkonto Zugriff zum Erstellen einer neuen Journal Regel zu gewähren. Eine Benachrichtigungs-e-Mail, die bestätigt, dass die Genehmigung erteilt wurde, wird an das globale Administratorkonto (der anfordernde Benutzer) gesendet.  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testen Erstellen einer neuen Journal Regel mit privilegiertem Zugriff genehmigt für die Aufgabe "New-JournalRule"

1. Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation** > **Microsoft Exchange Online Remote-PowerShell-Modul** mit dem globalen Administratorkonto für Ihre Testumgebung an.

2. Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Zeigt an, dass die neue Journal Regel in der Exchange-Verwaltungs-PowerShell erfolgreich erstellt wurde.

## <a name="next-step"></a>Nächster Schritt

Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
