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
ms.openlocfilehash: 557a6832807c1768f482e76c76c0e92b027e49a7
ms.sourcegitcommit: 2810d1347e5016412074b2dd18e654aee7e593de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "48819231"
---
# <a name="quarantine-tags"></a><span data-ttu-id="bc110-103">Quarantäne-Tags</span><span class="sxs-lookup"><span data-stu-id="bc110-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="bc110-104">Die in diesem Artikel beschriebenen Features sind derzeit in der Vorschau, stehen nicht für alle zur Verfügung und können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="bc110-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="bc110-105">Mit Quarantine Tags in Exchange Online Protection (EoP) können Administratoren steuern, welche Benutzer in der Lage sind, Ihre Nachrichten in Quarantäne zu übernehmen, je nachdem, wie die Nachricht in Quarantäne eingetroffen ist.</span><span class="sxs-lookup"><span data-stu-id="bc110-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="bc110-106">EoP hat traditionell bestimmte Ebenen der Interaktivität für Nachrichten in [Quarantäne](find-and-release-quarantined-messages-as-a-user.md) und in [Spambenachrichtigungen für Endbenutzer](use-spam-notifications-to-release-and-report-quarantined-messages.md)zugelassen oder verhindert.</span><span class="sxs-lookup"><span data-stu-id="bc110-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="bc110-107">Endbenutzer können beispielsweise Nachrichten anzeigen und freigeben, die von der antispambehandlung als Spam oder Massen isoliert wurden, aber Sie können Nachrichten, die als vertrauenswürdiges Phishing für hohe Zuverlässigkeit isoliert wurden, nicht anzeigen oder freigeben.</span><span class="sxs-lookup"><span data-stu-id="bc110-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="bc110-108">Für [unterstützte Schutzfunktionen](#step-2-assign-a-quarantine-tag-to-supported-features)geben Quarantine-Tags an, welche Benutzer in Spambenachrichtigungen für Endbenutzer und in ihren isolierten Nachrichten in Quarantäne (Nachrichten, bei denen der Benutzer ein Empfänger ist) zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="bc110-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="bc110-109">Standardmäßige Quarantäne Tags werden automatisch zugewiesen, um die Verlaufsfunktionen für Endbenutzer in unter Quarantäne gestellten Nachrichten zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="bc110-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="bc110-110">Sie können auch benutzerdefinierte Quarantäne Tags erstellen und zuweisen, um Endbenutzern das Ausführen bestimmter Aktionen für isolierte Nachrichten zu ermöglichen oder zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="bc110-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="bc110-111">Die einzelnen Berechtigungen werden in den folgenden vordefinierten Berechtigungsgruppen zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="bc110-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="bc110-112">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-112">No access</span></span>
- <span data-ttu-id="bc110-113">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-113">Limited access</span></span>
- <span data-ttu-id="bc110-114">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-114">Full access</span></span>

