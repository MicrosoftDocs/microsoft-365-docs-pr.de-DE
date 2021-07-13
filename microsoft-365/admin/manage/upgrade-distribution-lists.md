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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Erfahren Sie, wie Sie eine oder mehrere Verteilerlisten auf Microsoft 365 Gruppen in Outlook aktualisieren und wie Sie PowerShell verwenden, um mehrere Verteilerlisten gleichzeitig zu aktualisieren.
ms.openlocfilehash: aef797a2bf052fcc84c9220993c2e6706eae5f61
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391387"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen in Outlook

Sie können Verteilerlisten auf Microsoft 365 Gruppen in Outlook aktualisieren. Dies ist eine großartige Möglichkeit, um den Verteilerlisten Ihrer Organisation alle Features und Funktionen von Microsoft 365-Gruppen bereitzustellen. [Warum Sie Ihre Verteilerlisten für Gruppen in Outlook aktualisieren sollten](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

Sie können ein Upgrade für eine einzelne Verteilerliste oder für mehrere Verteilerlisten gleichzeitig ausführen.

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Aktualisieren einer oder mehrerer Verteilerlistengruppen auf Microsoft 365 Gruppen in Outlook

Sie müssen ein globaler Administrator oder Exchange Administrator sein, um ein Upgrade einer Verteilerlistengruppe durchzuführen. Um auf Microsoft 365 Gruppen zu aktualisieren, muss die Verteilerlistengruppe über einen Besitzer mit einem Postfach verfügen.

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Verwenden sie das neue EAC, um eine oder viele Verteilerlistengruppen auf Microsoft 365 Gruppen in Outlook

1. Wechseln Sie zum neuen [Exchange Admin Center,](https://admin.exchange.microsoft.com)und navigieren Sie zu  \> **Empfängergruppen.**

2. Wählen Sie auf der Seite **"Gruppen"** die Verteilerlistengruppe (auch **Verteilergruppe** genannt) aus, die Sie auf Microsoft 365 Gruppe aktualisieren möchten.

3. Wählen Sie die **Verteilergruppe "Upgrade"** in der Toolleiste aus.

4. Klicken Sie im Dialogfeld **Bereit für das Upgrade?** auf **"Upgrade".** Der Prozess beginnt sofort. Je nach Größe und Anzahl der Verteilerlistengruppen, die Sie aktualisieren, kann der Vorgang Minuten oder Stunden dauern.

> [!NOTE]
> Ein Banner oben zeigt das Upgrade an, z. B. *verteilergruppen wurden aktualisiert. Es dauert 5 Minuten, um die Änderungen widerzuspiegeln. Filtern Sie nach Microsoft 365 Gruppen, um die aktualisierten Distrubtionsgruppen anzuzeigen.*

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Verwenden des klassischen EAC, um eine oder viele Verteilerlistengruppen auf Microsoft 365 Gruppen in Outlook

1. Wechseln Sie zum klassischen <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center.</a>

2. Wechseln Sie im klassischen Exchange Admin  Center zu \> **Empfängergruppen.**<br/>Es wird ein Hinweis angezeigt, der angibt, dass Sie Verteilerlisten (auch **verteilergruppen** genannt) haben, die für das Upgrade auf Microsoft 365 Gruppen berechtigt sind.<br/> ![Wählen Sie die Schaltfläche "Erste Schritte" aus.](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Wählen Sie auf **der** Gruppenseite eine oder mehrere Verteilerlisten (auch **Verteilergruppe** genannt) aus.<br/>![Auswählen einer Verteilergruppe](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Wählen Sie das Upgradesymbol aus.<br/>![Symbol "Auf Microsoft 365 Gruppen aktualisieren"](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. Wählen Sie im Dialogfeld "Informationen" die Option **"Ja"** aus, um das Upgrade zu bestätigen. Der Prozess beginnt sofort. Je nach Größe und Anzahl der DLs, die Sie aktualisieren, kann der Vorgang Minuten oder Stunden dauern.<br/>Wenn für die Verteilerliste kein Upgrade ausgeführt werden kann, wird ein Dialogfeld mit einer entsprechenden Meldung angezeigt. Siehe [Welche Verteilerlisten können nicht aktualisiert werden?](#which-distribution-lists-cant-be-upgraded).

6. Wenn Sie mehrere Verteilerlisten aktualisieren, verwenden Sie die Dropdownliste, um zu filtern, welche Verteilerlisten aktualisiert wurden. Wenn die Liste nicht abgeschlossen ist, warten Sie eine Weile, und wählen Sie **"Aktualisieren"** aus, um zu sehen, was erfolgreich aktualisiert wurde.<br/>Es wird keine Benachrichtigung ausgegeben, die Sie informiert, wann das Upgrade für alle ausgewählten Verteilerlisten abgeschlossen wurde. Sie können dies jedoch herausfinden, indem Sie die Elemente untersuchen, die unter **Für Upgrade verfügbar** oder **Aktualisierte Verteilerlisten** angezeigt werden.

7. Wenn Sie eine DL für das Upgrade ausgewählt haben, diese jedoch weiterhin auf der Seite als für das Upgrade verfügbar angezeigt wird, konnte das Upgrade nicht durchgeführt werden. Lesen Sie in diesem Fall [Wie gehe ich vor, wenn das Upgrade nicht funktioniert?](#what-to-do-if-the-upgrade-doesnt-work)

> [!NOTE]
> Wenn Sie die Digest-E-Mails der Gruppen erhalten, wird im unteren Bereich ggf. angeboten, ein Upgrade für alle geeigneten Verteilerlisten auszuführen, deren Besitzer Sie sind. Weitere Informationen zu Digest-E-Mails finden Sie unter [Führen einer Gruppenunterhaltung in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Wie gehe ich vor, wenn das Upgrade nicht funktioniert?

Verteilerlisten, für die beim Upgrade ein Fehler auftritt, bleiben unverändert.

Wenn für mindestens eine **geeignete** Verteilerliste beim Upgrade ein Fehler auftritt, öffnen Sie ein [Supportticket](../../business-video/get-help-support.md). Das Problem muss an das Gruppenentwicklungsteam eskaliert werden, damit dieses das Problem ermitteln kann.

Es ist möglich, dass die Verteilerliste aufgrund eines Dienstausfalls nicht aktualisiert wurde, aber unwahrscheinlich. Wenn Sie möchten, warten Sie eine Weile, und versuchen Sie dann erneut, die DL zu aktualisieren.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Verwenden von PowerShell zum gleichzeitigen Ausführen eines Upgrades mehrerer Verteilerlisten

Wenn Sie im Umgang mit PowerShell erfahren sind, können Sie diese Methode anstelle der Benutzeroberfläche verwenden. Wir verfügen über eine Reihe von Cmdlets, die Ihnen beim Upgrade von Verteilerlisten helfen. Siehe unten.

### <a name="upgrade-a-single-dl"></a>Upgrade einer einzelnen DL

Führen Sie den folgenden Befehl aus, um ein einzelnes DL zu aktualisieren:

```PowerShell
Upgrade-DistributionGroup -DlIdentities <Dl SMTP address>
```

Wenn Sie beispielsweise eine DL mit SMTP-Adresse dl1@contoso.com aktualisieren möchten, führen Sie den folgenden Befehl aus:

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> Sie können auch eine einzelne Verteilerliste auf eine Microsoft 365 Gruppe aktualisieren, indem Sie das [PowerShell-Cmdlet "New-UnifiedGroup"](/powershell/module/exchange/new-unifiedgroup) verwenden.

### <a name="upgrade-multiple-dls-in-a-batch"></a>Upgrade mehrerer DLs in einem Batch

Sie können auch mehrere DLs als Batch übergeben und gemeinsam aktualisieren:

```PowerShell
Upgrade-DistributionGroup -DlIdentities <DL SMTP address1>, <DL SMTP address2>,
<DL SMTP address3>, <DL SMTP address4>
```

Wenn Sie beispielsweise fünf DLs mit SMTP-Adresse aktualisieren möchten, führen Sie `dl1@contoso.com` `dl2@contoso.com` den folgenden Befehl `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` aus:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Aktualisieren aller berechtigten DLs

Es gibt zwei Möglichkeiten, um alle berechtigten DLs zu aktualisieren.

> [!NOTE]
> Das cmdlet Upgrade-DistributionGroup empfängt keine Daten aus der Pipeline. Aus diesem Grund muss der Operator "foreach-object" verwendet {} werden, um erfolgreich ausgeführt zu werden.

1. Rufen Sie die berechtigten DLs im Mandanten ab, und aktualisieren Sie sie mithilfe des Upgradebefehls:

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Rufen Sie die Liste aller DLs ab, und aktualisieren Sie nur die berechtigten DLs:

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Häufig gestellte Fragen zum Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen in Outlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>Welche Verteilerlisten können nicht aktualisiert werden?

Sie können nur für in der Cloud verwaltete, einfache, nicht geschachtelte Verteilerlisten ein Upgrade ausführen. In der folgenden Tabelle sind Verteilerlisten aufgeführt, die nicht aktualisiert werden **können.**

|**Eigenschaft**|**Geeignet?**|
|:-----|:-----|
|Lokal verwaltete Verteilerliste.  <br/> |Nein  <br/> |
|Geschachtelte Verteilerliste. Die Verteilerliste hat untergeordnete Gruppen oder ist Mitglied einer anderen Gruppe.  <br/> |Nein  <br/> |
|Verteilerlisten mit member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**  <br/> |Nein  <br/> |
|Verteilerliste mit mehr als 100 Besitzern  <br/> |Nein  <br/> |
|Verteilerliste, die nur Mitglieder, aber keinen Besitzer hat  <br/> |Nein  <br/> |
|Verteilerliste mit Alias mit Sonderzeichen  <br/> |Nein  <br/> |
|Die Verteilerliste ist als Weiterleitungsadresse für das freigegebene Postfach konfiguriert  <br/> |Nein  <br/> |
|Wenn die DL Teil der **Absendereinschränkung** in einer anderen DL ist.  <br/> |Nein  <br/> |
|Sicherheitsgruppen  <br/> |Nein  <br/> |
|Dynamische Verteilerlisten  <br/> |Nein  <br/> |
|Verteilerlisten, die in **RoomLists** konvertiert wurden  <br/> |Nein  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>Überprüfen, welche DLs für ein Upgrade berechtigt sind

Wenn Sie überprüfen möchten, ob eine DL berechtigt ist oder nicht, können Sie den folgenden Befehl ausführen:

`Get-DistributionGroup <DL SMTP address> | Get-EligibleDistributionGroupForMigration`

Wenn Sie überprüfen möchten, welche DLs für das Upgrade berechtigt sind, führen Sie einfach den folgenden Befehl aus:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Wer kann die Upgradeskripts ausführen?

Personen mit globalen Administratorrechten oder Exchange Administratorrechten.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Warum wird auf der Visitenkarte weiterhin eine Verteilerliste angezeigt? Was soll ich tun, um zu verhindern, dass eine aktualisierte Verteilerliste in meiner Liste mit automatischen Vorschlägen angezeigt wird?

- For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group. Die Visitenkarte des Empfängers entspricht der Visitenkarte der Verteilerliste. Der Grund hierfür liegt im Empfängercache oder "Spitznamen"-Cache von Outlook. Die E-Mail wird erfolgreich an die Gruppe gesendet, kann jedoch zu Verwirrung für den Absender führen.<br/>Sie können die Schritte in diesem Artikel ausführen, [Informationen zum Outlook AutoVervollständigen-Liste,](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) um den Cache zurückzusetzen, wodurch dieses Problem behoben wird.

- Für Outlook im Web: Bei Outlook im Web verbleibt der Empfänger der Verteilerliste weiterhin im Cache. Sie können die Schritte unter ["Vorgeschlagenen Namen oder E-Mail-Adresse entfernen" aus der AutoVervollständigen-Liste](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) ausführen, um den Cache zu aktualisieren, um die Visitenkarte der Gruppe anzuzeigen.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>Erhalten neue Gruppenmitglieder in ihrem Posteingang eine Willkommensnachricht?

Nein. Die Einstellung zum Aktivieren von Willkommensnachrichten ist standardmäßig auf FALSE festgelegt. Diese Einstellung wirkt sich auf vorhandene und neue Gruppenmitglieder aus, die beitreten können, nachdem die Migration abgeschlossen wurde. Wenn der Besitzer der Gruppe später Gastbenutzer zulässt, empfangen Gastbenutzer keine Willkommensnachricht in ihrem Posteingang. Gastmitglieder können weiterhin mit der Gruppe zusammenarbeiten.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Was geschieht, wenn eine oder einige der DLs nicht aktualisiert werden?

Es gibt einige Fälle, in denen DL zwar berechtigt ist, aber nicht aktualisiert werden konnte. Die DL wird nicht aktualisiert und bleibt als DL erhalten.

- Wenn der Administrator die **Gruppen-E-Mail-Adressrichtlinie** für die Gruppen in einer Organisation angewendet hat und versucht, DLs zu aktualisieren, die die Kriterien nicht erfüllen, wird die DL nicht aktualisiert.

- DLs, bei **denen "MemberJoinRestriction"** oder **"MemberDepartRestriction"** auf **"Closed"** festgelegt ist, konnten nicht aktualisiert werden.

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>Was geschieht mit der Verteilerliste, wenn beim Upgrade aus EAC ein Fehler auftritt?

Das Upgrade erfolgt nur, wenn der Aufruf an den Server übermittelt wird. Wenn beim Upgrade ein Fehler auftritt, bleiben Ihre Verteilerlisten erhalten. Sie funktionieren wie bisher.

## <a name="related-content"></a>Verwandte Inhalte

[Vergleichen von Gruppen](../create-groups/compare-groups.md) (Artikel)\
[Erläutern Microsoft 365 Gruppen für Ihre Benutzer](../create-groups/explain-groups-knowledge-worker.md) (Artikel)\
[Hinzufügen oder Entfernen von Mitgliedern aus Microsoft 365 Gruppen mithilfe des Admin Centers](../create-groups/add-or-remove-members-from-groups.md)
