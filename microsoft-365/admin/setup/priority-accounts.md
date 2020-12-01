---
title: Verwalten und Überwachen von Prioritäts Konten
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
description: Überwachen von fehlerhaften und verzögerten e-Mail-Nachrichten, die an oder von Konten mit hohem geschäftlichen Einfluss gesendet wurden.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477613"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="2d325-103">Verwalten und Überwachen von Prioritäts Konten</span><span class="sxs-lookup"><span data-stu-id="2d325-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="2d325-104">In jeder Microsoft 365-Organisation gibt es wichtige Personen wie Führungskräfte, Führungskräfte, Führungskräfte oder andere Benutzer, die Zugriff auf vertrauliche, proprietäre oder Informationen mit hoher Priorität haben.</span><span class="sxs-lookup"><span data-stu-id="2d325-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="2d325-105">Um Ihre Organisation beim Schutz dieser Konten zu unterstützen, können Sie nun bestimmte Benutzer als Prioritäts Konten festlegen und App-spezifische Features nutzen, die Ihnen zusätzlichen Schutz bieten.</span><span class="sxs-lookup"><span data-stu-id="2d325-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="2d325-106">In Zukunft unterstützen weitere apps und Features vorrangige Konten, und zunächst haben wir zwei Funktionen angekündigt: **Priority Account Protection** und **Premium-Nachrichtenfluss Überwachung**.</span><span class="sxs-lookup"><span data-stu-id="2d325-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="2d325-107">**Priority Account Protection** – Microsoft Defender für Office 365 (früher Office 365 Advanced Threat Protection) unterstützt Prioritäts Konten als Tags, die in Filtern in Warnungen, Berichten und Untersuchungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="2d325-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="2d325-108">Weitere Informationen finden Sie unter [Benutzer Tags in Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="2d325-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="2d325-109">**Premium-Nachrichtenfluss Überwachung** – ein einwandfreier Nachrichtenfluss kann für den geschäftlichen Erfolg von entscheidender Bedeutung sein, und Übermittlungsverzögerungen oder-Fehler können sich negativ auf das Unternehmen auswirken.</span><span class="sxs-lookup"><span data-stu-id="2d325-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="2d325-110">Sie können einen Schwellenwert für fehlerhafte oder verzögerte e-Mails auswählen, Warnungen empfangen, wenn dieser Schwellenwert überschritten wird, und einen Bericht über e-Mail-Probleme für Prioritäts Konten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d325-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="2d325-111">Weitere Informationen finden Sie [in der modernen Exchange-Verwaltungskonsole unter e-Mail Issues for Priority Accounts Report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span><span class="sxs-lookup"><span data-stu-id="2d325-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2d325-112">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="2d325-112">Before you begin</span></span>

<span data-ttu-id="2d325-113">Das in diesem Thema beschriebene Feature für den **Priority-Kontoschutz** steht nur Organisationen zur Verfügung, die die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="2d325-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="2d325-114">Microsoft Defender für Office 365 Plan 2, einschließlich der Office 365 E3, Office 365 E5, Microsoft 365 E5 oder Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="2d325-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="2d325-115">Das Feature für die **erstklassige Nachrichtenfluss Überwachung** , das in diesem Thema beschrieben wird, steht nur Organisationen zur Verfügung, die die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="2d325-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="2d325-116">Ihre Organisation muss eine Lizenzanzahl von mindestens 10.000, entweder aus einer oder aus einer Kombination der folgenden Produkte haben: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2d325-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="2d325-117">Beispielsweise kann Ihre Organisation 3000 Office 365 E3-Lizenzen und 8500 Microsoft 365 E5 für insgesamt 11.500 Lizenzen von den qualifizierten Produkten haben.</span><span class="sxs-lookup"><span data-stu-id="2d325-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="2d325-118">Ihre Organisation muss mindestens 50 monatliche aktive Exchange Online Benutzer haben.</span><span class="sxs-lookup"><span data-stu-id="2d325-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="2d325-119">Sie können bis zu 250-Prioritäts Konten überwachen.</span><span class="sxs-lookup"><span data-stu-id="2d325-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="2d325-120">Hinzufügen von Prioritäts Konten auf der Seite "Setup"</span><span class="sxs-lookup"><span data-stu-id="2d325-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="2d325-121">Fügen Sie auf der **Seite Setup** die Prioritäts Konten hinzu.</span><span class="sxs-lookup"><span data-stu-id="2d325-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="2d325-122">Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="2d325-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="2d325-123">Wechseln Sie zu **Setup**  >  **Organizational Knowledge**, und wählen Sie **Ansicht** unter **Überwachen Sie Ihre wichtigsten Konten**.</span><span class="sxs-lookup"><span data-stu-id="2d325-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="2d325-124">Wählen Sie **Erste Schritte** oder **Verwaltung** aus.</span><span class="sxs-lookup"><span data-stu-id="2d325-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="2d325-125">Geben Sie auf der Seite " **Prioritäts Konten hinzufügen** " im Suchfeld den Namen oder die e-Mail-Adresse der Person ein, die Sie der Liste Priority Accounts hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="2d325-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="2d325-126">Sie können auch Ihren e-Mail-Schwellenwert für fehlerhafte oder verzögerte e-Mails festlegen und einen wöchentlichen Bericht über Probleme für Prioritäts Konten erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d325-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="2d325-127">Wählen Sie den Benutzer aus, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2d325-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="2d325-128">Sie können auch Prioritäts Konten von der Seite aktive Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2d325-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="2d325-129">Seite "aktive Benutzer" Hinzufügen von Prioritäten Konten</span><span class="sxs-lookup"><span data-stu-id="2d325-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="2d325-130">Fügen Sie auf der Seite aktive Benutzer Prioritäts Konten hinzu.</span><span class="sxs-lookup"><span data-stu-id="2d325-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="2d325-131">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="2d325-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="2d325-132">Wechseln Sie zu **Benutzer**  >  **aktive Benutzer** , und wählen Sie oben auf der Seite. **..** aus.</span><span class="sxs-lookup"><span data-stu-id="2d325-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="2d325-133">Wählen Sie **Prioritäten Konten verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="2d325-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="2d325-134">Wählen Sie **Konten hinzufügen** aus, und geben Sie auf der Seite **Priority Accounts hinzufügen** im Suchfeld den Namen der Person ein, die Sie der Liste Priority Accounts hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="2d325-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="2d325-135">Wählen Sie den Benutzer aus, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2d325-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="2d325-136">Entfernen eines Benutzers aus der Liste "Priority Accounts"</span><span class="sxs-lookup"><span data-stu-id="2d325-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="2d325-137">Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="2d325-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="2d325-138">Wechseln Sie zu **Setup**  >  **Organizational Knowledge**, und wählen Sie **Ansicht** unter **Überwachen Sie Ihre wichtigsten Konten**.</span><span class="sxs-lookup"><span data-stu-id="2d325-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="2d325-139">Wählen Sie auf der Seite "die **meisten Konten überwachen** " unter **Diese Funktion verwalten** die Option **Priority Accounts** aus.</span><span class="sxs-lookup"><span data-stu-id="2d325-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="2d325-140">Wählen Sie auf der Seite **Priority Accounts** die Benutzer aus der Liste aus, die Sie entfernen möchten, und klicken Sie dann auf **Konten entfernen**.</span><span class="sxs-lookup"><span data-stu-id="2d325-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2d325-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2d325-141">Related topics</span></span>

[<span data-ttu-id="2d325-142">Verwenden von Prioritäts Konten in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d325-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)