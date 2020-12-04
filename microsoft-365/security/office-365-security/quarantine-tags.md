---
title: Quarantäne-Tags
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Administratoren erfahren, wie Sie mithilfe von Quarantäne Tags steuern können, welche Benutzer in der Lage sind, ihre unter Quarantäne gestellten Nachrichten zu übernehmen.
ms.openlocfilehash: 68f28e2dff3bdeada2685ef6806489f5e57f5daf
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572669"
---
# <a name="quarantine-tags"></a><span data-ttu-id="f6941-103">Quarantäne-Tags</span><span class="sxs-lookup"><span data-stu-id="f6941-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="f6941-104">Die in diesem Artikel beschriebenen Features sind derzeit in der Vorschau, stehen nicht für alle zur Verfügung und können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f6941-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="f6941-105">Mit Quarantine Tags in Exchange Online Protection (EoP) können Administratoren steuern, welche Benutzer in der Lage sind, Ihre Nachrichten in Quarantäne zu übernehmen, je nachdem, wie die Nachricht in Quarantäne eingetroffen ist.</span><span class="sxs-lookup"><span data-stu-id="f6941-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="f6941-106">EoP hat traditionell bestimmte Ebenen der Interaktivität für Nachrichten in [Quarantäne](find-and-release-quarantined-messages-as-a-user.md) und in [Spambenachrichtigungen für Endbenutzer](use-spam-notifications-to-release-and-report-quarantined-messages.md)zugelassen oder verhindert.</span><span class="sxs-lookup"><span data-stu-id="f6941-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="f6941-107">Endbenutzer können beispielsweise Nachrichten anzeigen und freigeben, die von der antispambehandlung als Spam oder Massen isoliert wurden, aber Sie können Nachrichten, die als vertrauenswürdiges Phishing für hohe Zuverlässigkeit isoliert wurden, nicht anzeigen oder freigeben.</span><span class="sxs-lookup"><span data-stu-id="f6941-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="f6941-108">Für [unterstützte Schutzfunktionen](#step-2-assign-a-quarantine-tag-to-supported-features)geben Quarantine-Tags an, welche Benutzer in Spambenachrichtigungen für Endbenutzer und in ihren isolierten Nachrichten in Quarantäne (Nachrichten, bei denen der Benutzer ein Empfänger ist) zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="f6941-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="f6941-109">Standardmäßige Quarantäne Tags werden automatisch zugewiesen, um die Verlaufsfunktionen für Endbenutzer in unter Quarantäne gestellten Nachrichten zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="f6941-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="f6941-110">Sie können auch benutzerdefinierte Quarantäne Tags erstellen und zuweisen, um Endbenutzern das Ausführen bestimmter Aktionen für isolierte Nachrichten zu ermöglichen oder zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="f6941-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="f6941-111">Die einzelnen Berechtigungen werden in den folgenden vordefinierten Berechtigungsgruppen zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="f6941-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="f6941-112">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-112">No access</span></span>
- <span data-ttu-id="f6941-113">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-113">Limited access</span></span>
- <span data-ttu-id="f6941-114">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-114">Full access</span></span>

