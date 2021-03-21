---
title: Quarantänetags
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Administratoren können erfahren, wie Sie Mithilfe von Quarantänetags steuern, was Benutzer mit ihren isolierten Nachrichten tun können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8024894cdb4a4718422c250eff87fa6da5443a84
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922412"
---
# <a name="quarantine-tags"></a><span data-ttu-id="9e6fa-103">Quarantänetags</span><span class="sxs-lookup"><span data-stu-id="9e6fa-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="9e6fa-104">Die in diesem Artikel beschriebenen Features befinden sich derzeit in Der Vorschau, sind nicht für alle verfügbar und können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="9e6fa-105">Quarantänetags in Exchange Online Protection (EOP) ermöglichen Es Administratoren, zu steuern, was Benutzer mit ihren isolierten Nachrichten tun können, basierend darauf, wie die Nachricht in Quarantäne eingetroffen ist.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="9e6fa-106">EOP hat traditionell bestimmte Interaktivitätsstufen für Nachrichten [in](find-and-release-quarantined-messages-as-a-user.md) Quarantäne und in [Spambenachrichtigungen](use-spam-notifications-to-release-and-report-quarantined-messages.md)von Endbenutzern zugelassen oder verhindert.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="9e6fa-107">Endbenutzer können z. B. Nachrichten anzeigen und veröffentlichen, die von der Antispamfilterung als Spam oder Massenfilter isoliert wurden, aber sie können keine Nachrichten anzeigen oder veröffentlichen, die als Phishing mit hoher Sicherheit isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="9e6fa-108">Für [unterstützte Schutzfunktionen](#step-2-assign-a-quarantine-tag-to-supported-features)geben Quarantänetags an, was Benutzer in Spambenachrichtigungen von Endbenutzern und in ihren isolierten Nachrichten in Quarantäne (Nachrichten, bei denen der Benutzer ein Empfänger ist) tun dürfen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="9e6fa-109">Standardmäßige Quarantänetags werden automatisch zugewiesen, um die historischen Funktionen für Endbenutzer in isolierten Nachrichten zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="9e6fa-110">Sie können auch benutzerdefinierte Quarantänetags erstellen und zuweisen, um Endbenutzern das Ausführen bestimmter Aktionen für isolierte Nachrichten zu ermöglichen oder zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="9e6fa-111">Die einzelnen Berechtigungen werden in den folgenden vordefinierten Berechtigungsgruppen kombiniert:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="9e6fa-112">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-112">No access</span></span>
- <span data-ttu-id="9e6fa-113">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-113">Limited access</span></span>
- <span data-ttu-id="9e6fa-114">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-114">Full access</span></span>

