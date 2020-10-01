---
title: Einrichten von Richtlinien für sichere Links in Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Richtlinien für sichere Links und globale Einstellungen für sichere Links in Office 365 Advanced Threat Protection (ATP) anzeigen, erstellen, ändern und löschen.
ms.openlocfilehash: 58088955a6909238c1fe5202688e0b8d1ab8e6c6
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327225"
---
# <a name="set-up-safe-links-policies-in-office-365-atp"></a><span data-ttu-id="f98c1-103">Einrichten von Richtlinien für sichere Links in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="f98c1-103">Set up Safe Links policies in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="f98c1-104">Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="f98c1-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="f98c1-105">Wenn Sie ein Privatbenutzer sind, der nach Informationen zu Safelinks in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="f98c1-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="f98c1-106">Sichere Links sind ein Feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) , das die URL-Überprüfung eingehender e-Mail-Nachrichten im Nachrichtenfluss und die Zeit der Klick Überprüfung von URLs und Links in e-Mail-Nachrichten und an anderen Speicherorten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="f98c1-107">Weitere Informationen finden Sie unter [sichere Links in Office 365 ATP](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="f98c1-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="f98c1-108">Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="f98c1-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="f98c1-109">Um sichere Links beim Scannen von URLs zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere Links erstellen, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f98c1-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

<span data-ttu-id="f98c1-110">Sie können Richtlinien für sichere Links im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Office 365 ATP-Add-on-Abonnements) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f98c1-110">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

