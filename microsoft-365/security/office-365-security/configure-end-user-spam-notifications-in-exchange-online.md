---
title: Konfigurieren von Spambenachrichtigungen für Endbenutzer in Exchange Online
f1.keywords:
- NOCSH
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
ms.openlocfilehash: c8690a64e222bca2bbdc6be62d1077a9d361ae85
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341287"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="48841-103">Konfigurieren von Spambenachrichtigungen für Endbenutzer in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="48841-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48841-104">Dieses Thema richtet sich an Exchange Online-Kunden, die cloudgehostete Postfächer schützen.</span><span class="sxs-lookup"><span data-stu-id="48841-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="48841-105">Selbstständige Kunden mit Exchange Online Protection (EoP), die lokale Postfächer schützen, sollten stattdessen das folgende Thema lesen: [configure End-User Spam Notifications in EoP](configure-end-user-spam-notifications-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="48841-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="48841-106">Sie können Spambenachrichtigungen für Endbenutzer für die standardmäßige unternehmensweite Spamfilter Richtlinie oder für benutzerdefinierte Spamfilter Richtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="48841-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="48841-107">Durch die Aktivierung von Spambenachrichtigungen für Endbenutzer können Ihre Benutzer ihre eigenen isolierten Spam-, Massen-und Phishing-Nachrichten verwalten.</span><span class="sxs-lookup"><span data-stu-id="48841-107">Enabling end-user spam notification messages lets your users manage their own quarantined spam, bulk, and phishing messages.</span></span>   
  
<span data-ttu-id="48841-p103">Spambenachrichtigungen für Endbenutzer enthalten eine Liste aller Nachrichten in der Spamquarantäne, die der Endbenutzer in dem von Ihnen konfigurierten Zeitraum (zwischen 1 und 15 Tagen) erhalten hat. Sie können auch die Sprache festlegen, in der die Benachrichtigung geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="48841-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="48841-110">Nach dem Empfang einer Benachrichtigung können Endbenutzer eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="48841-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="48841-111">**Absender blockieren** , wenn Office 365 den Absender zu Ihrer Liste blockierter Absender hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="48841-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="48841-112">**Release** wenn es sich bei der Nachricht nicht um Spam handelt und Sie möchten, dass Office 365 die Nachricht an Ihr Postfach sendet.</span><span class="sxs-lookup"><span data-stu-id="48841-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="48841-113">**Überprüfen** Sie, um zum Quarantäne Portal im Sicherheits & Compliance Center zu navigieren, wenn Sie andere Aktionen wie Vorschau oder Release ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="48841-113">**Review** to navigate to the Quarantine Portal within the Security & Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="48841-114">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="48841-114">What do you need to know before you begin?</span></span>

<span data-ttu-id="48841-115">Geschätzte Zeit bis zum Abschließen des Vorgangs: 2 Minuten</span><span class="sxs-lookup"><span data-stu-id="48841-115">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="48841-116">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="48841-116">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="48841-117">Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Anti-Spam" im Thema [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) .</span><span class="sxs-lookup"><span data-stu-id="48841-117">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span> 
  
<span data-ttu-id="48841-118">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="48841-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="48841-119">Konfigurieren von Spambenachrichtigungen für Endbenutzer über die Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="48841-119">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="48841-120">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Schutz** \> **Spamfilter**.</span><span class="sxs-lookup"><span data-stu-id="48841-120">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="48841-121">Wählen Sie die Spamfilter Richtlinie aus, für die Sie Spambenachrichtigungen für Endbenutzer aktivieren möchten (Sie sind standardmäßig deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="48841-121">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="48841-122">Klicken Sie im rechten Teilfenster, in dem eine Übersicht über Ihre Richtlinie angezeigt wird, auf den Link **Configure End-user spam notifications** (Spambenachrichtigungen für Endbenutzer konfigurieren).</span><span class="sxs-lookup"><span data-stu-id="48841-122">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="48841-123">Konfigurieren Sie im daraufhin angezeigten Dialogfeld die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="48841-123">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="48841-p105">**Enable end-user spam notifications** (Spambenachrichtigungen für Endbenutzer aktivieren) Markieren Sie dieses Kontrollkästchen, um Benachrichtigungen an Endbenutzer für diese Richtlinie zu aktivieren. (Wenn diese Richtlinie aktiviert ist, können Sie auf das Kontrollkästchen klicken, um Spambenachrichtigungen an Endbenutzer für diese Richtlinie zu deaktivieren.)</span><span class="sxs-lookup"><span data-stu-id="48841-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="48841-p106">**Send end-user spam notifications every (days)** (Spambenachrichtigungen an Endbenutzer senden alle ... Tage) Gibt an, wie oft Spambenachrichtigungen an Endbenutzer gesendet werden sollen. Der Standardwert beträgt 3 Tage. Sie können zwischen 1 und 15 Tagen angeben. Wenn Sie beispielsweise 7 Tage angeben, enthält die Benachrichtigung eine Liste aller Nachrichten der letzten 7 Tage für diesen Benutzer, die stattdessen in die Spamquarantäne verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="48841-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="48841-130">**Notification language** (Benachrichtigungssprache) Wählen Sie in der Dropdown-Liste die Sprache aus, in der Endbenutzer-Spambenachrichtigungen für diese Richtlinie geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="48841-130">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="48841-131">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="48841-131">Click **Save**.</span></span> <span data-ttu-id="48841-132">Eine Zusammenfassung der Einstellungen für Spamfilter Richtlinien, einschließlich der Einstellungen für Spambenachrichtigungen für Endbenutzer, wird im rechten Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48841-132">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="48841-133">Spambenachrichtigungen für Endbenutzer sind nur für aktivierte Spamfilter Richtlinien funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="48841-133">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="48841-134">>  Spam Endbenutzerbenachrichtigungen sind nur einmal pro Tag versendet.</span><span class="sxs-lookup"><span data-stu-id="48841-134">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="48841-135">Die Zustellungszeit der Benachrichtigung kann für einen bestimmten Kunden nicht garantiert werden und kann nicht konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="48841-135">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="48841-136">**Tipp:** Wenn Sie Spambenachrichtigungen für Endbenutzer testen möchten, indem Sie Sie an eine beschränkte Gruppe von Benutzern senden, bevor Sie sie vollständig implementieren, erstellen Sie eine benutzerdefinierte Spamfilter Richtlinie, die Endbenutzer-Spambenachrichtigungen für die Domänen ermöglicht, in denen sich die Benutzer befinden.</span><span class="sxs-lookup"><span data-stu-id="48841-136">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="48841-137">Erstellen Sie dann in der Exchange-Verwaltungskonsole unter **Nachrichtenfluss \> Regeln**eine Nachrichtenfluss Regel (auch als Transportregel bezeichnet), um Nachrichten von Quarantine@Messaging.Microsoft.com (der e-Mail-Adresse, die Benachrichtigungen sendet) mit Ausnahmen für die Benutzer zu blockieren, die die Benachrichtigungen erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="48841-137">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="48841-138">Die folgende Abbildung zeigt ein Beispiel für die Erstellung einer Ausnahme für zwei Benutzer (SaraD and AlexD) in der Domäne Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="48841-138">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Transportregel zum Testen von Spambenachrichtigungen für Endbenutzer](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a><span data-ttu-id="48841-140">Konfigurieren von Spambenachrichtigungen für Endbenutzer mithilfe der SCC</span><span class="sxs-lookup"><span data-stu-id="48841-140">Use the SCC to configure end-user spam notifications</span></span>

<span data-ttu-id="48841-141">Sie können auch das Security and Compliance Center (SCC) verwenden, um Spambenachrichtigungen für Endbenutzer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="48841-141">You can also use the Security and Compliance Center (SCC) to configure end-user spam notifications.</span></span> <span data-ttu-id="48841-142">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="48841-142">Follow these steps:</span></span>

1. <span data-ttu-id="48841-143">Öffnen Sie das Security and Compliance Center, navigieren Sie zu **Threat Management** \> **Policy** \> **Anti-Spam** , oder verwenden https://protection.office.com/antispamSie den Direct Link.</span><span class="sxs-lookup"><span data-stu-id="48841-143">Open the Security and Compliance Center, navigate to **Threat management** \> **Policy** \> **Anti-spam** or use the direct link https://protection.office.com/antispam.</span></span>

2. <span data-ttu-id="48841-144">Klicken Sie auf den Pfeil nach unten neben der Spamfilter Richtlinie, für die Sie Spambenachrichtigungen für Endbenutzer aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="48841-144">Click the down arrow next to the spam filter policy for which you want to enable end-user spam notifications.</span></span>

3. <span data-ttu-id="48841-145">Klicken Sie auf den Link **Endbenutzer-Spambenachrichtigungen konfigurieren** .</span><span class="sxs-lookup"><span data-stu-id="48841-145">Click on the **Configure End-user spam notifications** link.</span></span>

4. <span data-ttu-id="48841-146">Konfigurieren Sie im daraufhin angezeigten Dialogfeld die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="48841-146">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="48841-p111">**Enable end-user spam notifications** (Spambenachrichtigungen für Endbenutzer aktivieren) Markieren Sie dieses Kontrollkästchen, um Benachrichtigungen an Endbenutzer für diese Richtlinie zu aktivieren. (Wenn diese Richtlinie aktiviert ist, können Sie auf das Kontrollkästchen klicken, um Spambenachrichtigungen an Endbenutzer für diese Richtlinie zu deaktivieren.)</span><span class="sxs-lookup"><span data-stu-id="48841-p111">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="48841-p112">**Send end-user spam notifications every (days)** (Spambenachrichtigungen an Endbenutzer senden alle ... Tage) Gibt an, wie oft Spambenachrichtigungen an Endbenutzer gesendet werden sollen. Der Standardwert beträgt 3 Tage. Sie können zwischen 1 und 15 Tagen angeben. Wenn Sie beispielsweise 7 Tage angeben, enthält die Benachrichtigung eine Liste aller Nachrichten der letzten 7 Tage für diesen Benutzer, die stattdessen in die Spamquarantäne verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="48841-p112">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="48841-153">**Notification language** (Benachrichtigungssprache) Wählen Sie in der Dropdown-Liste die Sprache aus, in der Endbenutzer-Spambenachrichtigungen für diese Richtlinie geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="48841-153">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="48841-154">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="48841-154">Click **Save**.</span></span> <span data-ttu-id="48841-155">Eine Zusammenfassung der Einstellungen für Spamfilter Richtlinien, einschließlich der Einstellungen für Spambenachrichtigungen für Endbenutzer, wird im Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48841-155">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the pane.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="48841-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48841-156">For more information</span></span>

[<span data-ttu-id="48841-157">Konfigurieren von Spamfilterrichtlinien</span><span class="sxs-lookup"><span data-stu-id="48841-157">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="48841-158">Gruppe-hostedcontentfilterpolicy dient zum</span><span class="sxs-lookup"><span data-stu-id="48841-158">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)
  