<span data-ttu-id="9e6fa-115">Die verfügbaren individuellen Berechtigungen und was in den vordefinierten Berechtigungsgruppen enthalten ist oder nicht, werden in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="9e6fa-116">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9e6fa-116">Permission</span></span>|<span data-ttu-id="9e6fa-117">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-117">No access</span></span>|<span data-ttu-id="9e6fa-118">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-118">Limited access</span></span>|<span data-ttu-id="9e6fa-119">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="9e6fa-120">**Absender zulassen** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Häkchen](../../media/checkmark.png)|
|<span data-ttu-id="9e6fa-122">**Absender blockieren** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|<span data-ttu-id="9e6fa-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-125">**Delete** (_PermissionToDelete_)</span></span>||![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|<span data-ttu-id="9e6fa-128">**Vorschau** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-128">**Preview** (_PermissionToPreview_)</span></span>||![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|<span data-ttu-id="9e6fa-131">**Zulassen, dass Empfänger eine Nachricht aus der Quarantäne frei lassen** (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Häkchen](../../media/checkmark.png)|
|<span data-ttu-id="9e6fa-133">**Empfänger dürfen anfordern, dass eine Nachricht aus der Quarantäne** freigegeben wird (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Häkchen](../../media/checkmark.png)||
|

<span data-ttu-id="9e6fa-135">Wenn Ihnen die Standardberechtigungen in den vordefinierten Berechtigungsgruppen nicht gefällt, können Sie benutzerdefinierte Berechtigungen verwenden, wenn Sie benutzerdefinierte Quarantänetags erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="9e6fa-136">Weitere Informationen zu den einzelnen Berechtigungen finden Sie im Abschnitt [Quarantänetagberechtigungsdetails](#quarantine-tag-permission-details) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="9e6fa-137">Sie erstellen und weisen Quarantänetags im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Exchange Online-Postfächern; eigenständige EOP PowerShell in & ohne Exchange Online-Postfächer) zu.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9e6fa-138">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="9e6fa-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9e6fa-139">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9e6fa-140">Öffnen Sie , um direkt zur **Seite Quarantänetags zu** <https://protection.office.com/quarantineTags> wechseln.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="9e6fa-141">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9e6fa-142">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9e6fa-143">Zum Anzeigen, Erstellen, Ändern oder Entfernen von Quarantänetags müssen  Sie  Mitglied der Rollen Organisationsverwaltung oder Sicherheitsadministrator im [Security & Compliance Center sein.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="9e6fa-144">Schritt 1: Erstellen von Quarantänetags im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="9e6fa-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="9e6fa-145">Wechseln Sie im Security & Compliance Center **zu** Richtlinie für die Bedrohungsverwaltung, und wählen Sie dann \>  **Quarantänetags aus.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="9e6fa-146">Wählen Sie **auf der Seite Quarantänetags** die Option **Benutzerdefiniertes Tag hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="9e6fa-147">Der **Assistent für neue Tags** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="9e6fa-148">Geben Sie auf der Seite **Tagname** einen kurzen, aber eindeutigen Namen in das **Feld Tagname** ein.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="9e6fa-149">Sie müssen das Tag in den nächsten Schritten nach Namen identifizieren und auswählen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="9e6fa-150">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9e6fa-151">Wählen Sie **auf der** Seite Empfängernachrichtenzugriff einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="9e6fa-152">**Kein Zugriff**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-152">**No access**</span></span>
   - <span data-ttu-id="9e6fa-153">**Eingeschränkter Zugriff**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-153">**Limited access**</span></span>
   - <span data-ttu-id="9e6fa-154">**Vollzugriff**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-154">**Full access**</span></span>

   <span data-ttu-id="9e6fa-155">Die einzelnen Berechtigungen, die in diesen Berechtigungsgruppen enthalten sind, werden weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="9e6fa-156">Um benutzerdefinierte Berechtigungen anzugeben, wählen **Sie Bestimmten Zugriff festlegen (Erweitert)** aus, und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="9e6fa-157">**Einstellung für Freigabeaktion auswählen:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="9e6fa-158">**Keine Veröffentlichungsaktion:** Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="9e6fa-159">**Zulassen, dass Empfänger eine Nachricht aus der Quarantäne frei lassen**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="9e6fa-160">**Zulassen, dass Empfänger die Isolierung einer Nachricht anfordern**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="9e6fa-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="9e6fa-162">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-162">**Delete**</span></span>
       - <span data-ttu-id="9e6fa-163">**Preview**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-163">**Preview**</span></span>
       - <span data-ttu-id="9e6fa-164">**Absender zulassen**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-164">**Allow sender**</span></span>
       - <span data-ttu-id="9e6fa-165">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-165">**Block sender**</span></span>

   <span data-ttu-id="9e6fa-166">Diese Berechtigungen und ihre Auswirkungen auf isolierte Nachrichten und Spambenachrichtigungen für Endbenutzer werden weiter unten in diesem Artikel im Abschnitt Quarantänetagberechtigungsdetails beschrieben. [](#quarantine-tag-permission-details)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="9e6fa-167">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9e6fa-168">Überprüfen Sie **auf** der angezeigten Seite Zusammenfassung Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="9e6fa-169">Sie können **für** jede Einstellung auf Bearbeiten klicken, um sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="9e6fa-170">Klicken Sie nach Abschluss des Abschlusses auf **Absenden**.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="9e6fa-171">Klicken **Sie auf** der angezeigten Bestätigungsseite auf Fertig.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="9e6fa-172">Jetzt können Sie das Quarantänetag einem Quarantänefeature zuweisen, wie im [Abschnitt Schritt 2](#step-2-assign-a-quarantine-tag-to-supported-features) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="9e6fa-173">Erstellen von Quarantänetags in PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e6fa-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="9e6fa-174">Wenn Sie PowerShell lieber zum Erstellen von Quarantänetags verwenden möchten, stellen Sie eine Verbindung mit Exchange Online PowerShell oder Exchange Online Protection PowerShell ein, und verwenden Sie das **Cmdlet New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="9e6fa-175">Sie haben zwei verschiedene Methoden zur Auswahl:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="9e6fa-176">Verwenden Sie _den Parameter EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="9e6fa-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="9e6fa-177">Verwenden Sie _den Parameter EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="9e6fa-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="9e6fa-178">Diese Methoden werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="9e6fa-179">Verwenden des Parameters EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="9e6fa-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="9e6fa-180">Verwenden Sie die folgende Syntax, um ein Quarantänetag mit dem _Parameter EndUserQuarantinePermissionsValue_ zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="9e6fa-181">Der _Parameter EndUserQuarantinePermissionsValue_ verwendet einen Dezimalwert, der aus einem binären Wert konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="9e6fa-182">Der binäre Wert entspricht den verfügbaren Endbenutzerquarantäneberechtigungen in einer bestimmten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="9e6fa-183">Für jede Berechtigung ist der Wert 1 true und der Wert 0 gleich False.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="9e6fa-184">Die erforderliche Reihenfolge und werte für jede einzelne Berechtigung in vordefinierten Berechtigungsgruppen werden in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="9e6fa-185">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9e6fa-185">Permission</span></span>|<span data-ttu-id="9e6fa-186">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-186">No access</span></span>|<span data-ttu-id="9e6fa-187">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-187">Limited access</span></span>|<span data-ttu-id="9e6fa-188">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="9e6fa-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="9e6fa-189">PermissionToAllowSender</span></span>|<span data-ttu-id="9e6fa-190">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-190">0</span></span>|<span data-ttu-id="9e6fa-191">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-191">0</span></span>|<span data-ttu-id="9e6fa-192">1</span><span class="sxs-lookup"><span data-stu-id="9e6fa-192">1</span></span>|
|<span data-ttu-id="9e6fa-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="9e6fa-193">PermissionToBlockSender</span></span>|<span data-ttu-id="9e6fa-194">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-194">0</span></span>|<span data-ttu-id="9e6fa-195">1</span><span class="sxs-lookup"><span data-stu-id="9e6fa-195">1</span></span>|<span data-ttu-id="9e6fa-196">1</span><span class="sxs-lookup"><span data-stu-id="9e6fa-196">1</span></span>|
|<span data-ttu-id="9e6fa-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="9e6fa-197">PermissionToDelete</span></span>|<span data-ttu-id="9e6fa-198">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-198">0</span></span>|<span data-ttu-id="9e6fa-199">1</span><span class="sxs-lookup"><span data-stu-id="9e6fa-199">1</span></span>|<span data-ttu-id="9e6fa-200">1</span><span class="sxs-lookup"><span data-stu-id="9e6fa-200">1</span></span>|
|<span data-ttu-id="9e6fa-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e6fa-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="9e6fa-202">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-202">0</span></span>|<span data-ttu-id="9e6fa-203">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-203">0</span></span>|<span data-ttu-id="9e6fa-204">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-204">0</span></span>|
|<span data-ttu-id="9e6fa-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="9e6fa-205">PermissionToPreview</span></span>|<span data-ttu-id="9e6fa-206">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-206">0</span></span>|<span data-ttu-id="9e6fa-207">1</span><span class="sxs-lookup"><span data-stu-id="9e6fa-207">1</span></span>|<span data-ttu-id="9e6fa-208">1</span><span class="sxs-lookup"><span data-stu-id="9e6fa-208">1</span></span>|
|<span data-ttu-id="9e6fa-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e6fa-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="9e6fa-210">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-210">0</span></span>|<span data-ttu-id="9e6fa-211">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-211">0</span></span>|<span data-ttu-id="9e6fa-212">1</span><span class="sxs-lookup"><span data-stu-id="9e6fa-212">1</span></span>|
|<span data-ttu-id="9e6fa-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e6fa-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="9e6fa-214">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-214">0</span></span>|<span data-ttu-id="9e6fa-215">1</span><span class="sxs-lookup"><span data-stu-id="9e6fa-215">1</span></span>|<span data-ttu-id="9e6fa-216">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-216">0</span></span>|
|<span data-ttu-id="9e6fa-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e6fa-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="9e6fa-218">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-218">0</span></span>|<span data-ttu-id="9e6fa-219">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-219">0</span></span>|<span data-ttu-id="9e6fa-220">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-220">0</span></span>|
|<span data-ttu-id="9e6fa-221">Binärwert</span><span class="sxs-lookup"><span data-stu-id="9e6fa-221">Binary value</span></span>|<span data-ttu-id="9e6fa-222">00000000</span><span class="sxs-lookup"><span data-stu-id="9e6fa-222">00000000</span></span>|<span data-ttu-id="9e6fa-223">01101010</span><span class="sxs-lookup"><span data-stu-id="9e6fa-223">01101010</span></span>|<span data-ttu-id="9e6fa-224">11101100</span><span class="sxs-lookup"><span data-stu-id="9e6fa-224">11101100</span></span>|
|<span data-ttu-id="9e6fa-225">Zu verwendende Dezimalwert</span><span class="sxs-lookup"><span data-stu-id="9e6fa-225">Decimal value to use</span></span>|<span data-ttu-id="9e6fa-226">0</span><span class="sxs-lookup"><span data-stu-id="9e6fa-226">0</span></span>|<span data-ttu-id="9e6fa-227">106</span><span class="sxs-lookup"><span data-stu-id="9e6fa-227">106</span></span>|<span data-ttu-id="9e6fa-228">236</span><span class="sxs-lookup"><span data-stu-id="9e6fa-228">236</span></span>|

<span data-ttu-id="9e6fa-229"><sup>\*</sup> Derzeit ist dieser Wert immer 0.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="9e6fa-230">Für PermissionToViewHeader blendet der Wert 0 die Schaltfläche Nachrichtenkopf anzeigen nicht in den Details der isolierten Nachricht aus (die Schaltfläche ist immer verfügbar). </span><span class="sxs-lookup"><span data-stu-id="9e6fa-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="9e6fa-231"><sup>\*\*</sup> Legen Sie beide Werte nicht auf 1.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="9e6fa-232">Legen Sie einen auf 1 und den anderen auf 0 oder beide auf 0.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="9e6fa-233">In diesem Beispiel wird ein neuer Quarantänetagname NoAccess erstellt, der die Berechtigungen "Kein Zugriff" wie in der vorherigen Tabelle beschrieben zu weist.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="9e6fa-234">Verwenden Sie für Eingeschränkte Zugriffsberechtigungen den Wert 106.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="9e6fa-235">Verwenden Sie für Vollzugriffsberechtigungen den Wert 236.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="9e6fa-236">Verwenden Sie für benutzerdefinierte Berechtigungen die vorherige Tabelle, um den binären Wert zu erhalten, der den von Ihnen benötigten Berechtigungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="9e6fa-237">Konvertieren Sie den binären Wert in einen Dezimalwert, und verwenden Sie den Dezimalwert für den _Parameter EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="9e6fa-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="9e6fa-238">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-238">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="9e6fa-239">Verwenden des Parameters EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="9e6fa-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="9e6fa-240">Gehen Sie wie folgt vor, um ein Quarantänetag mit dem _Parameter EndUserQuarantinePermissionsValue_ zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="9e6fa-241">A.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-241">A.</span></span> <span data-ttu-id="9e6fa-242">Speichern Sie ein Quarantäneberechtigungsobjekt in einer Variablen mithilfe des **Cmdlets New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="9e6fa-243">B.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-243">B.</span></span> <span data-ttu-id="9e6fa-244">Verwenden Sie die Variable als _EndUserQuarantinePermissions-Wert_ im **Befehl New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="9e6fa-245">Schritt A: Speichern eines Quarantäneberechtigungsobjekts in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="9e6fa-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="9e6fa-246">Sowohl exExchangeNoVersion als auch AD FS müssen dasselbe Token für denselben Benutzer anfordern, damit eine ordnungsgemäße Funktionalität für ein standortübergreifendes exExchangeNoVersion-Bereitstellungsszenario gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="9e6fa-247">Der Standardwert für alle nicht verwendeten Parameter ist , daher müssen Sie nur die Parameter verwenden, für die Sie den Wert `$false` auf festlegen `$true` möchten.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="9e6fa-248">Die folgenden Beispiele zeigen, wie Sie Berechtigungsobjekte erstellen, die den vordefinierten Berechtigungsgruppen entsprechen:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="9e6fa-249">**Kein Zugriff**:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="9e6fa-250">**Eingeschränkter Zugriff:**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="9e6fa-251">**Vollzugriff**:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="9e6fa-252">Um die festgelegten Werte zu sehen, führen Sie den Variablennamen als Befehl aus (führen Sie z. B. den Befehl `$NoAccess` aus).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="9e6fa-253">Legen Sie für benutzerdefinierte Berechtigungen die Parameter _PermissionToRelease_ und _PermissionToRequestRelease nicht_ auf `$true` fest.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="9e6fa-254">Legen Sie eins auf und lassen Sie das andere als `$true` , oder lassen Sie beide als `$false` `$false` .</span><span class="sxs-lookup"><span data-stu-id="9e6fa-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="9e6fa-255">Sie können auch eine vorhandene Berechtigungsobjektvariable ändern, nachdem Sie sie erstellt haben, aber bevor Sie sie verwenden, indem Sie das **Cmdlet Set-QuarantinePermissions** verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="9e6fa-256">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) und [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="9e6fa-257">Schritt B: Verwenden der Variablen im befehl New-QuarantineTag</span><span class="sxs-lookup"><span data-stu-id="9e6fa-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="9e6fa-258">Nachdem Sie das Permissions-Objekt in einer Variablen erstellt und gespeichert haben, verwenden Sie die Variable für den _EndUserQuarantinePermission-Parameterwert_ im folgenden **New-QuarantineTag-Befehl:**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="9e6fa-259">In diesem Beispiel wird ein neues Quarantänetag namens LimitedAccess mit dem berechtigungsobjekt erstellt, das im vorherigen Schritt `$LimitedAccess` beschrieben und erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="9e6fa-260">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-260">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="9e6fa-261">Schritt 2: Zuweisen eines Quarantänetags zu unterstützten Features</span><span class="sxs-lookup"><span data-stu-id="9e6fa-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="9e6fa-262">In _unterstützten_ Schutzfunktionen, die Nachrichten oder Dateien unter Quarantäne stellen (automatisch oder als konfigurierbare Aktion), können Sie den verfügbaren Quarantäneaktionen ein Quarantänetag zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="9e6fa-263">Features zum Isolieren von Nachrichten und zur Verfügbarkeit von Quarantänetags werden in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="9e6fa-264">Feature</span><span class="sxs-lookup"><span data-stu-id="9e6fa-264">Feature</span></span>|<span data-ttu-id="9e6fa-265">Quarantänetags unterstützt?</span><span class="sxs-lookup"><span data-stu-id="9e6fa-265">Quarantine tags supported?</span></span>|<span data-ttu-id="9e6fa-266">Verwendete Standardquarantänetags</span><span class="sxs-lookup"><span data-stu-id="9e6fa-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="9e6fa-267">[Antispamrichtlinien:](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="9e6fa-268">**Spam** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="9e6fa-269">**Spam mit hoher Konfidenz** (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="9e6fa-270">**Phishing-E-Mails** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="9e6fa-271">**Phishing-E-Mails mit** hoher Vertrauenssicherheit (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="9e6fa-272">**Massen-E-Mail** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="9e6fa-273">Ja</span><span class="sxs-lookup"><span data-stu-id="9e6fa-273">Yes</span></span>|<ul><li><span data-ttu-id="9e6fa-274">DefaultSpamTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="9e6fa-275">DefaultHighConfSpamTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="9e6fa-276">DefaultPhishTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="9e6fa-277">DefaultHighConfPhishTag (Kein Zugriff)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="9e6fa-278">DefaultBulkTag (Vollzugriff)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="9e6fa-279">Antiphishingrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="9e6fa-280">[Spoof Intelligence Protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="9e6fa-281">[Identitätswechselschutz](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e6fa-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="9e6fa-282">**Wenn E-Mails von einem imitierten Benutzer** gesendet werden (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="9e6fa-283">**Wenn E-Mails von einer imitierten Domäne** gesendet werden (_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="9e6fa-284">**Postfachintelligenz** \> **Wenn E-Mails von einem identitätswechselten** Benutzer gesendet werden (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="9e6fa-285">Nein</span><span class="sxs-lookup"><span data-stu-id="9e6fa-285">No</span></span>|<span data-ttu-id="9e6fa-286">N/V</span><span class="sxs-lookup"><span data-stu-id="9e6fa-286">n/a</span></span>|
|<span data-ttu-id="9e6fa-287">[An malware-Richtlinien:](configure-anti-malware-policies.md)Alle erkannten Nachrichten werden immer unter Quarantäne gestellt.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="9e6fa-288">Nein</span><span class="sxs-lookup"><span data-stu-id="9e6fa-288">No</span></span>|<span data-ttu-id="9e6fa-289">N/V</span><span class="sxs-lookup"><span data-stu-id="9e6fa-289">n/a</span></span>|
|[<span data-ttu-id="9e6fa-290">Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e6fa-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="9e6fa-291">Nein</span><span class="sxs-lookup"><span data-stu-id="9e6fa-291">No</span></span>|<span data-ttu-id="9e6fa-292">N/V</span><span class="sxs-lookup"><span data-stu-id="9e6fa-292">n/a</span></span>|
|<span data-ttu-id="9e6fa-293">[Nachrichtenflussregeln](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bekannt) mit der Aktion: Senden der Nachricht an die **gehostete Quarantäne** (_Quarantäne_).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-293">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="9e6fa-294">Nein</span><span class="sxs-lookup"><span data-stu-id="9e6fa-294">No</span></span>|<span data-ttu-id="9e6fa-295">N/V</span><span class="sxs-lookup"><span data-stu-id="9e6fa-295">n/a</span></span>|
|

<span data-ttu-id="9e6fa-296"><sup>\*</sup> Identitätswechselschutzeinstellungen sind nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="9e6fa-297">Wenn Sie mit den Endbenutzerberechtigungen zufrieden sind, die von den Standardquarantänetags bereitgestellt werden, müssen Sie nichts tun.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="9e6fa-298">Wenn Sie die Endbenutzerfunktionen (verfügbare Schaltflächen) in Spambenachrichtigungen für Endbenutzer oder in Quarantänenachrichtendetails anpassen möchten, können Sie ein benutzerdefiniertes Quarantänetag zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="9e6fa-299">Zuweisen von Quarantänetags in Antispamrichtlinien im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="9e6fa-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="9e6fa-300">Vollständige Anweisungen zum Erstellen und Ändern von Antispamrichtlinien finden Sie unter [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="9e6fa-301">Wechseln Sie im Security & Compliance Center **zu** Richtlinie für die Bedrohungsverwaltung, und wählen Sie dann \>  \> **Antispam aus.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="9e6fa-302">Oder öffnen Sie <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="9e6fa-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="9e6fa-303">Suchen Und wählen Sie eine vorhandene Antispamrichtlinie aus, die bearbeitet werden soll, oder erstellen Sie eine neue Antispamrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="9e6fa-304">Erweitern Sie im Flyout für Richtliniendetails den Abschnitt **Spam- und Massenaktionen.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="9e6fa-305">Wenn Sie quarantäne  nachricht für die Aktion eines verfügbaren Spamfilter-Urteils ausgewählt haben, ist das Feld Quarantänerichtlinientag anwenden verfügbar, damit Sie das Quarantänetag für dieses Urteil auswählen können. </span><span class="sxs-lookup"><span data-stu-id="9e6fa-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="9e6fa-306">**Hinweis**: Wenn Sie eine neue Richtlinie erstellen, gibt ein leerer Quarantänetagwert für ein Spamfilter-Urteil an, dass das Standardquarantänetag für dieses Urteil verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="9e6fa-307">Wenn Sie die Richtlinie später bearbeiten, werden die leeren Werte durch die tatsächlichen Standardquarantänetagnamen ersetzt, wie in der vorherigen Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![Quarantänetagauswahl in einer Antispamrichtlinie](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="9e6fa-309">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="9e6fa-310">Zuweisen von Quarantänetags in Antispamrichtlinien in PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e6fa-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="9e6fa-311">Wenn Sie Lieber PowerShell verwenden möchten, um Quarantänetags in Antispamrichtlinien zuzuordnen, stellen Sie eine Verbindung mit Exchange Online PowerShell oder Exchange Online Protection PowerShell auf, und verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="9e6fa-312">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-312">**Notes**:</span></span>

- <span data-ttu-id="9e6fa-313">Der Standardwert für den _Parameter HighConfidencePhishAction_ ist Quarantine, daher müssen Sie die Quarantäneaktion für Phishingerkennungen mit hoher Vertrauen in neuen Antispamrichtlinien nicht festlegen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="9e6fa-314">Bei allen anderen Spamfilterungen in neuen oder vorhandenen Antispamrichtlinien ist das Quarantänetag nur dann wirksam, wenn der Aktionswert Quarantine lautet.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="9e6fa-315">Führen Sie den folgenden Befehl aus, um die Aktionswerte in vorhandenen Antispamrichtlinien zu sehen:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="9e6fa-316">Informationen zu den Standardaktionswerten und den empfohlenen Aktionswerten für Standard und Strict finden Sie unter [EOP Antispamrichtlinieneinstellungen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="9e6fa-317">Ein Spamfilter-Urteil ohne einen entsprechenden Quarantänetag-Parameter bedeutet, dass das [Standardquarantänetag](#step-2-assign-a-quarantine-tag-to-supported-features) für dieses Urteil verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="9e6fa-318">Sie müssen nur ein Standardquarantänetag durch ein benutzerdefiniertes Quarantänetag ersetzen, wenn Sie die Standardfunktionen des Endbenutzers für isolierte Nachrichten ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="9e6fa-319">Eine neue Antispamrichtlinie in PowerShell erfordert eine Spamfilterrichtlinie (Einstellungen) mit dem **Cmdlet New-HostedContentFilterPolicy** und eine neue Spamfilterregel (Empfängerfilter) mithilfe des **Cmdlets New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="9e6fa-320">Anweisungen finden Sie unter [Verwenden von PowerShell zum Erstellen von Antispamrichtlinien](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="9e6fa-321">In diesem Beispiel wird eine neue Spamfilterrichtlinie namens "Research Department" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="9e6fa-322">Die Aktion für alle Spamfilterungs-Urteile ist auf Quarantäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="9e6fa-323">Das benutzerdefinierte Quarantänetag NoAccess, das Keine Zugriffsberechtigungen zu weist,  ersetzt standardmäßige Quarantänetags, die noch keine Zugriffsberechtigungen standardmäßig zuweisen. </span><span class="sxs-lookup"><span data-stu-id="9e6fa-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="9e6fa-324">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="9e6fa-325">In diesem Beispiel wird die vorhandene Spamfilterrichtlinie "Personalwesen" geändert.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="9e6fa-326">Die Aktion für das Spamquarantäne-Urteil ist auf Quarantäne festgelegt, und das benutzerdefinierte Quarantänetag NoAccess wird zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="9e6fa-327">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="9e6fa-328">Konfigurieren globaler Quarantänebenachrichtigungseinstellungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="9e6fa-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="9e6fa-329">Mit den globalen Einstellungen für Quarantänetags können Sie die Spambenachrichtigungen für Endbenutzer anpassen, die an Empfänger von Nachrichten gesendet werden, die isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="9e6fa-330">Weitere Informationen zu diesen Benachrichtigungen finden Sie unter [Endbenutzerspambenachrichtigungen](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="9e6fa-331">Wechseln Sie im Security & Compliance Center **zu** Richtlinie für die Bedrohungsverwaltung, und wählen Sie dann \>  **Quarantänetags aus.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="9e6fa-332">Wählen Sie auf der Seite **Quarantänetags** die Option **Globale Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="9e6fa-333">Konfigurieren Sie **im geöffneten** Flyout Quarantänebenachrichtigungseinstellungen einige oder alle der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="9e6fa-334">**Verwenden Sie mein Firmenlogo:** Wählen Sie diese Option aus, um das standardmäßige Microsoft-Logo zu ersetzen, das am Anfang von Spambenachrichtigungen für Endbenutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="9e6fa-335">Bevor Sie dies tun, müssen Sie die Anweisungen unter Anpassen des [Microsoft 365-Designs](../../admin/setup/customize-your-organization-theme.md) für Ihre Organisation befolgen, um Ihr benutzerdefiniertes Logo hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="9e6fa-336">Der folgende Screenshot zeigt ein benutzerdefiniertes Logo in einer Spambenachrichtigung für Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Ein benutzerdefiniertes Logo in einer Spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="9e6fa-338">**Sprache auswählen:** Spambenachrichtigungen für Endbenutzer werden bereits basierend auf den Spracheinstellungen des Empfängers lokalisiert.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="9e6fa-339">Sie können benutzerdefinierten Text für den Anzeigenamen und **haftungsausschluss** in **verschiedenen** Sprachen angeben.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="9e6fa-340">Wählen Sie im ersten Sprachfeld mindestens eine Sprache aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="9e6fa-341">Sie können mehrere Sprachen auswählen, indem **Sie** nach jeder Sprache auf Hinzufügen klicken.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="9e6fa-342">In einem Abschnittssprachenfeld werden alle von Ihnen ausgewählten Sprachen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Ausgewählte Sprachen im zweiten Sprachfeld in den globalen Quarantänebenachrichtigungseinstellungen von Quarantänetags](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="9e6fa-344">**Anzeigename**: Passen Sie den Anzeigenamen des Absenders an, der in Spambenachrichtigungen für Endbenutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="9e6fa-345">Wählen Sie für jede hinzugefügte Sprache die Sprache im zweiten Sprachfeld aus (klicken Sie nicht auf das X), und geben Sie den text-Wert in das Feld **Anzeigename** ein.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="9e6fa-346">Der folgende Screenshot zeigt den angepassten Anzeigenamen in einer Spambenachrichtigung für Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Ein benutzerdefinierter Absenderanzeigename in einer Spambenachrichtigung des Endbenutzers](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="9e6fa-348">**Haftungsausschluss**: Fügen Sie am Ende von Spambenachrichtigungen für Endbenutzer einen benutzerdefinierten Haftungsausschluss hinzu.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="9e6fa-349">Der lokalisierte Text, **Ein Haftungsausschluss aus Ihrer Organisation:** ist immer zuerst enthalten, gefolgt von dem angegebenen Text.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="9e6fa-350">Wählen Sie für jede hinzugefügte Sprache die Sprache im zweiten Sprachfeld aus (klicken Sie nicht auf das X), und geben Sie den textwert ein, den Sie im Feld **Haftungsausschluss** verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="9e6fa-351">Der folgende Screenshot zeigt den angepassten Haftungsausschluss in einer Spambenachrichtigung für Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Ein benutzerdefinierter Haftungsausschluss am Ende einer Spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="9e6fa-353">Anzeigen von Quarantänetags im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="9e6fa-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="9e6fa-354">Wechseln Sie im Security & Compliance Center **zu** Richtlinie für die Bedrohungsverwaltung, und wählen Sie dann \>  **Quarantänetags aus.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="9e6fa-355">Wenn Sie die Einstellungen von integrierten oder benutzerdefinierten Quarantänetags anzeigen möchten, aktivieren Sie das Quarantänetag in der Liste (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="9e6fa-356">Wenn Sie die globalen Einstellungen anzeigen möchten, wählen Sie **Globale Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="9e6fa-357">Anzeigen von Quarantänetags in PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e6fa-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="9e6fa-358">Wenn Sie lieber PowerShell zum Anzeigen von Quarantänetags verwenden möchten, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="9e6fa-359">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller integrierten oder benutzerdefinierten Tags anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="9e6fa-360">Ersetzen Sie zum Anzeigen der Einstellungen von integrierten oder benutzerdefinierten Quarantänetags durch den Namen des Quarantänetags, und führen \<TagName\> Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="9e6fa-361">Führen Sie zum Anzeigen der globalen Einstellungen den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="9e6fa-362">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="9e6fa-363">Entfernen von Quarantänetags im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="9e6fa-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="9e6fa-364">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-364">**Notes**:</span></span>

- <span data-ttu-id="9e6fa-365">Integrierte Quarantänetags können nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="9e6fa-366">Vergewissern Sie sich vor dem Entfernen eines benutzerdefinierten Quarantänetags, dass es nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="9e6fa-367">Führen Sie beispielsweise den folgenden Befehl in PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="9e6fa-368">Wenn das Quarantänetag verwendet wird, ersetzen Sie das [zugewiesene Quarantänetag,](#step-2-assign-a-quarantine-tag-to-supported-features) bevor Sie es entfernen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="9e6fa-369">Wechseln Sie im Security & Compliance Center **zu** Richtlinie für die Bedrohungsverwaltung, und wählen Sie dann \>  **Quarantänetags aus.**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="9e6fa-370">Wählen Sie **auf** der Seite Quarantänetags das benutzerdefinierte Quarantänetag aus, das Sie entfernen möchten, und klicken Sie auf **Tag löschen**.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="9e6fa-371">Klicken **Sie im angezeigten** Bestätigungsdialogfeld auf Tag entfernen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="9e6fa-372">Entfernen von Quarantänetags in PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e6fa-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="9e6fa-373">Wenn Sie lieber PowerShell verwenden möchten, um ein benutzerdefiniertes Quarantänetag zu entfernen, ersetzen Sie durch den Namen des Quarantänetags, und führen Sie \<TagName\> den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="9e6fa-374">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="9e6fa-375">Quarantänetag-Berechtigungsdetails</span><span class="sxs-lookup"><span data-stu-id="9e6fa-375">Quarantine tag permission details</span></span>

<span data-ttu-id="9e6fa-376">In den folgenden Abschnitten werden die Auswirkungen vordefinierter Berechtigungsgruppen und einzelner Berechtigungen in den Details von isolierten Nachrichten und in Spambenachrichtigungen für Endbenutzer beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="9e6fa-377">Voreingestellte Berechtigungsgruppen</span><span class="sxs-lookup"><span data-stu-id="9e6fa-377">Preset permissions groups</span></span>

<span data-ttu-id="9e6fa-378">Die einzelnen Berechtigungen, die in vordefinierten Berechtigungsgruppen enthalten sind, sind in der Tabelle am Anfang dieses Artikels aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="9e6fa-379">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-379">No access</span></span>

<span data-ttu-id="9e6fa-380">Wenn das Quarantänetag die Zugriffsberechtigungen **"Kein** Zugriff" (keine Berechtigungen) zu weist, erhalten Benutzer weiterhin einige grundlegende Funktionen:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="9e6fa-381">**Nachrichtendetails in Quarantäne:** Die Schaltfläche **Nachrichtenkopf anzeigen** ist immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Verfügbare Schaltflächen in den Quarantänenachrichtendetails, wenn das Quarantänetag dem Benutzer keine Zugriffsberechtigungen gewährt](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="9e6fa-383">**Spambenachrichtigungen für Endbenutzer:** Die Schaltfläche **Überprüfen,** die den Benutzer zur Nachricht in Quarantäne führt, ist immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Verfügbare Schaltflächen in der Spambenachrichtigung des Endbenutzers, wenn das Quarantänetag dem Benutzer keine Zugriffsberechtigungen erteilt](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="9e6fa-385">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-385">Limited access</span></span>

<span data-ttu-id="9e6fa-386">Wenn das Quarantänetag die **Eingeschränkten** Zugriffsberechtigungen zu weist, erhalten Benutzer die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="9e6fa-387">**Details zu isolierten Nachrichten:** Die folgenden Schaltflächen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="9e6fa-388">**Anforderungsversion**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-388">**Request release**</span></span>
  - <span data-ttu-id="9e6fa-389">**Nachrichtenkopfzeile anzeigen**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-389">**View message header**</span></span>
  - <span data-ttu-id="9e6fa-390">**Vorschaumeldung**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-390">**Preview message**</span></span>
  - <span data-ttu-id="9e6fa-391">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-391">**Block sender**</span></span>
  - <span data-ttu-id="9e6fa-392">**Entfernen aus der Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-392">**Remove from quarantine**</span></span>

  ![Verfügbare Schaltflächen in den Quarantänenachrichtendetails, wenn das Quarantänetag dem Benutzer eingeschränkte Zugriffsberechtigungen gewährt](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="9e6fa-394">**Spambenachrichtigungen für Endbenutzer:** Die folgenden Schaltflächen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="9e6fa-395">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-395">**Block sender**</span></span>
  - <span data-ttu-id="9e6fa-396">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-396">**Review**</span></span>

  ![Verfügbare Schaltflächen in der Spambenachrichtigung des Endbenutzers, wenn das Quarantänetag dem Benutzer eingeschränkte Zugriffsberechtigungen gewährt](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="9e6fa-398">Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="9e6fa-398">Full access</span></span>

<span data-ttu-id="9e6fa-399">Wenn das Quarantänetag  die Vollzugriffsberechtigungen (alle verfügbaren Berechtigungen) zu weist, erhalten Benutzer die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="9e6fa-400">**Details zu isolierten Nachrichten:** Die folgenden Schaltflächen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="9e6fa-401">**Veröffentlichungsnachricht**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-401">**Release message**</span></span>
  - <span data-ttu-id="9e6fa-402">**Nachrichtenkopfzeile anzeigen**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-402">**View message header**</span></span>
  - <span data-ttu-id="9e6fa-403">**Vorschaumeldung**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-403">**Preview message**</span></span>
  - <span data-ttu-id="9e6fa-404">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-404">**Block sender**</span></span>
  - <span data-ttu-id="9e6fa-405">**Absender zulassen**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-405">**Allow sender**</span></span>
  - <span data-ttu-id="9e6fa-406">**Entfernen aus der Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-406">**Remove from quarantine**</span></span>

  ![Verfügbare Schaltflächen in den Isolierten Nachrichtendetails, wenn das Quarantänetag dem Benutzer Vollzugriffsberechtigungen erteilt](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="9e6fa-408">**Spambenachrichtigungen für Endbenutzer:** Die folgenden Schaltflächen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="9e6fa-409">**Absender blockieren**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-409">**Block sender**</span></span>
  - <span data-ttu-id="9e6fa-410">**Freigabe**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-410">**Release**</span></span>
  - <span data-ttu-id="9e6fa-411">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-411">**Review**</span></span>

  ![Verfügbare Schaltflächen in der Spambenachrichtigung des Endbenutzers, wenn das Quarantänetag dem Benutzer Vollzugriff gewährt](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="9e6fa-413">Individuelle Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9e6fa-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="9e6fa-414">Denken Sie daran, dass Benutzer immer die schaltflächen erhalten, die im [Abschnitt Kein Zugriff beschrieben](#no-access) sind.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="9e6fa-415">Diese Schaltflächen sind nicht in den einzelnen Berechtigungsbeschreibungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="9e6fa-416">Absenderberechtigung zulassen</span><span class="sxs-lookup"><span data-stu-id="9e6fa-416">Allow sender permission</span></span>

<span data-ttu-id="9e6fa-417">Die **Berechtigung Absender zulassen** (_PermissionToAllowSender_) steuert den Zugriff auf die Schaltfläche, mit der Benutzer den isolierten Nachrichtensender bequem zur Liste sicherer Absender hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="9e6fa-418">**Isolierte Nachrichtendetails**:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9e6fa-419">**Absenderberechtigung** zulassen: Die Schaltfläche Absender **zulassen** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="9e6fa-420">**Absenderberechtigung zulassen** deaktiviert: Die Schaltfläche Absender **zulassen** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="9e6fa-421">**Spambenachrichtigungen für Endbenutzer:** Keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="9e6fa-422">Weitere Informationen zur Liste sicherer Absender finden Sie unter [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and Use Exchange Online [PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9e6fa-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="9e6fa-423">Absenderberechtigung blockieren</span><span class="sxs-lookup"><span data-stu-id="9e6fa-423">Block sender permission</span></span>

<span data-ttu-id="9e6fa-424">Die **Berechtigung Absender blockieren** (_PermissionToBlockSender_) steuert den Zugriff auf die Schaltfläche, mit der Benutzer den isolierten Nachrichtensender bequem zur Liste blockierter Absender hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="9e6fa-425">**Isolierte Nachrichtendetails**:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9e6fa-426">**Absenderberechtigung** blockieren aktiviert: Die Schaltfläche **Absender blockieren** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="9e6fa-427">**Absenderberechtigung blockieren** deaktiviert: Die Schaltfläche **Absender blockieren** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="9e6fa-428">**Spambenachrichtigungen für Endbenutzer:**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="9e6fa-429">**Absenderberechtigung blockieren** deaktiviert: Die Schaltfläche **Absender blockieren** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="9e6fa-430">**Absenderberechtigung** blockieren aktiviert: Die Schaltfläche **Absender blockieren** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="9e6fa-431">Weitere Informationen zur Liste blockierter Absender finden Sie unter [Blockieren](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) von Nachrichten von einer Person und Konfigurieren der Sammlung sicherer Listen in einem Postfach mithilfe von [Exchange Online PowerShell.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="9e6fa-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="9e6fa-432">Löschen</span><span class="sxs-lookup"><span data-stu-id="9e6fa-432">Delete permission</span></span>

<span data-ttu-id="9e6fa-433">Die **Delete-Berechtigung** (_PermissionToDelete_) steuert die Möglichkeit von Benutzern, ihre Nachrichten (Nachrichten, bei denen der Benutzer ein Empfänger ist) aus der Quarantäne zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="9e6fa-434">**Isolierte Nachrichtendetails**:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9e6fa-435">**Berechtigung** löschen aktiviert: Die **Schaltfläche Aus Quarantäne** entfernen ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="9e6fa-436">**Berechtigung** löschen deaktiviert: Die **Schaltfläche Aus Quarantäne** entfernen ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="9e6fa-437">**Spambenachrichtigungen für Endbenutzer:** Keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="9e6fa-438">Vorschauberechtigung</span><span class="sxs-lookup"><span data-stu-id="9e6fa-438">Preview permission</span></span>

<span data-ttu-id="9e6fa-439">Die **Vorschauberechtigung** (_PermissionToPreview_) steuert die Möglichkeit von Benutzern, eine Vorschau ihrer Nachrichten in Quarantäne anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="9e6fa-440">**Isolierte Nachrichtendetails**:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9e6fa-441">**Vorschauberechtigung** aktiviert: Die Schaltfläche **Nachrichtenvorschau** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="9e6fa-442">**Vorschauberechtigung** deaktiviert: Die Schaltfläche **Nachrichtenvorschau** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="9e6fa-443">**Spambenachrichtigungen für Endbenutzer:** Keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="9e6fa-444">Zulassen, dass Empfänger eine Nachricht aus der Quarantäneberechtigung frei lassen</span><span class="sxs-lookup"><span data-stu-id="9e6fa-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="9e6fa-445">Das **Zulassen,** dass Empfänger eine Nachricht aus der Quarantäneberechtigung (_PermissionToRelease_) frei lassen, steuert die Möglichkeit von Benutzern, ihre isolierten Nachrichten direkt und ohne Genehmigung eines Administrator freizubeauftragen.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="9e6fa-446">**Isolierte Nachrichtendetails**:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9e6fa-447">Berechtigung aktiviert: Die **Schaltfläche Nachricht veröffentlichen** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="9e6fa-448">Berechtigung deaktiviert: Die **Schaltfläche Nachricht veröffentlichen** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="9e6fa-449">**Spambenachrichtigungen für Endbenutzer:**</span><span class="sxs-lookup"><span data-stu-id="9e6fa-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="9e6fa-450">Berechtigung aktiviert: Die **Schaltfläche Freigabe** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="9e6fa-451">Berechtigung deaktiviert: Die **Schaltfläche Freigabe** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="9e6fa-452">Zulassen, dass Empfänger anfordern, dass eine Nachricht aus der Quarantäneberechtigung freigegeben wird</span><span class="sxs-lookup"><span data-stu-id="9e6fa-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="9e6fa-453">Das **Zulassen,** dass Empfänger eine Nachricht aus der Quarantäneberechtigung (_PermissionToRequestRelease_) anfordern, steuert die Möglichkeit von Benutzern, die Freigabe ihrer isolierten Nachrichten anzu fordern. </span><span class="sxs-lookup"><span data-stu-id="9e6fa-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="9e6fa-454">Die Nachricht wird erst freigegeben, nachdem ein Administrator die Anforderung genehmigt hat.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="9e6fa-455">**Isolierte Nachrichtendetails**:</span><span class="sxs-lookup"><span data-stu-id="9e6fa-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9e6fa-456">Berechtigung aktiviert: Die **Schaltfläche "Freigabe anfordern"** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="9e6fa-457">Berechtigung deaktiviert: Die **Schaltfläche "Freigabe anfordern"** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="9e6fa-458">**Spambenachrichtigungen für Endbenutzer:** Die **Schaltfläche "Freigabe"** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e6fa-458">**End-user spam notifications**: The **Release** button is not available.</span></span>