<span data-ttu-id="bc110-115">In der folgenden Tabelle werden die verfügbaren einzelnen Berechtigungen und die in den vordefinierten Berechtigungsgruppen enthaltenen oder nicht enthaltenen Elemente beschrieben:</span><span class="sxs-lookup"><span data-stu-id="bc110-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="bc110-116">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bc110-116">Permission</span></span>|<span data-ttu-id="bc110-117">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-117">No access</span></span>|<span data-ttu-id="bc110-118">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-118">Limited access</span></span>|<span data-ttu-id="bc110-119">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="bc110-120">**Absender zulassen** ( _PermissionToAllowSender_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-120">**Allow sender** ( _PermissionToAllowSender_ )</span></span>|||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="bc110-122">**Absender blockieren** ( _PermissionToBlockSender_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-122">**Block sender** ( _PermissionToBlockSender_ )</span></span>||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="bc110-125">**Delete** ( _PermissionToDelete_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-125">**Delete** ( _PermissionToDelete_ )</span></span>||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="bc110-128">**Vorschau** ( _PermissionToPreview_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-128">**Preview** ( _PermissionToPreview_ )</span></span>||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="bc110-131">**Zulassen, dass Empfänger eine Nachricht aus der Quarantäne freigeben** ( _PermissionToRelease_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-131">**Allow recipients to release a message from quarantine** ( _PermissionToRelease_ )</span></span>|||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="bc110-133">**Zulassen, dass Empfänger eine Nachricht anfordern, die aus der Quarantäne freigegeben wird** ( _PermissionToRequestRelease_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-133">**Allow recipients to request a message to be released from quarantine** ( _PermissionToRequestRelease_ )</span></span>||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

<span data-ttu-id="bc110-135">Wenn Ihnen die Standardberechtigungen in den vordefinierten Berechtigungsgruppen nicht gefällt, können Sie benutzerdefinierte Berechtigungen verwenden, wenn Sie benutzerdefinierte Quarantäne Tags erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="bc110-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="bc110-136">Weitere Informationen zu den einzelnen Berechtigungen finden Sie im Abschnitt [Quarantine Tag Permission Details](#quarantine-tag-permission-details) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="bc110-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="bc110-137">Sie erstellen und Zuweisen von Quarantäne Tags im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Exchange Online Postfächern; eigenständige EoP PowerShell in EoP-Organisationen ohne Exchange Online Postfächer).</span><span class="sxs-lookup"><span data-stu-id="bc110-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bc110-138">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="bc110-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bc110-139">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="bc110-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="bc110-140">Um direkt zur Seite **Quarantine Tags** zu wechseln, öffnen Sie <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="bc110-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="bc110-141">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="bc110-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="bc110-142">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="bc110-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="bc110-143">Zum Anzeigen, erstellen, ändern oder Entfernen von Quarantäne Tags müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="bc110-143">To view, create, modify, or remove quarantine tags, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="bc110-144">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bc110-144">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="bc110-145">**Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="bc110-145">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="bc110-146">Schritt 1: Erstellen von Quarantäne Tags im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="bc110-146">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="bc110-147">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** , und wählen Sie dann **Quarantine Tags** aus.</span><span class="sxs-lookup"><span data-stu-id="bc110-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags** .</span></span>

2. <span data-ttu-id="bc110-148">Wählen Sie auf der Seite **Tags isolieren** die Option **benutzerdefiniertes Tag hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="bc110-148">On the **Quarantine tags** page, select **Add custom tag** .</span></span>

3. <span data-ttu-id="bc110-149">Der Assistent für **neue Tags** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bc110-149">The **New tag** wizard opens.</span></span> <span data-ttu-id="bc110-150">Geben Sie auf der Seite **Tagname** einen kurzen, aber eindeutigen Namen in das Feld **Tag Name** ein.</span><span class="sxs-lookup"><span data-stu-id="bc110-150">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="bc110-151">In den nächsten Schritten müssen Sie das Tag anhand des Namens identifizieren und auswählen.</span><span class="sxs-lookup"><span data-stu-id="bc110-151">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="bc110-152">Klicken Sie nach Abschluss des Vorgangs auf **Weiter** .</span><span class="sxs-lookup"><span data-stu-id="bc110-152">When you're finished, click **Next** .</span></span>

4. <span data-ttu-id="bc110-153">Wählen Sie auf der Seite **Empfänger Nachrichtenzugriff** einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="bc110-153">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="bc110-154">**Kein Zugriff**</span><span class="sxs-lookup"><span data-stu-id="bc110-154">**No access**</span></span>
   - <span data-ttu-id="bc110-155">**Limitierter Zugriff**</span><span class="sxs-lookup"><span data-stu-id="bc110-155">**Limited access**</span></span>
   - <span data-ttu-id="bc110-156">**Vollzugriff**</span><span class="sxs-lookup"><span data-stu-id="bc110-156">**Full access**</span></span>

   <span data-ttu-id="bc110-157">Die einzelnen Berechtigungen, die in diesen Berechtigungsgruppen enthalten sind, werden weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc110-157">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="bc110-158">Um benutzerdefinierte Berechtigungen anzugeben, wählen Sie **bestimmten Zugriff festlegen (erweitert)** aus, und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="bc110-158">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="bc110-159">**Wählen Sie die Option "Freigabe Aktion** " aus: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="bc110-159">**Select release action preference** : Select one of the following values:</span></span>
       - <span data-ttu-id="bc110-160">**Keine Release-Aktion** : Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="bc110-160">**No release action** : This is the default value.</span></span>
       - <span data-ttu-id="bc110-161">**Zulassen, dass Empfänger eine Nachricht aus der Quarantäne freigeben**</span><span class="sxs-lookup"><span data-stu-id="bc110-161">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="bc110-162">**Zulassen, dass Empfänger eine Nachricht für die Freigabe aus der Quarantäne anfordern**</span><span class="sxs-lookup"><span data-stu-id="bc110-162">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="bc110-163">**Auswählen weiterer Aktionen, die Empfänger in unter Quarantäne gestellten Nachrichten annehmen können** : Wählen Sie einige, alle oder keine der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="bc110-163">**Select additional actions recipients can take on quarantined messages** : Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="bc110-164">**Delete**</span><span class="sxs-lookup"><span data-stu-id="bc110-164">**Delete**</span></span>
       - <span data-ttu-id="bc110-165">**Preview**</span><span class="sxs-lookup"><span data-stu-id="bc110-165">**Preview**</span></span>
       - <span data-ttu-id="bc110-166">**Absender zulassen**</span><span class="sxs-lookup"><span data-stu-id="bc110-166">**Allow sender**</span></span>
       - <span data-ttu-id="bc110-167">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="bc110-167">**Block sender**</span></span>

   <span data-ttu-id="bc110-168">Diese Berechtigungen und deren Auswirkungen auf isolierte Nachrichten und Spambenachrichtigungen für Endbenutzer werden im Abschnitt [Berechtigungen für Quarantäne-Tag-Details](#quarantine-tag-permission-details) weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc110-168">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="bc110-169">Klicken Sie nach Abschluss des Vorgangs auf **Weiter** .</span><span class="sxs-lookup"><span data-stu-id="bc110-169">When you're finished, click **Next** .</span></span>

5. <span data-ttu-id="bc110-170">Überprüfen Sie auf der angezeigten **Zusammenfassungs** Seite Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="bc110-170">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="bc110-171">Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bc110-171">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="bc110-172">Wenn Sie fertig sind, klicken Sie auf über **Mitteln** .</span><span class="sxs-lookup"><span data-stu-id="bc110-172">When you're finished, click **Submit** .</span></span>

6. <span data-ttu-id="bc110-173">Klicken Sie auf der angezeigten Bestätigungsseite auf **Fertig** .</span><span class="sxs-lookup"><span data-stu-id="bc110-173">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="bc110-174">Jetzt können Sie das Quarantäne-Tag einer Quarantänefunktion zuweisen, wie im Abschnitt [Schritt 2](#step-2-assign-a-quarantine-tag-to-supported-features) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc110-174">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="bc110-175">Erstellen von Quarantäne Tags in PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc110-175">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="bc110-176">Wenn Sie lieber PowerShell zum Erstellen von Quarantäne-Tags verwenden möchten, stellen Sie eine Verbindung mit Exchange Online PowerShell oder Exchange Online Protection PowerShell her, und verwenden Sie das **New-QuarantineTag-** Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bc110-176">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="bc110-177">Sie haben zwei verschiedene Methoden zur Auswahl:</span><span class="sxs-lookup"><span data-stu-id="bc110-177">You have two different methods to choose from:</span></span>

- <span data-ttu-id="bc110-178">Verwenden Sie den _EndUserQuarantinePermissionsValue_ -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bc110-178">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="bc110-179">Verwenden Sie den _EndUserQuarantinePermissions_ -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bc110-179">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="bc110-180">Diese Methoden werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc110-180">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="bc110-181">Verwenden des EndUserQuarantinePermissionsValue-Parameters</span><span class="sxs-lookup"><span data-stu-id="bc110-181">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="bc110-182">Verwenden Sie die folgende Syntax, um ein Quarantine-Tag mithilfe des _EndUserQuarantinePermissionsValue_ -Parameters zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bc110-182">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="bc110-183">Der _EndUserQuarantinePermissionsValue_ -Parameter verwendet einen Dezimalwert, der aus einem Binärwert konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="bc110-183">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="bc110-184">Der Binärwert entspricht den verfügbaren Benutzerquarantäne Berechtigungen in einer bestimmten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bc110-184">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="bc110-185">Für jede Berechtigung ist der Wert 1 gleich true und der Wert 0 gleich false.</span><span class="sxs-lookup"><span data-stu-id="bc110-185">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="bc110-186">Die erforderliche Reihenfolge und die Werte für jede einzelne Berechtigung in vordefinierten Berechtigungsgruppen werden in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="bc110-186">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="bc110-187">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bc110-187">Permission</span></span>|<span data-ttu-id="bc110-188">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-188">No access</span></span>|<span data-ttu-id="bc110-189">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-189">Limited access</span></span>|<span data-ttu-id="bc110-190">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-190">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="bc110-191">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="bc110-191">PermissionToAllowSender</span></span>|<span data-ttu-id="bc110-192">0</span><span class="sxs-lookup"><span data-stu-id="bc110-192">0</span></span>|<span data-ttu-id="bc110-193">0</span><span class="sxs-lookup"><span data-stu-id="bc110-193">0</span></span>|<span data-ttu-id="bc110-194">1</span><span class="sxs-lookup"><span data-stu-id="bc110-194">1</span></span>|
|<span data-ttu-id="bc110-195">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="bc110-195">PermissionToBlockSender</span></span>|<span data-ttu-id="bc110-196">0</span><span class="sxs-lookup"><span data-stu-id="bc110-196">0</span></span>|<span data-ttu-id="bc110-197">1</span><span class="sxs-lookup"><span data-stu-id="bc110-197">1</span></span>|<span data-ttu-id="bc110-198">1</span><span class="sxs-lookup"><span data-stu-id="bc110-198">1</span></span>|
|<span data-ttu-id="bc110-199">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="bc110-199">PermissionToDelete</span></span>|<span data-ttu-id="bc110-200">0</span><span class="sxs-lookup"><span data-stu-id="bc110-200">0</span></span>|<span data-ttu-id="bc110-201">1</span><span class="sxs-lookup"><span data-stu-id="bc110-201">1</span></span>|<span data-ttu-id="bc110-202">1</span><span class="sxs-lookup"><span data-stu-id="bc110-202">1</span></span>|
|<span data-ttu-id="bc110-203">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bc110-203">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="bc110-204">0</span><span class="sxs-lookup"><span data-stu-id="bc110-204">0</span></span>|<span data-ttu-id="bc110-205">0</span><span class="sxs-lookup"><span data-stu-id="bc110-205">0</span></span>|<span data-ttu-id="bc110-206">0</span><span class="sxs-lookup"><span data-stu-id="bc110-206">0</span></span>|
|<span data-ttu-id="bc110-207">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="bc110-207">PermissionToPreview</span></span>|<span data-ttu-id="bc110-208">0</span><span class="sxs-lookup"><span data-stu-id="bc110-208">0</span></span>|<span data-ttu-id="bc110-209">1</span><span class="sxs-lookup"><span data-stu-id="bc110-209">1</span></span>|<span data-ttu-id="bc110-210">1</span><span class="sxs-lookup"><span data-stu-id="bc110-210">1</span></span>|
|<span data-ttu-id="bc110-211">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="bc110-211">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="bc110-212">0</span><span class="sxs-lookup"><span data-stu-id="bc110-212">0</span></span>|<span data-ttu-id="bc110-213">0</span><span class="sxs-lookup"><span data-stu-id="bc110-213">0</span></span>|<span data-ttu-id="bc110-214">1</span><span class="sxs-lookup"><span data-stu-id="bc110-214">1</span></span>|
|<span data-ttu-id="bc110-215">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="bc110-215">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="bc110-216">0</span><span class="sxs-lookup"><span data-stu-id="bc110-216">0</span></span>|<span data-ttu-id="bc110-217">1</span><span class="sxs-lookup"><span data-stu-id="bc110-217">1</span></span>|<span data-ttu-id="bc110-218">0</span><span class="sxs-lookup"><span data-stu-id="bc110-218">0</span></span>|
|<span data-ttu-id="bc110-219">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bc110-219">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="bc110-220">0</span><span class="sxs-lookup"><span data-stu-id="bc110-220">0</span></span>|<span data-ttu-id="bc110-221">0</span><span class="sxs-lookup"><span data-stu-id="bc110-221">0</span></span>|<span data-ttu-id="bc110-222">0</span><span class="sxs-lookup"><span data-stu-id="bc110-222">0</span></span>|
|<span data-ttu-id="bc110-223">Binärer Wert</span><span class="sxs-lookup"><span data-stu-id="bc110-223">Binary value</span></span>|<span data-ttu-id="bc110-224">00000000</span><span class="sxs-lookup"><span data-stu-id="bc110-224">00000000</span></span>|<span data-ttu-id="bc110-225">01101010</span><span class="sxs-lookup"><span data-stu-id="bc110-225">01101010</span></span>|<span data-ttu-id="bc110-226">11101100</span><span class="sxs-lookup"><span data-stu-id="bc110-226">11101100</span></span>|
|<span data-ttu-id="bc110-227">Zu verwendender Dezimalwert</span><span class="sxs-lookup"><span data-stu-id="bc110-227">Decimal value to use</span></span>|<span data-ttu-id="bc110-228">0</span><span class="sxs-lookup"><span data-stu-id="bc110-228">0</span></span>|<span data-ttu-id="bc110-229">106</span><span class="sxs-lookup"><span data-stu-id="bc110-229">106</span></span>|<span data-ttu-id="bc110-230">236</span><span class="sxs-lookup"><span data-stu-id="bc110-230">236</span></span>|

<span data-ttu-id="bc110-231"><sup>\*</sup> Derzeit ist dieser Wert immer 0.</span><span class="sxs-lookup"><span data-stu-id="bc110-231"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="bc110-232">Bei PermissionToViewHeader wird der Wert 0 nicht ausgeblendet die Schaltfläche **Nachrichtenkopfzeile anzeigen** in den Details der isolierten Nachricht (die Schaltfläche ist immer verfügbar).</span><span class="sxs-lookup"><span data-stu-id="bc110-232">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="bc110-233"><sup>\*\*</sup> Legen Sie beide Werte nicht auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="bc110-233"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="bc110-234">Legen Sie eine auf 1 und die andere auf 0 fest, oder legen Sie beide auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="bc110-234">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="bc110-235">In diesem Beispiel wird ein neuer Quarantine Tag-Name NoAccess erstellt, der die in der vorherigen Tabelle beschriebenen Berechtigungen ohne Zugriff zuweist.</span><span class="sxs-lookup"><span data-stu-id="bc110-235">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="bc110-236">Verwenden Sie für beschränkte Zugriffsberechtigungen den Wert 106.</span><span class="sxs-lookup"><span data-stu-id="bc110-236">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="bc110-237">Verwenden Sie für Vollzugriff Berechtigungen den Wert 236.</span><span class="sxs-lookup"><span data-stu-id="bc110-237">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="bc110-238">Verwenden Sie für benutzerdefinierte Berechtigungen die vorherige Tabelle, um den Binärwert abzurufen, der den gewünschten Berechtigungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="bc110-238">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="bc110-239">Konvertieren Sie den Binärwert in einen Dezimalwert, und verwenden Sie den Decimal-Wert für den _EndUserQuarantinePermissionsValue_ -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bc110-239">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="bc110-240">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="bc110-240">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="bc110-241">Verwenden des EndUserQuarantinePermissions-Parameters</span><span class="sxs-lookup"><span data-stu-id="bc110-241">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="bc110-242">Führen Sie die folgenden Schritte aus, um ein Quarantine-Tag mithilfe des _EndUserQuarantinePermissionsValue_ -Parameters zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bc110-242">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="bc110-243">A.</span><span class="sxs-lookup"><span data-stu-id="bc110-243">A.</span></span> <span data-ttu-id="bc110-244">Speichern Sie ein Quarantäne Berechtigungsobjekt in einer Variablen mithilfe des **New-QuarantinePermissions-** Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="bc110-244">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>
<br/>
<span data-ttu-id="bc110-245">B.</span><span class="sxs-lookup"><span data-stu-id="bc110-245">B.</span></span> <span data-ttu-id="bc110-246">Verwenden Sie die Variable als _EndUserQuarantinePermissions_ -Wert im **New-QuarantineTag-** Befehl.</span><span class="sxs-lookup"><span data-stu-id="bc110-246">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="bc110-247">Schritt a: Speichern eines Quarantäne Berechtigungsobjekts in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="bc110-247">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="bc110-248">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="bc110-248">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="bc110-249">Der Standardwert für alle nicht verwendeten Parameter ist `$false` , sodass Sie nur die Parameter verwenden müssen, für die Sie den Wert festlegen möchten `$true` .</span><span class="sxs-lookup"><span data-stu-id="bc110-249">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="bc110-250">In den folgenden Beispielen wird gezeigt, wie Berechtigungsobjekte erstellt werden, die den vordefinierten Berechtigungsgruppen entsprechen:</span><span class="sxs-lookup"><span data-stu-id="bc110-250">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="bc110-251">**Kein Zugriff** :</span><span class="sxs-lookup"><span data-stu-id="bc110-251">**No access** :</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="bc110-252">**Limitierter Zugriff** :</span><span class="sxs-lookup"><span data-stu-id="bc110-252">**Limited access** :</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="bc110-253">**Vollzugriff** :</span><span class="sxs-lookup"><span data-stu-id="bc110-253">**Full access** :</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="bc110-254">Um die Werte anzuzeigen, die Sie festgelegt haben, führen Sie den Variablennamen als Befehl aus (führen Sie beispielsweise den Befehl aus `$NoAccess` ).</span><span class="sxs-lookup"><span data-stu-id="bc110-254">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="bc110-255">Legen Sie für benutzerdefinierte Berechtigungen nicht die Parameter _PermissionToRelease_ und _PermissionToRequestRelease_ auf fest `$true` .</span><span class="sxs-lookup"><span data-stu-id="bc110-255">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="bc110-256">Legen Sie eine auf fest, `$true` und lassen Sie die andere als `$false` , oder belassen Sie beide als `$false` .</span><span class="sxs-lookup"><span data-stu-id="bc110-256">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="bc110-257">Sie können eine vorhandene Berechtigungsobjekt Variable auch ändern, nachdem Sie Sie erstellt haben, jedoch bevor Sie Sie mithilfe des Cmdlets "Cmdlet **festlegen-QuarantinePermissions** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc110-257">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="bc110-258">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) und [Festlegen von QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="bc110-258">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="bc110-259">Schritt B: Verwenden der Variablen im New-QuarantineTag-Befehl</span><span class="sxs-lookup"><span data-stu-id="bc110-259">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="bc110-260">Nachdem Sie das Permissions-Objekt in einer Variablen erstellt und gespeichert haben, verwenden Sie die Variable für den Wert des _EndUserQuarantinePermission_ -Parameters im folgenden **New-QuarantineTag-** Befehl:</span><span class="sxs-lookup"><span data-stu-id="bc110-260">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="bc110-261">In diesem Beispiel wird mithilfe des `$LimitedAccess` Permissions-Objekts, das im vorherigen Schritt beschrieben und erstellt wurde, ein neues Quarantine-Tag mit dem Namen LimitedAccess erstellt.</span><span class="sxs-lookup"><span data-stu-id="bc110-261">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="bc110-262">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="bc110-262">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="bc110-263">Schritt 2: Zuweisen eines Quarantäne Tags zu unterstützten Features</span><span class="sxs-lookup"><span data-stu-id="bc110-263">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="bc110-264">In _unterstützten_ Schutzfunktionen, die Nachrichten oder Dateien isolieren (automatisch oder als konfigurierbare Aktion), können Sie die verfügbaren Quarantäneaktionen mit einem quarantänetag versehen.</span><span class="sxs-lookup"><span data-stu-id="bc110-264">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="bc110-265">In der folgenden Tabelle werden Features zum Isolieren von Nachrichten und zur Verfügbarkeit von Quarantäne Tags beschrieben:</span><span class="sxs-lookup"><span data-stu-id="bc110-265">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="bc110-266">Feature</span><span class="sxs-lookup"><span data-stu-id="bc110-266">Feature</span></span>|<span data-ttu-id="bc110-267">Unterstützte Quarantäne-Tags?</span><span class="sxs-lookup"><span data-stu-id="bc110-267">Quarantine tags supported?</span></span>|<span data-ttu-id="bc110-268">Verwendete standardmäßige Quarantäne Tags</span><span class="sxs-lookup"><span data-stu-id="bc110-268">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="bc110-269">[Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="bc110-269">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="bc110-270">**Spam** ( _Spam_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-270">**Spam** ( _SpamAction_ )</span></span></li><li><span data-ttu-id="bc110-271">**Spam mit hoher Zuverlässigkeit** ( _: highconfidencespamaction_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-271">**High confidence spam** ( _HighConfidenceSpamAction_ )</span></span></li><li><span data-ttu-id="bc110-272">**Phishing-e-Mails** ( _PhishSpamAction_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-272">**Phishing email** ( _PhishSpamAction_ )</span></span></li><li><span data-ttu-id="bc110-273">**Phishing-e-Mails mit hoher Zuverlässigkeit** ( _HighConfidencePhishAction_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-273">**High confidence phishing email** ( _HighConfidencePhishAction_ )</span></span></li><li><span data-ttu-id="bc110-274">**Massen-e-Mails** ( _BulkSpamAction_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-274">**Bulk email** ( _BulkSpamAction_ )</span></span></li></ul>|<span data-ttu-id="bc110-275">Ja</span><span class="sxs-lookup"><span data-stu-id="bc110-275">Yes</span></span>|<ul><li><span data-ttu-id="bc110-276">DefaultSpamTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="bc110-276">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="bc110-277">DefaultHighConfSpamTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="bc110-277">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="bc110-278">DefaultPhishTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="bc110-278">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="bc110-279">DefaultHighConfPhishTag (kein Zugriff)</span><span class="sxs-lookup"><span data-stu-id="bc110-279">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="bc110-280">DefaultBulkTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="bc110-280">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="bc110-281">Anti-Phishing-Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="bc110-281">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="bc110-282">[Spoof Intelligence Protection](set-up-anti-phishing-policies.md#spoof-settings) ( _AuthenticationFailAction_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-282">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) ( _AuthenticationFailAction_ )</span></span></li><li><span data-ttu-id="bc110-283">[Identitätswechsel Schutz](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bc110-283">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="bc110-284">**Wenn e-Mail von einem imitierten Benutzer gesendet wird** ( _TargetedUserProtectionAction_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-284">**If email is sent by an impersonated user** ( _TargetedUserProtectionAction_ )</span></span></li><li><span data-ttu-id="bc110-285">**Wenn e-Mail von einer imitierten Domäne gesendet wird** ( _TargetedDomainProtectionAction_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-285">**If email is sent by an impersonated domain** ( _TargetedDomainProtectionAction_ )</span></span></li><li><span data-ttu-id="bc110-286">**Post Fach Intelligenz** \> **Wenn e-Mail von einem imitierten Benutzer gesendet wird** ( _MailboxIntelligenceProtectionAction_ )</span><span class="sxs-lookup"><span data-stu-id="bc110-286">**Mailbox intelligence** \> **If email is sent by an impersonated user** ( _MailboxIntelligenceProtectionAction_ )</span></span></li></ul></li></ul></ul>|<span data-ttu-id="bc110-287">Nein</span><span class="sxs-lookup"><span data-stu-id="bc110-287">No</span></span>|<span data-ttu-id="bc110-288">n/v</span><span class="sxs-lookup"><span data-stu-id="bc110-288">n/a</span></span>|
|<span data-ttu-id="bc110-289">[Anti-Malware-Richtlinien](configure-anti-malware-policies.md): alle erkannten Nachrichten werden immer isoliert.</span><span class="sxs-lookup"><span data-stu-id="bc110-289">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="bc110-290">Nein</span><span class="sxs-lookup"><span data-stu-id="bc110-290">No</span></span>|<span data-ttu-id="bc110-291">n/v</span><span class="sxs-lookup"><span data-stu-id="bc110-291">n/a</span></span>|
|[<span data-ttu-id="bc110-292">ATP für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc110-292">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="bc110-293">Nein</span><span class="sxs-lookup"><span data-stu-id="bc110-293">No</span></span>|<span data-ttu-id="bc110-294">n/v</span><span class="sxs-lookup"><span data-stu-id="bc110-294">n/a</span></span>|
|<span data-ttu-id="bc110-295">[Nachrichtenfluss Regeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet) mit der Aktion: **Zustellung der Nachricht an die gehostete Quarantäne** ( _Quarantäne_ ).</span><span class="sxs-lookup"><span data-stu-id="bc110-295">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** ( _Quarantine_ ).</span></span>|<span data-ttu-id="bc110-296">Nein</span><span class="sxs-lookup"><span data-stu-id="bc110-296">No</span></span>|<span data-ttu-id="bc110-297">n/v</span><span class="sxs-lookup"><span data-stu-id="bc110-297">n/a</span></span>|
|

<span data-ttu-id="bc110-298"><sup>\*</sup> Einstellungen für den Identitätswechsel Schutz stehen nur in Anti-Phishing-Richtlinien in Microsoft Defender für Office 365 zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bc110-298"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="bc110-299">Wenn Sie mit den Endbenutzerberechtigungen zufrieden sind, die von den standardmäßigen Quarantäne-Tags bereitgestellt werden, müssen Sie nichts tun.</span><span class="sxs-lookup"><span data-stu-id="bc110-299">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="bc110-300">Wenn Sie die Endbenutzerfunktionen (verfügbare Schaltflächen) in Spambenachrichtigungen für Endbenutzer oder in isolierten Nachrichtendetails anpassen möchten, können Sie ein benutzerdefiniertes Quarantäne-Tag zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bc110-300">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="bc110-301">Zuweisen von Quarantäne Tags in Anti-Spam-Richtlinien im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="bc110-301">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="bc110-302">Ausführliche Anweisungen zum Erstellen und Ändern von Anti-Spam-Richtlinien finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bc110-302">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="bc110-303">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** , \> und wählen Sie dann **Anti-Spam** aus.</span><span class="sxs-lookup"><span data-stu-id="bc110-303">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam** .</span></span> <span data-ttu-id="bc110-304">Oder öffnen Sie <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="bc110-304">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="bc110-305">Suchen und Auswählen einer vorhandenen Antispam-Richtlinie zum Bearbeiten oder Erstellen einer neuen Antispampolitik.</span><span class="sxs-lookup"><span data-stu-id="bc110-305">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="bc110-306">Erweitern Sie im Flyout Richtlinie Details den Abschnitt **Spam-und Massenaktionen** .</span><span class="sxs-lookup"><span data-stu-id="bc110-306">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>
  
4. <span data-ttu-id="bc110-307">Wenn Sie die Option **Quarantäne Nachricht** für die Aktion eines verfügbaren Spam Filterungs Urteils ausgewählt haben, steht das Feld **Quarantäne-richtlinientag anwenden** zur Verfügung, um das Quarantäne-Tag für das Urteil auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="bc110-307">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="bc110-308">**Hinweis** : Wenn Sie eine neue Richtlinie erstellen, wird durch einen leeren Quarantäne-Tag-Wert für ein Spamfilter Urteil angegeben, dass das standardmäßige quarantänetag für dieses Urteil verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc110-308">**Note** : When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="bc110-309">Wenn Sie die Richtlinie später bearbeiten, werden die leeren Werte durch die tatsächlichen Standardnamen der Quarantäne Tags ersetzt, wie in der vorherigen Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc110-309">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>
  
   ![Auswählen von Quarantäne Tags in einer Anti-Spam-Richtlinie](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="bc110-311">Klicken Sie nach Abschluss des Vorgangs auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="bc110-311">When you're finished, click **Save** .</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="bc110-312">Zuweisen von Quarantäne Tags in Anti-Spam-Richtlinien in PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc110-312">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="bc110-313">Wenn Sie lieber PowerShell zum Zuweisen von Quarantäne Tags in Anti-Spam-Richtlinien verwenden möchten, stellen Sie eine Verbindung mit Exchange Online PowerShell oder Exchange Online Protection PowerShell her, und verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="bc110-313">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="bc110-314">**Hinweise** :</span><span class="sxs-lookup"><span data-stu-id="bc110-314">**Notes** :</span></span>

- <span data-ttu-id="bc110-315">Der Standardwert für den Parameter _HighConfidencePhishAction_ ist Quarantine, sodass Sie die Quarantäneaktion für hohe vertrauenswürdige Phishing-Erkennungen in neuen Anti-Spam-Richtlinien nicht festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="bc110-315">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="bc110-316">Bei allen anderen Spamfilter Urteilen in neuen oder vorhandenen Anti-Spam-Richtlinien ist das quarantänetag nur wirksam, wenn der Aktionswert Quarantine lautet.</span><span class="sxs-lookup"><span data-stu-id="bc110-316">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="bc110-317">Führen Sie den folgenden Befehl aus, um die Aktionswerte in vorhandenen Anti-Spam-Richtlinien anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="bc110-317">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="bc110-318">Informationen zu den Standard Aktionswerten und den empfohlenen Aktionswerten für Standard und Strict finden Sie unter [EoP Anti-Spam Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="bc110-318">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="bc110-319">Ein Spam Filterungs Urteil ohne einen entsprechenden Parameter für die Quarantäne Kennzeichnung bedeutet, dass das [standardmäßige quarantänetag](#step-2-assign-a-quarantine-tag-to-supported-features) für dieses Urteil verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc110-319">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="bc110-320">Sie müssen nur ein Standardmäßiges Quarantine-Tag durch ein benutzerdefiniertes Quarantine-Tag ersetzen, wenn Sie die standardmäßigen Endbenutzerfunktionen für isolierte Nachrichten ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="bc110-320">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="bc110-321">Eine neue Anti-Spam-Richtlinie in PowerShell erfordert eine Spamfilter Richtlinie (Einstellungen) mithilfe des **New-hostedcontentfilterpolicy dient zum-** Cmdlets und einer neuen Spamfilter Regel (Empfängerfilter) mithilfe des **New-HostedContentFilterRule-** Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="bc110-321">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="bc110-322">Anweisungen finden Sie unter [Verwenden von PowerShell zum Erstellen von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="bc110-322">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="bc110-323">In diesem Beispiel wird eine neue Spamfilter Richtlinie mit dem Namen "Research Department" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="bc110-323">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="bc110-324">Die Aktion für alle Spamfilter-Urteile wird auf Quarantäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bc110-324">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="bc110-325">Das benutzerdefinierte Quarantäne-Tag mit dem Namen NoAccess, das **keine Zugriffs** Berechtigungen zuweist, ersetzt alle standardmäßigen Quarantäne Tags, die nicht bereits standardmäßig **keine Zugriffs** Berechtigungen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bc110-325">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="bc110-326">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="bc110-326">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="bc110-327">In diesem Beispiel wird die vorhandene Spamfilter Richtlinie namens "Human Resources" geändert.</span><span class="sxs-lookup"><span data-stu-id="bc110-327">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="bc110-328">Die Aktion für das Spamquarantäne Urteil wird auf Quarantäne festgelegt, und das benutzerdefinierte Quarantäne-Tag mit dem Namen NoAccess wird zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="bc110-328">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="bc110-329">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="bc110-329">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="bc110-330">Konfigurieren globaler Quarantäne Benachrichtigungseinstellungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="bc110-330">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="bc110-331">Mit den globalen Einstellungen für Quarantäne-Tags können Sie die Endbenutzer-Spambenachrichtigungen anpassen, die an Empfänger von Nachrichten gesendet werden, die isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="bc110-331">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="bc110-332">Weitere Informationen zu diesen Benachrichtigungen finden Sie unter [End-User Spam Notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="bc110-332">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="bc110-333">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** , und wählen Sie dann **Quarantine Tags** aus.</span><span class="sxs-lookup"><span data-stu-id="bc110-333">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags** .</span></span>

2. <span data-ttu-id="bc110-334">Wählen Sie auf der Seite **Tags isolieren** die Option **globale Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="bc110-334">On the **Quarantine tags** page, select **Global settings** .</span></span>

3. <span data-ttu-id="bc110-335">Konfigurieren Sie im Flyout " **Quarantäne Benachrichtigungseinstellungen** ", das geöffnet wird, einige oder alle der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="bc110-335">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="bc110-336">**Mein Firmen Logo verwenden** : Wählen Sie diese Option aus, um das standardmäßige Microsoft-Logo zu ersetzen, das oben in Spambenachrichtigungen für Endbenutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc110-336">**Use my company logo** : Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="bc110-337">Bevor Sie dies tun, müssen Sie den Anweisungen unter [Anpassen des Microsoft 365-Designs für Ihre Organisation](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) folgen, um Ihr benutzerdefiniertes Logo hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="bc110-337">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="bc110-338">Der folgende Screenshot zeigt ein benutzerdefiniertes Logo in einer spambenachrichtigung für Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="bc110-338">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Ein benutzerdefiniertes Logo in einer spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="bc110-340">**Sprache auswählen** : Spambenachrichtigungen für Endbenutzer werden basierend auf den Spracheinstellungen des Empfängers bereits lokalisiert.</span><span class="sxs-lookup"><span data-stu-id="bc110-340">**Choose language** : End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="bc110-341">Sie können benutzerdefinierten Text in unterschiedlichen Sprachen für den **Anzeigenamen** und die **Haftungsausschluss** Werte angeben.</span><span class="sxs-lookup"><span data-stu-id="bc110-341">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="bc110-342">Wählen Sie mindestens eine Sprache aus dem Feld erste Sprache aus, und klicken Sie dann auf **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="bc110-342">Select at least one language from the first language box and then click **Add** .</span></span> <span data-ttu-id="bc110-343">Sie können mehrere Sprachen auswählen, indem Sie nacheinander auf **Hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="bc110-343">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="bc110-344">Ein Feld für Abschnitts Sprachen zeigt alle Sprachen an, die Sie ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="bc110-344">A section language box shows all of the languages that you've selected:</span></span>

     ![Ausgewählte Sprachen im Feld zweite Sprache in den globalen Quarantäne Benachrichtigungseinstellungen von Quarantäne Tags](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="bc110-346">**Anzeigename** : passen Sie den Anzeigenamen des Absenders an, der in Spambenachrichtigungen für Endbenutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc110-346">**Display name** : Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="bc110-347">Wählen Sie für jede Sprache, die Sie hinzugefügt haben, im Feld zweite Sprache die Sprache aus (Klicken Sie nicht auf das X), und geben Sie den gewünschten Textwert in das Feld **Anzeigename** ein.</span><span class="sxs-lookup"><span data-stu-id="bc110-347">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="bc110-348">Der folgende Screenshot zeigt den benutzerdefinierten Anzeigenamen in einer spambenachrichtigung für Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="bc110-348">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Ein benutzerdefinierter Absender Anzeigename in einer spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="bc110-350">**Haftungsausschluss** : Fügen Sie am Ende der Spambenachrichtigungen für Endbenutzer einen benutzerdefinierten Haftungsausschluss hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc110-350">**Disclaimer** : Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="bc110-351">Der lokalisierte Text, **ein Haftungsausschluss aus Ihrer Organisation:** ist immer zuerst enthalten, gefolgt von dem von Ihnen angegebenen Text.</span><span class="sxs-lookup"><span data-stu-id="bc110-351">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="bc110-352">Wählen Sie für jede Sprache, die Sie hinzugefügt haben, im Feld zweite Sprache die Sprache aus (Klicken Sie nicht auf das X), und geben Sie den gewünschten Textwert in das Feld **Disclaimer** ein.</span><span class="sxs-lookup"><span data-stu-id="bc110-352">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="bc110-353">Der folgende Screenshot zeigt den benutzerdefinierten Haftungsausschluss in einer spambenachrichtigung für Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="bc110-353">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Ein benutzerdefinierter Haftungsausschluss am Ende einer spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="bc110-355">Anzeigen von Quarantäne Tags im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="bc110-355">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="bc110-356">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** , und wählen Sie dann **Quarantine Tags** aus.</span><span class="sxs-lookup"><span data-stu-id="bc110-356">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags** .</span></span>

- <span data-ttu-id="bc110-357">Wenn Sie die Einstellungen integrierter oder benutzerdefinierter Quarantäne Tags anzeigen möchten, wählen Sie das Quarantäne-Tag aus der Liste aus (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="bc110-357">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="bc110-358">Um die globalen Einstellungen anzuzeigen, wählen Sie **globale Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="bc110-358">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="bc110-359">Anzeigen von Quarantäne Tags in PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc110-359">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="bc110-360">Wenn Sie lieber PowerShell zum Anzeigen von Quarantäne Tags verwenden möchten, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bc110-360">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="bc110-361">Um eine Zusammenfassungsliste aller integrierten oder benutzerdefinierten Tags anzuzeigen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bc110-361">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="bc110-362">Um die Einstellungen integrierter oder benutzerdefinierter Quarantäne Tags anzuzeigen, ersetzen Sie \<TagName\> durch den Namen des Quarantäne Tags, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bc110-362">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="bc110-363">Führen Sie den folgenden Befehl aus, um die globalen Einstellungen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="bc110-363">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="bc110-364">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="bc110-364">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="bc110-365">Entfernen von Quarantäne Tags im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="bc110-365">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="bc110-366">**Hinweise** :</span><span class="sxs-lookup"><span data-stu-id="bc110-366">**Notes** :</span></span>

- <span data-ttu-id="bc110-367">Integrierte Quarantäne Tags können nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="bc110-367">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="bc110-368">Vergewissern Sie sich vor dem Entfernen eines benutzerdefinierten Quarantäne Tags, dass es nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc110-368">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="bc110-369">Führen Sie beispielsweise den folgenden Befehl in PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="bc110-369">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="bc110-370">Wenn das Quarantäne-Tag verwendet wird, [Ersetzen Sie das zugewiesene Quarantäne-Tag](#step-2-assign-a-quarantine-tag-to-supported-features) , bevor Sie es entfernen.</span><span class="sxs-lookup"><span data-stu-id="bc110-370">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="bc110-371">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** , und wählen Sie dann **Quarantine Tags** aus.</span><span class="sxs-lookup"><span data-stu-id="bc110-371">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags** .</span></span>

2. <span data-ttu-id="bc110-372">Wählen Sie auf der Seite **Tags isolieren** das benutzerdefinierte Quarantäne-Tag aus, das Sie entfernen möchten, und klicken Sie dann auf **Delete Tag** .</span><span class="sxs-lookup"><span data-stu-id="bc110-372">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag** .</span></span>

3. <span data-ttu-id="bc110-373">Klicken Sie im Bestätigungsdialogfeld, das angezeigt wird, auf **Tag entfernen** .</span><span class="sxs-lookup"><span data-stu-id="bc110-373">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="bc110-374">Entfernen von Quarantäne Tags in PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc110-374">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="bc110-375">Wenn Sie lieber PowerShell zum Entfernen eines benutzerdefinierten Quarantäne Tags verwenden möchten, ersetzen Sie \<TagName\> durch den Namen des Quarantine-Tags, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bc110-375">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="bc110-376">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="bc110-376">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="bc110-377">Details zu Quarantäne-Tag-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bc110-377">Quarantine tag permission details</span></span>

<span data-ttu-id="bc110-378">In den folgenden Abschnitten werden die Auswirkungen von vordefinierten Berechtigungsgruppen und einzelnen Berechtigungen in den Details von isolierten Nachrichten und Spambenachrichtigungen für Endbenutzer beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc110-378">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="bc110-379">Voreingestellte Berechtigungsgruppen</span><span class="sxs-lookup"><span data-stu-id="bc110-379">Preset permissions groups</span></span>

<span data-ttu-id="bc110-380">Die einzelnen Berechtigungen, die in vordefinierten Berechtigungsgruppen enthalten sind, werden in der Tabelle am Anfang dieses Artikels aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bc110-380">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="bc110-381">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-381">No access</span></span>

<span data-ttu-id="bc110-382">Wenn das Quarantine-Tag **keine Zugriffs** Berechtigungen (keine Berechtigungen) zuweist, erhalten Benutzer weiterhin einige grundlegende Funktionen:</span><span class="sxs-lookup"><span data-stu-id="bc110-382">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="bc110-383">**Details zur isolierten Nachricht** : die Schaltfläche **Nachrichtenkopfzeile anzeigen** ist immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-383">**Quarantined message details** : The **View message header** button is always available.</span></span>

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn das Quarantine-Tag dem Benutzer keine Zugriffsberechtigungen erteilt](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="bc110-385">**Spambenachrichtigungen für Endbenutzer** : die Schaltfläche **überprüfen** , mit der der Benutzer zur Nachricht in Quarantäne gelangen kann, ist immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-385">**End-user spam notifications** : The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Verfügbare Schaltflächen in der spambenachrichtigung für Endbenutzer, wenn das Quarantine-Tag dem Benutzer keine Zugriffsberechtigungen erteilt](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="bc110-387">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-387">Limited access</span></span>

<span data-ttu-id="bc110-388">Wenn das Quarantine-Tag die **begrenzten Zugriffs** Berechtigungen zuweist, erhalten Benutzer die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="bc110-388">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="bc110-389">**Details zur isolierten Nachricht** : die folgenden Schaltflächen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="bc110-389">**Quarantined message details** : The following buttons are available:</span></span>
  - <span data-ttu-id="bc110-390">**Anforderungs Version**</span><span class="sxs-lookup"><span data-stu-id="bc110-390">**Request release**</span></span>
  - <span data-ttu-id="bc110-391">**Nachrichtenkopfzeile anzeigen**</span><span class="sxs-lookup"><span data-stu-id="bc110-391">**View message header**</span></span>
  - <span data-ttu-id="bc110-392">**Vorschau Nachricht**</span><span class="sxs-lookup"><span data-stu-id="bc110-392">**Preview message**</span></span>
  - <span data-ttu-id="bc110-393">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="bc110-393">**Block sender**</span></span>
  - <span data-ttu-id="bc110-394">**Aus Quarantäne entfernen**</span><span class="sxs-lookup"><span data-stu-id="bc110-394">**Remove from quarantine**</span></span>

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn das quarantänetag dem Benutzer beschränkte Zugriffsberechtigungen erteilt](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="bc110-396">**Spambenachrichtigungen für Endbenutzer** : die folgenden Schaltflächen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="bc110-396">**End-user spam notifications** : The following buttons are available:</span></span>
  - <span data-ttu-id="bc110-397">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="bc110-397">**Block sender**</span></span>
  - <span data-ttu-id="bc110-398">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="bc110-398">**Review**</span></span>

  ![Verfügbare Schaltflächen in der spambenachrichtigung für Endbenutzer, wenn das Quarantine-Tag dem Benutzer beschränkte Zugriffsberechtigungen erteilt](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="bc110-400">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="bc110-400">Full access</span></span>

<span data-ttu-id="bc110-401">Wenn das Quarantine-Tag die **vollständigen Zugriffs** Berechtigungen (alle verfügbaren Berechtigungen) zuweist, erhalten Benutzer die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="bc110-401">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="bc110-402">**Details zur isolierten Nachricht** : die folgenden Schaltflächen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="bc110-402">**Quarantined message details** : The following buttons are available:</span></span>
  - <span data-ttu-id="bc110-403">**Nachricht freigeben**</span><span class="sxs-lookup"><span data-stu-id="bc110-403">**Release message**</span></span>
  - <span data-ttu-id="bc110-404">**Nachrichtenkopfzeile anzeigen**</span><span class="sxs-lookup"><span data-stu-id="bc110-404">**View message header**</span></span>
  - <span data-ttu-id="bc110-405">**Vorschau Nachricht**</span><span class="sxs-lookup"><span data-stu-id="bc110-405">**Preview message**</span></span>
  - <span data-ttu-id="bc110-406">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="bc110-406">**Block sender**</span></span>
  - <span data-ttu-id="bc110-407">**Absender zulassen**</span><span class="sxs-lookup"><span data-stu-id="bc110-407">**Allow sender**</span></span>
  - <span data-ttu-id="bc110-408">**Aus Quarantäne entfernen**</span><span class="sxs-lookup"><span data-stu-id="bc110-408">**Remove from quarantine**</span></span>

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn das Quarantine-Tag dem Benutzervollzugriff erteilt](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="bc110-410">**Spambenachrichtigungen für Endbenutzer** : die folgenden Schaltflächen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="bc110-410">**End-user spam notifications** : The following buttons are available:</span></span>
  - <span data-ttu-id="bc110-411">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="bc110-411">**Block sender**</span></span>
  - <span data-ttu-id="bc110-412">**Freigabe**</span><span class="sxs-lookup"><span data-stu-id="bc110-412">**Release**</span></span>
  - <span data-ttu-id="bc110-413">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="bc110-413">**Review**</span></span>

  ![Verfügbare Schaltflächen in der spambenachrichtigung für Endbenutzer, wenn das Quarantine-Tag dem Benutzervollzugriff erteilt](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="bc110-415">Einzelne Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bc110-415">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="bc110-416">Beachten Sie, dass Benutzer immer die im Abschnitt [kein Zugriff](#no-access) beschriebenen Schaltflächen erhalten.</span><span class="sxs-lookup"><span data-stu-id="bc110-416">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="bc110-417">Diese Schaltflächen sind nicht in den einzelnen Berechtigungs Beschreibungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc110-417">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="bc110-418">Absender Berechtigung zulassen</span><span class="sxs-lookup"><span data-stu-id="bc110-418">Allow sender permission</span></span>

<span data-ttu-id="bc110-419">Die Berechtigung " **Absender zulassen** " ( _PermissionToAllowSender_ ) steuert den Zugriff auf die Schaltfläche, mit der Benutzer den isolierten Nachrichtenabsender bequem zu Ihrer Liste sicherer Absender hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="bc110-419">The **Allow sender** permission ( _PermissionToAllowSender_ ) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="bc110-420">**Details zur isolierten Nachricht** :</span><span class="sxs-lookup"><span data-stu-id="bc110-420">**Quarantined message details** :</span></span>
  - <span data-ttu-id="bc110-421">**Absender Berechtigung zulassen** aktiviert: die Schaltfläche **Absender zulassen** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-421">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="bc110-422">**Absender** Berechtigung deaktiviert zulassen: die Schaltfläche **Absender zulassen** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-422">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="bc110-423">**Spambenachrichtigungen für Endbenutzer** : keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="bc110-423">**End-user spam notifications** : No effect.</span></span>

<span data-ttu-id="bc110-424">Weitere Informationen zur Liste sicherer Absender finden Sie unter verhindern, [dass vertrauenswürdige Absender blockiert werden](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) , und [verwenden Sie Exchange Online PowerShell, um die Sammlung von Listen sicherer Adressen für ein Postfach zu konfigurieren](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="bc110-424">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

### <a name="block-sender-permission"></a><span data-ttu-id="bc110-425">Absender Berechtigung blockieren</span><span class="sxs-lookup"><span data-stu-id="bc110-425">Block sender permission</span></span>

<span data-ttu-id="bc110-426">Die **Block Sender** Permission ( _PermissionToBlockSender_ ) steuert den Zugriff auf die Schaltfläche, mit der Benutzer den isolierten Nachrichtenabsender bequem zu Ihrer Liste blockierter Absender hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="bc110-426">The **Block sender** permission ( _PermissionToBlockSender_ ) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="bc110-427">**Details zur isolierten Nachricht** :</span><span class="sxs-lookup"><span data-stu-id="bc110-427">**Quarantined message details** :</span></span>
  - <span data-ttu-id="bc110-428">Berechtigung " **Absender blockieren** " aktiviert: die Schaltfläche " **Absender blockieren** " ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-428">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="bc110-429">**Absender Berechtigung blockieren** deaktiviert: die Schaltfläche " **Absender blockieren** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="bc110-430">**Spambenachrichtigungen für Endbenutzer** :</span><span class="sxs-lookup"><span data-stu-id="bc110-430">**End-user spam notifications** :</span></span>
  - <span data-ttu-id="bc110-431">**Absender Berechtigung blockieren** deaktiviert: die Schaltfläche " **Absender blockieren** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-431">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="bc110-432">Berechtigung " **Absender blockieren** " aktiviert: die Schaltfläche " **Absender blockieren** " ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-432">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="bc110-433">Weitere Informationen zur Liste blockierter Absender finden Sie unter [Blockieren von Nachrichten von einem Benutzer](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) und [verwenden Exchange Online PowerShell zum Konfigurieren der Sammlung von Listen sicherer Adressen für ein Postfach](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="bc110-433">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

### <a name="delete-permission"></a><span data-ttu-id="bc110-434">Löschen</span><span class="sxs-lookup"><span data-stu-id="bc110-434">Delete permission</span></span>

<span data-ttu-id="bc110-435">Die Berechtigung " **Löschen** " ( _PermissionToDelete_ ) steuert die Möglichkeit der Benutzer, Ihre Nachrichten (Nachrichten, bei denen der Benutzer ein Empfänger ist) aus der Quarantäne zu löschen.</span><span class="sxs-lookup"><span data-stu-id="bc110-435">The **Delete** permission ( _PermissionToDelete_ ) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="bc110-436">**Details zur isolierten Nachricht** :</span><span class="sxs-lookup"><span data-stu-id="bc110-436">**Quarantined message details** :</span></span>
  - <span data-ttu-id="bc110-437">Berechtigung **Löschen** aktiviert: die Schaltfläche **aus Quarantäne entfernen** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-437">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="bc110-438">**Lösch** Berechtigung deaktiviert: die Schaltfläche **aus Quarantäne entfernen** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-438">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="bc110-439">**Spambenachrichtigungen für Endbenutzer** : keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="bc110-439">**End-user spam notifications** : No effect.</span></span>

### <a name="preview-permission"></a><span data-ttu-id="bc110-440">Vorschau Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bc110-440">Preview permission</span></span>

<span data-ttu-id="bc110-441">Die **Preview** -Berechtigung ( _PermissionToPreview_ ) steuert die Möglichkeit der Benutzer, Ihre Nachrichten in der Quarantäne anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bc110-441">The **Preview** permission ( _PermissionToPreview_ ) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="bc110-442">**Details zur isolierten Nachricht** :</span><span class="sxs-lookup"><span data-stu-id="bc110-442">**Quarantined message details** :</span></span>
  - <span data-ttu-id="bc110-443">**Vorschau** Berechtigung aktiviert: die Schaltfläche **Vorschau Nachricht** steht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bc110-443">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="bc110-444">**Vorschau** Berechtigung deaktiviert: die Schaltfläche **Vorschau Nachricht** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-444">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="bc110-445">**Spambenachrichtigungen für Endbenutzer** : keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="bc110-445">**End-user spam notifications** : No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="bc110-446">Zulassen, dass Empfänger eine Nachricht aus der Quarantäne Berechtigung freigeben</span><span class="sxs-lookup"><span data-stu-id="bc110-446">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="bc110-447">Das **zulassen, dass Empfänger eine Nachricht aus Quarantine** Permission ( _PermissionToRelease_ ) freigeben, steuert, dass Benutzer Ihre isolierten Nachrichten direkt und ohne Genehmigung eines Administrators freigeben können.</span><span class="sxs-lookup"><span data-stu-id="bc110-447">The **Allow recipients to release a message from quarantine** permission ( _PermissionToRelease_ ) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="bc110-448">**Details zur isolierten Nachricht** :</span><span class="sxs-lookup"><span data-stu-id="bc110-448">**Quarantined message details** :</span></span>
  - <span data-ttu-id="bc110-449">Berechtigung aktiviert: die Schaltfläche **Nachricht freigeben** steht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bc110-449">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="bc110-450">Berechtigung deaktiviert: die Schaltfläche " **Nachricht freigeben** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-450">Permission disabled: The **Release message** button is not available.</span></span>
  
- <span data-ttu-id="bc110-451">**Spambenachrichtigungen für Endbenutzer** :</span><span class="sxs-lookup"><span data-stu-id="bc110-451">**End-user spam notifications** :</span></span>
  - <span data-ttu-id="bc110-452">Berechtigung aktiviert: die Schaltfläche **Version** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-452">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="bc110-453">Berechtigung deaktiviert: die Schaltfläche " **Version** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-453">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="bc110-454">Zulassen, dass Empfänger eine Nachricht für die Freigabe aus der Quarantäne Berechtigung anfordern</span><span class="sxs-lookup"><span data-stu-id="bc110-454">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="bc110-455">Das **zulassen, dass Empfänger eine Nachricht aus der Quarantäne** Berechtigung (Quarantine Permission, _PermissionToRequestRelease_ ) freigegeben werden, steuert, ob Benutzer die Freigabe ihrer isolierten Nachrichten _anfordern_ können.</span><span class="sxs-lookup"><span data-stu-id="bc110-455">The **Allow recipients to request a message to be released from quarantine** permission ( _PermissionToRequestRelease_ ) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="bc110-456">Die Nachricht wird nur freigegeben, nachdem ein Administrator die Anforderung genehmigt hat.</span><span class="sxs-lookup"><span data-stu-id="bc110-456">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="bc110-457">**Details zur isolierten Nachricht** :</span><span class="sxs-lookup"><span data-stu-id="bc110-457">**Quarantined message details** :</span></span>
  - <span data-ttu-id="bc110-458">Berechtigung aktiviert: die Schaltfläche **Version anfordern** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-458">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="bc110-459">Berechtigung deaktiviert: die Schaltfläche " **Anforderungs Version** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-459">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="bc110-460">**Spambenachrichtigungen für Endbenutzer** : die Schaltfläche " **Version** " ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc110-460">**End-user spam notifications** : The **Release** button is not available.</span></span>
