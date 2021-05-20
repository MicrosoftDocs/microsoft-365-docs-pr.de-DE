---
title: Einrichten der Basisprüfung in Microsoft 365
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
description: In diesem Artikel wird beschrieben, wie Sie die Basisüberwachung einrichten, damit Sie mit der Suche nach Überwachungsaktivitäten beginnen können, die von Benutzern und Administratoren in Ihrer Organisation ausgeführt werden.
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564825"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a>Einrichten der Basisprüfung in Microsoft 365

Mit Der Basisprüfung in Microsoft 365 können Sie nach Überwachungsdatensätzen für Aktivitäten suchen, die in den verschiedenen Microsoft 365 Diensten von Benutzern und Administratoren ausgeführt werden. Da die Basisüberwachung für die meisten Microsoft 365 und Office 365 Organisationen standardmäßig aktiviert ist, müssen Sie nur einige Dinge tun, bevor Sie und andere In Ihrer Organisation das Überwachungsprotokoll durchsuchen können.

In diesem Artikel werden die folgenden Schritte erläutert, die zum Einrichten der Basisprüfung erforderlich sind.

![Schritte zum Einrichten der Basisprüfung](../media/BasicAuditingWorkflow.png)

Zu diesen Schritten gehören die Sicherstellung der richtigen Organisationsabonnements und Benutzerlizenzen, die zum Generieren und Aufbewahren von Überwachungsdatensätzen erforderlich sind, sowie das Zuweisen von Berechtigungen zu Teammitgliedern Ihrer Sicherheitsvorgänge, IT-, Compliance- und Rechtsteams, damit das Überwachungsprotokoll durchsucht werden kann.