<span data-ttu-id="f98c1-111">Die grundlegenden Elemente einer Richtlinie zu sicheren Links sind:</span><span class="sxs-lookup"><span data-stu-id="f98c1-111">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="f98c1-112">**Richtlinie zu sicheren Links**: Aktivieren Sie den Schutz für sichere Links, aktivieren Sie den Echt Zeit-URL-Scan, geben Sie an, ob der Abschluss der Echtzeitüberprüfung vor dem Senden der Nachricht gewartet werden soll, aktivieren Sie die Überprüfung interner Nachrichten, geben Sie an, ob Benutzerklicks auf URLs nachverfolgt werden sollen, und geben Sie an, ob Benutzer auf die ursprüngliche URL klicken können</span><span class="sxs-lookup"><span data-stu-id="f98c1-112">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="f98c1-113">**Die Regel für sichere Links**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) an.</span><span class="sxs-lookup"><span data-stu-id="f98c1-113">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="f98c1-114">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Links im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="f98c1-114">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f98c1-115">Wenn Sie eine Richtlinie für sichere Links erstellen, erstellen Sie tatsächlich eine Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit dem gleichen Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="f98c1-115">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="f98c1-116">Wenn Sie eine Richtlinie für sichere Links ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die Regel für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="f98c1-116">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="f98c1-117">Alle anderen Einstellungen ändern die zugehörige Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="f98c1-117">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="f98c1-118">Wenn Sie eine Richtlinie für sichere Links entfernen, werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links entfernt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-118">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="f98c1-119">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="f98c1-120">Weitere Informationen finden Sie im Abschnitt [Verwenden von Exchange Online PowerShell oder eigenständige EoP PowerShell zum Konfigurieren von Richtlinien für sichere Links](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="f98c1-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="f98c1-121">Sie konfigurieren die globalen Einstellungen für den Schutz von sicheren Links **außerhalb** der Richtlinien für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="f98c1-121">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="f98c1-122">Anweisungen finden Sie unter [Configure Global Settings for Safe Links in Office 365 ATP](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="f98c1-122">For instructions, see [Configure global settings for Safe Links in Office 365 ATP](configure-global-settings-for-safe-links.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f98c1-123">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="f98c1-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f98c1-124">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f98c1-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f98c1-125">Wenn Sie direkt zur Seite **ATP-sichere Links** wechseln möchten, verwenden Sie <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="f98c1-125">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="f98c1-126">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f98c1-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f98c1-127">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f98c1-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f98c1-128">Zum Anzeigen, erstellen, ändern und Löschen von Richtlinien für sichere Links müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="f98c1-128">To view, create, modify, and delete Safe Links policies, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="f98c1-129">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f98c1-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="f98c1-130">**Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f98c1-130">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="f98c1-131">Die empfohlenen Einstellungen für Richtlinien zu sicheren Links finden Sie unter [Richtlinieneinstellungen für sichere Links](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="f98c1-131">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="f98c1-132">Erlauben Sie bis zu 30 Minuten, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f98c1-132">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="f98c1-133">[Neue Features werden kontinuierlich zu ATP hinzugefügt](office-365-atp.md#new-features-in-office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="f98c1-133">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="f98c1-134">Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren bestehenden Richtlinien für sichere Links vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f98c1-134">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="f98c1-135">Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-135">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="f98c1-136">Durch das Erstellen einer benutzerdefinierten Richtlinie für sichere Links im Security & Compliance Center werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit dem gleichen Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-136">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="f98c1-137">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f98c1-138">Klicken Sie auf der Seite **sichere Links** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-138">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="f98c1-139">Der Assistent für **neue Richtlinien für sichere Links** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f98c1-139">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="f98c1-140">Konfigurieren Sie auf der Seite **Ihre Richtlinie benennen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f98c1-140">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="f98c1-141">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="f98c1-141">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="f98c1-142">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="f98c1-142">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="f98c1-143">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-143">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f98c1-144">Konfigurieren Sie auf der angezeigten Seite **Einstellungen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f98c1-144">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f98c1-145">**Wählen Sie die Aktion für unbekannte potenziell bösartige URLs in Nachrichten**aus: SELECT **on**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-145">**Select the action for unknown potentially malicious URLs in messages**: Select **On**.</span></span>

   - <span data-ttu-id="f98c1-146">**Wählen Sie die Aktion für unbekannte potenziell bösartige URLs in Nachrichten**aus: Wählen Sie **ein** oder lassen Sie den Standardwert **deaktiviert** ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-146">**Select the action for unknown potentially malicious URLs in messages**: Select **On** or leave the default value **Off** selected.</span></span>

   - <span data-ttu-id="f98c1-147">Über **Prüfen der Echt Zeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen**: Wählen Sie diese Einstellung aus, um die Echtzeitüberprüfung von Links in e-Mail-Nachrichten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f98c1-147">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="f98c1-148">**Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht**übermitteln: Wählen Sie diese Einstellung, um zu warten, bis die URL-Überprüfung in Echtzeit abgeschlossen ist, bevor Sie die Nachricht</span><span class="sxs-lookup"><span data-stu-id="f98c1-148">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="f98c1-149">**Anwenden sicherer Links auf e-Mail-Nachrichten, die innerhalb der Organisation gesendet**werden: Wählen Sie diese Einstellung aus, um die Richtlinie für sichere Links auf Nachrichten zwischen internen Absendern und internen Empfängern anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="f98c1-149">**Apply safe links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="f98c1-150">**Benutzerklicks nicht nachverfolgen**: lassen Sie diese Einstellung nicht ausgewählt, damit der nach Verfolgungs Benutzer auf URLs in e-Mail-Nachrichten klickt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-150">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="f98c1-151">**Benutzer dürfen nicht auf die ursprüngliche URL klicken**: Wählen Sie diese Einstellung aus, um zu verhindern, dass Benutzer auf die ursprüngliche URL in [Warn Seiten](atp-safe-links.md#warning-pages-from-safe-links)klicken.</span><span class="sxs-lookup"><span data-stu-id="f98c1-151">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="f98c1-152">**Die folgenden URLs dürfen nicht umgeschrieben**werden: ermöglicht den Zugriff auf die angegebenen URLs, die andernfalls durch sichere Links blockiert würden.</span><span class="sxs-lookup"><span data-stu-id="f98c1-152">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="f98c1-153">Geben Sie in das Feld die gewünschte URL oder den gewünschten Wert ein, und klicken Sie dann auf</span><span class="sxs-lookup"><span data-stu-id="f98c1-153">In the box, type the URL or value that you want, and then click</span></span> ![Schaltflächensymbol hinzufügen](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="f98c1-155">.</span><span class="sxs-lookup"><span data-stu-id="f98c1-155">.</span></span>

     <span data-ttu-id="f98c1-156">Um einen vorhandenen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie dann auf</span><span class="sxs-lookup"><span data-stu-id="f98c1-156">To remove an existing entry, select it and then click</span></span> ![Symbol für die Schaltfläche "Löschen"](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="f98c1-158">.</span><span class="sxs-lookup"><span data-stu-id="f98c1-158">.</span></span>

     <span data-ttu-id="f98c1-159">Informationen zur Eingabesyntax finden Sie unter [Eintrags Syntax für die Liste "folgende URLs nicht umschreiben"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="f98c1-159">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="f98c1-160">Ausführliche Informationen zu diesen Einstellungen finden Sie unter Einstellungen für [sichere Links für e-Mail-Nachrichten](atp-safe-links.md#safe-links-settings-for-email-messages) und [Einstellungen für sichere Links für Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="f98c1-160">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="f98c1-161">Weitere empfohlene Werte für Standard mäßige und strenge Richtlinieneinstellungen finden Sie unter [Richtlinieneinstellungen für sichere Links](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="f98c1-161">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="f98c1-162">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f98c1-163">Identifizieren Sie auf der Seite **angewendet auf** , die angezeigt wird, die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f98c1-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="f98c1-164">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="f98c1-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="f98c1-165">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="f98c1-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="f98c1-166">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="f98c1-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="f98c1-167">Klicken Sie auf **Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-167">Click **Add a condition**.</span></span> <span data-ttu-id="f98c1-168">Wählen Sie in der Dropdownliste, die angezeigt wird, eine Bedingung unter **angewendet, wenn**:</span><span class="sxs-lookup"><span data-stu-id="f98c1-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="f98c1-169">**Der Empfänger lautet**: gibt ein oder mehrere Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="f98c1-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="f98c1-170">**Der Empfänger ist Mitglied von**: gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="f98c1-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="f98c1-171">**Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="f98c1-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="f98c1-172">Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **der folgenden** Felder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="f98c1-173">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der zu markierende Werte durch.</span><span class="sxs-lookup"><span data-stu-id="f98c1-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="f98c1-174">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f98c1-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="f98c1-175">Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="f98c1-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="f98c1-176">Wenn Sie einzelne Einträge entfernen möchten **Remove** , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Wert entfernen.</span><span class="sxs-lookup"><span data-stu-id="f98c1-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="f98c1-177">Wenn Sie die gesamte Bedingung entfernen möchten **, klicken Sie** ![ in der Bedingung auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="f98c1-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="f98c1-178">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen** , und wählen Sie einen verbleibenden Wert unter **angewendet bei**aus.</span><span class="sxs-lookup"><span data-stu-id="f98c1-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="f98c1-179">Wenn Sie Ausnahmen hinzufügen möchten, klicken Sie auf **Bedingung hinzufügen** , und wählen Sie unter **außer if**eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="f98c1-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="f98c1-180">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="f98c1-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="f98c1-181">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-181">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f98c1-182">Überprüfen Sie auf der angezeigten Seite **Ihre Einstellungen überprüfen** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f98c1-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="f98c1-183">Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f98c1-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="f98c1-184">Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-184">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="f98c1-185">Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien zu sicheren Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-185">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="f98c1-186">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f98c1-187">Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="f98c1-187">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="f98c1-188">Die Richtliniendetails werden in einem Fly Out angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-188">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="f98c1-189">Verwenden der Sicherheits & Compliance Center zum Ändern von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-189">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="f98c1-190">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-190">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f98c1-191">Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="f98c1-191">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="f98c1-192">Klicken Sie in der angezeigten Richtlinie Details ausfliegen, die angezeigt wird, auf **Richtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-192">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="f98c1-193">Die verfügbaren Einstellungen im angezeigten ausfliegen sind mit denen identisch, die im Abschnitt [Verwenden der Sicherheits & Compliance Center zum Erstellen von Richtlinien für sichere Links](#use-the-security--compliance-center-to-create-safe-links-policies) beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="f98c1-193">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="f98c1-194">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinien Priorität finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="f98c1-194">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="f98c1-195">Aktivieren oder Deaktivieren von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-195">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="f98c1-196">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f98c1-197">Beachten Sie den Wert in der Spalte **Status** :</span><span class="sxs-lookup"><span data-stu-id="f98c1-197">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="f98c1-198">Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="f98c1-198">Move the toggle to the left to disable the policy:</span></span> ![Deaktivieren der Richtlinie](../../media/scc-toggle-off.png)<span data-ttu-id="f98c1-200">.</span><span class="sxs-lookup"><span data-stu-id="f98c1-200">.</span></span>

   - <span data-ttu-id="f98c1-201">Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f98c1-201">Move the toggle to the right to enable the policy:</span></span> ![Richtlinie aktivieren](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="f98c1-203">.</span><span class="sxs-lookup"><span data-stu-id="f98c1-203">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="f98c1-204">Festlegen der Priorität von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-204">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="f98c1-205">Standardmäßig erhalten Richtlinien für sichere Links eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Policen haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="f98c1-205">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="f98c1-206">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="f98c1-206">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="f98c1-207">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f98c1-207">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="f98c1-208">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="f98c1-208">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="f98c1-209">Richtlinien für sichere Links werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0).</span><span class="sxs-lookup"><span data-stu-id="f98c1-209">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="f98c1-210">**Hinweis**: im Security & Compliance Center können Sie die Priorität der Richtlinie für sichere Links nur ändern, nachdem Sie Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f98c1-210">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="f98c1-211">In PowerShell können Sie die Standardpriorität außer Kraft setzen, wenn Sie die Regel für sichere Links erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="f98c1-211">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="f98c1-212">Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="f98c1-212">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="f98c1-213">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-213">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f98c1-214">Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="f98c1-214">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="f98c1-215">Klicken Sie im daraufhin angezeigten Richtliniendetails-Steuerelement auf die Schaltfläche verfügbare Priorität:</span><span class="sxs-lookup"><span data-stu-id="f98c1-215">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="f98c1-216">Für die Richtlinie für sichere Links mit dem **Prioritäts** Wert **0** ist nur die Schaltfläche **Priorität verringern** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f98c1-216">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="f98c1-217">Die Richtlinie für sichere Links mit dem Wert der niedrigsten **Priorität** (beispielsweise **3**) hat nur die Schaltfläche **Priorität verlängern** .</span><span class="sxs-lookup"><span data-stu-id="f98c1-217">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="f98c1-218">Wenn Sie über drei oder mehr Richtlinien für sichere Links verfügen, stehen für Richtlinien zwischen den **Werten der höchsten** und der niedrigsten Priorität sowohl die Tasten "Priorität" als auch " **Priorität verringern** " zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f98c1-218">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="f98c1-219">Klicken Sie auf Priorität Verb **Essern** oder **Priorität verringern** , um den **Prioritäts** Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f98c1-219">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="f98c1-220">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-220">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="f98c1-221">Verwenden der Sicherheits & Compliance Center zum Entfernen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-221">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="f98c1-222">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-222">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f98c1-223">Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="f98c1-223">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="f98c1-224">Klicken Sie im daraufhin angezeigten Richtliniendetails-Steuerelement auf **Richtlinie löschen**, und klicken Sie dann im angezeigten Warndialogfeld auf **Ja** .</span><span class="sxs-lookup"><span data-stu-id="f98c1-224">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="f98c1-225">Verwenden von Exchange Online PowerShell oder eigenständigen EoP PowerShell zum Konfigurieren von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-225">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="f98c1-226">Wie bereits beschrieben, besteht eine Richtlinie zu sicheren Links aus einer Richtlinie zu sicheren Links und einer Regel für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="f98c1-226">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="f98c1-227">In PowerShell ist der Unterschied zwischen Richtlinien für sichere Links und Regeln für sichere Links offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="f98c1-227">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="f98c1-228">Sie verwalten Richtlinien für sichere Links mithilfe der \*\* \* -SafeLinksPolicy-\*\* Cmdlets und verwalten Regeln für sichere Links mithilfe der \*\* \* -SafeLinksRule-\*\* Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f98c1-228">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="f98c1-229">In PowerShell erstellen Sie zuerst die Richtlinie für sichere Links, dann erstellen Sie die Regel für sichere Links, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f98c1-229">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="f98c1-230">In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Links und in der Regel für sichere Links separat.</span><span class="sxs-lookup"><span data-stu-id="f98c1-230">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="f98c1-231">Wenn Sie eine Richtlinie für sichere Links aus PowerShell entfernen, wird die entsprechende Regel für sichere Links nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-231">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="f98c1-232">Verwenden von PowerShell zum Erstellen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-232">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="f98c1-233">Das Erstellen einer Richtlinie zu sicheren Links in PowerShell erfolgt in einem zweistufigen Prozess:</span><span class="sxs-lookup"><span data-stu-id="f98c1-233">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f98c1-234">Erstellen Sie die Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="f98c1-234">Create the safe links policy.</span></span>
2. <span data-ttu-id="f98c1-235">Erstellen Sie die Regel für sichere Links, die die Richtlinie für sichere Links angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f98c1-235">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="f98c1-236">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="f98c1-236">**Notes**:</span></span>

- <span data-ttu-id="f98c1-237">Sie können eine neue Regel für sichere Links erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für sichere Links zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f98c1-237">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="f98c1-238">Eine Regel für sichere Links kann nicht mehr als einer Richtlinie für sichere Links zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f98c1-238">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="f98c1-239">Sie können die folgenden Einstellungen für neue Richtlinien für sichere Links in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="f98c1-239">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="f98c1-240">Erstellen Sie die neue Richtlinie als deaktiviert (_aktiviert_ im `$false` Cmdlet **New-SafeLinksRule** ).</span><span class="sxs-lookup"><span data-stu-id="f98c1-240">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="f98c1-241">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-SafeLinksRule** fest).</span><span class="sxs-lookup"><span data-stu-id="f98c1-241">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="f98c1-242">Eine neue Richtlinie für sichere Links, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer Regel für sichere Links zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f98c1-242">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="f98c1-243">Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-243">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="f98c1-244">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f98c1-244">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="f98c1-245">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="f98c1-245">**Notes**:</span></span>

- <span data-ttu-id="f98c1-246">Ausführliche Informationen zur Eingabesyntax, die für den _DoNotRewriteUrls_ -Parameter verwendet werden kann, finden Sie unter [Entry-Syntax für die Liste "nicht umschreiben der folgenden URLs"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="f98c1-246">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="f98c1-247">Weitere Syntax, die Sie für den Parameter _DoNotRewriteUrls_ verwenden können, wenn Sie vorhandene Richtlinien für sichere Links mithilfe des Cmdlets " **Satz-SafeLinksPolicy** " ändern, finden Sie im Abschnitt [Verwenden von PowerShell zum Ändern von Richtlinien für sichere Links](#use-powershell-to-modify-safe-links-policies) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="f98c1-247">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="f98c1-248">In diesem Beispiel wird eine Richtlinie für sichere Links namens "Contoso all" mit den folgenden Werten erstellt:</span><span class="sxs-lookup"><span data-stu-id="f98c1-248">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="f98c1-249">Aktivieren Sie die URL-Überprüfung und das Umschreiben in e-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f98c1-249">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="f98c1-250">Aktivieren Sie die URL-Überprüfung in Microsoft Teams (nur Tippen Sie auf Vorschau).</span><span class="sxs-lookup"><span data-stu-id="f98c1-250">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="f98c1-251">Aktivieren Sie die Echtzeitüberprüfung von angeklickten URLs, einschließlich geklickter Links, die auf Dateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="f98c1-251">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="f98c1-252">Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht senden.</span><span class="sxs-lookup"><span data-stu-id="f98c1-252">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="f98c1-253">Aktivieren Sie die URL-Überprüfung und Umschreibung für interne Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f98c1-253">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="f98c1-254">Nachverfolgen von Benutzerklicks im Zusammenhang mit Safe Links Protection (der Parameter _DoNotTrackUserClicks_ wird nicht verwendet, und der Standardwert ist $false, was bedeutet, dass Benutzerklicks nachverfolgt werden).</span><span class="sxs-lookup"><span data-stu-id="f98c1-254">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="f98c1-255">Benutzer können nicht auf die ursprüngliche URL klicken.</span><span class="sxs-lookup"><span data-stu-id="f98c1-255">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="f98c1-256">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="f98c1-256">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="f98c1-257">Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-257">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="f98c1-258">Verwenden Sie die folgende Syntax, um eine Regel für sichere Links zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f98c1-258">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="f98c1-259">In diesem Beispiel wird eine Regel für sichere Links namens "Contoso all" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="f98c1-259">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="f98c1-260">Die Regel ist mit der Richtlinie für sichere Links namens "Contoso all" verknüpft.</span><span class="sxs-lookup"><span data-stu-id="f98c1-260">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="f98c1-261">Die Regel gilt für alle Empfänger in der contoso.com-Domäne.</span><span class="sxs-lookup"><span data-stu-id="f98c1-261">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="f98c1-262">Da wir den _Priority_ -Parameter nicht verwenden, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="f98c1-262">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="f98c1-263">Die Regel ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="f98c1-263">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="f98c1-264">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="f98c1-264">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="f98c1-265">Verwenden von PowerShell zum Anzeigen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-265">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="f98c1-266">Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Links anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f98c1-266">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f98c1-267">In diesem Beispiel wird eine Zusammenfassungsliste aller Richtlinien für sichere Links zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f98c1-267">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="f98c1-268">In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Links namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f98c1-268">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="f98c1-269">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="f98c1-269">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="f98c1-270">Verwenden von PowerShell zum Anzeigen von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-270">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="f98c1-271">Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Links anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f98c1-271">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f98c1-272">In diesem Beispiel wird eine Zusammenfassungsliste aller Regeln für sichere Links zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f98c1-272">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="f98c1-273">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="f98c1-273">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="f98c1-274">In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Links namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f98c1-274">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="f98c1-275">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="f98c1-275">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="f98c1-276">Verwenden von PowerShell zum Ändern von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-276">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="f98c1-277">Sie können keine Richtlinie für sichere Links in PowerShell umbenennen (das Cmdlet " **SafeLinksPolicy** " verfügt über keinen Parameter " _Name_ ").</span><span class="sxs-lookup"><span data-stu-id="f98c1-277">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="f98c1-278">Wenn Sie eine Richtlinie für sichere Links im Security & Compliance Center umbenennen, benennen Sie die _Regel_für sichere Links nur um.</span><span class="sxs-lookup"><span data-stu-id="f98c1-278">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="f98c1-279">Die einzige zusätzliche Überlegung beim Ändern von Richtlinien für sichere Links in PowerShell ist die verfügbare Syntax für den _DoNotRewriteUrls_ -Parameter (die [Liste "nicht umschreiben der folgenden URLs"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="f98c1-279">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="f98c1-280">Verwenden Sie die folgende Syntax, um Werte hinzuzufügen, die vorhandene Einträge ersetzen werden: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="f98c1-280">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="f98c1-281">Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne andere vorhandene Einträge zu beeinflussen: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="f98c1-281">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="f98c1-282">Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Richtlinie zu sicheren Links erstellen, wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Links](#step-1-use-powershell-to-create-a-safe-links-policy) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f98c1-282">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="f98c1-283">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu ändern:</span><span class="sxs-lookup"><span data-stu-id="f98c1-283">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="f98c1-284">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="f98c1-284">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="f98c1-285">Verwenden von PowerShell zum Ändern von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-285">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="f98c1-286">Die einzige Einstellung, die beim Ändern einer Regel für sichere Links in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="f98c1-286">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="f98c1-287">Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Links finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-287">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="f98c1-288">Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Links](#step-2-use-powershell-to-create-a-safe-links-rule) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f98c1-288">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="f98c1-289">Verwenden Sie die folgende Syntax, um eine Regel für sichere Links zu ändern:</span><span class="sxs-lookup"><span data-stu-id="f98c1-289">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="f98c1-290">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="f98c1-290">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="f98c1-291">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-291">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="f98c1-292">Durch das Aktivieren oder Deaktivieren einer Regel für sichere Links in PowerShell wird die gesamte Richtlinie für sichere Links aktiviert oder deaktiviert (die Regel für sichere Links und die Richtlinie zugewiesene sichere Links).</span><span class="sxs-lookup"><span data-stu-id="f98c1-292">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="f98c1-293">Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="f98c1-293">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="f98c1-294">In diesem Beispiel wird die Regel für sichere Links namens "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f98c1-294">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f98c1-295">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f98c1-295">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f98c1-296">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) und [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="f98c1-296">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="f98c1-297">Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-297">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="f98c1-298">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="f98c1-298">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="f98c1-299">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="f98c1-299">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="f98c1-300">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="f98c1-300">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="f98c1-301">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="f98c1-301">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="f98c1-302">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="f98c1-302">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="f98c1-303">Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Links in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="f98c1-303">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="f98c1-p122">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="f98c1-p122">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="f98c1-306">**Hinweis**: Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="f98c1-306">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="f98c1-307">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="f98c1-307">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="f98c1-308">Verwenden von PowerShell zum Entfernen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-308">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="f98c1-309">Wenn Sie mithilfe von PowerShell eine Richtlinie für sichere Links entfernen, wird die entsprechende Regel für sichere Links nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-309">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="f98c1-310">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="f98c1-310">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="f98c1-311">In diesem Beispiel wird die Richtlinie für sichere Links namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-311">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="f98c1-312">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="f98c1-312">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="f98c1-313">Verwenden von PowerShell zum Entfernen von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="f98c1-313">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="f98c1-314">Wenn Sie mithilfe von PowerShell eine Regel für sichere Links entfernen, wird die entsprechende Richtlinie für sichere Links nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-314">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="f98c1-315">Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="f98c1-315">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="f98c1-316">In diesem Beispiel wird die Regel für sichere Links namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="f98c1-316">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f98c1-317">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="f98c1-317">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="f98c1-318">Überprüfen Sie die verfügbaren Advanced Threat Protection-Berichte, um zu überprüfen, ob Nachrichten von sicheren Links überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="f98c1-318">To verify that Safe Links is scanning messages, check the available Advanced Threat Protection reports.</span></span> <span data-ttu-id="f98c1-319">Weitere Informationen finden Sie unter [Anzeigen von Berichten für Office 365 ATP](view-reports-for-atp.md) und [Verwenden von Explorer im Security & Compliance Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="f98c1-319">For more information, see [View reports for Office 365 ATP](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f98c1-320">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="f98c1-320">How do you know these procedures worked?</span></span>

<span data-ttu-id="f98c1-321">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Richtlinien für sichere Links erfolgreich erstellt, geändert oder entfernt haben:</span><span class="sxs-lookup"><span data-stu-id="f98c1-321">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="f98c1-322">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="f98c1-322">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="f98c1-323">Überprüfen Sie die Liste der Richtlinien, deren **Status** Werte und deren **Prioritäts** Werte.</span><span class="sxs-lookup"><span data-stu-id="f98c1-323">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="f98c1-324">Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im verfliegt an.</span><span class="sxs-lookup"><span data-stu-id="f98c1-324">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="f98c1-325">Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f98c1-325">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
