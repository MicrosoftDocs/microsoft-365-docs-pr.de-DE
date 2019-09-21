---
title: Konfigurieren der Richtlinie für ausgehende Spamnachrichten
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Die Filterung ausgehender Spamnachrichten ist immer aktiviert, wenn Sie den Dienst für das Senden ausgehender E-Mails verwenden und dadurch Organisationen, die den Dienst nutzen, und ihre jeweiligen Empfänger schützen.
ms.openlocfilehash: 9c8c2f7e9ff0be02f11fa66409690cbb854d8c56
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081646"
---
# <a name="configure-the-outbound-spam-policy"></a><span data-ttu-id="371aa-103">Konfigurieren der Richtlinie für ausgehende Spamnachrichten</span><span class="sxs-lookup"><span data-stu-id="371aa-103">Configure the outbound spam policy</span></span>

<span data-ttu-id="371aa-p101">Die Filterung ausgehender Spamnachrichten ist immer aktiviert, wenn Sie den Dienst für das Senden ausgehender E-Mails verwenden und dadurch Organisationen, die den Dienst nutzen, und ihre jeweiligen Empfänger schützen. Ebenso wie die Filterung eingehender Nachrichten besteht die Filterung ausgehender Nachrichten aus einer Verbindungsfilterung und einer Inhaltsfilterung, wobei die Einstellungen für den ausgehenden Filter nicht konfiguriert werden können. Wenn eine ausgehende Nachricht als Spam identifiziert wird, wird sie durch den Pool für besonders riskante Zustellungen geleitet, der die Wahrscheinlichkeit reduziert, dass der normale Pool für ausgehende IP-Adressen einer Sperrliste hinzugefügt wird. Falls ein Kunde auch weiterhin ausgehende Spamnachrichten über den Dienst sendet, wird er für das Senden von Nachrichten gesperrt. Die Filterung ausgehender Spamnachrichten kann zwar nicht deaktiviert oder geändert werden, aber Sie können verschiedene unternehmensweite Spameinstellungen über die Standardrichtlinie für ausgehende Spamnachrichten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="371aa-p101">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients. Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable. If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list. If a customer continues to send outbound spam through the service, they will be blocked from sending messages. Although outbound spam filtering cannot be disabled or changed, you can configure several company-wide outbound spam settings via the default outbound spam policy.</span></span> 
  
