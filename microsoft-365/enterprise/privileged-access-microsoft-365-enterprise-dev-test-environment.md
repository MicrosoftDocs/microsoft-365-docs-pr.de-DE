---
title: Privilegierte Zugriffsverwaltung für Ihre Microsoft 365 für Enterprise-Testumgebung
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
description: Verwenden Sie diese Test Umgebungs Anleitung, um die privilegierte Zugriffsverwaltung für Ihre Microsoft 365 für Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487588"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Privilegierte Zugriffsverwaltung für Ihre Microsoft 365 für Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*

In diesem Artikel wird beschrieben, wie Sie die privilegierte Zugriffsverwaltung konfigurieren, um die Sicherheit in Ihrer Microsoft 365 for Enterprise-Testumgebung zu verbessern.

Das Konfigurieren der privilegierten-Zugriffsverwaltung umfasst drei Phasen:
- [Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Konfigurieren der Verwaltung von privilegierten Zugriffsrechten](#phase-2-configure-privileged-access-management)
- [Phase 3: überprüfen, ob eine Genehmigung für erweiterte und privilegierte Aufgaben erforderlich ist](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen

Wenn Sie die privilegierte Zugriffsverwaltung auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die privilegierte Zugriffsverwaltung in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>Zum Testen der privilegierten Zugriffsverwaltung ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste Gesamtstruktur umfasst. Er wird hier als Option bereitgestellt, damit Sie die privilegierte Zugriffsverwaltung testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.

## <a name="phase-2-configure-privileged-access-management"></a>Phase 2: Konfigurieren der Verwaltung von privilegierten Zugriffsrechten

Konfigurieren Sie in dieser Phase eine Gruppe Genehmigende Personen, und aktivieren Sie die privilegierte Zugriffsverwaltung für Ihre Microsoft 365 for Enterprise-Testumgebung. Weitere Details und eine Übersicht über die Verwaltung privilegierten Zugriffs finden Sie unter [privileged Access Management](../compliance/privileged-access-management-overview.md).

Führen Sie die folgenden Schritte aus, um den privilegierten Zugriff in Ihrer Organisation einzurichten und zu verwenden.

#### <a name="step-1-create-an-approvers-group"></a>[Schritt 1: Erstellen einer Gruppe einer genehmigenden Person](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Bevor Sie mit der Verwendung von privilegiertem Zugriff beginnen, müssen Sie ermitteln, wer über Genehmigungsautorität für eingehende Anforderungen für den Zugriff auf Erweiterte und privilegierte Aufgaben verfügt. Alle Benutzer, die Teil der Gruppe der genehmigenden Personen sind, können Zugriffsanforderungen genehmigen. Zum Verwenden des privilegierten Zugriffs müssen Sie eine e-Mail-aktivierte Sicherheitsgruppe in Microsoft 365 erstellen. Nennen Sie in Ihrer Testumgebung die neue Sicherheitsgruppe "genehmigende Personen mit privilegiertem Zugriff", und fügen Sie den "Benutzer 3" hinzu, der zuvor in den vorherigen Schritten der Test Umgebungs Anleitung erstellt wurde.

#### <a name="step-2-enable-privileged-access"></a>[Schritt 2: Aktivieren des privilegierten Zugriffs](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

Der privilegierte Zugriff muss in Microsoft 365 mit der standardmäßigen genehmigenden Gruppe explizit aktiviert werden, und er muss eine Reihe von Systemkonten enthalten, die von der Zugriffssteuerung für privilegierte Zugriffsverwaltung ausgeschlossen werden sollen. Achten Sie darauf, den privilegierten Zugriff in Ihrer Organisation zu aktivieren, bevor Sie Phase 3 dieses Handbuchs starten.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Phase 3: überprüfen, ob eine Genehmigung für erweiterte und privilegierte Aufgaben erforderlich ist

Stellen Sie in dieser Phase sicher, dass die Richtlinie für privilegierten Zugriff funktioniert und dass Benutzer eine Genehmigung zum Ausführen definierter erhöhter und privilegierter Aufgaben benötigen.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testen der Fähigkeit zum Ausführen einer Aufgabe, die nicht in einer privilegierten Zugriffsrichtlinie definiert ist

Stellen Sie zunächst eine Verbindung mit der Exchange-Verwaltungs-PowerShell mit den Anmeldeinformationen eines als globaler Administrator konfigurierten Benutzers in Ihrer Testumgebung her, und versuchen Sie, eine neue Journal Regel zu erstellen. Der [New-JournalRule-](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) Vorgang ist derzeit nicht in einer privilegierten Zugriffsrichtlinie für Ihre Organisation definiert.

1. Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation**  >  **Microsoft Exchange Online Remote-PowerShell-Modul** mit dem globalen Administratorkonto für Ihre Testumgebung an.

1. Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Zeigt an, dass die neue Journal Regel in der Exchange-Verwaltungs-PowerShell erfolgreich erstellt wurde.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Erstellen einer neuen Richtlinie für den privilegierten Zugriff für die New-JournalRule Aufgabe

>[!NOTE]
>Wenn Sie die Schritte 1 und 2 aus Phase 2 dieses Handbuchs noch nicht abgeschlossen haben, müssen Sie sicherstellen, dass Sie die Schritte zum Erstellen einer genehmigenden Gruppe mit dem Namen "Berechtigungen für den genehmigenden Personen Zugriff" ausführen, um den privilegierten Zugriff in Ihrer Testumgebung zu ermöglichen.

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen des globalen Administratorkontos für Ihre Testumgebung an.

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Sicherheit & Zugriff auf Datenschutz**  >  **privilegiert**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie **Richtlinien konfigurieren**aus, und wählen Sie dann **Richtlinie hinzufügen**aus.

5. Wählen Sie in den Dropdownfeldern die folgenden Werte aus, oder geben Sie Sie ein:

    **Richtlinientyp**: Aufgabe

    **Geltungsbereich der Richtlinie**: Exchange

    **Richtlinienname**: neue Journal Regel

    **Genehmigungs**: manuell

    **Genehmigungsgruppe**: genehmigende Personen mit privilegiertem Zugriff

6. Wählen Sie **Erstellen**aus, und klicken Sie dann auf **Schließen**. Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist. Achten Sie darauf, dass die Richtlinie erst vollständig aktiviert ist, bevor Sie die Genehmigungsanforderung im nächsten Schritt testen.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Testen der Genehmigungsanforderung für die in einer privilegierten Zugriffsrichtlinie definierte New-JournalRule Aufgabe

1. Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation**  >  **Microsoft Exchange Online-Remote-PowerShell-Modul** mithilfe eines globalen Administratorkontos für Ihre Testumgebung an.

2. Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Zeigen Sie den Fehler "unzureichende Berechtigungen" in der Exchange-Verwaltungs-PowerShell an:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Anfordern von Zugriff zum Erstellen einer neuen Journal Regel mithilfe der New-JournalRule Aufgabe

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit dem globalen Administratorkonto für Ihre Testumgebung an.

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Sicherheit & Zugriff auf Datenschutz**  >  **privilegiert**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie **neue Anforderung**aus. Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:

    **Anforderungstyp**: Aufgabe

    **Geltungsbereich der Anforderung**: Exchange

    **Anforderung für**: neue Journal Regel

    **Dauer (Stunden)**: 2

    **Kommentare**: Anfordern einer Berechtigung zum Erstellen einer neuen Journal Regel

5. Wählen Sie **Speichern**aus, und klicken Sie dann auf **Schließen**. Ihre Anfrage wird per e-Mail an die Gruppe der genehmigenden Person gesendet.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Genehmigen einer privilegierten Zugriffsanforderung für die Erstellung einer neuen Journal Regel

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen für Benutzer 3 in Ihrer Testumgebung an (Mitglied der Sicherheitsgruppe "privilegierte Zugriffs genehmigende Personen" in Ihrer Testumgebung).

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Sicherheit & Zugriff auf Datenschutz**  >  **privilegiert**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie die ausstehende Anforderung aus, und wählen Sie dann **genehmigen** aus, um dem globalen Administratorkonto Zugriff zum Erstellen einer neuen Journal Regel zu gewähren. Das globale Administratorkonto (der anfordernde Benutzer) erhält eine e-Mail-Bestätigung, dass die Genehmigung erteilt wurde.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testen Erstellen einer neuen Journal Regel mit privilegiertem Zugriff für die New-JournalRule Aufgabe genehmigt

1. Öffnen Sie auf Ihrem lokalen Computer, und melden Sie sich beim Exchange Online Remote-PowerShell-Modul bei der **Microsoft Corporation**  >  **Microsoft Exchange Online Remote-PowerShell-Modul** mit dem globalen Administratorkonto für Ihre Testumgebung an.

1. Erstellen Sie in der Exchange-Verwaltungs-PowerShell eine neue Journal Regel für Ihre Organisation:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Zeigt an, dass die neue Journal Regel in der Exchange-Verwaltungs-PowerShell erfolgreich erstellt wurde.

## <a name="next-step"></a>Nächster Schritt

Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
