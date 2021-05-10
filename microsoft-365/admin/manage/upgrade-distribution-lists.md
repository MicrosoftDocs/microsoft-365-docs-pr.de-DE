---
title: Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen in Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Erfahren Sie, wie Sie eine oder mehrere Verteilerlisten auf Microsoft 365 Gruppen in Outlook aktualisieren und wie Sie PowerShell verwenden, um mehrere Verteilerlisten gleichzeitig zu aktualisieren.
ms.openlocfilehash: 72a98cdfda441dc71fcc5ae21f0042dafef3aefb
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297080"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen in Outlook

Sie können Verteilerlisten auf Microsoft 365 Gruppen in Outlook. Dies ist eine hervorragende Möglichkeit, um den Verteilerlisten Ihrer Organisation alle Features und Funktionen von Microsoft 365 zu geben. [Warum Sie Ihre Verteilerlisten für Gruppen in Outlook aktualisieren sollten](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

Sie können ein Upgrade für eine einzelne Verteilerliste oder für mehrere Verteilerlisten gleichzeitig ausführen.

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Aktualisieren Sie eine oder mehrere Verteilerlistengruppen auf Microsoft 365 Gruppen in Outlook

Sie müssen ein globaler Administrator oder Exchange administrator sein, um eine Verteilerlistengruppe aktualisieren zu können. Zum Upgrade auf Microsoft 365 Gruppen muss die Verteilerlistengruppe über einen Besitzer mit einem Postfach verfügen.

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Verwenden Sie die neue EAC, um eine oder mehrere Verteilerlistengruppen auf Microsoft 365 gruppen in Outlook

1. Wechseln Sie zum neuen [Exchange Admin Center,](https://admin.exchange.microsoft.com)und navigieren Sie zu  \> **Empfängergruppen**.

2. Wählen Sie auf der Seite Gruppen die Verteilerlistengruppe (auch Verteilergruppe **genannt)** aus, die Sie auf Microsoft 365 Gruppe **aktualisieren** möchten.

3. Wählen Sie **auf der Toolleiste** die Verteilergruppe Upgrade aus.

4. Klicken Sie im Dialogfeld **Bereit zum Upgrade?** auf **Upgrade**. Der Prozess beginnt sofort. Je nach Größe und Anzahl der Verteilerlistengruppen, die Sie aktualisieren, kann der Vorgang Minuten oder Stunden dauern.

> [!NOTE]
> Ein Banner oben zeigt das Upgrade an, z. B. wurde ein Upgrade für *Verteilergruppen durchgeführt. Es dauert 5 Minuten, bis die Änderungen widerspiegelt werden. Filtern Sie nach Microsoft 365 Gruppen, um die aktualisierten Distrubtionsgruppen (en) zu sehen.*

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Verwenden Sie die klassische EAC, um eine oder mehrere Verteilerlistengruppen auf Microsoft 365 gruppen in Outlook

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">klassischen Exchange Admin Center</a>.

2. Wechseln Sie im Exchange Admin Center  zu \> **Empfängergruppen**.<br/>Es wird eine Meldung angezeigt, dass Sie Verteilerlisten (auch Verteilergruppen **genannt)** haben, die berechtigt sind, ein Upgrade auf Microsoft 365 zu erhalten.<br/> ![Wählen Sie die Schaltfläche Erste Schritte aus.](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Wählen Sie auf der Seite Gruppen eine oder mehrere Verteilerlisten (auch **Verteilergruppe genannt)** aus.<br/>![Auswählen einer Verteilergruppe](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Wählen Sie das Upgradesymbol aus.<br/>![Upgrade auf Microsoft 365 Gruppensymbol](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. Wählen Sie im Dialogfeld Informationen **Ja** aus, um das Upgrade zu bestätigen. Der Prozess beginnt sofort. Je nach Größe und Anzahl der DLs, die Sie aktualisieren, kann der Prozess Minuten oder Stunden dauern.<br/>Wenn für die Verteilerliste kein Upgrade ausgeführt werden kann, wird ein Dialogfeld mit einer entsprechenden Meldung angezeigt. Weitere [Informationen finden Sie unter Welche Verteilerlisten können nicht aktualisiert werden?](#which-distribution-lists-cant-be-upgraded).

6. Wenn Sie mehrere Verteilerlisten aktualisieren, verwenden Sie die Dropdownliste, um zu filtern, welche Verteilerlisten aktualisiert wurden. Wenn die Liste nicht vollständig ist, warten Sie  etwas länger, und wählen Sie Aktualisieren aus, um zu sehen, was erfolgreich aktualisiert wurde.<br/>Es wird keine Benachrichtigung ausgegeben, die Sie informiert, wann das Upgrade für alle ausgewählten Verteilerlisten abgeschlossen wurde. Sie können dies jedoch herausfinden, indem Sie die Elemente untersuchen, die unter **Für Upgrade verfügbar** oder **Aktualisierte Verteilerlisten** angezeigt werden.

7. Wenn Sie eine DL für das Upgrade ausgewählt haben, sie jedoch weiterhin auf der Seite als Verfügbar für ein Upgrade angezeigt wird, konnte sie nicht aktualisiert werden. Lesen Sie in diesem Fall [Wie gehe ich vor, wenn das Upgrade nicht funktioniert?](#what-to-do-if-the-upgrade-doesnt-work)

> [!NOTE]
> Wenn Sie die Digest-E-Mails der Gruppen erhalten, wird im unteren Bereich ggf. angeboten, ein Upgrade für alle geeigneten Verteilerlisten auszuführen, deren Besitzer Sie sind. Weitere Informationen zu Digest-E-Mails finden Sie unter [Führen einer Gruppenunterhaltung in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Wie gehe ich vor, wenn das Upgrade nicht funktioniert?

Verteilerlisten, für die beim Upgrade ein Fehler auftritt, bleiben unverändert.

Wenn für mindestens eine **geeignete** Verteilerliste beim Upgrade ein Fehler auftritt, öffnen Sie ein [Supportticket](../../business-video/get-help-support.md). Das Problem muss an das Gruppenentwicklungsteam eskaliert werden, damit dieses das Problem ermitteln kann.

Es ist möglich, dass die Verteilerliste aufgrund eines Dienstausfalls nicht aktualisiert wurde, aber unwahrscheinlich. Warten Sie, falls sie möchten, eine Weile, und versuchen Sie dann, die DL erneut zu aktualisieren.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Verwenden von PowerShell zum gleichzeitigen Ausführen eines Upgrades mehrerer Verteilerlisten

Wenn Sie im Umgang mit PowerShell erfahren sind, können Sie diese Methode anstelle der Benutzeroberfläche verwenden. Wir verfügen über eine Reihe von Cmdlets, mit deren Hilfe Sie Verteilerlisten aktualisieren können. Siehe unten.

### <a name="upgrade-a-single-dl"></a>Upgrade einer einzelnen DL

Führen Sie zum Aktualisieren einer einzelnen DL den folgenden Befehl aus:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

Wenn Sie z. B. ein Upgrade einer DLs mit SMTP-Dl1@contoso.com möchten, führen Sie den folgenden Befehl aus:

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> Mit dem [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell-Cmdlet können Sie auch eine einzelne Verteilerliste auf eine Microsoft 365 aktualisieren.

### <a name="upgrade-multiple-dls-in-a-batch"></a>Upgrade mehrerer DLs in einem Batch

Sie können auch mehrere DLs als Batch übergeben und gemeinsam aktualisieren:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Wenn Sie beispielsweise fünf DLs mit SMTP-Adresse und , und aktualisieren möchten, führen `dl1@contoso.com` Sie den folgenden Befehl `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` aus:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Upgrade aller berechtigten DLs

Es gibt zwei Möglichkeiten, wie Sie alle berechtigten DLs aktualisieren können.

> [!NOTE]
> Das Upgrade-DistributionGroup-Cmdlet erhält keine Daten von der Pipeline, daher muss es den Operator "foreach-object" verwenden, um {} erfolgreich ausgeführt zu werden.

1. Holen Sie sich die berechtigten DLs im Mandanten, und aktualisieren Sie sie mithilfe des Upgradebefehls:

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Hier erhalten Sie die Liste aller DLs, und aktualisieren Sie nur die berechtigten DLs:

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Häufig gestellte Fragen zum Upgrade von Verteilerlisten Microsoft 365 Gruppen in Outlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>Welche Verteilerlisten können nicht aktualisiert werden?

Sie können nur für in der Cloud verwaltete, einfache, nicht geschachtelte Verteilerlisten ein Upgrade ausführen. In der folgenden Tabelle sind Verteilerlisten aufgeführt, die **NICHT aktualisiert** werden können.

|**Eigenschaft**|**Geeignet?**|
|:-----|:-----|
|Lokal verwaltete Verteilerliste.  <br/> |Nein  <br/> |
|Geschachtelte Verteilerliste. Die Verteilerliste hat untergeordnete Gruppen oder ist Mitglied einer anderen Gruppe.  <br/> |Nein  <br/> |
|Verteilerlisten mit dem Mitglied **RecipientTypeDetails,** mit Ausnahme **von UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**  <br/> |Nein  <br/> |
|Verteilerliste mit mehr als 100 Besitzern  <br/> |Nein  <br/> |
|Verteilerliste, die nur Mitglieder, aber keinen Besitzer hat  <br/> |Nein  <br/> |
|Verteilerliste mit Alias mit Sonderzeichen  <br/> |Nein  <br/> |
|Die Verteilerliste ist als Weiterleitungsadresse für das freigegebene Postfach konfiguriert  <br/> |Nein  <br/> |
|Wenn die DL Teil der **Absendereinschränkung** in einer anderen DL ist.  <br/> |Nein  <br/> |
|Sicherheitsgruppen  <br/> |Nein  <br/> |
|Dynamische Verteilerlisten  <br/> |Nein  <br/> |
|Verteilerlisten, die in **RoomLists konvertiert wurden**  <br/> |Nein  <br/> |
|Verteilerlisten, in denen **MemberJoinRestriction** und/oder **MemberDepartRestriction** geschlossen **ist**  <br/> |Nein  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>Überprüfen, welche DLs für ein Upgrade berechtigt sind

Wenn Sie überprüfen möchten, ob eine DL berechtigt ist oder nicht, können Sie den folgenden Befehl ausführen:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Wenn Sie überprüfen möchten, welche DLs für ein Upgrade berechtigt sind, führen Sie den folgenden Befehl aus:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Wer kann die Upgradeskripts ausführen?

Personen mit globalen Administrator- oder Exchange Administratorrechten.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Warum wird auf der Visitenkarte weiterhin eine Verteilerliste angezeigt? Was soll ich tun, um zu verhindern, dass eine aktualisierte Verteilerliste in meiner Liste für automatische Vorschläge angezeigt wird?

- For Outlook: When someone tries to send an email in Outlook by tipping the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group. Die Visitenkarte des Empfängers entspricht der Visitenkarte der Verteilerliste. Der Grund hierfür liegt im Empfängercache oder "Spitznamen"-Cache von Outlook. Die E-Mail wird erfolgreich an die Gruppe gesendet, kann jedoch zu Verwirrung beim Absender führen.<br/>Sie können die Schritte in diesem Artikel, Informationen zur liste [Outlook AutoComplete](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) ausführen, um den Cache zurückzusetzen, wodurch dieses Problem behoben wird.

- For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache. Sie können die Schritte unter Entfernen des vorgeschlagenen Namens oder der [E-Mail-Adresse](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) aus der Liste der automatischen Vervollständigen ausführen, um den Cache zu aktualisieren, um die Gruppenkontaktkarte zu sehen.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>Erhalten neue Gruppenmitglieder in ihrem Posteingang eine Willkommensnachricht?

Nein. Die Einstellung zum Aktivieren von Willkommensnachrichten ist standardmäßig auf FALSE festgelegt. Diese Einstellung wirkt sich auf vorhandene und neue Gruppenmitglieder aus, die beitreten können, nachdem die Migration abgeschlossen wurde. Wenn der Besitzer der Gruppe später Gastbenutzer zulässt, empfangen Gastbenutzer keine Willkommensnachricht in ihrem Posteingang. Gastmitglieder können weiterhin mit der Gruppe zusammenarbeiten.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Was passiert, wenn eine oder einige der DLs nicht aktualisiert werden?

Es gibt einige Fälle, in denen DL zwar berechtigt ist, aber nicht aktualisiert werden konnte. Die DL wird nicht aktualisiert und bleibt als DL erhalten.

- Wenn der Administrator eine **Gruppen-E-Mail-Adressrichtlinie** für die Gruppen in einer Organisation angewendet hat und versucht, DLs zu aktualisieren, die die Kriterien nicht erfüllen, wird die DL nicht aktualisiert.

- DLs mit **MemberJoinRestriction** oder **MemberDepartRestriction,** die auf **Closed** festgelegt sind, konnten nicht aktualisiert werden.

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>Was geschieht mit der Verteilerliste, wenn beim Upgrade aus EAC ein Fehler auftritt?

Das Upgrade erfolgt nur, wenn der Aufruf an den Server übermittelt wird. Wenn beim Upgrade ein Fehler auftritt, bleiben Ihre Verteilerlisten erhalten. Sie funktionieren wie bisher.