<span data-ttu-id="371aa-109">Das folgende Video zeigt, wie die Richtlinie für ausgehende Spamnachrichten konfiguriert wird:</span><span class="sxs-lookup"><span data-stu-id="371aa-109">The following video shows how to configure the outbound spam policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
> [!NOTE]
> <span data-ttu-id="371aa-110">Für die besten Filterergebnisse sollte der Inhalt im Video oben mit einer ordnungsgemäßen Einrichtung und Vertrautheit mit [ausgehenden Spam Steuerelementen in Office 365](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="371aa-110">For the best filtering results, the content in the video above should used with a proper setup, and familiarity with [Outbound spam controls in Office 365](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="371aa-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="371aa-111">What do you need to know before you begin?</span></span>
<span data-ttu-id="371aa-112"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="371aa-112"></span></span>

<span data-ttu-id="371aa-113">Geschätzte Zeit bis zum Abschließen des Vorgangs: 5 Minuten</span><span class="sxs-lookup"><span data-stu-id="371aa-113">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="371aa-114">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="371aa-114">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="371aa-115">Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Antispam-Eintrag im [Feature Berechtigungen in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) Thema.</span><span class="sxs-lookup"><span data-stu-id="371aa-115">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="371aa-116">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="371aa-116">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
<span data-ttu-id="371aa-117">Das folgende Verfahren kann auch über Remote-PowerShell erfolgen.</span><span class="sxs-lookup"><span data-stu-id="371aa-117">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="371aa-118">Mit dem Cmdlet [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) können Sie Ihre Einstellungen überprüfen und mit dem Cmdlet [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) Ihre Einstellungen für ausgehende Spamnachrichten bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="371aa-118">Use the [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet to review your settings, and the [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) to edit your outbound spam policy settings.</span></span> <span data-ttu-id="371aa-119">Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online Protection herstellen, können Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290) nachlesen.</span><span class="sxs-lookup"><span data-stu-id="371aa-119">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span> <span data-ttu-id="371aa-120">Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online herstellen, können Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554) nachlesen.</span><span class="sxs-lookup"><span data-stu-id="371aa-120">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a><span data-ttu-id="371aa-121">Bearbeiten der Standardrichtlinie für ausgehende Spamnachrichten mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="371aa-121">Use the EAC to edit the default outbound spam policy</span></span>
<span data-ttu-id="371aa-122"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="371aa-122"></span></span>

<span data-ttu-id="371aa-123">Verwenden Sie das folgende Verfahren, um die Standardrichtlinie für ausgehende Spamnachrichten zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="371aa-123">Use the following procedure to edit the default outbound spam policy:</span></span>
  
### <a name="to-configure-the-default-outbound-spam-policy"></a><span data-ttu-id="371aa-124">So konfigurieren Sie die Standardrichtlinie für ausgehende Spamnachrichten</span><span class="sxs-lookup"><span data-stu-id="371aa-124">To configure the default outbound spam policy</span></span>

1. <span data-ttu-id="371aa-125">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Schutz** \> **Ausgehende Spamnachrichten**, und doppelklicken Sie dann auf die Standardrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="371aa-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Outbound spam**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="371aa-126">Wählen Sie die Menüoption **Einstellungen für ausgehenden Spam** aus.</span><span class="sxs-lookup"><span data-stu-id="371aa-126">Select the **Outbound spam preferences** menu option.</span></span> 
    
3. <span data-ttu-id="371aa-127">Aktivieren Sie folgende Kontrollkästchen für ausgehende Nachrichten, und geben Sie dann eine oder mehrere zugehörige E-Mail-Adressen in dem nebenstehenden Eingabefeld ein (es kann sich dabei um Verteilerlisten handelt, wenn diese gültige SMTP-Ziele ergeben):</span><span class="sxs-lookup"><span data-stu-id="371aa-127">Select the following check boxes pertaining to outbound messages, and then specify an associated email address or addresses in the accompanying input box (these can be distribution lists if they resolve as valid SMTP destinations):</span></span>
    
1. <span data-ttu-id="371aa-p104">**Eine Kopie aller verdächtigen ausgehenden E-Mails an folgende E-Mail-Adressen senden**. Dabei handelt es sich um Nachrichten, die vom Filter als Spam markiert wurden (unabhängig von der SCL-Bewertung). Sie werden vom Filter nicht zurückgewiesen, sondern durch den Pool für besonders riskante Zustellungen geleitet. Trennen Sie mehrere Adressen durch ein Semikolon. Beachten Sie, dass die angegebenen Empfänger die Nachrichten als "Bcc" (Blind Carbon Copy, nicht sichtbare Kopie) erhalten (in den Feldern "Von" und "An" sind der ursprüngliche Sender und Empfänger angegeben).</span><span class="sxs-lookup"><span data-stu-id="371aa-p104">**Send a copy of all suspicious outbound email messages to the following email address or addresses**. These are messages that are marked as spam by the filter (regardless of the SCL rating). They are not rejected by the filter but are routed through the higher risk delivery pool. Separate multiple addresses with a semicolon. Note that the recipients specified will receive the messages as a Blind carbon copy (Bcc) address (the From and To fields are the original sender and recipient).</span></span>
    
2. <span data-ttu-id="371aa-p105">**Senden Sie eine Benachrichtigung an die folgende E-Mail-Adresse, wenn ein Absender für das Senden ausgehender Spamnachrichten blockiert wird**. Trennen Sie mehrere Adressen durch ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="371aa-p105">**Send a notification to the following email address when a sender is blocked sending outbound spam**. Separate multiple addresses with a semicolon.</span></span>
    
    <span data-ttu-id="371aa-p106">Wenn eine auffällige Menge an Spamnachrichten von einem bestimmten Benutzer stammt, wird dieser Benutzer für das Senden von E-Mails gesperrt. Der Administrator der Domäne, der in dieser Einstellung angegeben ist, wird darüber informiert, dass ausgehende Nachrichten für diesen Benutzer blockiert werden. Ein Beispiel für diese Benachrichtigung finden Sie unter [Beispielbenachrichtigung, wenn ein Absender aufgrund des Versendens von ausgehendem Spam blockiert wird](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). Informationen zur erneuten Aktivierung finden Sie unter [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span><span class="sxs-lookup"><span data-stu-id="371aa-p106">When a significant amount of spam is originating from a particular user, the user is disabled from sending email messages. The administrator for the domain, who is specified using this setting, will be informed that outbound messages are blocked for this user. To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>
    
4. <span data-ttu-id="371aa-p107">Klicken Sie auf **Speichern**. Im Bereich auf der rechten Seite wird eine Zusammenfassung der Standardrichtlinieneinstellungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="371aa-p107">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="371aa-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="371aa-141">For more information</span></span>
<span data-ttu-id="371aa-142"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="371aa-142"></span></span>

[<span data-ttu-id="371aa-143">Pool für besonders riskante Zustellungen für ausgehende Nachrichten</span><span class="sxs-lookup"><span data-stu-id="371aa-143">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)
  
[<span data-ttu-id="371aa-144">Häufig gestellte Fragen zum Anti-Spam-Schutz</span><span class="sxs-lookup"><span data-stu-id="371aa-144">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

