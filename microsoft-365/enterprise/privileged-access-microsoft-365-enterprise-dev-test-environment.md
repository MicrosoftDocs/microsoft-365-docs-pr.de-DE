---
title: Privileged access management for your Microsoft 365 for Enterprise test environment
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
description: Verwenden Sie diese Testumgebungsanleitung, um die Verwaltung des privilegierten Zugriffs Microsoft 365 unternehmensweite Testumgebung zu aktivieren.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126417"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Privileged access management for your Microsoft 365 for Enterprise test environment

*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 als auch für Office 365 Enterprise verwendet werden.*

In diesem Artikel wird beschrieben, wie Sie die Verwaltung des privilegierten Zugriffs konfigurieren, um die Sicherheit in Microsoft 365 Unternehmenstestumgebung zu erhöhen.

Die Konfiguration der zugriffssteuerung umfasst drei Phasen:
- [Phase 1: Build out your Microsoft 365 for Enterprise test environment](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Konfigurieren der Verwaltung des privilegierten Zugriffs](#phase-2-configure-privileged-access-management)
- [Phase 3: Überprüfen, ob die Genehmigung für Aufgaben mit erhöhten rechten Rechten erforderlich ist](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Build out your Microsoft 365 for Enterprise test environment

Wenn Sie die Verwaltung privilegierter Zugriffe auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die Verwaltung des privilegierten Zugriffs in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>Für das Testen der Verwaltung des privilegierten Zugriffs ist keine simulierte Unternehmenstestumgebung erforderlich, die ein simuliertes Intranet, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services-Gesamtstruktur umfasst. Es wird hier als Option bereitgestellt, damit Sie die Verwaltung privilegierter Zugriffe testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.

## <a name="phase-2-configure-privileged-access-management"></a>Phase 2: Konfigurieren der Verwaltung des privilegierten Zugriffs

Konfigurieren Sie in dieser Phase eine Gruppe genehmiger Benutzer, und aktivieren Sie die Verwaltung des privilegierten Zugriffs für Microsoft 365 Unternehmenstestumgebung. Weitere Informationen und eine Übersicht über die Verwaltung privilegierter Zugriffe finden Sie unter [Privileged access management](../compliance/privileged-access-management-overview.md).

Führen Sie die folgenden Schritte aus, um privilegierten Zugriff in Ihrer Organisation einrichten und verwenden zu können.

#### <a name="step-1-create-an-approvers-group"></a>[Schritt 1: Erstellen einer Genehmigergruppe](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Bevor Sie mit der Verwendung des privilegierten Zugriffs beginnen, bestimmen Sie, wer über eine Genehmigungsstelle für eingehende Anforderungen für den Zugriff auf Aufgaben mit erhöhten rechten Rechten verfügen soll. Alle Benutzer, die Teil der Gruppe genehmiger Personen sind, können Zugriffsanforderungen genehmigen. Um privilegierten Zugriff zu verwenden, müssen Sie eine E-Mail-aktivierte Sicherheitsgruppe in Microsoft 365. Nennen Sie in Ihrer Testumgebung die neue Sicherheitsgruppe "Privileged Access Approvers", und fügen Sie den "Benutzer 3" hinzu, der zuvor in vorherigen Testumgebungsanleitungsschritten erstellt wurde.

#### <a name="step-2-enable-privileged-access"></a>[Schritt 2: Aktivieren des privilegierten Zugriffs](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

Der privilegierte Zugriff muss in Microsoft 365 der Standardgruppe der genehmigende Benutzer explizit aktiviert werden, und er muss einen Satz von Systemkonten enthalten, die von der Zugriffssteuerung für die privilegierte Zugriffsverwaltung ausgeschlossen werden sollen. Achten Sie darauf, den privilegierten Zugriff in Ihrer Organisation zu aktivieren, bevor Sie Phase 3 dieses Handbuchs starten.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Phase 3: Überprüfen, ob die Genehmigung für Aufgaben mit erhöhten rechten Rechten erforderlich ist

Überprüfen Sie in dieser Phase, ob die Richtlinie für den privilegierten Zugriff funktioniert und dass Benutzer die Genehmigung benötigen, um definierte Aufgaben mit erhöhten rechten Rechten auszuführen.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testen der Möglichkeit, eine Aufgabe auszuführen, die nicht in einer Richtlinie für den privilegierten Zugriff definiert ist

Stellen Sie zunächst eine Verbindung mit Exchange Management PowerShell mit den Anmeldeinformationen eines Benutzers dar, der in Ihrer Testumgebung als globaler Administrator konfiguriert ist, und versuchen Sie, eine neue Journalregel zu erstellen. Die [New-JournalRule-Aufgabe](/powershell/module/exchange/new-journalrule) ist derzeit nicht in einer Privilegierten Zugriffsrichtlinie für Ihre Organisation definiert.

1. Öffnen Sie auf Ihrem lokalen Computer das Exchange Online Remote PowerShell Module bei **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell Module,** und melden Sie sich mit dem globalen Administratorkonto für Ihre Testumgebung an.

1. Erstellen Exchange In Exchange Management PowerShell eine neue Journalregel für Ihre Organisation:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Zeigen Sie an, dass die neue Journalregel erfolgreich in der Exchange PowerShell erstellt wurde.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Erstellen einer neuen Richtlinie für den privilegierten Zugriff für New-JournalRule Aufgabe

>[!NOTE]
>Wenn Sie die Schritte 1 und 2 aus Phase 2 dieses Handbuchs noch nicht abgeschlossen haben, führen Sie unbedingt die Schritte aus, um die Gruppe der genehmigenden Genehmiger mit dem Namen "Privilege Access Approvers" zu erstellen, um den privilegierten Zugriff in Ihrer Testumgebung zu aktivieren.

1. Melden Sie sich beim [Microsoft 365 Admin Center mit](https://admin.microsoft.com) den Anmeldeinformationen des globalen Administratorkontos für Ihre Testumgebung an.

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Security & Privacy** Privileged  >  **access**.

3. Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**

4. Wählen **Sie Richtlinien konfigurieren** aus, und wählen Sie dann Richtlinie hinzufügen **aus.**

5. Wählen Oder geben Sie in den Dropdownfeldern die folgenden Werte ein:

    **Richtlinientyp**: Task

    **Geltungsbereich der Richtlinie**: Exchange

    **Richtlinienname**: Neue Journalregel

    **Genehmigungstyp**: Manuell

    **Genehmigungsgruppe**: Genehmiger für privilegierten Zugriff

6. Wählen Sie **Erstellen** und dann **Schließen**. Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist. Lassen Sie vor dem Testen der Genehmigungsanforderung im nächsten Schritt unbedingt zeit, bis die Richtlinie vollständig aktiviert ist.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Testgenehmigungsanforderung für die New-JournalRule, die in einer Privilegierten Zugriffsrichtlinie definiert ist

1. Öffnen Sie auf Ihrem lokalen Computer das Exchange Online Remote PowerShell Module bei **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell Module** mithilfe eines globalen Administratorkontos für Ihre Testumgebung.

2. Erstellen Exchange In Exchange Management PowerShell eine neue Journalregel für Ihre Organisation:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Anzeigen des Fehlers "Unzureichende Berechtigungen" in Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Anfordern des Zugriffs zum Erstellen einer neuen Journalregel mithilfe der New-JournalRule Aufgabe

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit dem globalen Administratorkonto für Ihre Testumgebung an.

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Security & Privacy** Privileged  >  **access**.

3. Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**

4. Wählen **Sie Neue Anforderung aus.** Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:

    **Anforderungstyp**: Task

    **Geltungsbereich der Anforderung**: Exchange

    **Anforderung für**: Neue Journalregel

    **Dauer (Stunden):** 2

    **Kommentare**: Anfordern der Berechtigung zum Erstellen einer neuen Journalregel

5. Wählen **Sie Speichern** aus, und wählen Sie dann Schließen **aus.** Ihre Anforderung wird per E-Mail an die Gruppe der Genehmigende gesendet.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Genehmigen der Privilegierten Zugriffsanforderung für die Erstellung einer neuen Journalregel

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit den Anmeldeinformationen für Benutzer 3 in Ihrer Testumgebung an (Mitglied der Sicherheitsgruppe "Genehmiger für privilegierten Zugriff" in Ihrer Testumgebung).

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Security & Privacy** Privileged  >  **access**.

3. Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**

4. Wählen Sie die ausstehende Anforderung aus, und wählen Sie dann **Genehmigen** aus, um Zugriff auf das globale Administratorkonto zu gewähren, um eine neue Journalregel zu erstellen. Das globale Administratorkonto (der anfordernde Benutzer) erhält eine E-Mail-Bestätigung, dass die Genehmigung erteilt wurde.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testen der Erstellung einer neuen Journalregel mit dem für die New-JournalRule genehmigten privilegierten Zugriff

1. Öffnen Sie auf Ihrem lokalen Computer das Exchange Online Remote PowerShell Module bei **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell Module,** und melden Sie sich mit dem globalen Administratorkonto für Ihre Testumgebung an.

1. Erstellen Exchange In Exchange Management PowerShell eine neue Journalregel für Ihre Organisation:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Zeigen Sie an, dass die neue Journalregel erfolgreich in der Exchange PowerShell erstellt wurde.

## <a name="next-step"></a>Nächster Schritt

Erkunden Sie [zusätzliche Features und](m365-enterprise-test-lab-guides.md#information-protection) Funktionen zum Schutz von Informationen in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)
