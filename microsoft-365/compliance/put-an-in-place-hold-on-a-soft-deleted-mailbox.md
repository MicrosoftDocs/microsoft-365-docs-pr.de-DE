---
title: Einfügen eines In-situ für ein vorläufig gelöschtes Postfach in Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie einen In-Situ-Speicher für ein vorläufig gelöschtes Postfach erstellen können, damit es inaktiv wird und der Inhalt bewahrt wird.
ms.openlocfilehash: d72a5407bfafabed30466447e404cdd4196678ae
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226095"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Einfügen eines In-situ für ein vorläufig gelöschtes Postfach in Exchange Online

Erfahren Sie, wie Sie einen In-Situ-Speicher für ein vorläufig gelöschtes Postfach erstellen können, damit es inaktiv wird und der Inhalt bewahrt wird. Anschließend können Sie zum Durchsuchen des inaktiven Postfachs die Microsoft eDiscovery-Tools verwenden.

> [!IMPORTANT]
> Da wir weiterhin auf unterschiedliche Weise in die Aufbewahrung von Postfachinhalten investieren, kündigen wir die Einstellung von In-Place Haltebereichen im Exchange Admin Center (EAC) an. Ab dem 1. Juli 2020 können Sie keine neuen In-Place Haltebereiche in Exchange Online erstellen. Sie können jedoch weiterhin In-Place Haltebereiche im EAC oder mithilfe des Cmdlets **"Set-MailboxSearch"** in Exchange Online PowerShell verwalten. Ab dem 1. Oktober 2020 können Sie jedoch In-Place Haltebereiche nicht mehr verwalten. Sie werden nur im EAC oder mithilfe des Cmdlets **"Remove-MailboxSearch"** entfernt. Weitere Informationen zum Ausmustern von In-Place Haltebereichen finden Sie unter ["Ausmustern älterer eDiscovery-Tools".](legacy-ediscovery-retirement.md)

You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? Wenn der Aufbewahrungszeitraum für gelöschte Postfächer nicht abgelaufen ist, können Sie eine In-Place Aufbewahrung für das gelöschte Postfach (als vorläufig gelöschtes Postfach bezeichnet) festlegen und es als inaktives Postfach festlegen. An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. Nachdem das Postfach inaktiv gemacht wurde, können Sie das Postfach durchsuchen, indem Sie In-Place eDiscovery in Exchange Online, die Inhaltssuche im Security & Compliance Center oder das eDiscovery Center in SharePoint Online verwenden.

> [!NOTE]
> In Exchange Online ist ein vorläufig gelöschtes Postfach ein Postfach, das zwar gelöscht wurde, aber innerhalb eines bestimmten Aufbewahrungszeitraums wiederhergestellt werden kann. Dieser Aufbewahrungszeitraum für vorläufig gelöschte Postfächer beträgt in Exchange Online 30 Tage. Das bedeutet, dass das Postfach innerhalb von 30 Tagen nach dem vorläufigen Löschen wiederhergestellt werden kann. Nach 30 Tagen wird ein vorläufig gelöschtes Postfach für das dauerhafte Löschen markiert und kann dann nicht mehr wiederhergestellt oder inaktiviert werden.

## <a name="requirements-for-in-place-holds"></a>Anforderungen für In-Place Haltebereiche

- Sie müssen das **New-MailboxSearch** -Cmdlet in Windows PowerShell verwenden, um einen In-Situ-Speicher für ein vorläufig gelöschtes Postfach zu erstellen. Sie können nicht das Exchange-Verwaltungskonsole (EAC) oder das eDiscovery Center in SharePoint Online verwenden.

- Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online herstellen, können Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) nachlesen.

- Führen Sie den folgenden Befehl aus, um die Identitätsinformationen zu den vorläufig gelöschten Postfächern in Ihrer Organisation abzurufen.

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Weitere Informationen zu inaktiven Postfächern finden Sie unter [Übersicht über inaktive Postfächer in Office 365.](inactive-mailboxes-in-office-365.md)

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Erstellen eines In-Situ-Speichers für ein vorläufig gelöschtes Postfach, um daraus ein inaktives Postfach zu machen

Verwenden Sie das **New-MailboxSearch** -Cmdlet, um aus dem vorläufig gelöschten Postfach ein inaktives Postfach zu machen. Weitere Informationen finden Sie unter [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).

1. Erstellen Sie eine Variable, die die Eigenschaften des vorläufig gelöschten Postfachs enthält.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > Verwenden Sie im vorherigen Befehl den Wert der Eigenschaft **DistinguishedName** oder **ExchangeGuid** zum Identifizieren des vorläufig gelöschten Postfachs. Diese Eigenschaften sind für jedes Postfach in Ihrer Organisation eindeutig, wobei ein aktives und ein inaktives Postfach die gleiche primäre SMTP-Adresse haben können.

2. Erstellen Sie einen In-Situ-Speicher und wenden Sie ihn auf das vorläufig gelöschte Postfach an. In diesem Beispiel wird nicht angegeben, wie lange der Speicher aktiv sein soll. Das bedeutet, dass Elemente auf unbestimmte Zeit oder bis der In-Situ-Speicher für das inaktive Postfach entfernt wird, beibehalten werden.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   Beim Erstellen des In-Situ-Speichers können Sie auch eine Aufbewahrungsdauer angeben. In diesem Beispiel werden Elemente im inaktiven Postfach für ca. 7 Jahre aufbewahrt.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Führen Sie nach ein paar Augenblicken einen der folgenden Befehle aus, um sicherzustellen, dass es sich bei dem vorläufig gelöschten Postfach um ein inaktives Postfach handelt.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    Oder

   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Weitere Informationen

Nachdem Sie aus einem vorläufig gelöschten Postfach ein inaktives Postfach gemacht haben, gibt es eine Reihe von Methoden, mit denen Sie das Postfach verwalten können. Weitere Informationen finden Sie unter:

- [Ändern der Aufbewahrungsdauer für ein inaktives Postfach](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Wiederherstellen eines inaktiven Postfachs](recover-an-inactive-mailbox.md)

- [Rückspeichern eines inaktiven Postfachs](restore-an-inactive-mailbox.md)

- [Löschen eines inaktiven Postfachs](delete-an-inactive-mailbox.md) (durch Entfernen des Haltebereichs)