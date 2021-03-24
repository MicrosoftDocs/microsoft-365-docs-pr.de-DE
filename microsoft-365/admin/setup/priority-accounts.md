---
title: Verwalten und Überwachen von Prioritätskonten
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Überwachen sie fehlgeschlagene und verzögerte E-Mail-Nachrichten, die an oder von Konten gesendet werden, die hohe geschäftliche Auswirkungen haben.
ms.openlocfilehash: 0bba1f87f80de9fea249ce2604e83ceeadfb79ee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050642"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="b3404-103">Verwalten und Überwachen von Prioritätskonten</span><span class="sxs-lookup"><span data-stu-id="b3404-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="b3404-104">In jeder Microsoft 365-Organisation gibt es wichtige Personen, z. B. Führungskräfte, Führungskräfte, Manager oder andere Benutzer, die Zugriff auf vertrauliche, proprietäre oder informationen mit hoher Priorität haben.</span><span class="sxs-lookup"><span data-stu-id="b3404-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="b3404-105">Um Ihre Organisation beim Schutz dieser Konten zu unterstützen, können Sie nun bestimmte Benutzer als Prioritätskonten festlegen und app-spezifische Features nutzen, die ihnen zusätzlichen Schutz bieten.</span><span class="sxs-lookup"><span data-stu-id="b3404-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="b3404-106">In Zukunft werden mehr Apps und Features Prioritätskonten unterstützen, und zu Beginn haben wir zwei Funktionen **angekündigt:** Den Schutz von Prioritätskonten und die Premium-Nachrichtenflussüberwachung. </span><span class="sxs-lookup"><span data-stu-id="b3404-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="b3404-107">**Prioritätskontoschutz** – Microsoft Defender für Office 365 (früher Office 365 Advanced Threat Protection) unterstützt Prioritätskonten als Tags, die in Filtern in Warnungen, Berichten und Untersuchungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b3404-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="b3404-108">Weitere Informationen finden Sie unter [Benutzertags in Microsoft Defender für Office 365](../../security/defender-365-security/user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="b3404-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/defender-365-security/user-tags.md).</span></span>
- <span data-ttu-id="b3404-109">**Premium-Nachrichtenflussüberwachung** – Ein fehlerfreier Nachrichtenfluss kann für den Geschäftserfolg von entscheidender Bedeutung sein, und Verzögerungen oder Fehler bei der Zustellung können sich negativ auf das Unternehmen auswirken.</span><span class="sxs-lookup"><span data-stu-id="b3404-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="b3404-110">Sie können einen Schwellenwert für fehlgeschlagene oder verzögerte E-Mails auswählen, Benachrichtigungen empfangen, wenn dieser Schwellenwert überschritten wird, und einen Bericht über E-Mail-Probleme für Prioritätskonten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b3404-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="b3404-111">Weitere Informationen finden Sie unter [E-Mail-Probleme für Prioritätskontenbericht in der modernen EAC.](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="b3404-111">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="b3404-112">Bewährte Sicherheitsmethoden für Prioritätskonten finden Sie unter [Sicherheitsempfehlungen für Prioritätskonten](../../security/defender-365-security/security-recommendations-for-priority-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="b3404-112">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/defender-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b3404-113">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="b3404-113">Before you begin</span></span>

