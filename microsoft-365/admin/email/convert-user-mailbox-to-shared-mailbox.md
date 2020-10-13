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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Hier erfahren Sie, wie Sie ein privates Postfach in ein freigegebenes Postfach konvertieren, auf das mehrere Benutzer zugreifen können. '
ms.openlocfilehash: bc867c9b43656e40149eb7cd7a7e5ce186c10798
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445687"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach

Wenn Sie das Postfach eines Benutzers in ein freigegebenes Postfach konvertieren, werden alle vorhandenen E-Mails und Kalender beibehalten. Sie befinden sich nun nur in einem freigegebenen Postfach, auf das mehrere Personen (nicht nur eine Person) zugreifen können. Zu einem späteren Zeitpunkt können Sie ein freigegebenes Postfach wieder in ein Benutzerpostfach (privat) konvertieren.

**Hier sind einige wirklich wichtige Dinge, die Sie kennen müssen:**

- Das Benutzerpostfach, das Sie konvertieren möchten, benötigt eine Lizenz, die ihm zugewiesen ist, bevor Sie es in ein freigegebenes Postfach konvertieren. Andernfalls wird die Option zum Konvertieren des Postfachs nicht angezeigt. Wenn Sie die Lizenz entfernt haben, fügen Sie sie erneut hinzu, damit Sie das Postfach konvertieren können. Nach dem Konvertieren des Postfachs in ein freigegebenes Postfach können Sie die Lizenz aus dem Benutzerkonto entfernen.

- Freigegebene Postfächer können bis zu 50 GB Daten haben, ohne dass Ihnen eine Lizenz zugewiesen ist. Um mehr Daten zu speichern, benötigen Sie eine Lizenz, die ihr zugewiesen ist. Möglicherweise müssen Sie eine Reihe großer e-Mails (sprich diejenigen mit Anlagen) aus dem freigegebenen Postfach löschen, um es zu verkleinern, damit Sie die Lizenz entfernen können.