<span data-ttu-id="f6941-115">In der folgenden Tabelle werden die verfügbaren einzelnen Berechtigungen und die in den vordefinierten Berechtigungsgruppen enthaltenen oder nicht enthaltenen Elemente beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f6941-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="f6941-116">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f6941-116">Permission</span></span>|<span data-ttu-id="f6941-117">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-117">No access</span></span>|<span data-ttu-id="f6941-118">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-118">Limited access</span></span>|<span data-ttu-id="f6941-119">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="f6941-120">**Absender zulassen** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="f6941-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="f6941-122">**Absender blockieren** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="f6941-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="f6941-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="f6941-125">**Delete** (_PermissionToDelete_)</span></span>||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="f6941-128">**Vorschau** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="f6941-128">**Preview** (_PermissionToPreview_)</span></span>||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="f6941-131">**Zulassen, dass Empfänger eine Nachricht aus der Quarantäne freigeben** (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="f6941-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="f6941-133">**Zulassen, dass Empfänger eine Nachricht anfordern, die aus der Quarantäne freigegeben wird** (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="f6941-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

<span data-ttu-id="f6941-135">Wenn Ihnen die Standardberechtigungen in den vordefinierten Berechtigungsgruppen nicht gefällt, können Sie benutzerdefinierte Berechtigungen verwenden, wenn Sie benutzerdefinierte Quarantäne Tags erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="f6941-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="f6941-136">Weitere Informationen zu den einzelnen Berechtigungen finden Sie im Abschnitt [Quarantine Tag Permission Details](#quarantine-tag-permission-details) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="f6941-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="f6941-137">Sie erstellen und Zuweisen von Quarantäne Tags im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Exchange Online Postfächern; eigenständige EoP PowerShell in EoP-Organisationen ohne Exchange Online Postfächer).</span><span class="sxs-lookup"><span data-stu-id="f6941-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f6941-138">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="f6941-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f6941-139">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f6941-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f6941-140">Um direkt zur Seite **Quarantine Tags** zu wechseln, öffnen Sie <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="f6941-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="f6941-141">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6941-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f6941-142">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6941-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f6941-143">Zum Anzeigen, erstellen, ändern oder Entfernen von Quarantäne Tags müssen Sie Mitglied der Rolle " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)sein.</span><span class="sxs-lookup"><span data-stu-id="f6941-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="f6941-144">Schritt 1: Erstellen von Quarantäne Tags im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f6941-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="f6941-145">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** , und wählen Sie dann **Quarantine Tags** aus.</span><span class="sxs-lookup"><span data-stu-id="f6941-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="f6941-146">Wählen Sie auf der Seite **Tags isolieren** die Option **benutzerdefiniertes Tag hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f6941-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="f6941-147">Der Assistent für **neue Tags** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f6941-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="f6941-148">Geben Sie auf der Seite **Tagname** einen kurzen, aber eindeutigen Namen in das Feld **Tag Name** ein.</span><span class="sxs-lookup"><span data-stu-id="f6941-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="f6941-149">In den nächsten Schritten müssen Sie das Tag anhand des Namens identifizieren und auswählen.</span><span class="sxs-lookup"><span data-stu-id="f6941-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="f6941-150">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f6941-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f6941-151">Wählen Sie auf der Seite **Empfänger Nachrichtenzugriff** einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="f6941-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="f6941-152">**Kein Zugriff**</span><span class="sxs-lookup"><span data-stu-id="f6941-152">**No access**</span></span>
   - <span data-ttu-id="f6941-153">**Limitierter Zugriff**</span><span class="sxs-lookup"><span data-stu-id="f6941-153">**Limited access**</span></span>
   - <span data-ttu-id="f6941-154">**Vollzugriff**</span><span class="sxs-lookup"><span data-stu-id="f6941-154">**Full access**</span></span>

   <span data-ttu-id="f6941-155">Die einzelnen Berechtigungen, die in diesen Berechtigungsgruppen enthalten sind, werden weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6941-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="f6941-156">Um benutzerdefinierte Berechtigungen anzugeben, wählen Sie **bestimmten Zugriff festlegen (erweitert)** aus, und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f6941-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="f6941-157">**Wählen Sie die Option "Freigabe Aktion**" aus: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="f6941-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="f6941-158">**Keine Release-Aktion**: Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="f6941-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="f6941-159">**Zulassen, dass Empfänger eine Nachricht aus der Quarantäne freigeben**</span><span class="sxs-lookup"><span data-stu-id="f6941-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="f6941-160">**Zulassen, dass Empfänger eine Nachricht für die Freigabe aus der Quarantäne anfordern**</span><span class="sxs-lookup"><span data-stu-id="f6941-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="f6941-161">**Auswählen weiterer Aktionen, die Empfänger in unter Quarantäne gestellten Nachrichten annehmen können**: Wählen Sie einige, alle oder keine der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="f6941-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="f6941-162">**Delete**</span><span class="sxs-lookup"><span data-stu-id="f6941-162">**Delete**</span></span>
       - <span data-ttu-id="f6941-163">**Preview**</span><span class="sxs-lookup"><span data-stu-id="f6941-163">**Preview**</span></span>
       - <span data-ttu-id="f6941-164">**Absender zulassen**</span><span class="sxs-lookup"><span data-stu-id="f6941-164">**Allow sender**</span></span>
       - <span data-ttu-id="f6941-165">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="f6941-165">**Block sender**</span></span>

   <span data-ttu-id="f6941-166">Diese Berechtigungen und deren Auswirkungen auf isolierte Nachrichten und Spambenachrichtigungen für Endbenutzer werden im Abschnitt [Berechtigungen für Quarantäne-Tag-Details](#quarantine-tag-permission-details) weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6941-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="f6941-167">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f6941-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f6941-168">Überprüfen Sie auf der angezeigten **Zusammenfassungs** Seite Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f6941-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="f6941-169">Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f6941-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="f6941-170">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="f6941-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="f6941-171">Klicken Sie auf der angezeigten Bestätigungsseite auf **Fertig** .</span><span class="sxs-lookup"><span data-stu-id="f6941-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="f6941-172">Jetzt können Sie das Quarantäne-Tag einer Quarantänefunktion zuweisen, wie im Abschnitt [Schritt 2](#step-2-assign-a-quarantine-tag-to-supported-features) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6941-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="f6941-173">Erstellen von Quarantäne Tags in PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6941-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="f6941-174">Wenn Sie lieber PowerShell zum Erstellen von Quarantäne-Tags verwenden möchten, stellen Sie eine Verbindung mit Exchange Online PowerShell oder Exchange Online Protection PowerShell her, und verwenden Sie das **New-QuarantineTag-** Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f6941-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="f6941-175">Sie haben zwei verschiedene Methoden zur Auswahl:</span><span class="sxs-lookup"><span data-stu-id="f6941-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="f6941-176">Verwenden Sie den _EndUserQuarantinePermissionsValue_ -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f6941-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="f6941-177">Verwenden Sie den _EndUserQuarantinePermissions_ -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f6941-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="f6941-178">Diese Methoden werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6941-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="f6941-179">Verwenden des EndUserQuarantinePermissionsValue-Parameters</span><span class="sxs-lookup"><span data-stu-id="f6941-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="f6941-180">Verwenden Sie die folgende Syntax, um ein Quarantine-Tag mithilfe des _EndUserQuarantinePermissionsValue_ -Parameters zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f6941-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="f6941-181">Der _EndUserQuarantinePermissionsValue_ -Parameter verwendet einen Dezimalwert, der aus einem Binärwert konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="f6941-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="f6941-182">Der Binärwert entspricht den verfügbaren Benutzerquarantäne Berechtigungen in einer bestimmten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="f6941-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="f6941-183">Für jede Berechtigung ist der Wert 1 gleich true und der Wert 0 gleich false.</span><span class="sxs-lookup"><span data-stu-id="f6941-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="f6941-184">Die erforderliche Reihenfolge und die Werte für jede einzelne Berechtigung in vordefinierten Berechtigungsgruppen werden in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f6941-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="f6941-185">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f6941-185">Permission</span></span>|<span data-ttu-id="f6941-186">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-186">No access</span></span>|<span data-ttu-id="f6941-187">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-187">Limited access</span></span>|<span data-ttu-id="f6941-188">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="f6941-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="f6941-189">PermissionToAllowSender</span></span>|<span data-ttu-id="f6941-190">0</span><span class="sxs-lookup"><span data-stu-id="f6941-190">0</span></span>|<span data-ttu-id="f6941-191">0</span><span class="sxs-lookup"><span data-stu-id="f6941-191">0</span></span>|<span data-ttu-id="f6941-192">1 </span><span class="sxs-lookup"><span data-stu-id="f6941-192">1</span></span>|
|<span data-ttu-id="f6941-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="f6941-193">PermissionToBlockSender</span></span>|<span data-ttu-id="f6941-194">0</span><span class="sxs-lookup"><span data-stu-id="f6941-194">0</span></span>|<span data-ttu-id="f6941-195">1 </span><span class="sxs-lookup"><span data-stu-id="f6941-195">1</span></span>|<span data-ttu-id="f6941-196">1 </span><span class="sxs-lookup"><span data-stu-id="f6941-196">1</span></span>|
|<span data-ttu-id="f6941-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="f6941-197">PermissionToDelete</span></span>|<span data-ttu-id="f6941-198">0</span><span class="sxs-lookup"><span data-stu-id="f6941-198">0</span></span>|<span data-ttu-id="f6941-199">1 </span><span class="sxs-lookup"><span data-stu-id="f6941-199">1</span></span>|<span data-ttu-id="f6941-200">1 </span><span class="sxs-lookup"><span data-stu-id="f6941-200">1</span></span>|
|<span data-ttu-id="f6941-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6941-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="f6941-202">0</span><span class="sxs-lookup"><span data-stu-id="f6941-202">0</span></span>|<span data-ttu-id="f6941-203">0</span><span class="sxs-lookup"><span data-stu-id="f6941-203">0</span></span>|<span data-ttu-id="f6941-204">0</span><span class="sxs-lookup"><span data-stu-id="f6941-204">0</span></span>|
|<span data-ttu-id="f6941-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="f6941-205">PermissionToPreview</span></span>|<span data-ttu-id="f6941-206">0</span><span class="sxs-lookup"><span data-stu-id="f6941-206">0</span></span>|<span data-ttu-id="f6941-207">1 </span><span class="sxs-lookup"><span data-stu-id="f6941-207">1</span></span>|<span data-ttu-id="f6941-208">1 </span><span class="sxs-lookup"><span data-stu-id="f6941-208">1</span></span>|
|<span data-ttu-id="f6941-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6941-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="f6941-210">0</span><span class="sxs-lookup"><span data-stu-id="f6941-210">0</span></span>|<span data-ttu-id="f6941-211">0</span><span class="sxs-lookup"><span data-stu-id="f6941-211">0</span></span>|<span data-ttu-id="f6941-212">1 </span><span class="sxs-lookup"><span data-stu-id="f6941-212">1</span></span>|
|<span data-ttu-id="f6941-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6941-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="f6941-214">0</span><span class="sxs-lookup"><span data-stu-id="f6941-214">0</span></span>|<span data-ttu-id="f6941-215">1 </span><span class="sxs-lookup"><span data-stu-id="f6941-215">1</span></span>|<span data-ttu-id="f6941-216">0</span><span class="sxs-lookup"><span data-stu-id="f6941-216">0</span></span>|
|<span data-ttu-id="f6941-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6941-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="f6941-218">0</span><span class="sxs-lookup"><span data-stu-id="f6941-218">0</span></span>|<span data-ttu-id="f6941-219">0</span><span class="sxs-lookup"><span data-stu-id="f6941-219">0</span></span>|<span data-ttu-id="f6941-220">0</span><span class="sxs-lookup"><span data-stu-id="f6941-220">0</span></span>|
|<span data-ttu-id="f6941-221">Binärer Wert</span><span class="sxs-lookup"><span data-stu-id="f6941-221">Binary value</span></span>|<span data-ttu-id="f6941-222">00000000</span><span class="sxs-lookup"><span data-stu-id="f6941-222">00000000</span></span>|<span data-ttu-id="f6941-223">01101010</span><span class="sxs-lookup"><span data-stu-id="f6941-223">01101010</span></span>|<span data-ttu-id="f6941-224">11101100</span><span class="sxs-lookup"><span data-stu-id="f6941-224">11101100</span></span>|
|<span data-ttu-id="f6941-225">Zu verwendender Dezimalwert</span><span class="sxs-lookup"><span data-stu-id="f6941-225">Decimal value to use</span></span>|<span data-ttu-id="f6941-226">0</span><span class="sxs-lookup"><span data-stu-id="f6941-226">0</span></span>|<span data-ttu-id="f6941-227">106</span><span class="sxs-lookup"><span data-stu-id="f6941-227">106</span></span>|<span data-ttu-id="f6941-228">236</span><span class="sxs-lookup"><span data-stu-id="f6941-228">236</span></span>|

<span data-ttu-id="f6941-229"><sup>\*</sup> Derzeit ist dieser Wert immer 0.</span><span class="sxs-lookup"><span data-stu-id="f6941-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="f6941-230">Bei PermissionToViewHeader wird der Wert 0 nicht ausgeblendet die Schaltfläche **Nachrichtenkopfzeile anzeigen** in den Details der isolierten Nachricht (die Schaltfläche ist immer verfügbar).</span><span class="sxs-lookup"><span data-stu-id="f6941-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="f6941-231"><sup>\*\*</sup> Legen Sie beide Werte nicht auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="f6941-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="f6941-232">Legen Sie eine auf 1 und die andere auf 0 fest, oder legen Sie beide auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="f6941-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="f6941-233">In diesem Beispiel wird ein neuer Quarantine Tag-Name NoAccess erstellt, der die in der vorherigen Tabelle beschriebenen Berechtigungen ohne Zugriff zuweist.</span><span class="sxs-lookup"><span data-stu-id="f6941-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="f6941-234">Verwenden Sie für beschränkte Zugriffsberechtigungen den Wert 106.</span><span class="sxs-lookup"><span data-stu-id="f6941-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="f6941-235">Verwenden Sie für Vollzugriff Berechtigungen den Wert 236.</span><span class="sxs-lookup"><span data-stu-id="f6941-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="f6941-236">Verwenden Sie für benutzerdefinierte Berechtigungen die vorherige Tabelle, um den Binärwert abzurufen, der den gewünschten Berechtigungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="f6941-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="f6941-237">Konvertieren Sie den Binärwert in einen Dezimalwert, und verwenden Sie den Decimal-Wert für den _EndUserQuarantinePermissionsValue_ -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f6941-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="f6941-238">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="f6941-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="f6941-239">Verwenden des EndUserQuarantinePermissions-Parameters</span><span class="sxs-lookup"><span data-stu-id="f6941-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="f6941-240">Führen Sie die folgenden Schritte aus, um ein Quarantine-Tag mithilfe des _EndUserQuarantinePermissionsValue_ -Parameters zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f6941-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="f6941-241">A.</span><span class="sxs-lookup"><span data-stu-id="f6941-241">A.</span></span> <span data-ttu-id="f6941-242">Speichern Sie ein Quarantäne Berechtigungsobjekt in einer Variablen mithilfe des **New-QuarantinePermissions-** Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f6941-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>
<br/>
<span data-ttu-id="f6941-243">B.</span><span class="sxs-lookup"><span data-stu-id="f6941-243">B.</span></span> <span data-ttu-id="f6941-244">Verwenden Sie die Variable als _EndUserQuarantinePermissions_ -Wert im **New-QuarantineTag-** Befehl.</span><span class="sxs-lookup"><span data-stu-id="f6941-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="f6941-245">Schritt a: Speichern eines Quarantäne Berechtigungsobjekts in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="f6941-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="f6941-246">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="f6941-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="f6941-247">Der Standardwert für alle nicht verwendeten Parameter ist `$false` , sodass Sie nur die Parameter verwenden müssen, für die Sie den Wert festlegen möchten `$true` .</span><span class="sxs-lookup"><span data-stu-id="f6941-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="f6941-248">In den folgenden Beispielen wird gezeigt, wie Berechtigungsobjekte erstellt werden, die den vordefinierten Berechtigungsgruppen entsprechen:</span><span class="sxs-lookup"><span data-stu-id="f6941-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="f6941-249">**Kein Zugriff**:</span><span class="sxs-lookup"><span data-stu-id="f6941-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="f6941-250">**Limitierter Zugriff**:</span><span class="sxs-lookup"><span data-stu-id="f6941-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="f6941-251">**Vollzugriff**:</span><span class="sxs-lookup"><span data-stu-id="f6941-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="f6941-252">Um die Werte anzuzeigen, die Sie festgelegt haben, führen Sie den Variablennamen als Befehl aus (führen Sie beispielsweise den Befehl aus `$NoAccess` ).</span><span class="sxs-lookup"><span data-stu-id="f6941-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="f6941-253">Legen Sie für benutzerdefinierte Berechtigungen nicht die Parameter _PermissionToRelease_ und _PermissionToRequestRelease_ auf fest `$true` .</span><span class="sxs-lookup"><span data-stu-id="f6941-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="f6941-254">Legen Sie eine auf fest, `$true` und lassen Sie die andere als `$false` , oder belassen Sie beide als `$false` .</span><span class="sxs-lookup"><span data-stu-id="f6941-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="f6941-255">Sie können eine vorhandene Berechtigungsobjekt Variable auch ändern, nachdem Sie Sie erstellt haben, jedoch bevor Sie Sie mithilfe des Cmdlets "Cmdlet **festlegen-QuarantinePermissions** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6941-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="f6941-256">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) und [Festlegen von QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="f6941-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="f6941-257">Schritt B: Verwenden der Variablen im New-QuarantineTag-Befehl</span><span class="sxs-lookup"><span data-stu-id="f6941-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="f6941-258">Nachdem Sie das Permissions-Objekt in einer Variablen erstellt und gespeichert haben, verwenden Sie die Variable für den Wert des _EndUserQuarantinePermission_ -Parameters im folgenden **New-QuarantineTag-** Befehl:</span><span class="sxs-lookup"><span data-stu-id="f6941-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="f6941-259">In diesem Beispiel wird mithilfe des `$LimitedAccess` Permissions-Objekts, das im vorherigen Schritt beschrieben und erstellt wurde, ein neues Quarantine-Tag mit dem Namen LimitedAccess erstellt.</span><span class="sxs-lookup"><span data-stu-id="f6941-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="f6941-260">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="f6941-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="f6941-261">Schritt 2: Zuweisen eines Quarantäne Tags zu unterstützten Features</span><span class="sxs-lookup"><span data-stu-id="f6941-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="f6941-262">In _unterstützten_ Schutzfunktionen, die Nachrichten oder Dateien isolieren (automatisch oder als konfigurierbare Aktion), können Sie die verfügbaren Quarantäneaktionen mit einem quarantänetag versehen.</span><span class="sxs-lookup"><span data-stu-id="f6941-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="f6941-263">In der folgenden Tabelle werden Features zum Isolieren von Nachrichten und zur Verfügbarkeit von Quarantäne Tags beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f6941-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="f6941-264">Feature</span><span class="sxs-lookup"><span data-stu-id="f6941-264">Feature</span></span>|<span data-ttu-id="f6941-265">Unterstützte Quarantäne-Tags?</span><span class="sxs-lookup"><span data-stu-id="f6941-265">Quarantine tags supported?</span></span>|<span data-ttu-id="f6941-266">Verwendete standardmäßige Quarantäne Tags</span><span class="sxs-lookup"><span data-stu-id="f6941-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="f6941-267">[Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="f6941-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="f6941-268">**Spam** (_Spam_)</span><span class="sxs-lookup"><span data-stu-id="f6941-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="f6941-269">**Spam mit hoher Zuverlässigkeit** (_: highconfidencespamaction_)</span><span class="sxs-lookup"><span data-stu-id="f6941-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="f6941-270">**Phishing-e-Mails** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="f6941-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="f6941-271">**Phishing-e-Mails mit hoher Zuverlässigkeit** (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="f6941-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="f6941-272">**Massen-e-Mails** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="f6941-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="f6941-273">Ja</span><span class="sxs-lookup"><span data-stu-id="f6941-273">Yes</span></span>|<ul><li><span data-ttu-id="f6941-274">DefaultSpamTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="f6941-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="f6941-275">DefaultHighConfSpamTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="f6941-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="f6941-276">DefaultPhishTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="f6941-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="f6941-277">DefaultHighConfPhishTag (kein Zugriff)</span><span class="sxs-lookup"><span data-stu-id="f6941-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="f6941-278">DefaultBulkTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="f6941-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="f6941-279">Anti-Phishing-Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="f6941-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="f6941-280">[Spoof Intelligence Protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="f6941-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="f6941-281">[Identitätswechsel Schutz](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6941-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="f6941-282">**Wenn e-Mail von einem imitierten Benutzer gesendet wird** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="f6941-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="f6941-283">**Wenn e-Mail von einer imitierten Domäne gesendet wird** (_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="f6941-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="f6941-284">**Post Fach Intelligenz** \> **Wenn e-Mail von einem imitierten Benutzer gesendet wird** (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="f6941-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="f6941-285">Nein</span><span class="sxs-lookup"><span data-stu-id="f6941-285">No</span></span>|<span data-ttu-id="f6941-286">n/v</span><span class="sxs-lookup"><span data-stu-id="f6941-286">n/a</span></span>|
|<span data-ttu-id="f6941-287">[Anti-Malware-Richtlinien](configure-anti-malware-policies.md): alle erkannten Nachrichten werden immer isoliert.</span><span class="sxs-lookup"><span data-stu-id="f6941-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="f6941-288">Nein</span><span class="sxs-lookup"><span data-stu-id="f6941-288">No</span></span>|<span data-ttu-id="f6941-289">n/v</span><span class="sxs-lookup"><span data-stu-id="f6941-289">n/a</span></span>|
|[<span data-ttu-id="f6941-290">ATP für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6941-290">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="f6941-291">Nein</span><span class="sxs-lookup"><span data-stu-id="f6941-291">No</span></span>|<span data-ttu-id="f6941-292">n/v</span><span class="sxs-lookup"><span data-stu-id="f6941-292">n/a</span></span>|
|<span data-ttu-id="f6941-293">[Nachrichtenfluss Regeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet) mit der Aktion: **Zustellung der Nachricht an die gehostete Quarantäne** (_Quarantäne_).</span><span class="sxs-lookup"><span data-stu-id="f6941-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="f6941-294">Nein</span><span class="sxs-lookup"><span data-stu-id="f6941-294">No</span></span>|<span data-ttu-id="f6941-295">n/v</span><span class="sxs-lookup"><span data-stu-id="f6941-295">n/a</span></span>|
|

<span data-ttu-id="f6941-296"><sup>\*</sup> Einstellungen für den Identitätswechsel Schutz stehen nur in Anti-Phishing-Richtlinien in Microsoft Defender für Office 365 zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f6941-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="f6941-297">Wenn Sie mit den Endbenutzerberechtigungen zufrieden sind, die von den standardmäßigen Quarantäne-Tags bereitgestellt werden, müssen Sie nichts tun.</span><span class="sxs-lookup"><span data-stu-id="f6941-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="f6941-298">Wenn Sie die Endbenutzerfunktionen (verfügbare Schaltflächen) in Spambenachrichtigungen für Endbenutzer oder in isolierten Nachrichtendetails anpassen möchten, können Sie ein benutzerdefiniertes Quarantäne-Tag zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f6941-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="f6941-299">Zuweisen von Quarantäne Tags in Anti-Spam-Richtlinien im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f6941-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="f6941-300">Ausführliche Anweisungen zum Erstellen und Ändern von Anti-Spam-Richtlinien finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f6941-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="f6941-301">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** , \> und wählen Sie dann **Anti-Spam** aus.</span><span class="sxs-lookup"><span data-stu-id="f6941-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="f6941-302">Oder öffnen Sie <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="f6941-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="f6941-303">Suchen und Auswählen einer vorhandenen Antispam-Richtlinie zum Bearbeiten oder Erstellen einer neuen Antispampolitik.</span><span class="sxs-lookup"><span data-stu-id="f6941-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="f6941-304">Erweitern Sie im Flyout Richtlinie Details den Abschnitt **Spam-und Massenaktionen** .</span><span class="sxs-lookup"><span data-stu-id="f6941-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>
  
4. <span data-ttu-id="f6941-305">Wenn Sie die Option **Quarantäne Nachricht** für die Aktion eines verfügbaren Spam Filterungs Urteils ausgewählt haben, steht das Feld **Quarantäne-richtlinientag anwenden** zur Verfügung, um das Quarantäne-Tag für das Urteil auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f6941-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="f6941-306">**Hinweis**: Wenn Sie eine neue Richtlinie erstellen, wird durch einen leeren Quarantäne-Tag-Wert für ein Spamfilter Urteil angegeben, dass das standardmäßige quarantänetag für dieses Urteil verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6941-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="f6941-307">Wenn Sie die Richtlinie später bearbeiten, werden die leeren Werte durch die tatsächlichen Standardnamen der Quarantäne Tags ersetzt, wie in der vorherigen Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6941-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>
  
   ![Auswählen von Quarantäne Tags in einer Anti-Spam-Richtlinie](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="f6941-309">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f6941-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="f6941-310">Zuweisen von Quarantäne Tags in Anti-Spam-Richtlinien in PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6941-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="f6941-311">Wenn Sie lieber PowerShell zum Zuweisen von Quarantäne Tags in Anti-Spam-Richtlinien verwenden möchten, stellen Sie eine Verbindung mit Exchange Online PowerShell oder Exchange Online Protection PowerShell her, und verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="f6941-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="f6941-312">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="f6941-312">**Notes**:</span></span>

- <span data-ttu-id="f6941-313">Der Standardwert für den Parameter _HighConfidencePhishAction_ ist Quarantine, sodass Sie die Quarantäneaktion für hohe vertrauenswürdige Phishing-Erkennungen in neuen Anti-Spam-Richtlinien nicht festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="f6941-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="f6941-314">Bei allen anderen Spamfilter Urteilen in neuen oder vorhandenen Anti-Spam-Richtlinien ist das quarantänetag nur wirksam, wenn der Aktionswert Quarantine lautet.</span><span class="sxs-lookup"><span data-stu-id="f6941-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="f6941-315">Führen Sie den folgenden Befehl aus, um die Aktionswerte in vorhandenen Anti-Spam-Richtlinien anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f6941-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="f6941-316">Informationen zu den Standard Aktionswerten und den empfohlenen Aktionswerten für Standard und Strict finden Sie unter [EoP Anti-Spam Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="f6941-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="f6941-317">Ein Spam Filterungs Urteil ohne einen entsprechenden Parameter für die Quarantäne Kennzeichnung bedeutet, dass das [standardmäßige quarantänetag](#step-2-assign-a-quarantine-tag-to-supported-features) für dieses Urteil verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6941-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="f6941-318">Sie müssen nur ein Standardmäßiges Quarantine-Tag durch ein benutzerdefiniertes Quarantine-Tag ersetzen, wenn Sie die standardmäßigen Endbenutzerfunktionen für isolierte Nachrichten ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f6941-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="f6941-319">Eine neue Anti-Spam-Richtlinie in PowerShell erfordert eine Spamfilter Richtlinie (Einstellungen) mithilfe des **New-hostedcontentfilterpolicy dient zum-** Cmdlets und einer neuen Spamfilter Regel (Empfängerfilter) mithilfe des **New-HostedContentFilterRule-** Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f6941-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="f6941-320">Anweisungen finden Sie unter [Verwenden von PowerShell zum Erstellen von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="f6941-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="f6941-321">In diesem Beispiel wird eine neue Spamfilter Richtlinie mit dem Namen "Research Department" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="f6941-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="f6941-322">Die Aktion für alle Spamfilter-Urteile wird auf Quarantäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f6941-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="f6941-323">Das benutzerdefinierte Quarantäne-Tag mit dem Namen NoAccess, das **keine Zugriffs** Berechtigungen zuweist, ersetzt alle standardmäßigen Quarantäne Tags, die nicht bereits standardmäßig **keine Zugriffs** Berechtigungen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f6941-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="f6941-324">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="f6941-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="f6941-325">In diesem Beispiel wird die vorhandene Spamfilter Richtlinie namens "Human Resources" geändert.</span><span class="sxs-lookup"><span data-stu-id="f6941-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="f6941-326">Die Aktion für das Spamquarantäne Urteil wird auf Quarantäne festgelegt, und das benutzerdefinierte Quarantäne-Tag mit dem Namen NoAccess wird zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f6941-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="f6941-327">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="f6941-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="f6941-328">Konfigurieren globaler Quarantäne Benachrichtigungseinstellungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f6941-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="f6941-329">Mit den globalen Einstellungen für Quarantäne-Tags können Sie die Endbenutzer-Spambenachrichtigungen anpassen, die an Empfänger von Nachrichten gesendet werden, die isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="f6941-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="f6941-330">Weitere Informationen zu diesen Benachrichtigungen finden Sie unter [End-User Spam Notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f6941-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="f6941-331">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** , und wählen Sie dann **Quarantine Tags** aus.</span><span class="sxs-lookup"><span data-stu-id="f6941-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="f6941-332">Wählen Sie auf der Seite **Tags isolieren** die Option **globale Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="f6941-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="f6941-333">Konfigurieren Sie im Flyout " **Quarantäne Benachrichtigungseinstellungen** ", das geöffnet wird, einige oder alle der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f6941-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="f6941-334">**Mein Firmen Logo verwenden**: Wählen Sie diese Option aus, um das standardmäßige Microsoft-Logo zu ersetzen, das oben in Spambenachrichtigungen für Endbenutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6941-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="f6941-335">Bevor Sie dies tun, müssen Sie den Anweisungen unter [Anpassen des Microsoft 365-Designs für Ihre Organisation](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) folgen, um Ihr benutzerdefiniertes Logo hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="f6941-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="f6941-336">Der folgende Screenshot zeigt ein benutzerdefiniertes Logo in einer spambenachrichtigung für Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="f6941-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Ein benutzerdefiniertes Logo in einer spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="f6941-338">**Sprache auswählen**: Spambenachrichtigungen für Endbenutzer werden basierend auf den Spracheinstellungen des Empfängers bereits lokalisiert.</span><span class="sxs-lookup"><span data-stu-id="f6941-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="f6941-339">Sie können benutzerdefinierten Text in unterschiedlichen Sprachen für den **Anzeigenamen** und die **Haftungsausschluss** Werte angeben.</span><span class="sxs-lookup"><span data-stu-id="f6941-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="f6941-340">Wählen Sie mindestens eine Sprache aus dem Feld erste Sprache aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f6941-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="f6941-341">Sie können mehrere Sprachen auswählen, indem Sie nacheinander auf **Hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="f6941-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="f6941-342">Ein Feld für Abschnitts Sprachen zeigt alle Sprachen an, die Sie ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="f6941-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Ausgewählte Sprachen im Feld zweite Sprache in den globalen Quarantäne Benachrichtigungseinstellungen von Quarantäne Tags](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="f6941-344">**Anzeigename**: passen Sie den Anzeigenamen des Absenders an, der in Spambenachrichtigungen für Endbenutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6941-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="f6941-345">Wählen Sie für jede Sprache, die Sie hinzugefügt haben, im Feld zweite Sprache die Sprache aus (Klicken Sie nicht auf das X), und geben Sie den gewünschten Textwert in das Feld **Anzeigename** ein.</span><span class="sxs-lookup"><span data-stu-id="f6941-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="f6941-346">Der folgende Screenshot zeigt den benutzerdefinierten Anzeigenamen in einer spambenachrichtigung für Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="f6941-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Ein benutzerdefinierter Absender Anzeigename in einer spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="f6941-348">**Haftungsausschluss**: Fügen Sie am Ende der Spambenachrichtigungen für Endbenutzer einen benutzerdefinierten Haftungsausschluss hinzu.</span><span class="sxs-lookup"><span data-stu-id="f6941-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="f6941-349">Der lokalisierte Text, **ein Haftungsausschluss aus Ihrer Organisation:** ist immer zuerst enthalten, gefolgt von dem von Ihnen angegebenen Text.</span><span class="sxs-lookup"><span data-stu-id="f6941-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="f6941-350">Wählen Sie für jede Sprache, die Sie hinzugefügt haben, im Feld zweite Sprache die Sprache aus (Klicken Sie nicht auf das X), und geben Sie den gewünschten Textwert in das Feld **Disclaimer** ein.</span><span class="sxs-lookup"><span data-stu-id="f6941-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="f6941-351">Der folgende Screenshot zeigt den benutzerdefinierten Haftungsausschluss in einer spambenachrichtigung für Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="f6941-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Ein benutzerdefinierter Haftungsausschluss am Ende einer spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="f6941-353">Anzeigen von Quarantäne Tags im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f6941-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="f6941-354">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** , und wählen Sie dann **Quarantine Tags** aus.</span><span class="sxs-lookup"><span data-stu-id="f6941-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="f6941-355">Wenn Sie die Einstellungen integrierter oder benutzerdefinierter Quarantäne Tags anzeigen möchten, wählen Sie das Quarantäne-Tag aus der Liste aus (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="f6941-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="f6941-356">Um die globalen Einstellungen anzuzeigen, wählen Sie **globale Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="f6941-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="f6941-357">Anzeigen von Quarantäne Tags in PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6941-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="f6941-358">Wenn Sie lieber PowerShell zum Anzeigen von Quarantäne Tags verwenden möchten, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f6941-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="f6941-359">Um eine Zusammenfassungsliste aller integrierten oder benutzerdefinierten Tags anzuzeigen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f6941-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="f6941-360">Um die Einstellungen integrierter oder benutzerdefinierter Quarantäne Tags anzuzeigen, ersetzen Sie \<TagName\> durch den Namen des Quarantäne Tags, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f6941-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="f6941-361">Führen Sie den folgenden Befehl aus, um die globalen Einstellungen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f6941-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="f6941-362">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="f6941-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="f6941-363">Entfernen von Quarantäne Tags im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f6941-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="f6941-364">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="f6941-364">**Notes**:</span></span>

- <span data-ttu-id="f6941-365">Integrierte Quarantäne Tags können nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f6941-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="f6941-366">Vergewissern Sie sich vor dem Entfernen eines benutzerdefinierten Quarantäne Tags, dass es nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6941-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="f6941-367">Führen Sie beispielsweise den folgenden Befehl in PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="f6941-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="f6941-368">Wenn das Quarantäne-Tag verwendet wird, [Ersetzen Sie das zugewiesene Quarantäne-Tag](#step-2-assign-a-quarantine-tag-to-supported-features) , bevor Sie es entfernen.</span><span class="sxs-lookup"><span data-stu-id="f6941-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="f6941-369">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** , und wählen Sie dann **Quarantine Tags** aus.</span><span class="sxs-lookup"><span data-stu-id="f6941-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="f6941-370">Wählen Sie auf der Seite **Tags isolieren** das benutzerdefinierte Quarantäne-Tag aus, das Sie entfernen möchten, und klicken Sie dann auf **Delete Tag**.</span><span class="sxs-lookup"><span data-stu-id="f6941-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="f6941-371">Klicken Sie im Bestätigungsdialogfeld, das angezeigt wird, auf **Tag entfernen** .</span><span class="sxs-lookup"><span data-stu-id="f6941-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="f6941-372">Entfernen von Quarantäne Tags in PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6941-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="f6941-373">Wenn Sie lieber PowerShell zum Entfernen eines benutzerdefinierten Quarantäne Tags verwenden möchten, ersetzen Sie \<TagName\> durch den Namen des Quarantine-Tags, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f6941-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="f6941-374">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="f6941-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="f6941-375">Details zu Quarantäne-Tag-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f6941-375">Quarantine tag permission details</span></span>

<span data-ttu-id="f6941-376">In den folgenden Abschnitten werden die Auswirkungen von vordefinierten Berechtigungsgruppen und einzelnen Berechtigungen in den Details von isolierten Nachrichten und Spambenachrichtigungen für Endbenutzer beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6941-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="f6941-377">Voreingestellte Berechtigungsgruppen</span><span class="sxs-lookup"><span data-stu-id="f6941-377">Preset permissions groups</span></span>

<span data-ttu-id="f6941-378">Die einzelnen Berechtigungen, die in vordefinierten Berechtigungsgruppen enthalten sind, werden in der Tabelle am Anfang dieses Artikels aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f6941-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="f6941-379">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-379">No access</span></span>

<span data-ttu-id="f6941-380">Wenn das Quarantine-Tag **keine Zugriffs** Berechtigungen (keine Berechtigungen) zuweist, erhalten Benutzer weiterhin einige grundlegende Funktionen:</span><span class="sxs-lookup"><span data-stu-id="f6941-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="f6941-381">**Details zur isolierten Nachricht**: die Schaltfläche **Nachrichtenkopfzeile anzeigen** ist immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn das Quarantine-Tag dem Benutzer keine Zugriffsberechtigungen erteilt](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="f6941-383">**Spambenachrichtigungen für Endbenutzer**: die Schaltfläche **überprüfen** , mit der der Benutzer zur Nachricht in Quarantäne gelangen kann, ist immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Verfügbare Schaltflächen in der spambenachrichtigung für Endbenutzer, wenn das Quarantine-Tag dem Benutzer keine Zugriffsberechtigungen erteilt](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="f6941-385">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-385">Limited access</span></span>

<span data-ttu-id="f6941-386">Wenn das Quarantine-Tag die **begrenzten Zugriffs** Berechtigungen zuweist, erhalten Benutzer die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="f6941-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="f6941-387">**Details zur isolierten Nachricht**: die folgenden Schaltflächen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f6941-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="f6941-388">**Anforderungs Version**</span><span class="sxs-lookup"><span data-stu-id="f6941-388">**Request release**</span></span>
  - <span data-ttu-id="f6941-389">**Nachrichtenkopfzeile anzeigen**</span><span class="sxs-lookup"><span data-stu-id="f6941-389">**View message header**</span></span>
  - <span data-ttu-id="f6941-390">**Vorschau Nachricht**</span><span class="sxs-lookup"><span data-stu-id="f6941-390">**Preview message**</span></span>
  - <span data-ttu-id="f6941-391">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="f6941-391">**Block sender**</span></span>
  - <span data-ttu-id="f6941-392">**Aus Quarantäne entfernen**</span><span class="sxs-lookup"><span data-stu-id="f6941-392">**Remove from quarantine**</span></span>

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn das quarantänetag dem Benutzer beschränkte Zugriffsberechtigungen erteilt](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="f6941-394">**Spambenachrichtigungen für Endbenutzer**: die folgenden Schaltflächen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f6941-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="f6941-395">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="f6941-395">**Block sender**</span></span>
  - <span data-ttu-id="f6941-396">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="f6941-396">**Review**</span></span>

  ![Verfügbare Schaltflächen in der spambenachrichtigung für Endbenutzer, wenn das Quarantine-Tag dem Benutzer beschränkte Zugriffsberechtigungen erteilt](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="f6941-398">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="f6941-398">Full access</span></span>

<span data-ttu-id="f6941-399">Wenn das Quarantine-Tag die **vollständigen Zugriffs** Berechtigungen (alle verfügbaren Berechtigungen) zuweist, erhalten Benutzer die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="f6941-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="f6941-400">**Details zur isolierten Nachricht**: die folgenden Schaltflächen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f6941-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="f6941-401">**Nachricht freigeben**</span><span class="sxs-lookup"><span data-stu-id="f6941-401">**Release message**</span></span>
  - <span data-ttu-id="f6941-402">**Nachrichtenkopfzeile anzeigen**</span><span class="sxs-lookup"><span data-stu-id="f6941-402">**View message header**</span></span>
  - <span data-ttu-id="f6941-403">**Vorschau Nachricht**</span><span class="sxs-lookup"><span data-stu-id="f6941-403">**Preview message**</span></span>
  - <span data-ttu-id="f6941-404">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="f6941-404">**Block sender**</span></span>
  - <span data-ttu-id="f6941-405">**Absender zulassen**</span><span class="sxs-lookup"><span data-stu-id="f6941-405">**Allow sender**</span></span>
  - <span data-ttu-id="f6941-406">**Aus Quarantäne entfernen**</span><span class="sxs-lookup"><span data-stu-id="f6941-406">**Remove from quarantine**</span></span>

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn das Quarantine-Tag dem Benutzervollzugriff erteilt](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="f6941-408">**Spambenachrichtigungen für Endbenutzer**: die folgenden Schaltflächen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f6941-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="f6941-409">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="f6941-409">**Block sender**</span></span>
  - <span data-ttu-id="f6941-410">**Freigabe**</span><span class="sxs-lookup"><span data-stu-id="f6941-410">**Release**</span></span>
  - <span data-ttu-id="f6941-411">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="f6941-411">**Review**</span></span>

  ![Verfügbare Schaltflächen in der spambenachrichtigung für Endbenutzer, wenn das Quarantine-Tag dem Benutzervollzugriff erteilt](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="f6941-413">Einzelne Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f6941-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="f6941-414">Beachten Sie, dass Benutzer immer die im Abschnitt [kein Zugriff](#no-access) beschriebenen Schaltflächen erhalten.</span><span class="sxs-lookup"><span data-stu-id="f6941-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="f6941-415">Diese Schaltflächen sind nicht in den einzelnen Berechtigungs Beschreibungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f6941-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="f6941-416">Absender Berechtigung zulassen</span><span class="sxs-lookup"><span data-stu-id="f6941-416">Allow sender permission</span></span>

<span data-ttu-id="f6941-417">Die Berechtigung " **Absender zulassen** " (_PermissionToAllowSender_) steuert den Zugriff auf die Schaltfläche, mit der Benutzer den isolierten Nachrichtenabsender bequem zu Ihrer Liste sicherer Absender hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="f6941-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="f6941-418">**Details zur isolierten Nachricht**:</span><span class="sxs-lookup"><span data-stu-id="f6941-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="f6941-419">**Absender Berechtigung zulassen** aktiviert: die Schaltfläche **Absender zulassen** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="f6941-420">**Absender** Berechtigung deaktiviert zulassen: die Schaltfläche **Absender zulassen** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="f6941-421">**Spambenachrichtigungen für Endbenutzer**: keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="f6941-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="f6941-422">Weitere Informationen zur Liste sicherer Absender finden Sie unter verhindern, [dass vertrauenswürdige Absender blockiert werden](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) , und [verwenden Sie Exchange Online PowerShell, um die Sammlung von Listen sicherer Adressen für ein Postfach zu konfigurieren](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="f6941-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="f6941-423">Absender Berechtigung blockieren</span><span class="sxs-lookup"><span data-stu-id="f6941-423">Block sender permission</span></span>

<span data-ttu-id="f6941-424">Die **Block Sender** Permission (_PermissionToBlockSender_) steuert den Zugriff auf die Schaltfläche, mit der Benutzer den isolierten Nachrichtenabsender bequem zu Ihrer Liste blockierter Absender hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="f6941-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="f6941-425">**Details zur isolierten Nachricht**:</span><span class="sxs-lookup"><span data-stu-id="f6941-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="f6941-426">Berechtigung " **Absender blockieren** " aktiviert: die Schaltfläche " **Absender blockieren** " ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="f6941-427">**Absender Berechtigung blockieren** deaktiviert: die Schaltfläche " **Absender blockieren** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="f6941-428">**Spambenachrichtigungen für Endbenutzer**:</span><span class="sxs-lookup"><span data-stu-id="f6941-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="f6941-429">**Absender Berechtigung blockieren** deaktiviert: die Schaltfläche " **Absender blockieren** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="f6941-430">Berechtigung " **Absender blockieren** " aktiviert: die Schaltfläche " **Absender blockieren** " ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="f6941-431">Weitere Informationen zur Liste blockierter Absender finden Sie unter [Blockieren von Nachrichten von einem Benutzer](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) und [verwenden Exchange Online PowerShell zum Konfigurieren der Sammlung von Listen sicherer Adressen für ein Postfach](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="f6941-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="f6941-432">Berechtigung löschen</span><span class="sxs-lookup"><span data-stu-id="f6941-432">Delete permission</span></span>

<span data-ttu-id="f6941-433">Die Berechtigung " **Löschen** " (_PermissionToDelete_) steuert die Möglichkeit der Benutzer, Ihre Nachrichten (Nachrichten, bei denen der Benutzer ein Empfänger ist) aus der Quarantäne zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f6941-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="f6941-434">**Details zur isolierten Nachricht**:</span><span class="sxs-lookup"><span data-stu-id="f6941-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="f6941-435">Berechtigung **Löschen** aktiviert: die Schaltfläche **aus Quarantäne entfernen** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="f6941-436">**Lösch** Berechtigung deaktiviert: die Schaltfläche **aus Quarantäne entfernen** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="f6941-437">**Spambenachrichtigungen für Endbenutzer**: keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="f6941-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="f6941-438">Vorschau Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f6941-438">Preview permission</span></span>

<span data-ttu-id="f6941-439">Die **Preview** -Berechtigung (_PermissionToPreview_) steuert die Möglichkeit der Benutzer, Ihre Nachrichten in der Quarantäne anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f6941-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="f6941-440">**Details zur isolierten Nachricht**:</span><span class="sxs-lookup"><span data-stu-id="f6941-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="f6941-441">**Vorschau** Berechtigung aktiviert: die Schaltfläche **Vorschau Nachricht** steht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f6941-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="f6941-442">**Vorschau** Berechtigung deaktiviert: die Schaltfläche **Vorschau Nachricht** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="f6941-443">**Spambenachrichtigungen für Endbenutzer**: keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="f6941-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="f6941-444">Zulassen, dass Empfänger eine Nachricht aus der Quarantäne Berechtigung freigeben</span><span class="sxs-lookup"><span data-stu-id="f6941-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="f6941-445">Das **zulassen, dass Empfänger eine Nachricht aus Quarantine** Permission (_PermissionToRelease_) freigeben, steuert, dass Benutzer Ihre isolierten Nachrichten direkt und ohne Genehmigung eines Administrators freigeben können.</span><span class="sxs-lookup"><span data-stu-id="f6941-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="f6941-446">**Details zur isolierten Nachricht**:</span><span class="sxs-lookup"><span data-stu-id="f6941-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="f6941-447">Berechtigung aktiviert: die Schaltfläche **Nachricht freigeben** steht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f6941-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="f6941-448">Berechtigung deaktiviert: die Schaltfläche " **Nachricht freigeben** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-448">Permission disabled: The **Release message** button is not available.</span></span>
  
- <span data-ttu-id="f6941-449">**Spambenachrichtigungen für Endbenutzer**:</span><span class="sxs-lookup"><span data-stu-id="f6941-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="f6941-450">Berechtigung aktiviert: die Schaltfläche **Version** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="f6941-451">Berechtigung deaktiviert: die Schaltfläche " **Version** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="f6941-452">Zulassen, dass Empfänger eine Nachricht für die Freigabe aus der Quarantäne Berechtigung anfordern</span><span class="sxs-lookup"><span data-stu-id="f6941-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="f6941-453">Das **zulassen, dass Empfänger eine Nachricht aus der Quarantäne** Berechtigung (Quarantine Permission,_PermissionToRequestRelease_) freigegeben werden, steuert, ob Benutzer die Freigabe ihrer isolierten Nachrichten _anfordern_ können.</span><span class="sxs-lookup"><span data-stu-id="f6941-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="f6941-454">Die Nachricht wird nur freigegeben, nachdem ein Administrator die Anforderung genehmigt hat.</span><span class="sxs-lookup"><span data-stu-id="f6941-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="f6941-455">**Details zur isolierten Nachricht**:</span><span class="sxs-lookup"><span data-stu-id="f6941-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="f6941-456">Berechtigung aktiviert: die Schaltfläche **Version anfordern** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="f6941-457">Berechtigung deaktiviert: die Schaltfläche " **Anforderungs Version** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="f6941-458">**Spambenachrichtigungen für Endbenutzer**: die Schaltfläche " **Version** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6941-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