Weitere Informationen finden Sie unter [Grundlegende Saachtung in Microsoft 365](auditing-solutions-overview.md#basic-audit).

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>Schritt 1: Überprüfen der Organisationsabonnements und der Benutzerlizenzierung

Die Lizenzierung für die Basisüberwachung erfordert das entsprechende Organisationsabonnement, das Zugriff auf das Überwachungsprotokollsuchtool und die Benutzerlizenzierung bietet, die zum Protokollieren und Aufbewahren von Überwachungsdatensätzen erforderlich ist.

Wenn eine überwachte Aktivität von einem Benutzer oder Administrator ausgeführt wird, wird ein Überwachungsdatensatz erstellt und im Überwachungsprotokoll Ihrer Organisation gespeichert. In der Basisprüfung werden Überwachungsdatensätze 90 Tage lang im Überwachungsprotokoll aufbewahrt und durchsucht werden können.

Eine Liste der Abonnement- und Lizenzanforderungen für Basic Audit finden [Sie unter Überwachungslösungen in Microsoft 365](auditing-solutions-overview.md#licensing-requirements).

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>Schritt 2: Zuweisen von Berechtigungen zum Durchsuchen des Überwachungsprotokolls

Administratoren und Mitgliedern von Ermittlungsteams muss die Rolle View-Only Überwachungsprotokolle oder Überwachungsprotokolle in Exchange Online zugewiesen werden, um das Überwachungsprotokoll zu durchsuchen. Standardmäßig sind diese Rollen im Exchange Admin Center zugewiesen den Rollengruppen „Complianceverwaltung“ und „Organisationsverwaltung“ auf der Seite **Berechtigungen**. Globale Administratoren in Office 365 und Microsoft 365 werden automatisch als Mitglieder der Rollengruppe Organisationsverwaltung in Exchange Online hinzugefügt. Damit ein Benutzer die Möglichkeit hat, das Überwachungsprotokoll mit minimalen Rechten zu durchsuchen, können Sie in Exchange Online eine benutzerdefinierte Rollengruppe erstellen, ihr die Rollen "Überwachungsprotokolle nur anzeigen" oder "Überwachungsprotokolle" hinzufügen und den Benutzer dann als Mitglied der neuen Rollengruppe hinzufügen. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](/Exchange/permissions-exo/role-groups).

Der folgende Screenshot zeigt die beiden überwachungsbezogenen Rollen, die der Rollengruppe Organisationsverwaltung im Exchange Admin Center zugewiesen sind.

![Überwachungsrollen, die der Rollengruppe in Exchange Online zugewiesen sind](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>Schritt 3: Durchsuchen des Überwachungsprotokolls

Jetzt können Sie das Überwachungsprotokoll im Microsoft 365 Compliance Center durchsuchen.

1. Wechseln Sie zu <https://compliance.microsoft.com> einem Konto, dem die entsprechenden Überwachungsberechtigungen zugewiesen wurden, und melden Sie sich mit einem Konto an, dem die entsprechenden Überwachungsberechtigungen zugewiesen wurden.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Center auf **Alle anzeigen,** und klicken Sie dann auf **Überwachen**.

3. Konfigurieren Sie die Suche auf der Seite **Überwachung** mithilfe der folgenden Bedingungen auf der Registerkarte **Suchen.** 

   ![Konfigurationseinstellungen für die Überwachungsprotokollsuche](../media/AuditLogSearchToolMCCCallouts.png)

   1. **Datum und Zeitbereich**. Wählen Sie einen Datums- und Uhrzeitbereich aus, um die Ereignisse anzuzeigen, die innerhalb dieses Zeitraums aufgetreten sind. Das Datum und die Uhrzeit werden in Ortszeit angezeigt. Die letzten sieben Tage sind standardmäßig ausgewählt.
  
   2. **Aktivitäten**. Wählen Sie die Aktivitäten aus, nach der gesucht werden soll. Verwenden Sie das Suchfeld, um nach Aktivitäten zu suchen, die der Liste hinzugefügt werden sollen. Eine teilaufgesagte Liste der geprüften Aktivitäten finden Sie unter [Geprüfte Aktivitäten](search-the-audit-log-in-security-and-compliance.md#audited-activities). Lassen Sie dieses Feld leer, um Posten für alle überwachten Aktivitäten zurückzugeben.
  
   3. **Benutzer**.  Klicken Sie in dieses Feld, und geben Sie den Namen der Benutzer ein, für die Suchergebnisse angezeigt werden sollen. Die Überwachungsprotokolleinträge für die ausgewählten Aktivitäten, die von den in diesem Feld ausgewählten Benutzern ausgeführt werden, werden in der Ergebnisliste angezeigt. Lassen Sie dieses Feld leer, um die Einträge für alle Benutzer (und Dienstkonten) in Ihrer Organisation zurückzugeben.
  
   4. **Datei, Ordner oder Website**. Geben Sie einen Datei- oder Ordnernamen ein, um nach Aktivitäten zu suchen, die sich auf die Ordnerdatei beziehen, die das angegebene Schlüsselwort enthält. Sie können auch die URL einer Datei oder eines Ordners verwenden. Wenn Sie eine URL einer Datei oder eines Ordners verwenden, stellen Sie sicher, dass der vollständige URL-Pfad eingegeben wurde, oder wenn Sie einen Teil der URL eingeben, keine Sonderzeichen oder Leerzeichen enthalten. Lassen Sie dieses Feld leer, um Einträge für alle Dateien und Ordner in Ihrer Organisation zurückzugeben.

4. Klicken Sie auf **Suchen,** um die Suche auszuführen.

Es wird eine neue Seite angezeigt, auf der die Überwachungsprotokollsuche ausgeführt wird. Wenn die Suche abgeschlossen ist, werden Überwachungsdatensätze auf der Seite angezeigt. Klicken Sie auf einen Datensatz, um eine Flyoutseite mit detaillierten Eigenschaften anzuzeigen.

Ausführlichere Anweisungen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Compliance Center](search-the-audit-log-in-security-and-compliance.md).