- Löschen Sie das alte Konto des Benutzers nicht. Es ist für das Verankern des freigegebenen Postfachs erforderlich. Wenn Sie das Benutzerkonto bereits gelöscht haben, lesen Sie [Konvertieren des Postfachs eines gelöschten Benutzers](#convert-the-mailbox-of-a-deleted-user).

- Die Regeln sind intakt, nachdem das Postfach in ein freigegebenes Postfach konvertiert wurde.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Verwenden der Exchange-Verwaltungskonsole zum Konvertieren eines Postfachs
 
1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.

2. Wählen Sie **Empfänger** \> **Postfächer**aus.

3. Wählen Sie das Benutzerpostfach aus. Wählen Sie unter **in freigegebenes Postfach konvertieren die**Option **konvertieren**aus.

4. Wenn das Postfach kleiner als 50 GB ist, können Sie die [Lizenz vom Benutzer](../manage/remove-licenses-from-users.md)entfernen und nicht mehr bezahlen. Löschen Sie das Konto des Benutzers nicht. Das freigegebene Postfach benötigt dieses als Anker. Wenn Sie das Postfach eines Mitarbeiters, der Ihre Organisation verlässt, konvertieren möchten, sollten Sie zusätzliche Schritte Unternehmen, um sicherzustellen, dass Sie sich nicht mehr anmelden können. Weitere Informationen finden Sie unter [Entfernen eines ehemaligen Mitarbeiters von Microsoft 365](../add-users/remove-former-employee.md).
    
> [!NOTE]
> Es ist nicht erforderlich, das Kennwort des Benutzers während der Post Fach Konvertierung zurückzusetzen. Wenn das Kennwort jedoch nicht zurückgesetzt wird, **Funktionieren der ursprüngliche Benutzername und das Kennwort** nach Abschluss der Post Fach Konvertierung weiterhin.

Alles, was Sie über freigegebene Postfächer wissen müssen, finden Sie unter [Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) und [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).

> [!NOTE]
> Freigegebene Postfächer erfordern keine separate Lizenz. Wenn Sie jedoch In-Place Archiv aktivieren oder ein In-Place halten oder ein Beweissicherungsverfahren für ein freigegebenes Postfach speichern möchten, müssen Sie dem Postfach einen Exchange Onlineplan 1 mit Exchange Online Archivierungs-oder Exchange Online Plan 2-Lizenz zuweisen.


## <a name="convert-the-mailbox-of-a-deleted-user"></a>Konvertieren des Postfachs eines gelöschten Benutzers

Angenommen, Sie haben ein Benutzerkonto gelöscht und möchten nun das alte Postfach in ein freigegebenes Postfach konvertieren. Nachstehend wird beschrieben, wie Sie vorgehen müssen:

1. [Stellen Sie das Konto des Benutzers wieder her](../add-users/restore-user.md).

2. Stellen Sie sicher, dass eine Microsoft 365-Lizenz zugewiesen ist.

3. Setzen Sie das Kennwort des Benutzers zurück.
    
4. Warten Sie 20 bis 30 Minuten, bis das Postfach erneut erstellt wurde.
    
5. Befolgen Sie nun die Anweisungen auf dieser Seite, um das Postfach in ein freigegebenes Postfach zu konvertieren.
    
6. Nachdem das erledigt ist, können Sie die Lizenz aus dem Postfach des Benutzers entfernen. Löschen Sie das alte Postfach des Benutzers nicht. Das freigegebene Postfach benötigt dieses als Anker.
    
7. Fügen Sie dem freigegebenen Postfach Mitglieder hinzu.


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Konvertieren eines freigegebenen Postfachs zurück in das (private) Postfach eines Benutzers

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.
   
2. Wählen Sie **Empfänger** \> **freigegeben**aus.

3. Wählen Sie das freigegebene Postfach aus. Wählen Sie unter **Convert to Regular Mailbox die**Option **Convert**aus.

4. Wechseln Sie zurück zum Admin Center. Wählen Sie unter **Benutzer** das Benutzerkonto aus, das dem alten freigegebenen Postfach zugeordnet ist. Weisen Sie dem Konto eine Lizenz zu, und setzen Sie das Kennwort zurück.

   Es dauert einige Minuten, bis das Postfach eingerichtet wurde. Anschließend kann die Person, die für die Verwendung dieses Kontos vorgesehen ist, das Postfach nutzen. Beim Anmelden werden die E-Mail- und Kalenderelemente angezeigt, die sich zuvor im freigegebenen Postfach befunden haben.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Konvertieren des Postfachs eines Benutzers in einer Hybridumgebung

Wenn sich dieses freigegebene Postfach in einer Hybridumgebung befindet, wird **dringend empfohlen** , das Benutzerpostfach wieder in ein lokales Postfach zu migrieren, das Benutzerpostfach in ein freigegebenes Postfach zu konvertieren und das freigegebene Postfach dann wieder in die Cloud zu migrieren. 

Hier ist der Grund: Wenn Sie das Postfach in der Cloud konvertieren, kann es konvertiert werden, doch lokal ist das Postfach das Benutzerpostfach, da die neue Realität nicht wieder lokal synchronisiert wird.

Normalerweise handelt es sich nicht um ein Problem, aber es gibt einige Szenarien, in denen die lokalen Attribute (die denken, dass das Postfach das Benutzerpostfach ist) die neuen Cloud-Versionen dieser Attribute überschreiben können und daher das Postfach möglicherweise wieder zurückkonvertiert wird. Dies ist ein Problem, da Benutzerpostfächer Lizenzen erfordern **oder nach 30 Tagen weich gelöscht werden**!

Wir haben die meisten der Gründe behandelt, warum dies geschieht, aber es kann immer noch passieren, obwohl selten. Am besten ist es, sicher zu sein und das Postfach zurück in die lokale Umgebung zu versetzen, es zu konvertieren und dann das freigegebene Postfach wieder in die Cloud zu migrieren. Diese empfohlene Lösung verstößt nicht gegen den Lizenzvertrag für Hybrid Umgebungen, da das vorhanden sein des Benutzerpostfachs lokal nur temporär ist. Sie verletzen Ihre Lizenz, wenn Sie das Benutzerpostfach oder das freigegebene Postfach in Ihrer lokalen Organisation verwaltet haben und es nicht wieder in die Cloud zurückversetzen.

> [!NOTE]
> Wenn Sie Mitglied der Rollengruppe "Organisationsverwaltung" oder "Empfängerverwaltung" sind, können Sie die Exchange-Verwaltungsshell verwenden, um ein Benutzerpostfach in ein freigegebenes Postfach lokal zu ändern. Beispiel: `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.

> [!TIP]
> Sehen Sie sich die Problemumgehung in dieser Support Lösung für Instanzen an [, wenn freigegebene Postfächer unerwarteterweise in Benutzerpostfächer konvertiert werden](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).
  
## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md)

[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md)

[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md)

[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md)

[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md)