<span data-ttu-id="b3404-114">Die **in diesem** Thema beschriebene Prioritätskontoschutzfunktion ist nur für Organisationen verfügbar, die die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="b3404-114">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="b3404-115">Microsoft Defender für Office 365 Plan 2, einschließlich derer mit Office 365 E3, Office 365 E5, Microsoft 365 E5 oder Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="b3404-115">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="b3404-116">Die in diesem Thema beschriebene Premium Mail **Flow Monitoring-Funktion** ist nur für Organisationen verfügbar, die die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="b3404-116">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="b3404-117">Ihre Organisation muss eine Lizenzanzahl von mindestens 10.000 aus einem der folgenden Produkte oder einer Kombination der folgenden Produkte haben: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b3404-117">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="b3404-118">Beispielsweise kann Ihre Organisation über 3000 Office 365 E3-Lizenzen und 8500 Microsoft 365 E5 verfügen, für insgesamt 11.500 Lizenzen aus den qualifizierenden Produkten.</span><span class="sxs-lookup"><span data-stu-id="b3404-118">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="b3404-119">Ihre Organisation muss über mindestens 50 monatlich aktive Exchange Online-Benutzer verfügen.</span><span class="sxs-lookup"><span data-stu-id="b3404-119">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="b3404-120">Sie können bis zu 250 Prioritätskonten überwachen.</span><span class="sxs-lookup"><span data-stu-id="b3404-120">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="b3404-121">Hinzufügen von Prioritätskonten von der Seite "Setup"</span><span class="sxs-lookup"><span data-stu-id="b3404-121">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="b3404-122">Fügen Sie auf der Seite **Setup Prioritätskonten hinzu.**</span><span class="sxs-lookup"><span data-stu-id="b3404-122">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="b3404-123">Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="b3404-123">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b3404-124">Wechseln Sie **zu**  >  **Setup-Organisationswissen,** und wählen **Sie Anzeigen** unter Überwachen Ihrer wichtigsten **Konten aus.**</span><span class="sxs-lookup"><span data-stu-id="b3404-124">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="b3404-125">Wählen **Sie Erste Schritte** oder Verwalten **aus.**</span><span class="sxs-lookup"><span data-stu-id="b3404-125">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="b3404-126">Geben Sie **auf** der Seite Prioritätskonten hinzufügen im Suchfeld den Namen oder die E-Mail-Adresse der Person ein, die Sie der Liste prioritätskonten hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="b3404-126">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="b3404-127">Sie können auch Ihren E-Mail-Schwellenwert für fehlgeschlagene oder verzögerte E-Mails festlegen und einen wöchentlichen Bericht über Probleme für Prioritätskonten erhalten.</span><span class="sxs-lookup"><span data-stu-id="b3404-127">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="b3404-128">Wählen Sie den Benutzer aus, und wählen Sie **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="b3404-128">Select the user and choose **Save**.</span></span>

<span data-ttu-id="b3404-129">Sie können auch Prioritätskonten auf der Seite Aktive Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b3404-129">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="b3404-130">Hinzufügen von Prioritätskonten von der Seite Aktive Benutzer</span><span class="sxs-lookup"><span data-stu-id="b3404-130">Add priority accounts from Active users page</span></span>

<span data-ttu-id="b3404-131">Fügen Sie auf der Seite Aktive Benutzer Prioritätskonten hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3404-131">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="b3404-132">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="b3404-132">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b3404-133">Wechseln Sie **zu Benutzer**  >  **Aktive Benutzer,** und wählen Sie **oben** auf der Seite ... aus.</span><span class="sxs-lookup"><span data-stu-id="b3404-133">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="b3404-134">Wählen **Sie Verwalten von Prioritätskonten aus.**</span><span class="sxs-lookup"><span data-stu-id="b3404-134">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="b3404-135">Wählen **Sie Konten** hinzufügen  aus, und geben Sie auf der Seite Prioritätskonten hinzufügen im Suchfeld den Namen der Person ein, die Sie der Liste prioritätskonten hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="b3404-135">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="b3404-136">Wählen Sie den Benutzer aus, und wählen Sie **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="b3404-136">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="b3404-137">Entfernen eines Benutzers aus der Liste der Prioritätskonten</span><span class="sxs-lookup"><span data-stu-id="b3404-137">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="b3404-138">Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="b3404-138">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b3404-139">Wechseln Sie **zu**  >  **Setup-Organisationswissen,** und wählen **Sie Anzeigen** unter Überwachen Ihrer wichtigsten **Konten aus.**</span><span class="sxs-lookup"><span data-stu-id="b3404-139">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="b3404-140">Wählen Sie **auf der Seite** Ihre meisten Konten überwachen die Option **Prioritätskonten** unter **Verwalten dieses Features aus.**</span><span class="sxs-lookup"><span data-stu-id="b3404-140">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="b3404-141">Wählen Sie **auf der** Seite Prioritätskonten den Benutzer aus, den Sie aus der Liste entfernen möchten, und wählen Sie Konten **entfernen aus.**</span><span class="sxs-lookup"><span data-stu-id="b3404-141">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b3404-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b3404-142">Related topics</span></span>

[<span data-ttu-id="b3404-143">Verwenden von Prioritätskonten in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3404-143">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)