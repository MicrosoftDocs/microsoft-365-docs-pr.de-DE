---
title: Einrichten der erweiterten Überwachung in Microsoft 365
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
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In diesem Artikel wird beschrieben, wie Sie die erweiterte Überwachung einrichten, damit Sie forensische Untersuchungen durchführen können, wenn Benutzerkonten kompromittiert sind, oder um andere sicherheitsrelevante Vorfälle zu untersuchen.
ms.openlocfilehash: 825dadee5260a263d005eb3a37f280381f9425a2
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339226"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a>Einrichten der erweiterten Überwachung in Microsoft 365

Wenn Ihre Organisation über eine Abonnement- und Endbenutzerlizenzierung verfügt, die die erweiterte Überwachung unterstützt, führen Sie die folgenden Schritte aus, um die zusätzlichen Funktionen in der erweiterten Überwachung einzurichten und zu verwenden.

![Workflow zum Einrichten der Erweiterten Überwachung](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-advanced-audit-for-users"></a>Schritt 1: Einrichten der erweiterten Überwachung für Benutzer

Die Funktionen der Erweiterten Überwachung, wie z.B. die Möglichkeit wichtige Ereignisse, wie z.B. MailItemsAccessed und das Send-Ereignis, zu protokollieren, erfordern eine geeignete E5-Lizenz, die den Benutzern zugewiesen ist. Darüber hinaus muss die Erweiterte Überwachungs-App/ der Serviceplan für diese Benutzer aktiviert sein. Um zu bestätigen, dass die Erweiterte Überwachungs-App an Benutzer zugewiesen ist, führen Sie für jeden Benutzer die folgenden Schritte durch:

1. Navigieren Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/Adminportal) zu **Benutzer** > **Aktive Benutzer**, und wählen Sie einen Benutzer aus.

2. Klicken Sie auf der Benutzereigenschaften-Flyoutseite auf **Lizenzen und Apps**.

3. Überprüfen Sie im Abschnitt **"Lizenzen",** ob dem Benutzer eine E5-Lizenz oder eine entsprechende Add-On-Lizenz zugewiesen ist. Eine Liste der Lizenzen, die die erweiterte Überwachung unterstützen, finden Sie unter ["Erweiterte Überwachung – Lizenzierungsanforderungen".](auditing-solutions-overview.md#advanced-audit-1)

4. Erweitern Sie den Abschnitt **Apps** und bestätigen Sie das Kontrollkästchen **Microsoft 365 – Erweiterte Überwachung** aktiviert ist.

5. Wenn das Kontrollkästchen nicht aktiviert ist, aktivieren Sie es, und klicken Sie dann auf **"Änderungen speichern".**

   Die Protokollierung von Überwachungsdatensätzen für MailItemsAccessed und Send beginnt innerhalb von 24 Stunden. Sie müssen Schritt 3 ausführen, um mit der Protokollierung von zwei weiteren wichtigen Ereignissen der erweiterten Überwachung zu beginnen: SearchQueryInitiatedExchange und SearchQueryInitiatedSharePoint.

Für Organisationen, die Gruppen von Benutzern mithilfe einer gruppenbasierten Lizenzierung Lizenzen zuweisen, müssen Sie die Lizenzzuweisung für Microsoft 365 Advanced Auditing für die Gruppe deaktivieren. Nachdem Sie die Änderungen gespeichert haben, stellen Sie sicher, dass Microsoft 365 Erweiterte Überwachung für die Gruppe deaktiviert ist. Aktivieren Sie dann die Lizenzierungszuordnung für die Gruppe wieder. Lesen Sie [Zuweisen von Lizenzen zu Benutzern mithilfe der Gruppenmitgliedschaft in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign) für Anweisungen zur gruppenbasierten Lizenzierung.

Wenn Sie die Postfachaktionen angepasst haben, die in Benutzerpostfächern oder freigegebenen Postfächern angemeldet sind, werden alle neuen wichtigen Ereignisse, die von Microsoft veröffentlicht werden, nicht automatisch für diese Postfächer überwacht. Weitere Informationen über das Ändern von Postfachaktionen, die für jeden Anmeldetyp überwacht werden, finden Sie unter „Standardmäßig überwachte Postfachaktionen ändern oder wiederherstellen“ in [Verwalten der Postfächern](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).

## <a name="step-2-enable-crucial-events"></a>Schritt 2: Aktivieren wichtiger Ereignisse

Sie müssen zwei wichtige Ereignisse (SearchQueryInitiatedExchange und SearchQueryInitiatedSharePoint) aktivieren, um protokolliert zu werden, wenn Benutzer Suchvorgänge in Exchange Online und SharePoint Online ausführen. Um die Überwachung dieser beiden Ereignisse für Benutzer zu ermöglichen, führen Sie den folgenden Befehl (für jeden Benutzer) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)aus:

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

In einer Multi-Geo-Umgebung müssen Sie den vorherigen Befehl **"Postfach festlegen"** in der Gesamtstruktur ausführen, in der sich das Postfach des Benutzers befindet. Führen Sie den folgenden Befehl aus, um den Postfachspeicherort des Benutzers zu identifizieren: 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

Wenn der Befehl zum Aktivieren der Überwachung von Suchabfragen zuvor in einer Gesamtstruktur ausgeführt wurde, die sich von der Gesamtstruktur unterscheidet, in der sich das Postfach des Benutzers befindet, müssen Sie den SearchQueryInitiated-Wert durch Ausführen aus dem Postfach des Benutzers entfernen `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` und ihn dann dem Postfach des Benutzers in der Gesamtstruktur hinzufügen, in der sich das Postfach des Benutzers befindet.

## <a name="step-3-set-up-audit-retention-policies"></a>Schritt 3: Einrichten von Aufbewahrungsrichtlinien für die Überwachung

Zusätzlich zur Standardrichtlinie, die Exchange-, SharePoint- und Azure AD-Überwachungsprotokolle ein Jahr lang aufbewahrt, können Sie weitere Richtlinien zur Aufbewahrung von Überwachungsprotokollen erstellen, um die Anforderungen der Sicherheits-, IT- und Compliance-Teams Ihres Unternehmens zu erfüllen. Weitere Informationen finden Sie unter [Verwalten der Aufbewahrungsrichtlinien für Überwachungsprotokolle](audit-log-retention-policies.md).

## <a name="step-4-search-for-crucial-events"></a>Schritt 4: Suchen nach wichtigen Ereignissen

Nachdem Sie die erweiterte Überwachung für Ihre Organisation eingerichtet haben, können Sie bei forensischen Untersuchungen nach wichtigen Ereignissen und anderen Aktivitäten suchen. Nach Abschluss von Schritt 1 und Schritt 2 können Sie das Überwachungsprotokoll nach wichtigen Ereignissen und anderen Aktivitäten während forensischer Untersuchungen kompromittierte Konten und anderer Arten von Sicherheits- oder Complianceuntersuchungen durchsuchen. Weitere Informationen zum Durchführen einer forensischen Untersuchung kompromittierte Benutzerkonten mithilfe des wichtigen MailItemsAccessed-Ereignisses finden Sie unter Verwenden der [erweiterten Überwachung, um kompromittierte Konten zu untersuchen.](mailitemsaccessed-forensics-investigations.md)
