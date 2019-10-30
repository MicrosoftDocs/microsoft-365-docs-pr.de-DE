---
title: Konfigurieren von Spambenachrichtigungen für Endbenutzer in EOP
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: Sie können Spambenachrichtigungen für Endbenutzer für die standardmäßige unternehmensweite Inhaltsfilterrichtlinie oder für benutzerdefinierte Inhaltsfilterrichtlinien, die auf Domänen angewendet werden, konfigurieren.
ms.openlocfilehash: d20186afaa25b70a40efa88f692a04f3428abb65
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772229"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a><span data-ttu-id="3bd3e-103">Konfigurieren von Spambenachrichtigungen für Endbenutzer in EOP</span><span class="sxs-lookup"><span data-stu-id="3bd3e-103">Configure end-user spam notifications in EOP</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3bd3e-104">Dieses Thema betrifft die Kunden einer eigenständigen Lösung von Exchange Online Protection (EOP), die lokale Postfächer schützen möchten.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-104">This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes.</span></span> <span data-ttu-id="3bd3e-105">Exchange Online Kunden, die in der Cloud gehostete Postfächer schützen, sollten stattdessen das folgende Thema lesen: [configure End-User Spam Notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="3bd3e-105">Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
<span data-ttu-id="3bd3e-p102">Sie können Spambenachrichtigungen für Endbenutzer für die standardmäßige unternehmensweite Inhaltsfilterrichtlinie oder für benutzerdefinierte Inhaltsfilterrichtlinien, die auf Domänen angewendet werden, konfigurieren. Wenn Sie Spambenachrichtigungen für Endbenutzer aktivieren, können Ihre Endbenutzer ihre Nachrichten in der Spamquarantäne selbst verwalten. Spambenachrichtigungen für Endbenutzer können nicht bei Richtlinien angewendet werden, die auf Benutzer oder Gruppen oder eine Richtlinie mit Ausnahmen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-p102">You can configure end-user spam notifications for the default company-wide content filter policy or for custom content filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="3bd3e-p103">Spambenachrichtigungen für Endbenutzer enthalten eine Liste aller Nachrichten in der Spamquarantäne, die der Endbenutzer in dem von Ihnen konfigurierten Zeitraum (zwischen 1 und 15 Tagen) erhalten hat. Sie können auch die Sprache festlegen, in der die Benachrichtigung geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="3bd3e-111">Nach dem Empfang einer Benachrichtigung können Endbenutzer eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="3bd3e-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="3bd3e-112">**Absender blockieren** , wenn Office 365 den Absender zu Ihrer Liste blockierter Absender hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-112">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="3bd3e-113">**Überprüfen** Sie, um zum Quarantäne Portal innerhalb des Security and Compliance Centers zu navigieren, wenn Sie andere Aktionen wie Preview oder Release durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-113">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3bd3e-114">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="3bd3e-114">What do you need to know before you begin?</span></span>
<span data-ttu-id="3bd3e-115"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="3bd3e-115"></span></span>

<span data-ttu-id="3bd3e-116">Geschätzte Zeit bis zum Abschließen des Vorgangs: 5 Minuten</span><span class="sxs-lookup"><span data-stu-id="3bd3e-116">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="3bd3e-p104">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Antispam" im Thema [Featureberechtigungen in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="3bd3e-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
  
<span data-ttu-id="3bd3e-119">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="3bd3e-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="3bd3e-120">Konfigurieren von Spambenachrichtigungen für Endbenutzer über die Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="3bd3e-120">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="3bd3e-121">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Schutz** > -**Spam Filter**.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-121">In the Exchange Admin Center (EAC), navigate to **Protection** > **Spam filter**.</span></span>
    
