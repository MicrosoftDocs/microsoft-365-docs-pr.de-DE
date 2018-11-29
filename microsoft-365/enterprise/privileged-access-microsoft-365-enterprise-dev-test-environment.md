---
title: Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: Verwenden Sie in diesem Test Lab Guide um Systemzugriff-Verwaltung aktivieren Ihrer unternehmensumgebung Microsoft 365 testen.
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867567"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung

Mit den Anweisungen in diesem Artikel konfigurieren Sie Systemzugriff Management zum Erhöhen der Sicherheit in Ihrer testumgebung Microsoft 365 Enterprise.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise

Wenn Sie auf einfache Weise mit den Mindestanforderungen Systemzugriff Management konfigurieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie in einer simulierten Enterprise Systemzugriff Management konfigurieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testen der Systemzugriff Management erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Hier bereitgestellten wird als Option, damit Sie testen können Berechtigungen Zugriff auf Verwaltung und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt. 

## <a name="phase-2-configure-privileged-access-management"></a>Phase 2: Konfigurieren der Verwaltung von Systemzugriff

In dieser Phase konfigurieren eine Gruppe der genehmigenden Personen und Aktivieren von Systemzugriff Management für Ihre Umgebung für Microsoft 365 Enterprise. Zusätzliche Informationen und eine Übersicht über Berechtigungen Management zugreifen, finden Sie unter [Systemzugriff Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

Führen Sie diese Schritte zum Einrichten und Verwenden von Systemzugriff in Office 365-Organisation aus:

- [Schritt 1: Erstellen einer genehmigenden Person Gruppe](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    Bevor Sie mit Berechtigung Access beginnen, bestimmen Sie die Genehmigungsberechtigung für eingehende Anforderungen für den Zugriff auf Aufgaben mit erhöhten Rechten und Berechtigungen besitzen. Jeder Benutzer, der Teil der Gruppe der genehmigenden Personen ist werden Genehmigen von zugriffsanforderungen. Dies ist aktiviert, indem Sie eine e-Mail-aktivierte Sicherheitsgruppe in Office 365 erstellen. Erstellen eine neuen Sicherheitsgruppe mit dem Namen "Privilegierten Zugriff genehmigende Personen" in Ihrer testumgebung und Hinzufügen der "Benutzer 3" in den vorherigen Test Lab Guide Schritten zuvor erstellt haben.

- [Schritt 2: Aktivieren von Systemzugriff](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    Systemzugriff muss explizit aktiviert werden in Office 365 mit der Standardgruppe genehmigende Person und einschließlich einer Reihe von Systemkonten, die Sie aus der Systemzugriff Management Zugriffssteuerung ausgeschlossen werden möchten. Achten Sie darauf, dass in Office 365-Organisation, bevor Sie beginnen Phase 3 dieses Handbuchs Systemzugriff aktiviert.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Phase 3: Stellen Sie sicher, dass die Genehmigung für Aufgaben mit erhöhten Rechten und Berechtigungen erforderlich ist
In dieser Phase überprüfen Sie, dass die Richtlinie Systemzugriff funktioniert und Benutzer genehmigt definierte mit erhöhten Rechten und privilegierte Aufgaben ausgeführt werden.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testen Sie die Möglichkeit zum Ausführen einer Aufgabe in einer Richtlinie Systemzugriff nicht definiert

Erstens Verbinden mit Exchange Management PowerShell mit den Anmeldeinformationen eines Benutzers als ein globaler Administrator in Ihrer testumgebung konfiguriert und versuchen, eine neue Journalregel zu erstellen. Die [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) Aufgabe ist derzeit nicht in einer Richtlinie Systemzugriff für Ihre Organisation definiert.

1. Öffnen Sie auf dem lokalen Computer, und melden Sie sich bei der der Exchange Online Remote PowerShell-Modul bei der **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell-Modul** mithilfe globaler Administrator Konto für Ihre testumgebung.

2. Erstellen Sie eine neue Journalregel für Ihre Organisation in Exchange Management Powershell:

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. Ansicht, dass die neue Journalregel erfolgreich in Exchange Management PowerShell erstellt wurde.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Erstellen einer neuen Systemzugriff Richtlinie für den New-JournalRule-Vorgang

> [!NOTE]
> Wenn Sie die Schritte 1 und 2 aus Phase 2 dieses Handbuchs bereits abgeschlossen haben, werden Sie sicher führen Sie die Schritte zum Erstellen einer genehmigenden Person Gruppe mit dem Namen "Berechtigung Access genehmigende Personen" und die Systemzugriff in Ihrer Umgebung Tests zu aktivieren.

1. Melden Sie sich bei der [Microsoft 365 Admin Center](https://portal.office.com) mit Anmeldeinformationen für Ihre Umgebung für das globale Administratorkonto.

2. Wechseln Sie in der Verwaltungskonsole auf **Einstellungen** > **Sicherheit und Datenschutz** > **Systemzugriff**.

3. Wählen Sie **Verwalten Zugriffsrichtlinien und Anforderungen**.

4. Wählen Sie **Richtlinien konfigurieren** , und wählen Sie **eine Richtlinie hinzufügen**.

5. Wählen Sie aus den Feldern Dropdown-aus, oder geben Sie die folgenden Werte:
    
    **Richtlinientyp**: Aufgabe

    **Richtlinie auf Benutzerebene**: Exchange

    **Richtlinienname**: neue Journalregel

    **Typ der statusgenehmigung**: Manual (engl.)

    **Genehmigungsgruppe**: privilegierten Zugriff genehmigende Personen

6. Wählen Sie **Erstellen** und dann auf **Schließen**. Es kann einige Minuten für die Richtlinie vollständig konfiguriert und aktiviert worden ist. Achten Sie darauf, dass Sie Zeit für die Richtlinie vollständig aktiviert werden soll, bevor Sie die Genehmigung-Anforderung im nächsten Schritt testen.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Testen der Genehmigung-Anforderung für das New-JournalRule Aufgabe in einer Richtlinie Systemzugriff definiert

1. Öffnen Sie auf dem lokalen Computer, und melden Sie sich bei der der Exchange Online Remote PowerShell-Modul bei der **Microsoft Corporation** > mit ein globaler Administrator mit**Microsoft Exchange Online Remote PowerShell-Modul** Konto für den Test Umgebung.

2. Erstellen Sie eine neue Journalregel für Ihre Organisation in Exchange Management Powershell:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Ansicht "Unzureichende Berechtigungen" Fehler in Exchange Management PowerShell:

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Anfordern von Zugriff auf eine neue Journalregel mithilfe des New-JournalRule Tasks erstellen

1. Melden Sie sich bei der [Microsoft 365 Admin Center](https://portal.office.com) über das globale Administratorkonto für Ihre testumgebung.

2. Wechseln Sie in der Verwaltungskonsole auf **Einstellungen** > **Sicherheit und Datenschutz** > **Systemzugriff**.

3. Wählen Sie **Verwalten Zugriffsrichtlinien und Anforderungen**.

4. Wählen Sie **neue Anforderung**. Wählen Sie aus dem Dropdown-Feldern die entsprechenden Werte für Ihre Organisation:

    **Anforderungstyp**: Aufgabe

    **Bereich anfordern**: Exchange

    **Anforderung für**: neue Journalregel

    **Dauer (in Stunden)**: 2

    **Kommentare**: Berechtigung zum Erstellen einer neuen Journalregel anfordern

5. Wählen Sie **Speichern** und dann auf **Schließen**. Ihre Anforderung wird der genehmigenden Person Gruppe per e-Mail gesendet werden.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Genehmigen Sie Anforderung für die Erstellung einer neuen Journalregel Systemzugriff

1. Melden Sie sich bei der [Microsoft 365 Admin Center](https://portal.office.com) mit den Anmeldeinformationen für Benutzer 3 in Ihrer testumgebung (Mitglied der Sicherheitsgruppe "Privilegierten Zugriff genehmigende Personen" in Ihrer testumgebung).

2. Wechseln Sie in der Verwaltungskonsole auf **Einstellungen** > **Sicherheit und Datenschutz** > **Systemzugriff**.

3. Wählen Sie **Verwalten Zugriffsrichtlinien und Anforderungen**.

4. Wählen Sie die ausstehende Anforderung, und wählen Sie **Genehmigen** , an das globale Administratorkonto zum Erstellen einer neuen Journalregel Zugriff zu gewähren. Eine Benachrichtigung e-Mail bestätigt, dass die Genehmigung erteilt wurde, wird an das globale Administratorkonto (dem anfordernden Benutzer) gesendet werden.  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Erstellen eine neue Journalregel mit Systemzugriff für den New-JournalRule Vorgang genehmigt Test

1. Öffnen Sie auf dem lokalen Computer, und melden Sie sich bei der der Exchange Online Remote PowerShell-Modul bei der **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell-Modul** mithilfe globaler Administrator Konto für Ihre testumgebung.

2. Erstellen Sie eine neue Journalregel für Ihre Organisation in Exchange Management Powershell:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Ansicht, dass die neue Journalregel erfolgreich in Exchange Management PowerShell erstellt wurde.

## <a name="next-step"></a>Nächster Schritt

Hier finden Sie zusätzliche [Informationen Protection](m365-enterprise-test-lab-guides.md#information-protection) Features und Funktionen in Ihrer testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)