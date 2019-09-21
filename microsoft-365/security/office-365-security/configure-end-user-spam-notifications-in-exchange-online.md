---
title: Konfigurieren von Spambenachrichtigungen für Endbenutzer in Exchange Online
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: Sie können Spambenachrichtigungen für Endbenutzer für die standardmäßige unternehmensweite Spamfilter Richtlinie oder für benutzerdefinierte Spamfilter Richtlinien konfigurieren, die auf Domänen angewendet werden.
ms.openlocfilehash: 1c2832110c98af07752ac7dc7fc985fcb75bc0dd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082133"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="74918-103">Konfigurieren von Spambenachrichtigungen für Endbenutzer in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="74918-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74918-104">Dieses Thema richtet sich an Exchange Online-Kunden, die cloudgehostete Postfächer schützen.</span><span class="sxs-lookup"><span data-stu-id="74918-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="74918-105">Selbstständige Kunden mit Exchange Online Protection (EoP), die lokale Postfächer schützen, sollten stattdessen das folgende Thema lesen: [configure End-User Spam Notifications in EoP](configure-end-user-spam-notifications-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="74918-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="74918-106">Sie können Spambenachrichtigungen für Endbenutzer für die standardmäßige unternehmensweite Spamfilter Richtlinie oder für benutzerdefinierte Spamfilter Richtlinien konfigurieren, die auf Domänen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="74918-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains.</span></span> <span data-ttu-id="74918-107">Wenn Sie Spambenachrichtigungen für Endbenutzer aktivieren, können Ihre Endbenutzer ihre Nachrichten in der Spamquarantäne selbst verwalten.</span><span class="sxs-lookup"><span data-stu-id="74918-107">Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages.</span></span> <span data-ttu-id="74918-108">Spambenachrichtigungen für Endbenutzer können nicht bei Richtlinien angewendet werden, die auf Benutzer oder Gruppen oder eine Richtlinie mit Ausnahmen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="74918-108">End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="74918-p103">Spambenachrichtigungen für Endbenutzer enthalten eine Liste aller Nachrichten in der Spamquarantäne, die der Endbenutzer in dem von Ihnen konfigurierten Zeitraum (zwischen 1 und 15 Tagen) erhalten hat. Sie können auch die Sprache festlegen, in der die Benachrichtigung geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="74918-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="74918-111">Nach dem Empfang einer Benachrichtigung können Endbenutzer eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="74918-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="74918-112">Zeigen Sie **eine Vorschau** der Nachricht an, wenn Sie eine Vorschau des Inhalts oder des Headers vor dem Ausführen der Aktion anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="74918-112">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

<span data-ttu-id="74918-113">**Laden** Sie die Nachricht herunter, wenn Sie die Nachricht und Anlagen (falls vorhanden) auf Ihrem Gerät überprüfen möchten, bevor Sie Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="74918-113">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

<span data-ttu-id="74918-114">**Release** wenn es sich bei der Nachricht nicht um Spam handelt und Sie möchten, dass Office 365 die Nachricht an Ihr Postfach sendet.</span><span class="sxs-lookup"><span data-stu-id="74918-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="74918-115">**Freigabe #a0 Absender zulassen** , wenn die Nachricht kein Spam ist, und Sie möchten, dass Office 365 den Absender zu Ihrer Liste sicherer Absender und Empfänger für zukünftige e-Mails hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="74918-115">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="74918-116">Beachten Sie, dass Ihr Administrator möglicherweise andere organisationsweite Allow/Block-Konfigurationen hat, die Ihre Liste sicherer Absender außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="74918-116">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

<span data-ttu-id="74918-117">Geben Sie **#a0 Bericht frei**, wenn es sich bei der Nachricht nicht um Spam handelt und Sie die Nachricht an Ihr Postfach senden und an Microsoft zur Analyse melden möchten.</span><span class="sxs-lookup"><span data-stu-id="74918-117">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

<span data-ttu-id="74918-118">**Blockieren** Sie, wenn Office 365 den Absender zu Ihrer Liste blockierter Absender hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="74918-118">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="74918-119">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="74918-119">What do you need to know before you begin?</span></span>

<span data-ttu-id="74918-120">Geschätzte Zeit bis zum Abschließen des Vorgangs: 2 Minuten</span><span class="sxs-lookup"><span data-stu-id="74918-120">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="74918-121">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="74918-121">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="74918-122">Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Anti-Spam" im Thema [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="74918-122">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="74918-123">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="74918-123">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="74918-124">Konfigurieren von Spambenachrichtigungen für Endbenutzer über die Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="74918-124">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="74918-125">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Schutz** \> **Spamfilter**.</span><span class="sxs-lookup"><span data-stu-id="74918-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="74918-126">Wählen Sie die Spamfilter Richtlinie aus, für die Sie Spambenachrichtigungen für Endbenutzer aktivieren möchten (Sie sind standardmäßig deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="74918-126">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="74918-127">Klicken Sie im rechten Teilfenster, in dem eine Übersicht über Ihre Richtlinie angezeigt wird, auf den Link **Configure End-user spam notifications** (Spambenachrichtigungen für Endbenutzer konfigurieren).</span><span class="sxs-lookup"><span data-stu-id="74918-127">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="74918-128">Konfigurieren Sie im daraufhin angezeigten Dialogfeld die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="74918-128">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="74918-p106">**Enable end-user spam notifications** (Spambenachrichtigungen für Endbenutzer aktivieren) Markieren Sie dieses Kontrollkästchen, um Benachrichtigungen an Endbenutzer für diese Richtlinie zu aktivieren. (Wenn diese Richtlinie aktiviert ist, können Sie auf das Kontrollkästchen klicken, um Spambenachrichtigungen an Endbenutzer für diese Richtlinie zu deaktivieren.)</span><span class="sxs-lookup"><span data-stu-id="74918-p106">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="74918-p107">**Send end-user spam notifications every (days)** (Spambenachrichtigungen an Endbenutzer senden alle ... Tage) Gibt an, wie oft Spambenachrichtigungen an Endbenutzer gesendet werden sollen. Der Standardwert beträgt 3 Tage. Sie können zwischen 1 und 15 Tagen angeben. Wenn Sie beispielsweise 7 Tage angeben, enthält die Benachrichtigung eine Liste aller Nachrichten der letzten 7 Tage für diesen Benutzer, die stattdessen in die Spamquarantäne verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="74918-p107">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="74918-135">**Notification language** (Benachrichtigungssprache) Wählen Sie in der Dropdown-Liste die Sprache aus, in der Endbenutzer-Spambenachrichtigungen für diese Richtlinie geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="74918-135">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="74918-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="74918-136">Click **save**.</span></span> <span data-ttu-id="74918-137">Eine Zusammenfassung der Einstellungen für Spamfilter Richtlinien, einschließlich der Einstellungen für Spambenachrichtigungen für Endbenutzer, wird im rechten Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74918-137">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="74918-138">Spambenachrichtigungen für Endbenutzer sind nur für aktivierte Spamfilter Richtlinien funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="74918-138">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="74918-139">>  Spam Endbenutzerbenachrichtigungen sind nur einmal pro Tag versendet.</span><span class="sxs-lookup"><span data-stu-id="74918-139">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="74918-140">Die Zustellungszeit der Benachrichtigung kann für einen bestimmten Kunden nicht garantiert werden und kann nicht konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="74918-140">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="74918-141">**Tipp:** Wenn Sie Spambenachrichtigungen für Endbenutzer testen möchten, indem Sie Sie an eine beschränkte Gruppe von Benutzern senden, bevor Sie sie vollständig implementieren, erstellen Sie eine benutzerdefinierte Spamfilter Richtlinie, die Endbenutzer-Spambenachrichtigungen für die Domänen ermöglicht, in denen sich die Benutzer befinden.</span><span class="sxs-lookup"><span data-stu-id="74918-141">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="74918-142">Erstellen Sie dann in der Exchange-Verwaltungskonsole unter **Nachrichtenfluss \> Regeln**eine Nachrichtenfluss Regel (auch als Transportregel bezeichnet), um Nachrichten von Quarantine@Messaging.Microsoft.com (die e-Mail-Adresse, die Benachrichtigungen sendet) mit Ausnahmen für die Benutzer zu blockieren, die Sie möchten. , um die Benachrichtigungen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="74918-142">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="74918-143">Die folgende Abbildung zeigt ein Beispiel für die Erstellung einer Ausnahme für zwei Benutzer (SaraD and AlexD) in der Domäne Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="74918-143">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Transportregel zum Testen von Spambenachrichtigungen für Endbenutzer](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="74918-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74918-145">For more information</span></span>

[<span data-ttu-id="74918-146">Konfigurieren von Spamfilterrichtlinien</span><span class="sxs-lookup"><span data-stu-id="74918-146">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