2. <span data-ttu-id="3bd3e-122">Wählen Sie die Inhaltsfilterrichtlinie aus, für die Sie Spambenachrichtigungen für Endbenutzer aktivieren möchten (sie sind standardmäßig deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="3bd3e-122">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="3bd3e-123">Klicken Sie im rechten Teilfenster, in dem eine Übersicht über Ihre Richtlinie angezeigt wird, auf den Link **Configure End-user spam notifications** (Spambenachrichtigungen für Endbenutzer konfigurieren).</span><span class="sxs-lookup"><span data-stu-id="3bd3e-123">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="3bd3e-124">Konfigurieren Sie im daraufhin angezeigten Dialogfeld die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="3bd3e-124">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="3bd3e-p105">**Enable end-user spam notifications** (Spambenachrichtigungen für Endbenutzer aktivieren) Markieren Sie dieses Kontrollkästchen, um Benachrichtigungen an Endbenutzer für diese Richtlinie zu aktivieren. (Wenn diese Richtlinie aktiviert ist, können Sie auf das Kontrollkästchen klicken, um Spambenachrichtigungen an Endbenutzer für diese Richtlinie zu deaktivieren.)</span><span class="sxs-lookup"><span data-stu-id="3bd3e-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="3bd3e-p106">**Send end-user spam notifications every (days)** (Spambenachrichtigungen an Endbenutzer senden alle ... Tage) Gibt an, wie oft Spambenachrichtigungen an Endbenutzer gesendet werden sollen. Der Standardwert beträgt 3 Tage. Sie können zwischen 1 und 15 Tagen angeben. Wenn Sie beispielsweise 7 Tage angeben, enthält die Benachrichtigung eine Liste aller Nachrichten der letzten 7 Tage für diesen Benutzer, die stattdessen in die Spamquarantäne verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="3bd3e-131">**Notification language** (Benachrichtigungssprache) Wählen Sie in der Dropdown-Liste die Sprache aus, in der Endbenutzer-Spambenachrichtigungen für diese Richtlinie geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-131">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="3bd3e-p107">Klicken Sie auf **Speichern**. Im Bereich auf der rechten Seite wird eine Zusammenfassung der Inhaltsfilter-Richtlinieneinstellungen angezeigt, einschließlich der Einstellungen für Endbenutzer-Spambenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-p107">Click **save**. A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="3bd3e-p108">Spambenachrichtigungen für Endbenutzer können nur bei Inhaltsfilterrichtlinien verwendet werden, die aktiviert sind. >  Spam Endbenutzerbenachrichtigungen sind nur einmal pro Tag versendet. Die Zustellungszeit der Benachrichtigung kann für einen bestimmten Kunden nicht garantiert werden und kann nicht konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-p108">End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="3bd3e-137">**Tipp:** Wenn Sie Spambenachrichtigungen für Endbenutzer testen möchten, indem Sie sie an eine begrenzte Gruppe von Benutzern senden, bevor Sie sie implementieren, erstellen Sie eine benutzerdefinierte Inhaltsfilterrichtlinie, die Spambenachrichtigungen für Endbenutzer für die Domänen aktiviert, in denen sich die Benutzer befinden.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-137">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="3bd3e-138">Erstellen Sie dann in der Exchange-Verwaltungskonsole unter **Nachrichtenfluss \> Regeln**eine Nachrichtenfluss Regel (auch als Transportregel bezeichnet), um Nachrichten von Quarantine@Messaging.Microsoft.com (die e-Mail-Adresse, die Benachrichtigungen sendet) mit Ausnahmen für die Benutzer zu blockieren, die Sie möchten. , um die Benachrichtigungen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="3bd3e-138">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="3bd3e-139">Die folgende Abbildung zeigt ein Beispiel für die Erstellung einer Ausnahme für zwei Benutzer (SaraD and AlexD) in der Domäne Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="3bd3e-139">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Transportregel zum Testen von Spambenachrichtigungen für Endbenutzer](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="3bd3e-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3bd3e-141">For more information</span></span>

[<span data-ttu-id="3bd3e-142">Konfigurieren von Spamfilterrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3bd3e-142">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
