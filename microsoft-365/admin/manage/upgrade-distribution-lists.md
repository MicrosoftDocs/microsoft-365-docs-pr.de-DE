---
title: Aktualisieren von Verteilerlisten auf Microsoft 365-Gruppen in Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
description: Erfahren Sie, wie Sie eine oder mehrere Verteilerlisten auf Microsoft 365-Gruppen in Outlook aktualisieren und wie Sie PowerShell verwenden, um mehrere Verteilerlisten gleichzeitig zu aktualisieren.
ms.openlocfilehash: 95f887b4386b349dc9d8bb471deab19b5425f6f5
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080527"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Aktualisieren von Verteilerlisten auf Microsoft 365-Gruppen in Outlook

Sie können Verteilerlisten mit Outlook auf Microsoft 365-Gruppen aktualisieren. Dies ist eine hervorragende Möglichkeit, um den Verteilerlisten Ihrer Organisation alle Features und Funktionen von Microsoft 365-Gruppen zu bieten. [Warum Sie Ihre Verteilerlisten für Gruppen in Outlook aktualisieren sollten](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

Sie können ein Upgrade für eine einzelne Verteilerliste oder für mehrere Verteilerlisten gleichzeitig ausführen.

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Upgrade einer oder vieler Verteilerlisten auf Microsoft 365-Gruppen in Outlook

Sie müssen ein globaler Administrator oder ein Exchange-Administrator sein, um eine Verteilerliste aktualisieren zu können. Um ein Upgrade auf Microsoft 365-Gruppen durchführen zu können, muss eine Verteilergruppe über einen Besitzer mit einem Postfach verfügen.

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.

2. Wechseln Sie im Exchange Admin Center **zu** \> **Empfängergruppen.**<br/>Es wird ein Hinweis angezeigt, dass Sie Verteilerlisten (auch verteilergruppen **genannt)** haben, die für ein Upgrade auf Microsoft 365-Gruppen berechtigt sind.<br/> ![Schaltfläche "Erste Schritte" auswählen](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Wählen Sie eine oder mehrere Verteilerlisten (auch als **Verteilergruppe** bezeichnet) auf der Seite **Gruppen** aus.<br/>![Auswählen einer Verteilergruppe](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Wählen Sie das Upgradesymbol aus.<br/>![Aktualisieren auf Microsoft 365-Gruppen (Symbol)](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. Wählen Sie im Dialogfeld "Informationen" die Option **"Ja"** aus, um das Upgrade zu bestätigen. Der Prozess beginnt sofort. Je nach Größe und Anzahl der DLs, die Sie aktualisieren, kann der Vorgang Minuten oder Stunden dauern.<br/>Wenn für die Verteilerliste kein Upgrade ausgeführt werden kann, wird ein Dialogfeld mit einer entsprechenden Meldung angezeigt. Informationen [zu den Verteilerlisten, die nicht aktualisiert werden können?](#which-distribution-lists-cant-be-upgraded)

6. Wenn Sie mehrere Verteilerlisten aktualisieren, filtern Sie mithilfe der Dropdownliste, welche Verteilerlisten aktualisiert wurden. Wenn die Liste nicht vollständig ist, warten Sie etwas länger, und wählen Sie dann **"Aktualisieren"** aus, um zu sehen, was erfolgreich aktualisiert wurde.<br/>Es wird keine Benachrichtigung ausgegeben, die Sie informiert, wann das Upgrade für alle ausgewählten Verteilerlisten abgeschlossen wurde. Sie können dies jedoch herausfinden, indem Sie die Elemente untersuchen, die unter **Für Upgrade verfügbar** oder **Aktualisierte Verteilerlisten** angezeigt werden.

7. Wenn Sie eine Verteilerliste für das Upgrade ausgewählt haben, diese aber auf der Seite noch als "Für Upgrade verfügbar" angezeigt wird, ist beim Upgrade ein Fehler aufgetreten. Lesen Sie in diesem Fall [Wie gehe ich vor, wenn das Upgrade nicht funktioniert?](#what-to-do-if-the-upgrade-doesnt-work)

> [!NOTE]
> Wenn Sie die Digest-E-Mails der Gruppen erhalten, wird im unteren Bereich ggf. angeboten, ein Upgrade für alle geeigneten Verteilerlisten auszuführen, deren Besitzer Sie sind. Weitere Informationen zu Digest-E-Mails finden Sie unter [Führen einer Gruppenunterhaltung in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Wie gehe ich vor, wenn das Upgrade nicht funktioniert?

Verteilerlisten, für die beim Upgrade ein Fehler auftritt, bleiben unverändert.

Wenn für mindestens eine **geeignete** Verteilerliste beim Upgrade ein Fehler auftritt, öffnen Sie ein [Supportticket](../contact-support-for-business-products.md). Das Problem muss an das Gruppenentwicklungsteam eskaliert werden, damit dieses das Problem ermitteln kann.

Es ist möglich, dass für die Verteilerliste aufgrund eines Dienstausfalls kein Upgrade ausgeführt wurde. Dies ist aber ziemlich unwahrscheinlich. Wenn Sie möchten, können Sie auch eine Weile warten und dann erneut versuchen, ein Upgrade für die Verteilerliste auszuführen.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Verwenden von PowerShell zum gleichzeitigen Ausführen eines Upgrades mehrerer Verteilerlisten

Wenn Sie im Umgang mit PowerShell erfahren sind, können Sie diese Methode anstelle der Benutzeroberfläche verwenden. Wir haben eine Reihe von Cmdlets, die Ihnen beim Upgrade von Verteilerlisten helfen. Siehe unten.

### <a name="upgrade-a-single-dl"></a>Upgrade einer einzelnen DL

Führen Sie den folgenden Befehl aus, um eine einzelne DL zu aktualisieren:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

Wenn Sie z. B. ein Upgrade einer DLs mit einer SMTP-Dl1@contoso.com möchten, führen Sie den folgenden Befehl aus:

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> Sie können eine einzelne Verteilerliste auch mithilfe des [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) -PowerShell-Cmdlets auf eine Microsoft 365-Gruppe aktualisieren.

### <a name="upgrade-multiple-dls-in-a-batch"></a>Upgrade mehrerer DLs in einem Batch

Sie können auch mehrere DLs als Batch übergeben und gemeinsam aktualisieren:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Wenn Sie beispielsweise fünf DLs mit der SMTP-Adresse und , und aktualisieren möchten, führen `dl1@contoso.com` Sie den folgenden Befehl `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` aus:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Aktualisieren aller berechtigten DLs

Es gibt zwei Möglichkeiten, alle berechtigten DLs zu aktualisieren.

> [!NOTE]
> Das Upgrade-DistributionGroup-Cmdlet erhält keine Daten von der Pipeline, daher muss für die erfolgreiche Ausführung der Operator "foreach-object" {} verwendet werden.

1. Erhalten Sie die berechtigten DLs im Mandanten, und aktualisieren Sie sie mithilfe des Upgradebefehls:

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Erhalten Sie die Liste aller DLs, und aktualisieren Sie nur die berechtigten DLs:

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Häufig gestellte Fragen zum Upgrade von Verteilerlisten auf Microsoft 365-Gruppen in Outlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>Welche Verteilerlisten können nicht aktualisiert werden?

Sie können nur für in der Cloud verwaltete, einfache, nicht geschachtelte Verteilerlisten ein Upgrade ausführen. In der folgenden Tabelle sind Verteilerlisten aufgeführt, für **die kein** Upgrade durchgeführt werden kann.

|**Eigenschaft**|**Geeignet?**|
|:-----|:-----|
|Lokal verwaltete Verteilerliste.  <br/> |Nein  <br/> |
|Geschachtelte Verteilerliste. Die Verteilerliste hat untergeordnete Gruppen oder ist Mitglied einer anderen Gruppe.  <br/> |Nein  <br/> |
|Verteilerlisten mit anderen **Membern recipientTypeDetails** als **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**  <br/> |Nein  <br/> |
|Verteilerliste mit mehr als 100 Besitzern  <br/> |Nein  <br/> |
|Verteilerliste, die nur Mitglieder aber keinen Besitzer enthält  <br/> |Nein  <br/> |
|Verteilerliste, die einen Alias mit Sonderzeichen enthält  <br/> |Nein  <br/> |
|Die Verteilerliste ist als Weiterleitungsadresse für das freigegebene Postfach konfiguriert  <br/> |Nein  <br/> |
|Wenn die Verteilerliste Teil der **Absendereinschränkung** in einer anderen DL ist.  <br/> |Nein  <br/> |
|Sicherheitsgruppen  <br/> |Nein  <br/> |
|Dynamische Verteilerlisten  <br/> |Nein  <br/> |
|Verteilerlisten, die in **RoomLists konvertiert wurden**  <br/> |Nein  <br/> |
|Verteilerlisten, **bei denen "MemberJoinRestriction"** und/oder **"MemberDepartRestriction"** geschlossen **ist**  <br/> |Nein  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>Überprüfen, welche DLs für ein Upgrade berechtigt sind

Wenn Sie überprüfen möchten, ob eine DL berechtigt ist oder nicht, können Sie den folgenden Befehl ausführen:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Wenn Sie überprüfen möchten, welche DLs für ein Upgrade berechtigt sind, führen Sie einfach den folgenden Befehl aus:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Wer kann die Upgradeskripts ausführen?

Personen mit globalen Administrator- oder Exchange-Administratorrechten.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Warum wird auf der Visitenkarte weiterhin eine Verteilerliste angezeigt? Wie kann ich vorgehen, um zu verhindern, dass eine Verteilerliste, für die ein Upgrade ausgeführt wurde, in meiner Vorschlagssuche angezeigt wird?

- Für Outlook: Wenn jemand versucht, eine E-Mail in Outlook zu senden, indem er nach der Migration den Microsoft 365-Gruppennamen eintippt, wird der Empfänger als Verteilerliste anstelle der Gruppe aufgelöst. Die Visitenkarte des Empfängers entspricht der Visitenkarte der Verteilerliste. Der Grund hierfür liegt im Empfängercache oder "Spitznamen"-Cache von Outlook. Die E-Mail wird erfolgreich an die Gruppe gesendet, kann jedoch für den Absender Verwirrung stiften.<br/>Sie können die Schritte im Thema [Informationen zur AutoVervollständigen-Liste von Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) ausführen, um den Cache zurückzusetzen und das Problem zu beheben.

- Für Outlook im Web: Bei Outlook im Web bleibt der Empfänger der Verteilerliste weiterhin im Cache. Sie können die Schritte unter "Vorgeschlagenen Namen oder [E-Mail-Adresse](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) aus der Liste automatisch abschließen" ausführen, um den Cache zu aktualisieren und die Gruppenkontaktkarte zu sehen.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>Erhalten neue Gruppenmitglieder in ihrem Posteingang eine Willkommensnachricht?

Nein. Die Einstellung zum Aktivieren von Willkommensnachrichten ist standardmäßig auf FALSE festgelegt. Diese Einstellung wirkt sich auf vorhandene und neue Gruppenmitglieder aus, die beitreten können, nachdem die Migration abgeschlossen wurde. Wenn der Besitzer der Gruppe später Gastbenutzer zulässt, empfangen Gastbenutzer keine Willkommensnachricht in ihrem Posteingang. Gastmitglieder können weiterhin mit der Gruppe zusammenarbeiten.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Was passiert, wenn eine oder einige der DLs nicht aktualisiert werden?

Es gibt einige Fälle, in denen DL berechtigt ist, aber nicht aktualisiert werden konnte. Die DL wird nicht aktualisiert und bleibt als DL.

- Wenn der Administrator die **Gruppen-E-Mail-Adressrichtlinie** für die Gruppen in einer Organisation angewendet hat und versucht, DLs zu aktualisieren, die die Kriterien nicht erfüllen, wird die Verteilerliste nicht aktualisiert.

- DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>Was geschieht mit der Verteilerliste, wenn beim Upgrade aus EAC ein Fehler auftritt?

Das Upgrade erfolgt nur, wenn der Aufruf an den Server übermittelt wird. Wenn beim Upgrade ein Fehler auftritt, bleiben Ihre Verteilerlisten erhalten. Sie funktionieren wie bisher.
