---
title: Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Richtlinien für sichere Links und globale Einstellungen für sichere Links in Microsoft Defender für Office 365 anzeigen, erstellen, ändern und löschen.
ms.openlocfilehash: 550be48d5f1cae490c53c8f4a9fcedb0b9f21f73
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572717"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="80f19-103">Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="80f19-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="80f19-104">Dieser Artikel richtet sich an Geschäftskunden, die [Microsoft Defender für Office 365](office-365-atp.md)haben.</span><span class="sxs-lookup"><span data-stu-id="80f19-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="80f19-105">Wenn Sie ein Privatbenutzer sind, der nach Informationen zu Safelinks in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="80f19-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="80f19-106">"Sichere Links" ist ein Feature in [Microsoft Defender für Office 365](office-365-atp.md) , das die URL-Überprüfung eingehender e-Mail-Nachrichten im Nachrichtenfluss und die Zeit der Klick Überprüfung von URLs und Links in e-Mail-Nachrichten und an anderen Speicherorten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="80f19-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="80f19-107">Weitere Informationen finden Sie unter [sichere Links in Microsoft Defender für Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="80f19-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="80f19-108">Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="80f19-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="80f19-109">Um sichere Links beim Scannen von URLs zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere Links erstellen, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="80f19-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

<span data-ttu-id="80f19-110">Sie können Richtlinien für sichere Links im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Microsoft Defender für Office 365 Add-on-Abonnements) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="80f19-110">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="80f19-111">Die grundlegenden Elemente einer Richtlinie zu sicheren Links sind:</span><span class="sxs-lookup"><span data-stu-id="80f19-111">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="80f19-112">**Richtlinie zu sicheren Links**: Aktivieren Sie den Schutz für sichere Links, aktivieren Sie den Echt Zeit-URL-Scan, geben Sie an, ob der Abschluss der Echtzeitüberprüfung vor dem Senden der Nachricht gewartet werden soll, aktivieren Sie die Überprüfung interner Nachrichten, geben Sie an, ob Benutzerklicks auf URLs nachverfolgt werden sollen, und geben Sie an, ob Benutzer auf die ursprüngliche URL klicken können</span><span class="sxs-lookup"><span data-stu-id="80f19-112">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="80f19-113">**Die Regel für sichere Links**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) an.</span><span class="sxs-lookup"><span data-stu-id="80f19-113">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="80f19-114">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Links im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="80f19-114">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="80f19-115">Wenn Sie eine Richtlinie für sichere Links erstellen, erstellen Sie tatsächlich eine Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit dem gleichen Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="80f19-115">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="80f19-116">Wenn Sie eine Richtlinie für sichere Links ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die Regel für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="80f19-116">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="80f19-117">Alle anderen Einstellungen ändern die zugehörige Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="80f19-117">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="80f19-118">Wenn Sie eine Richtlinie für sichere Links entfernen, werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links entfernt.</span><span class="sxs-lookup"><span data-stu-id="80f19-118">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="80f19-119">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt.</span><span class="sxs-lookup"><span data-stu-id="80f19-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="80f19-120">Weitere Informationen finden Sie im Abschnitt [Verwenden von Exchange Online PowerShell oder eigenständige EoP PowerShell zum Konfigurieren von Richtlinien für sichere Links](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="80f19-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="80f19-121">Sie konfigurieren die globalen Einstellungen für den Schutz von sicheren Links **außerhalb** der Richtlinien für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="80f19-121">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="80f19-122">Anweisungen finden Sie unter [Configure Global Settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="80f19-122">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="80f19-123">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="80f19-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="80f19-124">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="80f19-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="80f19-125">Wenn Sie direkt zur Seite **sichere Links** wechseln möchten, verwenden Sie <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="80f19-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="80f19-126">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="80f19-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="80f19-127">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="80f19-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="80f19-128">Sie müssen Berechtigungen im Security & Compliance Center zugewiesen werden, bevor Sie die Verfahren in diesem Artikel ausführen können:</span><span class="sxs-lookup"><span data-stu-id="80f19-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="80f19-129">Zum Erstellen, ändern und Löschen von Richtlinien für sichere Links müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="80f19-129">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="80f19-130">Für den schreibgeschützten Zugriff auf Richtlinien für sichere Links müssen Sie Mitglied der Rollengruppen " **globaler Leser** " oder " **Sicherheits Leser** " sein.</span><span class="sxs-lookup"><span data-stu-id="80f19-130">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="80f19-131">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="80f19-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="80f19-132">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="80f19-132">**Notes**:</span></span>

  - <span data-ttu-id="80f19-133">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80f19-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="80f19-134">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="80f19-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="80f19-135">Die Rollengruppe " **Organisationsverwaltung** " in der Ansicht "nur Leserechten" in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) bietet außerdem schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="80f19-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="80f19-136">Die empfohlenen Einstellungen für Richtlinien zu sicheren Links finden Sie unter [Richtlinieneinstellungen für sichere Links](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="80f19-136">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="80f19-137">Erlauben Sie bis zu 30 Minuten, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="80f19-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="80f19-138">[Für Office 365 werden fortlaufend neue Features zu Microsoft Defender hinzugefügt](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="80f19-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="80f19-139">Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren bestehenden Richtlinien für sichere Links vornehmen.</span><span class="sxs-lookup"><span data-stu-id="80f19-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="80f19-140">Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-140">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="80f19-141">Durch das Erstellen einer benutzerdefinierten Richtlinie für sichere Links im Security & Compliance Center werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit dem gleichen Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="80f19-141">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="80f19-142">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="80f19-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="80f19-143">Klicken Sie auf der Seite **sichere Links** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="80f19-143">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="80f19-144">Der Assistent für **neue Richtlinien für sichere Links** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="80f19-144">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="80f19-145">Konfigurieren Sie auf der Seite **Ihre Richtlinie benennen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="80f19-145">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="80f19-146">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="80f19-146">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="80f19-147">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="80f19-147">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="80f19-148">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="80f19-148">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="80f19-149">Konfigurieren Sie auf der angezeigten Seite **Einstellungen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="80f19-149">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="80f19-150">**Wählen Sie die Aktion für unbekannte potenziell bösartige URLs in Nachrichten** aus: Wählen Sie **ein** aus, um den Schutz für sichere Links in e-Mail-Nachrichten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="80f19-150">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="80f19-151">**Wählen Sie die Aktion für unbekannte oder potenziell schädliche URLs in Microsoft Teams** aus: Wählen Sie **ein** aus, um den Schutz für sichere Links für Links in Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="80f19-151">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="80f19-152">Über **Prüfen der Echt Zeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen**: Wählen Sie diese Einstellung aus, um die Echtzeitüberprüfung von Links in e-Mail-Nachrichten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="80f19-152">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="80f19-153">**Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht** übermitteln: Wählen Sie diese Einstellung, um zu warten, bis die URL-Überprüfung in Echtzeit abgeschlossen ist, bevor Sie die Nachricht</span><span class="sxs-lookup"><span data-stu-id="80f19-153">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="80f19-154">**Anwenden sicherer Links auf e-Mail-Nachrichten, die innerhalb der Organisation gesendet** werden: Wählen Sie diese Einstellung aus, um die Richtlinie für sichere Links auf Nachrichten zwischen internen Absendern und internen Empfängern anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="80f19-154">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="80f19-155">**Benutzerklicks nicht nachverfolgen**: lassen Sie diese Einstellung nicht ausgewählt, damit der nach Verfolgungs Benutzer auf URLs in e-Mail-Nachrichten klickt.</span><span class="sxs-lookup"><span data-stu-id="80f19-155">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="80f19-156">**Benutzer dürfen nicht auf die ursprüngliche URL klicken**: Wählen Sie diese Einstellung aus, um zu verhindern, dass Benutzer auf die ursprüngliche URL in [Warn Seiten](atp-safe-links.md#warning-pages-from-safe-links)klicken.</span><span class="sxs-lookup"><span data-stu-id="80f19-156">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="80f19-157">**Die folgenden URLs dürfen nicht umgeschrieben** werden: ermöglicht den Zugriff auf die angegebenen URLs, die andernfalls durch sichere Links blockiert würden.</span><span class="sxs-lookup"><span data-stu-id="80f19-157">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="80f19-158">Geben Sie in das Feld die gewünschte URL oder den gewünschten Wert ein, und klicken Sie dann auf</span><span class="sxs-lookup"><span data-stu-id="80f19-158">In the box, type the URL or value that you want, and then click</span></span> ![Schaltflächensymbol hinzufügen](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="80f19-160">.</span><span class="sxs-lookup"><span data-stu-id="80f19-160">.</span></span>

     <span data-ttu-id="80f19-161">Um einen vorhandenen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie dann auf</span><span class="sxs-lookup"><span data-stu-id="80f19-161">To remove an existing entry, select it and then click</span></span> ![Symbol für die Schaltfläche "Löschen"](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="80f19-163">.</span><span class="sxs-lookup"><span data-stu-id="80f19-163">.</span></span>

     <span data-ttu-id="80f19-164">Informationen zur Eingabesyntax finden Sie unter [Eintrags Syntax für die Liste "folgende URLs nicht umschreiben"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="80f19-164">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="80f19-165">Ausführliche Informationen zu diesen Einstellungen finden Sie unter Einstellungen für [sichere Links für e-Mail-Nachrichten](atp-safe-links.md#safe-links-settings-for-email-messages) und [Einstellungen für sichere Links für Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="80f19-165">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="80f19-166">Weitere empfohlene Werte für Standard mäßige und strenge Richtlinieneinstellungen finden Sie unter [Richtlinieneinstellungen für sichere Links](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="80f19-166">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="80f19-167">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="80f19-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="80f19-168">Identifizieren Sie auf der Seite **angewendet auf** , die angezeigt wird, die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="80f19-168">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="80f19-169">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="80f19-169">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="80f19-170">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="80f19-170">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="80f19-171">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="80f19-171">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="80f19-172">Klicken Sie auf **Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="80f19-172">Click **Add a condition**.</span></span> <span data-ttu-id="80f19-173">Wählen Sie in der Dropdownliste, die angezeigt wird, eine Bedingung unter **angewendet, wenn**:</span><span class="sxs-lookup"><span data-stu-id="80f19-173">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="80f19-174">**Der Empfänger lautet**: gibt ein oder mehrere Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="80f19-174">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="80f19-175">**Der Empfänger ist Mitglied von**: gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="80f19-175">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="80f19-176">**Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="80f19-176">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="80f19-177">Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **der folgenden** Felder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80f19-177">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="80f19-178">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der zu markierende Werte durch.</span><span class="sxs-lookup"><span data-stu-id="80f19-178">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="80f19-179">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="80f19-179">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="80f19-180">Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="80f19-180">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="80f19-181">Wenn Sie einzelne Einträge entfernen möchten **Remove** , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Wert entfernen.</span><span class="sxs-lookup"><span data-stu-id="80f19-181">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="80f19-182">Wenn Sie die gesamte Bedingung entfernen möchten **, klicken Sie** ![ in der Bedingung auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="80f19-182">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="80f19-183">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen** , und wählen Sie einen verbleibenden Wert unter **angewendet bei** aus.</span><span class="sxs-lookup"><span data-stu-id="80f19-183">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="80f19-184">Wenn Sie Ausnahmen hinzufügen möchten, klicken Sie auf **Bedingung hinzufügen** , und wählen Sie unter **außer if** eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="80f19-184">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="80f19-185">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="80f19-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="80f19-186">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="80f19-186">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="80f19-187">Überprüfen Sie auf der angezeigten Seite **Ihre Einstellungen überprüfen** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="80f19-187">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="80f19-188">Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="80f19-188">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="80f19-189">Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="80f19-189">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="80f19-190">Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien zu sicheren Links</span><span class="sxs-lookup"><span data-stu-id="80f19-190">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="80f19-191">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="80f19-191">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="80f19-192">Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="80f19-192">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="80f19-193">Die Richtliniendetails werden in einem Fly Out angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80f19-193">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="80f19-194">Verwenden der Sicherheits & Compliance Center zum Ändern von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-194">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="80f19-195">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="80f19-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="80f19-196">Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="80f19-196">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="80f19-197">Klicken Sie in der angezeigten Richtlinie Details ausfliegen, die angezeigt wird, auf **Richtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="80f19-197">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="80f19-198">Die verfügbaren Einstellungen im angezeigten ausfliegen sind mit denen identisch, die im Abschnitt [Verwenden der Sicherheits & Compliance Center zum Erstellen von Richtlinien für sichere Links](#use-the-security--compliance-center-to-create-safe-links-policies) beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="80f19-198">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="80f19-199">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinien Priorität finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="80f19-199">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="80f19-200">Aktivieren oder Deaktivieren von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-200">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="80f19-201">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="80f19-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="80f19-202">Beachten Sie den Wert in der Spalte **Status** :</span><span class="sxs-lookup"><span data-stu-id="80f19-202">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="80f19-203">Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="80f19-203">Move the toggle to the left to disable the policy:</span></span> ![Deaktivieren der Richtlinie](../../media/scc-toggle-off.png)<span data-ttu-id="80f19-205">.</span><span class="sxs-lookup"><span data-stu-id="80f19-205">.</span></span>

   - <span data-ttu-id="80f19-206">Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="80f19-206">Move the toggle to the right to enable the policy:</span></span> ![Richtlinie aktivieren](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="80f19-208">.</span><span class="sxs-lookup"><span data-stu-id="80f19-208">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="80f19-209">Festlegen der Priorität von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-209">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="80f19-210">Standardmäßig erhalten Richtlinien für sichere Links eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Policen haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="80f19-210">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="80f19-211">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="80f19-211">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="80f19-212">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="80f19-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="80f19-213">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="80f19-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="80f19-214">Richtlinien für sichere Links werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0).</span><span class="sxs-lookup"><span data-stu-id="80f19-214">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="80f19-215">**Hinweis**: im Security & Compliance Center können Sie die Priorität der Richtlinie für sichere Links nur ändern, nachdem Sie Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="80f19-215">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="80f19-216">In PowerShell können Sie die Standardpriorität außer Kraft setzen, wenn Sie die Regel für sichere Links erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="80f19-216">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="80f19-217">Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="80f19-217">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="80f19-218">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="80f19-218">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="80f19-219">Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="80f19-219">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="80f19-220">Klicken Sie im daraufhin angezeigten Richtliniendetails-Steuerelement auf die Schaltfläche verfügbare Priorität:</span><span class="sxs-lookup"><span data-stu-id="80f19-220">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="80f19-221">Für die Richtlinie für sichere Links mit dem **Prioritäts** Wert **0** ist nur die Schaltfläche **Priorität verringern** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="80f19-221">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="80f19-222">Die Richtlinie für sichere Links mit dem Wert der niedrigsten **Priorität** (beispielsweise **3**) hat nur die Schaltfläche **Priorität verlängern** .</span><span class="sxs-lookup"><span data-stu-id="80f19-222">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="80f19-223">Wenn Sie über drei oder mehr Richtlinien für sichere Links verfügen, stehen für Richtlinien zwischen den **Werten der höchsten** und der niedrigsten Priorität sowohl die Tasten "Priorität" als auch " **Priorität verringern** " zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="80f19-223">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="80f19-224">Klicken Sie auf Priorität Verb **Essern** oder **Priorität verringern** , um den **Prioritäts** Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="80f19-224">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="80f19-225">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="80f19-225">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="80f19-226">Verwenden der Sicherheits & Compliance Center zum Entfernen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-226">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="80f19-227">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="80f19-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="80f19-228">Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="80f19-228">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="80f19-229">Klicken Sie im daraufhin angezeigten Richtliniendetails-Steuerelement auf **Richtlinie löschen**, und klicken Sie dann im angezeigten Warndialogfeld auf **Ja** .</span><span class="sxs-lookup"><span data-stu-id="80f19-229">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="80f19-230">Verwenden von Exchange Online PowerShell oder eigenständigen EoP PowerShell zum Konfigurieren von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-230">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="80f19-231">Wie bereits beschrieben, besteht eine Richtlinie zu sicheren Links aus einer Richtlinie zu sicheren Links und einer Regel für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="80f19-231">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="80f19-232">In PowerShell ist der Unterschied zwischen Richtlinien für sichere Links und Regeln für sichere Links offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="80f19-232">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="80f19-233">Sie verwalten Richtlinien für sichere Links mithilfe der **\* -SafeLinksPolicy-** Cmdlets und verwalten Regeln für sichere Links mithilfe der **\* -SafeLinksRule-** Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="80f19-233">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="80f19-234">In PowerShell erstellen Sie zuerst die Richtlinie für sichere Links, dann erstellen Sie die Regel für sichere Links, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="80f19-234">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="80f19-235">In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Links und in der Regel für sichere Links separat.</span><span class="sxs-lookup"><span data-stu-id="80f19-235">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="80f19-236">Wenn Sie eine Richtlinie für sichere Links aus PowerShell entfernen, wird die entsprechende Regel für sichere Links nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="80f19-236">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="80f19-237">Verwenden von PowerShell zum Erstellen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-237">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="80f19-238">Das Erstellen einer Richtlinie zu sicheren Links in PowerShell erfolgt in einem zweistufigen Prozess:</span><span class="sxs-lookup"><span data-stu-id="80f19-238">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="80f19-239">Erstellen Sie die Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="80f19-239">Create the safe links policy.</span></span>
2. <span data-ttu-id="80f19-240">Erstellen Sie die Regel für sichere Links, die die Richtlinie für sichere Links angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="80f19-240">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="80f19-241">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="80f19-241">**Notes**:</span></span>

- <span data-ttu-id="80f19-242">Sie können eine neue Regel für sichere Links erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für sichere Links zuweisen.</span><span class="sxs-lookup"><span data-stu-id="80f19-242">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="80f19-243">Eine Regel für sichere Links kann nicht mehr als einer Richtlinie für sichere Links zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="80f19-243">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="80f19-244">Sie können die folgenden Einstellungen für neue Richtlinien für sichere Links in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="80f19-244">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="80f19-245">Erstellen Sie die neue Richtlinie als deaktiviert (_aktiviert_ im `$false` Cmdlet **New-SafeLinksRule** ).</span><span class="sxs-lookup"><span data-stu-id="80f19-245">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="80f19-246">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-SafeLinksRule** fest).</span><span class="sxs-lookup"><span data-stu-id="80f19-246">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="80f19-247">Eine neue Richtlinie für sichere Links, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer Regel für sichere Links zuweisen.</span><span class="sxs-lookup"><span data-stu-id="80f19-247">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="80f19-248">Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Links</span><span class="sxs-lookup"><span data-stu-id="80f19-248">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="80f19-249">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="80f19-249">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="80f19-250">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="80f19-250">**Notes**:</span></span>

- <span data-ttu-id="80f19-251">Ausführliche Informationen zur Eingabesyntax, die für den _DoNotRewriteUrls_ -Parameter verwendet werden kann, finden Sie unter [Entry-Syntax für die Liste "nicht umschreiben der folgenden URLs"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="80f19-251">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="80f19-252">Weitere Syntax, die Sie für den Parameter _DoNotRewriteUrls_ verwenden können, wenn Sie vorhandene Richtlinien für sichere Links mithilfe des Cmdlets " **Satz-SafeLinksPolicy** " ändern, finden Sie im Abschnitt [Verwenden von PowerShell zum Ändern von Richtlinien für sichere Links](#use-powershell-to-modify-safe-links-policies) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="80f19-252">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="80f19-253">In diesem Beispiel wird eine Richtlinie für sichere Links namens "Contoso all" mit den folgenden Werten erstellt:</span><span class="sxs-lookup"><span data-stu-id="80f19-253">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="80f19-254">Aktivieren Sie die URL-Überprüfung und das Umschreiben in e-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="80f19-254">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="80f19-255">Aktivieren Sie die URL-Überprüfung in Microsoft Teams (nur Tippen Sie auf Vorschau).</span><span class="sxs-lookup"><span data-stu-id="80f19-255">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="80f19-256">Aktivieren Sie die Echtzeitüberprüfung von angeklickten URLs, einschließlich geklickter Links, die auf Dateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="80f19-256">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="80f19-257">Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht senden.</span><span class="sxs-lookup"><span data-stu-id="80f19-257">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="80f19-258">Aktivieren Sie die URL-Überprüfung und Umschreibung für interne Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="80f19-258">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="80f19-259">Nachverfolgen von Benutzerklicks im Zusammenhang mit Safe Links Protection (der Parameter _DoNotTrackUserClicks_ wird nicht verwendet, und der Standardwert ist $false, was bedeutet, dass Benutzerklicks nachverfolgt werden).</span><span class="sxs-lookup"><span data-stu-id="80f19-259">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="80f19-260">Benutzer können nicht auf die ursprüngliche URL klicken.</span><span class="sxs-lookup"><span data-stu-id="80f19-260">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="80f19-261">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="80f19-261">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="80f19-262">Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-262">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="80f19-263">Verwenden Sie die folgende Syntax, um eine Regel für sichere Links zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="80f19-263">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="80f19-264">In diesem Beispiel wird eine Regel für sichere Links namens "Contoso all" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="80f19-264">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="80f19-265">Die Regel ist mit der Richtlinie für sichere Links namens "Contoso all" verknüpft.</span><span class="sxs-lookup"><span data-stu-id="80f19-265">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="80f19-266">Die Regel gilt für alle Empfänger in der contoso.com-Domäne.</span><span class="sxs-lookup"><span data-stu-id="80f19-266">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="80f19-267">Da wir den _Priority_ -Parameter nicht verwenden, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="80f19-267">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="80f19-268">Die Regel ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="80f19-268">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="80f19-269">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="80f19-269">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="80f19-270">Verwenden von PowerShell zum Anzeigen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-270">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="80f19-271">Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Links anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="80f19-271">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="80f19-272">In diesem Beispiel wird eine Zusammenfassungsliste aller Richtlinien für sichere Links zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="80f19-272">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="80f19-273">In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Links namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="80f19-273">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="80f19-274">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="80f19-274">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="80f19-275">Verwenden von PowerShell zum Anzeigen von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-275">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="80f19-276">Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Links anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="80f19-276">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="80f19-277">In diesem Beispiel wird eine Zusammenfassungsliste aller Regeln für sichere Links zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="80f19-277">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="80f19-278">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="80f19-278">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="80f19-279">In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Links namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="80f19-279">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="80f19-280">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="80f19-280">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="80f19-281">Verwenden von PowerShell zum Ändern von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-281">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="80f19-282">Sie können keine Richtlinie für sichere Links in PowerShell umbenennen (das Cmdlet " **SafeLinksPolicy** " verfügt über keinen Parameter " _Name_ ").</span><span class="sxs-lookup"><span data-stu-id="80f19-282">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="80f19-283">Wenn Sie eine Richtlinie für sichere Links im Security & Compliance Center umbenennen, benennen Sie die _Regel_ für sichere Links nur um.</span><span class="sxs-lookup"><span data-stu-id="80f19-283">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="80f19-284">Die einzige zusätzliche Überlegung beim Ändern von Richtlinien für sichere Links in PowerShell ist die verfügbare Syntax für den _DoNotRewriteUrls_ -Parameter (die [Liste "nicht umschreiben der folgenden URLs"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="80f19-284">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="80f19-285">Verwenden Sie die folgende Syntax, um Werte hinzuzufügen, die vorhandene Einträge ersetzen werden: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="80f19-285">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="80f19-286">Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne andere vorhandene Einträge zu beeinflussen: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="80f19-286">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="80f19-287">Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Richtlinie zu sicheren Links erstellen, wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Links](#step-1-use-powershell-to-create-a-safe-links-policy) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="80f19-287">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="80f19-288">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu ändern:</span><span class="sxs-lookup"><span data-stu-id="80f19-288">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="80f19-289">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="80f19-289">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="80f19-290">Verwenden von PowerShell zum Ändern von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-290">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="80f19-291">Die einzige Einstellung, die beim Ändern einer Regel für sichere Links in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="80f19-291">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="80f19-292">Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Links finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="80f19-292">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="80f19-293">Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Links](#step-2-use-powershell-to-create-a-safe-links-rule) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="80f19-293">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="80f19-294">Verwenden Sie die folgende Syntax, um eine Regel für sichere Links zu ändern:</span><span class="sxs-lookup"><span data-stu-id="80f19-294">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="80f19-295">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="80f19-295">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="80f19-296">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-296">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="80f19-297">Durch das Aktivieren oder Deaktivieren einer Regel für sichere Links in PowerShell wird die gesamte Richtlinie für sichere Links aktiviert oder deaktiviert (die Regel für sichere Links und die Richtlinie zugewiesene sichere Links).</span><span class="sxs-lookup"><span data-stu-id="80f19-297">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="80f19-298">Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="80f19-298">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="80f19-299">In diesem Beispiel wird die Regel für sichere Links namens "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="80f19-299">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="80f19-300">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="80f19-300">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="80f19-301">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) und [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="80f19-301">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="80f19-302">Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-302">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="80f19-303">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="80f19-303">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="80f19-304">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="80f19-304">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="80f19-305">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="80f19-305">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="80f19-306">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="80f19-306">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="80f19-307">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="80f19-307">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="80f19-308">Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Links in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="80f19-308">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="80f19-p123">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="80f19-p123">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="80f19-311">**Hinweis**: Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="80f19-311">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="80f19-312">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="80f19-312">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="80f19-313">Verwenden von PowerShell zum Entfernen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-313">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="80f19-314">Wenn Sie mithilfe von PowerShell eine Richtlinie für sichere Links entfernen, wird die entsprechende Regel für sichere Links nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="80f19-314">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="80f19-315">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="80f19-315">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="80f19-316">In diesem Beispiel wird die Richtlinie für sichere Links namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="80f19-316">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="80f19-317">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="80f19-317">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="80f19-318">Verwenden von PowerShell zum Entfernen von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="80f19-318">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="80f19-319">Wenn Sie mithilfe von PowerShell eine Regel für sichere Links entfernen, wird die entsprechende Richtlinie für sichere Links nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="80f19-319">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="80f19-320">Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="80f19-320">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="80f19-321">In diesem Beispiel wird die Regel für sichere Links namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="80f19-321">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="80f19-322">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="80f19-322">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="80f19-323">Um zu überprüfen, ob sichere Links Nachrichten scannen, überprüfen Sie den verfügbaren Microsoft Defender für Office 365 Berichte.</span><span class="sxs-lookup"><span data-stu-id="80f19-323">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="80f19-324">Weitere Informationen finden Sie unter [Anzeigen von Berichten für Defender für Office 365](view-reports-for-atp.md) und [Verwenden von Explorer im Security & Compliance Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="80f19-324">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="80f19-325">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="80f19-325">How do you know these procedures worked?</span></span>

<span data-ttu-id="80f19-326">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Richtlinien für sichere Links erfolgreich erstellt, geändert oder entfernt haben:</span><span class="sxs-lookup"><span data-stu-id="80f19-326">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="80f19-327">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.</span><span class="sxs-lookup"><span data-stu-id="80f19-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="80f19-328">Überprüfen Sie die Liste der Richtlinien, deren **Status** Werte und deren **Prioritäts** Werte.</span><span class="sxs-lookup"><span data-stu-id="80f19-328">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="80f19-329">Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im verfliegt an.</span><span class="sxs-lookup"><span data-stu-id="80f19-329">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="80f19-330">Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="80f19-330">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
