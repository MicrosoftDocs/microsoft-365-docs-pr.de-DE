---
title: Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Erfahren Sie, wie Sie ein privates Postfach in ein freigegebenes Postfach konvertieren, auf das von mehreren Personen anstelle von nur einer Person zugegriffen werden kann. '
ms.openlocfilehash: caf3935b1ffb36989b2884c6811111531a061098
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393967"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach

Wenn Sie das Postfach eines Benutzers in ein freigegebenes Postfach konvertieren, werden alle vorhandenen E-Mails und Kalender beibehalten. Sie befinden sich nun nur in einem freigegebenen Postfach, auf das mehrere Personen (nicht nur eine Person) zugreifen können. Zu einem späteren Zeitpunkt können Sie ein freigegebenes Postfach zurück in ein (privates) Benutzerpostfach konvertieren.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

**Hier sind einige wirklich wichtige Dinge, die Sie wissen müssen:**

- Das Benutzerpostfach, das Sie konvertieren, benötigt eine Zugewiesene Lizenz, bevor Sie es in ein freigegebenes Postfach konvertieren. Andernfalls wird die Option zum Konvertieren des Postfachs nicht angezeigt. Wenn Sie die Lizenz entfernt haben, fügen Sie sie erneut hinzu, damit Sie das Postfach konvertieren können. Nach dem Konvertieren des Postfachs in ein freigegebenes Postfach können Sie die Lizenz aus dem Benutzerkonto entfernen.

- Freigegebene Postfächer können bis zu 50 GB Daten enthalten, ohne dass ihnen eine Lizenz zugewiesen ist. Um mehr Daten als diese zu speichern, benötigen Sie eine Zugewiesene Lizenz. Möglicherweise müssen Sie eine Reihe großer E-Mails (z. B. solche mit Anlagen) aus dem freigegebenen Postfach löschen, um es zu verkleinern, damit Sie die Lizenz entfernen können.

- Löschen Sie das alte Konto des Benutzers nicht. Es ist für das Verankern des freigegebenen Postfachs erforderlich. Wenn Sie das Benutzerkonto bereits gelöscht haben, lesen Sie [Konvertieren des Postfachs eines gelöschten Benutzers](#convert-the-mailbox-of-a-deleted-user).

- Die Regeln sind intakt, nachdem das Postfach in ein freigegebenes Postfach konvertiert wurde.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Verwenden des Exchange Admin Centers zum Konvertieren eines Postfachs
 
1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.

2. Wählen Sie **"Empfängerpostfächer"** \> **aus.**

3. Wählen Sie das Benutzerpostfach aus. Wählen Sie unter **"In freigegebenes Postfach konvertieren"** die Option **"Konvertieren" aus.**

4. Wenn das Postfach kleiner als 50 GB ist, können Sie die [Lizenz vom Benutzer](../manage/remove-licenses-from-users.md)entfernen und die Zahlung beenden. Löschen Sie das Konto des Benutzers nicht. Das freigegebene Postfach benötigt dieses als Anker. Wenn Sie das Postfach eines Mitarbeiters konvertieren, der Ihre Organisation verlässt, sollten Sie zusätzliche Schritte ausführen, um sicherzustellen, dass er sich nicht mehr anmelden kann. Weitere Informationen finden Sie unter [Entfernen eines ehemaligen Mitarbeiters aus Microsoft 365.](../add-users/remove-former-employee.md)
    
> [!NOTE]
> Es ist nicht erforderlich, das Kennwort des Benutzers während der Postfachkonvertierung zurückzusetzen. Wenn das Kennwort jedoch nicht zurückgesetzt wird, funktionieren der ursprüngliche Benutzername und das Kennwort nach Abschluss der Postfachkonvertierung **weiterhin.**

Alle anderen Informationen zu freigegebenen Postfächern finden Sie unter "Informationen zu [freigegebenen Postfächern"](about-shared-mailboxes.md) und ["Erstellen eines freigegebenen](create-a-shared-mailbox.md)Postfachs".

> [!NOTE]
> Freigegebene Postfächer erfordern keine separate Lizenz. Wenn Sie jedoch In-Place Archiv aktivieren oder einem freigegebenen Postfach eine In-Place Aufbewahrung oder eine Beweissicherung für juristische Zwecke zuweisen möchten, müssen Sie dem Postfach einen Exchange Online Plan 1 mit Exchange Online-Archivierung- oder Exchange Online Plan 2-Lizenz zuweisen.

## <a name="convert-the-mailbox-of-a-deleted-user"></a>Konvertieren des Postfachs eines gelöschten Benutzers

Angenommen, Sie haben ein Benutzerkonto gelöscht und möchten nun das alte Postfach in ein freigegebenes Postfach konvertieren. Nachstehend wird beschrieben, wie Sie vorgehen müssen:

1. [Stellen Sie das Konto des Benutzers wieder her.](../add-users/restore-user.md)

2. Stellen Sie sicher, dass ihr eine Microsoft 365-Lizenz zugewiesen ist.

3. Setzen Sie das Kennwort des Benutzers zurück.
    
4. Warten Sie 20 bis 30 Minuten, bis das Postfach erneut erstellt wurde.
    
5. Befolgen Sie nun die Anweisungen auf dieser Seite, um das Postfach in ein freigegebenes Postfach zu konvertieren.
    
6. Danach können Sie die Lizenz aus dem Postfach des Benutzers entfernen. Löschen Sie das alte Postfach des Benutzers nicht. Das freigegebene Postfach benötigt dieses als Anker.
    
7. Fügen Sie dem freigegebenen Postfach Mitglieder hinzu.

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Konvertieren eines freigegebenen Postfachs zurück in das (private) Postfach eines Benutzers

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.
   
2. Wählen  Sie \> **"Empfänger freigegeben" aus.**

3. Wählen Sie das freigegebene Postfach aus. Wählen Sie unter **"In reguläres Postfach konvertieren"** die Option **"Konvertieren"** aus.

4. Wechseln Sie zurück zum Admin Center. Wählen Sie unter **Benutzer** das Benutzerkonto aus, das dem alten freigegebenen Postfach zugeordnet ist. Weisen Sie dem Konto eine Lizenz zu, und setzen Sie das Kennwort zurück.

   Es dauert einige Minuten, bis das Postfach eingerichtet wurde. Anschließend kann die Person, die für die Verwendung dieses Kontos vorgesehen ist, das Postfach nutzen. Beim Anmelden werden die E-Mail- und Kalenderelemente angezeigt, die sich zuvor im freigegebenen Postfach befunden haben.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Konvertieren des Postfachs eines Benutzers in einer Hybridumgebung

Weitere Informationen zum Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach in einer Exchange Hybridumgebung finden Sie unter:

 - [Cmdlets zum Erstellen oder Ändern eines freigegebenen Remotepostfachs in einer lokalen Exchange umgebung](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [Freigegebene Postfächer werden unerwartet in Benutzerpostfächer konvertiert, nachdem die Verzeichnissynchronisierung in einer Exchange Hybridbereitstellung ausgeführt wurde.](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> Wenn Sie Mitglied der Rollengruppe "Organisationsverwaltung" oder "Empfängerverwaltung" sind, können Sie die Exchange Verwaltungsshell verwenden, um ein Benutzerpostfach in ein lokales freigegebenes Postfach zu ändern. Beispiel: `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.

## <a name="related-content"></a>Verwandte Inhalte

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) (Artikel)\
[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md) (Artikel)\
[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md) (Artikel)\
[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md) (Artikel)\
[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md) (Artikel)