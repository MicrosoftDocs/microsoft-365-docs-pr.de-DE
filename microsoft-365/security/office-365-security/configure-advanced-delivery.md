---
title: Konfigurieren der Übermittlung von Phishingsimulationen von Drittanbietern an Benutzer und ungefilterte Nachrichten an SecOps-Postfächer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Administratoren können erfahren, wie Sie die erweiterte Übermittlungsrichtlinie in Exchange Online Protection (EOP) verwenden, um Nachrichten zu identifizieren, die in bestimmten unterstützten Szenarien (Phishingsimulationen von Drittanbietern und Nachrichten, die an Sicherheitsvorgänge (SecOps)-Postfächer übermittelt werden, nicht gefiltert werden sollten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d35c1f0c7abc7b6ce34fc9c2ec4d5fd5b228ae
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137739"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="366fb-103">Konfigurieren der Übermittlung von Phishingsimulationen von Drittanbietern an Benutzer und ungefilterte Nachrichten an SecOps-Postfächer</span><span class="sxs-lookup"><span data-stu-id="366fb-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="366fb-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="366fb-104">**Applies to**</span></span>
- [<span data-ttu-id="366fb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="366fb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="366fb-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="366fb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="366fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="366fb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="366fb-108">Das in diesem Artikel beschriebene Feature befindet sich in der Vorschau, ist nicht für alle verfügbar und kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="366fb-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="366fb-109">Um Ihre Organisation [standardmäßig zu schützen,](secure-by-default.md)lässt Exchange Online Protection (EOP) keine sicheren Listen oder Filterumgehungen für Nachrichten zu, die als Schadsoftware oder Phishing mit hoher Vertrauenswürdigkeit identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="366fb-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="366fb-110">Es gibt jedoch bestimmte Szenarien, die die Übermittlung ungefilterter Nachrichten erfordern.</span><span class="sxs-lookup"><span data-stu-id="366fb-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="366fb-111">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="366fb-111">For example:</span></span>

- <span data-ttu-id="366fb-112">**Phishingsimulationen von Drittanbietern:** Simulierte Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren, bevor sich ein tatsächlicher Angriff auf Ihre Organisation auswirkt.</span><span class="sxs-lookup"><span data-stu-id="366fb-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="366fb-113">**SecOps-Postfächer (Security Operations):** Dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um ungefilterte Nachrichten zu sammeln und zu analysieren (sowohl gute als auch schlechte).</span><span class="sxs-lookup"><span data-stu-id="366fb-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="366fb-114">Sie verwenden die _erweiterte Übermittlungsrichtlinie_ in Microsoft 365, um zu verhindern, dass diese Nachrichten _in diesen spezifischen Szenarien_ gefiltert werden. <sup>\*</sup> Die erweiterte Übermittlungsrichtlinie stellt sicher, dass Nachrichten in diesen Szenarien die folgenden Ergebnisse erzielen:</span><span class="sxs-lookup"><span data-stu-id="366fb-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="366fb-115">Filter in EOP und Microsoft Defender für Office 365 keine Aktion für diese Nachrichten ausführen.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="366fb-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="366fb-116">[Zero-Hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="366fb-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="366fb-117">[Standardsystemwarnungen](alerts.md) werden für diese Szenarien nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="366fb-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="366fb-118">[AIR und Clustering in Defender für Office 365](office-365-air.md) ignoriert diese Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="366fb-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="366fb-119">Speziell für Phishingsimulationen von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="366fb-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="366fb-120">[Administratorübermittlungen](admin-submission.md) generieren eine automatische Antwort, die besagt, dass die Nachricht Teil einer Phishingsimulationskampagne ist und keine echte Bedrohung ist.</span><span class="sxs-lookup"><span data-stu-id="366fb-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="366fb-121">Warnungen und AIR werden nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="366fb-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="366fb-122">[Tresor Links in Defender für Office 365](safe-links.md) blockieren oder detonieren die spezifisch identifizierten URLs in diesen Nachrichten nicht.</span><span class="sxs-lookup"><span data-stu-id="366fb-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="366fb-123">[Tresor Anlagen in Defender für Office 365](safe-attachments.md) detonieren anlagen in diesen Nachrichten nicht.</span><span class="sxs-lookup"><span data-stu-id="366fb-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="366fb-124"><sup>\*</sup> Sie können die Schadsoftwarefilterung oder ZAP für Schadsoftware nicht umgehen.</span><span class="sxs-lookup"><span data-stu-id="366fb-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="366fb-125">Nachrichten, die von der erweiterten Übermittlungsrichtlinie identifiziert werden, sind keine Sicherheitsbedrohungen, daher werden die Nachrichten als Systemüberschreibungen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="366fb-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="366fb-126">Administratoren können diese Systemüberschreibungen in den folgenden Umgebungen filtern und analysieren:</span><span class="sxs-lookup"><span data-stu-id="366fb-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="366fb-127">Bedrohungs-Explorer/Echtzeiterkennungen in Defender für Office 365 Plan 2</span><span class="sxs-lookup"><span data-stu-id="366fb-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="366fb-128">Die [Seite "E-Mail-Entität" im Bedrohungs-Explorer/Echtzeiterkennungen](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="366fb-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="366fb-129">Der [Statusbericht zum Bedrohungsschutz](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="366fb-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="366fb-130">Erweiterte Suche in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="366fb-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="366fb-131">Kampagnenansichten</span><span class="sxs-lookup"><span data-stu-id="366fb-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="366fb-132">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="366fb-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="366fb-133">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="366fb-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="366fb-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery> .</span><span class="sxs-lookup"><span data-stu-id="366fb-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="366fb-135">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="366fb-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="366fb-136">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="366fb-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="366fb-137">Um konfigurierte Einstellungen in der erweiterten Übermittlungsrichtlinie zu erstellen, zu ändern oder zu entfernen, müssen Sie Mitglied der **Rollengruppe "Sicherheitsadministrator"** im **Microsoft 365 Defender-Portal** und Mitglied der **Rollengruppe "Organisationsverwaltung"** in **Exchange Online** sein.</span><span class="sxs-lookup"><span data-stu-id="366fb-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>
  - <span data-ttu-id="366fb-138">Für den schreibgeschützten Zugriff auf die Erweiterte Übermittlungsrichtlinie müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.</span><span class="sxs-lookup"><span data-stu-id="366fb-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="366fb-139">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md) und [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="366fb-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="366fb-140">Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="366fb-140">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="366fb-141">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="366fb-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="366fb-142">Verwenden des Microsoft 365 Defender-Portals zum Konfigurieren von SecOps-Postfächern in der erweiterten Übermittlungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="366fb-142">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="366fb-143">Wechseln Sie im Microsoft 365 Defender Portal zur Seite **"E-Mail &** \> **Zusammenarbeitsrichtlinien & Richtlinien** für \> **Bedrohungsregeln"** im Abschnitt \>  \> **"Erweiterte Zustellung".**</span><span class="sxs-lookup"><span data-stu-id="366fb-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="366fb-144">Überprüfen Sie auf der Seite **"Erweiterte Zustellung",** ob die Registerkarte **"SecOps-Postfach"** ausgewählt ist, und führen Sie dann einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="366fb-144">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="366fb-145">Klicken Sie auf ![ ](../../media/m365-cc-sc-edit-icon.png) **"Bearbeiten"-Symbol**.</span><span class="sxs-lookup"><span data-stu-id="366fb-145">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="366fb-146">Wenn keine konfigurierten Phishingsimulationen vorhanden sind, klicken Sie auf **Hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="366fb-146">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="366fb-147">Geben Sie im Flyout **"SecOps-Postfächer bearbeiten",** das geöffnet wird, ein vorhandenes Exchange Online Postfach ein, das Sie als SecOps-Postfach festlegen möchten, indem Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="366fb-147">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="366fb-148">Klicken Sie in das Feld, lassen Sie die Liste der Postfächer auflösen, und wählen Sie dann das Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="366fb-148">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="366fb-149">Klicken Sie in das Feld, um einen Bezeichner für das Postfach (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.) einzugeben, und wählen Sie das Postfach (Anzeigename) aus den Ergebnissen aus.</span><span class="sxs-lookup"><span data-stu-id="366fb-149">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="366fb-150">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="366fb-150">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="366fb-151">Verteilergruppen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="366fb-151">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="366fb-152">Um einen vorhandenen Wert zu entfernen, klicken Sie auf das</span><span class="sxs-lookup"><span data-stu-id="366fb-152">To remove an existing value, click remove</span></span> ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="366fb-154">neben dem Wert.</span><span class="sxs-lookup"><span data-stu-id="366fb-154">next to the value.</span></span>

4. <span data-ttu-id="366fb-155">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="366fb-155">When you're finished, click **Save**.</span></span>

<span data-ttu-id="366fb-156">Die von Ihnen konfigurierten SecOps-Postfacheinträge werden auf der Registerkarte **"SecOps-Postfach"** angezeigt. Wenn Sie Änderungen vornehmen möchten, klicken Sie ![ auf der Registerkarte auf das ](../../media/m365-cc-sc-edit-icon.png) Bearbeitungssymbol **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="366fb-156">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="366fb-157">Verwenden des Microsoft 365 Defender Portals zum Konfigurieren von Phishingsimulationen von Drittanbietern in der erweiterten Übermittlungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="366fb-157">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="366fb-158">Wechseln Sie im Microsoft 365 Defender Portal zur Seite **"E-Mail &** \> **Zusammenarbeitsrichtlinien & Richtlinien** für \> **Bedrohungsregeln"** im Abschnitt \>  \> **"Erweiterte Zustellung".**</span><span class="sxs-lookup"><span data-stu-id="366fb-158">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="366fb-159">Wählen Sie auf der Seite **"Erweiterte Übermittlung"** die Registerkarte **"Phishingsimulation"** aus, und führen Sie dann einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="366fb-159">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="366fb-160">Klicken Sie auf ![ ](../../media/m365-cc-sc-edit-icon.png) **"Bearbeiten"-Symbol**.</span><span class="sxs-lookup"><span data-stu-id="366fb-160">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="366fb-161">Wenn keine konfigurierten Phishingsimulationen vorhanden sind, klicken Sie auf **Hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="366fb-161">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="366fb-162">Konfigurieren Sie im Flyout **"Phishingsimulation** von Drittanbietern bearbeiten", das geöffnet wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="366fb-162">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="366fb-163">**Sendende Domäne:** Erweitern Sie diese Einstellung, und geben Sie mindestens eine E-Mail-Adressdomäne (z. B. contoso.com) ein, indem Sie in das Feld klicken, einen Wert eingeben und dann die EINGABETASTE drücken oder den Wert auswählen, der unterhalb des Felds angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="366fb-163">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="366fb-164">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="366fb-164">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="366fb-165">Sie können bis zu 10 Einträge hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="366fb-165">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="366fb-166">**Senden der IP:** Erweitern Sie diese Einstellung, und geben Sie mindestens eine gültige IPv4-Adresse ein, indem Sie in das Feld klicken, einen Wert eingeben und dann die EINGABETASTE drücken oder den Wert auswählen, der unter dem Feld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="366fb-166">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="366fb-167">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="366fb-167">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="366fb-168">Sie können bis zu 10 Einträge hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="366fb-168">You can add up to 10 entries.</span></span> <span data-ttu-id="366fb-169">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="366fb-169">Valid values are:</span></span>
     - <span data-ttu-id="366fb-170">Single IP: For example, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="366fb-170">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="366fb-171">IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="366fb-171">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="366fb-172">CIDR-IP: Beispiel: 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="366fb-172">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="366fb-173">**Zuzulassende Simulations-URLs:** Erweitern Sie diese Einstellung, und geben Sie optional bestimmte URLs ein, die Teil Ihrer Phishingsimulationskampagne sind, die nicht blockiert oder detoniert werden soll, indem Sie in das Feld klicken, einen Wert eingeben und dann die EINGABETASTE drücken oder den Wert auswählen, der unter dem Feld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="366fb-173">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="366fb-174">Sie können bis zu 10 Einträge hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="366fb-174">You can add up to 10 entries.</span></span>

   <span data-ttu-id="366fb-175">Um einen vorhandenen Wert zu entfernen, klicken Sie auf das</span><span class="sxs-lookup"><span data-stu-id="366fb-175">To remove an existing value, click remove</span></span> ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="366fb-177">neben dem Wert.</span><span class="sxs-lookup"><span data-stu-id="366fb-177">next to the value.</span></span>

4. <span data-ttu-id="366fb-178">Wenn Sie fertig sind, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="366fb-178">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="366fb-179">**First time**: Click **Add**, and then click **Close**.</span><span class="sxs-lookup"><span data-stu-id="366fb-179">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="366fb-180">**Vorhandenes bearbeiten:** Klicken Sie auf **"Speichern"** und dann auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="366fb-180">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="366fb-181">Die von Ihnen konfigurierten Einträge für Phishingsimulationen von Drittanbietern werden auf der Registerkarte **"Phishingsimulation"** angezeigt. Wenn Sie Änderungen vornehmen möchten, klicken Sie ![ auf der Registerkarte auf das ](../../media/m365-cc-sc-edit-icon.png) Bearbeitungssymbol **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="366fb-181">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="366fb-182">Zusätzliche Szenarien, für die eine Filterumgehung erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="366fb-182">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="366fb-183">Zusätzlich zu den beiden Szenarien, die Ihnen mit der erweiterten Übermittlungsrichtlinie helfen können, gibt es weitere Szenarien, in denen Sie die Filterung umgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="366fb-183">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="366fb-184">**Filter von Drittanbietern:** Wenn der MX-Eintrag Ihrer Domäne *nicht* auf Office 365 verweist (Nachrichten werden zuerst an eine andere Stelle weitergeleitet), ist [die Standardmäßige Sicherheit](secure-by-default.md) nicht *verfügbar.*</span><span class="sxs-lookup"><span data-stu-id="366fb-184">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span> <span data-ttu-id="366fb-185">Wenn Sie Schutz hinzufügen möchten, müssen Sie die erweiterte Filterung für Connectors aktivieren (auch als *Skip-Eintrag* bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="366fb-185">If you'd like to add protection, you'll need to enable Enhanced Filtering for Connectors (also known as *skip listing*).</span></span> <span data-ttu-id="366fb-186">Weitere Informationen finden Sie unter Verwalten des [Nachrichtenflusses mithilfe eines Clouddiensts eines Drittanbieters mit Exchange Online.](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)</span><span class="sxs-lookup"><span data-stu-id="366fb-186">For more information, see [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span> <span data-ttu-id="366fb-187">Wenn Sie die erweiterte Filterung für Connectors nicht wünschen, verwenden Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet), um die Microsoft-Filterung für Nachrichten zu umgehen, die bereits von der Drittanbieterfilterung ausgewertet wurden.</span><span class="sxs-lookup"><span data-stu-id="366fb-187">If you don't want Enhanced Filtering for Connectors,use mail flow rules (also known as transport rules) to bypass Microsoft filtering for messages that have already been evaluated by third-party filtering.</span></span> <span data-ttu-id="366fb-188">Weitere Informationen finden Sie unter [Verwenden von Nachrichtenflussregeln, um die SCL in Nachrichten festzulegen.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)</span><span class="sxs-lookup"><span data-stu-id="366fb-188">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="366fb-189">**Falsch positive Ergebnisse, die überprüft** werden: Möglicherweise möchten Sie bestimmten Nachrichten, die noch von Microsoft über [Administratorübermittlungen](admin-submission.md) analysiert werden, vorübergehend gestatten, bekannte gute Nachrichten zu melden, die fälschlicherweise als falsch für Microsoft gekennzeichnet sind (falsch positive Ergebnisse).</span><span class="sxs-lookup"><span data-stu-id="366fb-189">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="366fb-190">Wie bei allen Außerkraftsetzungen wird **_dringend empfohlen,_** dass diese Außerkraftsetzungen temporär sind.</span><span class="sxs-lookup"><span data-stu-id="366fb-190">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="366fb-191">Exchange Online PowerShell-Verfahren für SecOps-Postfächer in der erweiterten Übermittlungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="366fb-191">Exchange Online PowerShell procedures for SecOps mailboxes in the advanced delivery policy</span></span>

<span data-ttu-id="366fb-192">In Exchange Online PowerShell sind die grundlegenden Elemente von SecOps-Postfächern in der erweiterten Übermittlungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="366fb-192">In Exchange Online PowerShell, the basic elements of SecOps mailboxes in the advanced delivery policy are:</span></span>

- <span data-ttu-id="366fb-193">**Die SecOps-Außerkraftsetzungsrichtlinie:** Gesteuert von den **\* -SecOpsOverridePolicy-Cmdlets.**</span><span class="sxs-lookup"><span data-stu-id="366fb-193">**The SecOps override policy**: Controlled by the **\*-SecOpsOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="366fb-194">**Die SecOps-Überschreibungsregel:** Gesteuert von den **\* -SecOpsOverrideRule-Cmdlets.**</span><span class="sxs-lookup"><span data-stu-id="366fb-194">**The SecOps override rule**: Controlled by the **\*-SecOpsOverrideRule** cmdlets.</span></span>

<span data-ttu-id="366fb-195">Dieses Verhalten hat die folgenden Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="366fb-195">This behavior has the following results:</span></span>

- <span data-ttu-id="366fb-196">Sie erstellen zuerst die Richtlinie, dann die Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="366fb-196">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="366fb-197">Wenn Sie eine Richtlinie aus PowerShell entfernen, wird auch die entsprechende Regel entfernt.</span><span class="sxs-lookup"><span data-stu-id="366fb-197">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="366fb-198">Wenn Sie eine Regel aus PowerShell entfernen, wird die entsprechende Richtlinie nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="366fb-198">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="366fb-199">Sie müssen die entsprechende Richtlinie manuell entfernen.</span><span class="sxs-lookup"><span data-stu-id="366fb-199">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-secops-mailboxes"></a><span data-ttu-id="366fb-200">Verwenden von PowerShell zum Konfigurieren von SecOps-Postfächern</span><span class="sxs-lookup"><span data-stu-id="366fb-200">Use PowerShell to configure SecOps mailboxes</span></span>

<span data-ttu-id="366fb-201">Das Konfigurieren eines SecOps-Postfachs in der erweiterten Übermittlungsrichtlinie in PowerShell besteht aus zwei Schritten:</span><span class="sxs-lookup"><span data-stu-id="366fb-201">Configuring a SecOps mailbox in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="366fb-202">Erstellen Sie die SecOps-Außerkraftsetzungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="366fb-202">Create the SecOps override policy.</span></span>
2. <span data-ttu-id="366fb-203">Erstellen Sie die SecOps-Überschreibungsregel, die die Richtlinie angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="366fb-203">Create the SecOps override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a><span data-ttu-id="366fb-204">Schritt 1: Verwenden von PowerShell zum Erstellen der SecOps-Außerkraftsetzungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="366fb-204">Step 1: Use PowerShell to create the SecOps override policy</span></span>

<span data-ttu-id="366fb-205">Verwenden Sie die folgende Syntax, um die SecOps-Außerkraftsetzungsrichtlinie zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="366fb-205">To create the SecOps override policy, use the following syntax:</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

<span data-ttu-id="366fb-206">**Hinweis:** Unabhängig vom angegebenen Namenswert lautet der Richtlinienname SecOpsOverridePolicy, daher können Sie diesen Wert auch verwenden.</span><span class="sxs-lookup"><span data-stu-id="366fb-206">**Note**: Regardless of the Name value you specify, the policy name will be SecOpsOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="366fb-207">In diesem Beispiel wird die SecOps-Postfachrichtlinie erstellt.</span><span class="sxs-lookup"><span data-stu-id="366fb-207">This example creates the SecOps mailbox policy.</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SendTo secops@contoso.com
```

<span data-ttu-id="366fb-208">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="366fb-208">For detailed syntax and parameter information, see [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a><span data-ttu-id="366fb-209">Schritt 2: Verwenden von PowerShell zum Erstellen der SecOps-Überschreibungsregel</span><span class="sxs-lookup"><span data-stu-id="366fb-209">Step 2: Use PowerShell to create the SecOps override rule</span></span>

<span data-ttu-id="366fb-210">In diesem Beispiel wird die SecOps-Postfachregel mit den angegebenen Einstellungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="366fb-210">This example creates the SecOps mailbox rule with the specified settings.</span></span>

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

<span data-ttu-id="366fb-211">\*\*Hinweis:\*\*\*\*Unabhängig vom angegebenen Namenswert lautet der Regelname SecOpsOverrideRule, wobei es sich um \<GUID\> \<GUID\> einen eindeutigen GUID-Wert handelt (z. B. 6fed4b63-3563-495d-a481-b24a311f8329).</span><span class="sxs-lookup"><span data-stu-id="366fb-211">**Note**: \*\*Regardless of the Name value you specify, the rule name will be SecOpsOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, 6fed4b63-3563-495d-a481-b24a311f8329).</span></span>

<span data-ttu-id="366fb-212">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span><span class="sxs-lookup"><span data-stu-id="366fb-212">For detailed syntax and parameter information, see [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span></span>

### <a name="use-powershell-to-view-the-secops-override-policy"></a><span data-ttu-id="366fb-213">Verwenden von PowerShell zum Anzeigen der SecOps-Überschreibungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="366fb-213">Use PowerShell to view the SecOps override policy</span></span>

<span data-ttu-id="366fb-214">In diesem Beispiel werden detaillierte Informationen zu der einzigen SecOps-Postfachrichtlinie zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="366fb-214">This example returns detailed information about the one and only SecOps mailbox policy.</span></span>

```powershell
Get-SecOpsOverridePolicy
```

<span data-ttu-id="366fb-215">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SecOpsOverridePolicy".](/powershell/module/exchange/get-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="366fb-215">For detailed syntax and parameter information, see [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-view-secops-override-rules"></a><span data-ttu-id="366fb-216">Verwenden von PowerShell zum Anzeigen von SecOps-Überschreibungsregeln</span><span class="sxs-lookup"><span data-stu-id="366fb-216">Use PowerShell to view SecOps override rules</span></span>

<span data-ttu-id="366fb-217">In diesem Beispiel werden detaillierte Informationen zu SecOps-Überschreibungsregeln zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="366fb-217">This example returns detailed information about SecOps override rules.</span></span>

```powershell
Get-SecOpsOverrideRule
```

<span data-ttu-id="366fb-218">Obwohl der vorherige Befehl nur eine Regel zurückgeben sollte, können alle Regeln, die gelöscht werden müssen, auch in die Ergebnisse einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="366fb-218">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="366fb-219">In diesem Beispiel werden die gültige Regel (eine) und alle ungültigen Regeln identifiziert.</span><span class="sxs-lookup"><span data-stu-id="366fb-219">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="366fb-220">Nachdem Sie die ungültigen Regeln identifiziert haben, können Sie sie mithilfe des Cmdlets **Remove-SecOpsOverrideRule** entfernen, wie [weiter unten in diesem Artikel](#use-powershell-to-remove-secops-override-rules)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="366fb-220">After you identify the invalid rules, you can remove them by using the **Remove-SecOpsOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-secops-override-rules).</span></span>

<span data-ttu-id="366fb-221">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SecOpsOverrideRule"](/powershell/module/exchange/get-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="366fb-221">For detailed syntax and parameter information, see [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span></span>

### <a name="use-powershell-to-modify-the-secops-override-policy"></a><span data-ttu-id="366fb-222">Verwenden von PowerShell zum Ändern der SecOps-Überschreibungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="366fb-222">Use PowerShell to modify the SecOps override policy</span></span>

<span data-ttu-id="366fb-223">Verwenden Sie die folgende Syntax, um die SecOps-Außerkraftsetzungsrichtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="366fb-223">To modify the SecOps override policy, use the following syntax:</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

<span data-ttu-id="366fb-224">In diesem Beispiel wird der SecOps-Überschreibungsrichtlinie secops2@contoso.com hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="366fb-224">This example adds secops2@contoso.com to the SecOps override policy.</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

<span data-ttu-id="366fb-225">**Hinweis:** Wenn eine zugeordnete, gültige SecOps-Außerkraftsetzungsregel vorhanden ist, werden auch die E-Mail-Adressen in der Regel aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="366fb-225">**Note**: If an associated, valid SecOps override rule exists, the email addresses in the rule will also be updated.</span></span>

<span data-ttu-id="366fb-226">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SecOpsOverridePolicy".](/powershell/module/exchange/set-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="366fb-226">For detailed syntax and parameter information, see [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-secops-override-rule"></a><span data-ttu-id="366fb-227">Verwenden von PowerShell zum Ändern einer SecOps-Überschreibungsregel</span><span class="sxs-lookup"><span data-stu-id="366fb-227">Use PowerShell to modify a SecOps override rule</span></span>

<span data-ttu-id="366fb-228">Das Cmdlet **"Set-SecOpsOverrideRule"** ändert die E-Mail-Adressen in der SecOps-Überschreibungsregel nicht.</span><span class="sxs-lookup"><span data-stu-id="366fb-228">The **Set-SecOpsOverrideRule** cmdlet does not modify the email addresses in the SecOps override rule.</span></span> <span data-ttu-id="366fb-229">Verwenden Sie das Cmdlet **"Set-SecOpsOverridePolicy", um die E-Mail-Adressen in der SecOps-Überschreibungsregel zu** ändern.</span><span class="sxs-lookup"><span data-stu-id="366fb-229">To modify the email addresses in the SecOps override rule, use the **Set-SecOpsOverridePolicy** cmdlet.</span></span>

<span data-ttu-id="366fb-230">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SecOpsOverrideRule".](/powershell/module/exchange/set-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="366fb-230">For detailed syntax and parameter information, see [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span></span>

### <a name="use-powershell-to-remove-the-secops-override-policy"></a><span data-ttu-id="366fb-231">Verwenden von PowerShell zum Entfernen der SecOps-Überschreibungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="366fb-231">Use PowerShell to remove the SecOps override policy</span></span>

<span data-ttu-id="366fb-232">In diesem Beispiel werden die SecOps-Postfachrichtlinie und die entsprechende Regel entfernt.</span><span class="sxs-lookup"><span data-stu-id="366fb-232">This example removes the SecOps Mailbox policy and the corresponding rule.</span></span>

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

<span data-ttu-id="366fb-233">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="366fb-233">For detailed syntax and parameter information, see [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-secops-override-rules"></a><span data-ttu-id="366fb-234">Verwenden von PowerShell zum Entfernen von SecOps-Überschreibungsregeln</span><span class="sxs-lookup"><span data-stu-id="366fb-234">Use PowerShell to remove SecOps override rules</span></span>

<span data-ttu-id="366fb-235">Verwenden Sie die folgende Syntax, um eine SecOps-Überschreibungsregel zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="366fb-235">To remove a SecOps override rule, use the following syntax:</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="366fb-236">In diesem Beispiel wird die angegebene SecOps-Überschreibungsregel entfernt.</span><span class="sxs-lookup"><span data-stu-id="366fb-236">This example removes the specified SecOps override rule.</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

<span data-ttu-id="366fb-237">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span><span class="sxs-lookup"><span data-stu-id="366fb-237">For detailed syntax and parameter information, see [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span></span>

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="366fb-238">Exchange Online PowerShell-Verfahren für Phishingsimulationen von Drittanbietern in der erweiterten Übermittlungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="366fb-238">Exchange Online PowerShell procedures for third-party phishing simulations in the advanced delivery policy</span></span>

<span data-ttu-id="366fb-239">In Exchange Online PowerShell sind die grundlegenden Elemente von Phishingsimulationen von Drittanbietern in der erweiterten Übermittlungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="366fb-239">In Exchange Online PowerShell, the basic elements of third-party phishing simulations in the advanced delivery policy are:</span></span>

- <span data-ttu-id="366fb-240">**Die Richtlinie zur Außerkraftsetzung der Phishingsimulation:** Gesteuert von den Cmdlets **\* "-PhishSimOverridePolicy".**</span><span class="sxs-lookup"><span data-stu-id="366fb-240">**The phishing simulation override policy**: Controlled by the **\*-PhishSimOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="366fb-241">**Die Überschreibungsregel für die Phishingsimulation:** Gesteuert von den **\* -PhishSimOverrideRule-Cmdlets.**</span><span class="sxs-lookup"><span data-stu-id="366fb-241">**The phishing simulation override rule**: Controlled by the **\*-PhishSimOverrideRule** cmdlets.</span></span>

<span data-ttu-id="366fb-242">Dieses Verhalten hat die folgenden Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="366fb-242">This behavior has the following results:</span></span>

- <span data-ttu-id="366fb-243">Sie erstellen zuerst die Richtlinie, dann die Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="366fb-243">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="366fb-244">Sie ändern die Einstellungen in der Richtlinie und der Regel separat.</span><span class="sxs-lookup"><span data-stu-id="366fb-244">You modify the settings in the policy and the rule separately.</span></span>
- <span data-ttu-id="366fb-245">Wenn Sie eine Richtlinie aus PowerShell entfernen, wird auch die entsprechende Regel entfernt.</span><span class="sxs-lookup"><span data-stu-id="366fb-245">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="366fb-246">Wenn Sie eine Regel aus PowerShell entfernen, wird die entsprechende Richtlinie nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="366fb-246">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="366fb-247">Sie müssen die entsprechende Richtlinie manuell entfernen.</span><span class="sxs-lookup"><span data-stu-id="366fb-247">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a><span data-ttu-id="366fb-248">Verwenden von PowerShell zum Konfigurieren von Phishingsimulationen von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="366fb-248">Use PowerShell to configure third-party phishing simulations</span></span>

<span data-ttu-id="366fb-249">Das Konfigurieren einer Phishingsimulation eines Drittanbieters in der erweiterten Übermittlungsrichtlinie in PowerShell besteht aus zwei Schritten:</span><span class="sxs-lookup"><span data-stu-id="366fb-249">Configuring a third-party phishing simulation in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="366fb-250">Erstellen Sie die Richtlinie für die Außerkraftsetzung der Phishingsimulation.</span><span class="sxs-lookup"><span data-stu-id="366fb-250">Create the phishing simulation override policy.</span></span>
2. <span data-ttu-id="366fb-251">Erstellen Sie die Überschreibungsregel für die Phishingsimulation, die die Richtlinie angibt, für die die Regel gilt.</span><span class="sxs-lookup"><span data-stu-id="366fb-251">Create the phishing simulation override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a><span data-ttu-id="366fb-252">Schritt 1: Verwenden von PowerShell zum Erstellen der Richtlinie zur Außerkraftsetzung der Phishingsimulation</span><span class="sxs-lookup"><span data-stu-id="366fb-252">Step 1: Use PowerShell to create the phishing simulation override policy</span></span>

<span data-ttu-id="366fb-253">In diesem Beispiel wird die Richtlinie für die Außerkraftsetzung der Phishingsimulation erstellt.</span><span class="sxs-lookup"><span data-stu-id="366fb-253">This example creates the phishing simulation override policy.</span></span>

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

<span data-ttu-id="366fb-254">**Hinweis:** Unabhängig vom angegebenen Namenswert lautet der Richtlinienname PhishSimOverridePolicy, daher können Sie diesen Wert auch verwenden.</span><span class="sxs-lookup"><span data-stu-id="366fb-254">**Note**: Regardless of the Name value you specify, the policy name will be PhishSimOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="366fb-255">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="366fb-255">For detailed syntax and parameter information, see [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a><span data-ttu-id="366fb-256">Schritt 2: Verwenden von PowerShell zum Erstellen der Außerkraftsetzungsregel für Phishingsimulationen</span><span class="sxs-lookup"><span data-stu-id="366fb-256">Step 2: Use PowerShell to create the phishing simulation override rule</span></span>

<span data-ttu-id="366fb-257">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="366fb-257">Use the following syntax:</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

<span data-ttu-id="366fb-258">Unabhängig vom angegebenen Namenswert lautet der Regelname PhishSimOverrideRule, wobei es sich um \<GUID\> \<GUID\> einen eindeutigen GUID-Wert handelt (z. B. a0eae53e-d755-4a42-9320-b9c6b55c5011).</span><span class="sxs-lookup"><span data-stu-id="366fb-258">Regardless of the Name value you specify, the rule name will be PhishSimOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span></span>

<span data-ttu-id="366fb-259">Ein gültiger IP-Adresseintrag ist einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="366fb-259">A valid IP address entry is one of the following values:</span></span>

- <span data-ttu-id="366fb-260">Single IP: For example, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="366fb-260">Single IP: For example, 192.168.1.1.</span></span>
- <span data-ttu-id="366fb-261">IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="366fb-261">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
- <span data-ttu-id="366fb-262">CIDR-IP: Beispiel: 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="366fb-262">CIDR IP: For example, 192.168.0.1/25.</span></span>

<span data-ttu-id="366fb-263">In diesem Beispiel wird die Überschreibungsregel für die Phishingsimulation mit den angegebenen Einstellungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="366fb-263">This example creates the phishing simulation override rule with the specified settings.</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

<span data-ttu-id="366fb-264">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="366fb-264">For detailed syntax and parameter information, see [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a><span data-ttu-id="366fb-265">Verwenden von PowerShell zum Anzeigen der Richtlinie zur Außerkraftsetzung der Phishingsimulation</span><span class="sxs-lookup"><span data-stu-id="366fb-265">Use PowerShell to view the phishing simulation override policy</span></span>

<span data-ttu-id="366fb-266">In diesem Beispiel werden detaillierte Informationen zu der einzigen Außerkraftsetzungsrichtlinie für Phishingsimulationen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="366fb-266">This example returns detailed information about the one and only phishing simulation override policy.</span></span>

```powershell
Get-PhishSimOverridePolicy
```

<span data-ttu-id="366fb-267">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-PhishSimOverridePolicy".](/powershell/module/exchange/get-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="366fb-267">For detailed syntax and parameter information, see [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a><span data-ttu-id="366fb-268">Verwenden von PowerShell zum Anzeigen von Überschreibungsregeln für Phishingsimulationen</span><span class="sxs-lookup"><span data-stu-id="366fb-268">Use PowerShell to view phishing simulation override rules</span></span>

<span data-ttu-id="366fb-269">In diesem Beispiel werden detaillierte Informationen zu Überschreibungsregeln für Phishingsimulationen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="366fb-269">This example returns detailed information about phishing simulation override rules.</span></span>

```powershell
Get-PhishSimOverrideRule
```

<span data-ttu-id="366fb-270">Obwohl der vorherige Befehl nur eine Regel zurückgeben sollte, können alle Regeln, die gelöscht werden müssen, auch in die Ergebnisse einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="366fb-270">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="366fb-271">In diesem Beispiel werden die gültige Regel (eine) und alle ungültigen Regeln identifiziert.</span><span class="sxs-lookup"><span data-stu-id="366fb-271">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="366fb-272">Nachdem Sie die ungültigen Regeln identifiziert haben, können Sie sie mithilfe des Cmdlets **Remove-PhisSimOverrideRule** entfernen, wie [weiter unten in diesem Artikel](#use-powershell-to-remove-phishing-simulation-override-rules)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="366fb-272">After you identify the invalid rules, you can remove them by using the **Remove-PhisSimOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-phishing-simulation-override-rules).</span></span>

<span data-ttu-id="366fb-273">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-PhishSimOverrideRule".](/powershell/module/exchange/get-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="366fb-273">For detailed syntax and parameter information, see [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a><span data-ttu-id="366fb-274">Verwenden von PowerShell zum Ändern der Richtlinie für die Außerkraftsetzung der Phishingsimulation</span><span class="sxs-lookup"><span data-stu-id="366fb-274">Use PowerShell to modify the phishing simulation override policy</span></span>

<span data-ttu-id="366fb-275">Verwenden Sie die folgende Syntax, um die Richtlinie für die Außerkraftsetzung der Phishingsimulation zu ändern:</span><span class="sxs-lookup"><span data-stu-id="366fb-275">To modify the phishing simulation override policy, use the following syntax:</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="366fb-276">In diesem Beispiel wird die Richtlinie für die Außerkraftsetzung der Phishingsimulation deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="366fb-276">This example disables the phishing simulation override policy.</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

<span data-ttu-id="366fb-277">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-PhishSimOverridePolicy".](/powershell/module/exchange/set-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="366fb-277">For detailed syntax and parameter information, see [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a><span data-ttu-id="366fb-278">Verwenden von PowerShell zum Ändern einer Überschreibungsregel für Phishingsimulationen</span><span class="sxs-lookup"><span data-stu-id="366fb-278">Use PowerShell to modify a phishing simulation override rule</span></span>

<span data-ttu-id="366fb-279">Verwenden Sie die folgende Syntax, um die Außerkraftsetzungsregel für phishingsimulationen zu ändern:</span><span class="sxs-lookup"><span data-stu-id="366fb-279">To modify the phishing simulation override rule, use the following syntax:</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

<span data-ttu-id="366fb-280">In diesem Beispiel wird die angegebene Außerkraftsetzungsregel für Phishingsimulationen mit den folgenden Einstellungen geändert:</span><span class="sxs-lookup"><span data-stu-id="366fb-280">This example modifies the specified phishing simulation override rule with the following settings:</span></span>

- <span data-ttu-id="366fb-281">Fügen Sie den Domäneneintrag blueyonderairlines.com hinzu.</span><span class="sxs-lookup"><span data-stu-id="366fb-281">Add the domain entry blueyonderairlines.com.</span></span>
- <span data-ttu-id="366fb-282">Entfernen Sie den IP-Adresseintrag 192.168.1.55.</span><span class="sxs-lookup"><span data-stu-id="366fb-282">Remove the IP address entry 192.168.1.55.</span></span>

<span data-ttu-id="366fb-283">Beachten Sie, dass sich diese Änderungen nicht auf vorhandene Einträge auswirken.</span><span class="sxs-lookup"><span data-stu-id="366fb-283">Note that these changes don't affect existing entries.</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

<span data-ttu-id="366fb-284">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-PhishSimOverrideRule".](/powershell/module/exchange/set-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="366fb-284">For detailed syntax and parameter information, see [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a><span data-ttu-id="366fb-285">Verwenden von PowerShell zum Entfernen einer Richtlinie zur Außerkraftsetzung einer Phishingsimulation</span><span class="sxs-lookup"><span data-stu-id="366fb-285">Use PowerShell to remove a phishing simulation override policy</span></span>

<span data-ttu-id="366fb-286">In diesem Beispiel werden die Richtlinie für die Außerkraftsetzung der Phishingsimulation und die entsprechende Regel entfernt.</span><span class="sxs-lookup"><span data-stu-id="366fb-286">This example removes the phishing simulation override policy and the corresponding rule.</span></span>

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

<span data-ttu-id="366fb-287">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="366fb-287">For detailed syntax and parameter information, see [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a><span data-ttu-id="366fb-288">Verwenden von PowerShell zum Entfernen von Außerkraftsetzungsregeln für Phishingsimulationen</span><span class="sxs-lookup"><span data-stu-id="366fb-288">Use PowerShell to remove phishing simulation override rules</span></span>

<span data-ttu-id="366fb-289">Verwenden Sie die folgende Syntax, um eine Außerkraftsetzungsregel für Phishingsimulationen zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="366fb-289">To remove a phishing simulation override rule, use the following syntax:</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="366fb-290">In diesem Beispiel wird die angegebene Überschreibungsregel für phishingsimulationen entfernt.</span><span class="sxs-lookup"><span data-stu-id="366fb-290">This example removes the specified phishing simulation override rule.</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

<span data-ttu-id="366fb-291">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="366fb-291">For detailed syntax and parameter information, see [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span></span>
