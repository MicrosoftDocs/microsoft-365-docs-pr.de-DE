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
description: Überwachen Sie fehlgeschlagene und verzögerte E-Mail-Nachrichten, die an oder von Konten gesendet werden, die hohe geschäftliche Auswirkungen haben.
ms.openlocfilehash: dbdd692a41d341564376960788054e70623daf5a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233362"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="a746c-103">Verwalten und Überwachen von Prioritätskonten</span><span class="sxs-lookup"><span data-stu-id="a746c-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="a746c-104">In jeder Microsoft 365-Organisation gibt es Personen, die wichtig sind, z. B. Führungskräfte, Führungskräfte, Manager oder andere Benutzer, die Zugriff auf vertrauliche, proprietäre oder wichtige Informationen haben.</span><span class="sxs-lookup"><span data-stu-id="a746c-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="a746c-105">Um Ihrer Organisation beim Schutz dieser Konten zu helfen, können Sie jetzt bestimmte Benutzer als Prioritätskonten festlegen und app-spezifische Features nutzen, die ihnen zusätzlichen Schutz bieten.</span><span class="sxs-lookup"><span data-stu-id="a746c-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="a746c-106">In Zukunft werden mehr Apps und Features Prioritätskonten unterstützen, und zu Beginn haben wir zwei Funktionen **angekündigt:** Den Schutz von Konten mit Priorität und die **Premium-Nachrichtenfluss-Überwachung.**</span><span class="sxs-lookup"><span data-stu-id="a746c-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="a746c-107">**Prioritätskontoschutz** – Microsoft Defender für Office 365 (früher Office 365 Advanced Threat Protection) unterstützt Prioritätskonten als Tags, die in Filtern in Warnungen, Berichten und Untersuchungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a746c-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="a746c-108">Weitere Informationen finden Sie unter ["Benutzertags" in Microsoft Defender für Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags)</span><span class="sxs-lookup"><span data-stu-id="a746c-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags).</span></span>
- <span data-ttu-id="a746c-109">**Premium-Nachrichtenfluss-Überwachung** : Ein fehlerfreier Nachrichtenfluss kann für den Geschäftserfolg entscheidend sein, und Verzögerungen oder Fehler bei der Zustellung können sich negativ auf das Unternehmen auswirken.</span><span class="sxs-lookup"><span data-stu-id="a746c-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="a746c-110">Sie können einen Schwellenwert für fehlgeschlagene oder verzögerte E-Mails auswählen, Benachrichtigungen erhalten, wenn dieser Schwellenwert überschritten wird, und einen Bericht über E-Mail-Probleme für Prioritätskonten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a746c-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="a746c-111">Weitere Informationen finden Sie im Bericht ["E-Mail-Probleme bei Prioritätskonten" in der modernen EAC.](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="a746c-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="a746c-112">Bewährte Sicherheitsmethoden für Prioritätskonten finden Sie unter [Sicherheitsempfehlungen für Prioritätskonten.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts)</span><span class="sxs-lookup"><span data-stu-id="a746c-112">For security best practices for priority accounts, see [Security recommendations for priority accounts](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a746c-113">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="a746c-113">Before you begin</span></span>

<span data-ttu-id="a746c-114">Das **in diesem** Thema beschriebene Feature zum Schutz des Prioritätskontos ist nur für Organisationen verfügbar, die die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="a746c-114">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="a746c-115">Microsoft Defender für Office 365 Plan 2, einschließlich derer mit Office 365 E3, Office 365 E5, Microsoft 365 E5 oder Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="a746c-115">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="a746c-116">Das **in diesem** Thema beschriebene Premium-Nachrichtenfluss-Überwachungsfeature ist nur für Organisationen verfügbar, die die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="a746c-116">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="a746c-117">Ihre Organisation muss mindestens 10.000 Lizenzen aus einem der folgenden Produkte oder eine Kombination der folgenden Produkte haben: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a746c-117">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="a746c-118">Beispielsweise kann Ihre Organisation über 3000 Office 365 E3-Lizenzen und 8500 Microsoft 365 E5 für insgesamt 11.500 Lizenzen aus den qualifizierenden Produkten verfügen.</span><span class="sxs-lookup"><span data-stu-id="a746c-118">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="a746c-119">Ihre Organisation muss über mindestens 50 monatlich aktive Exchange Online-Benutzer verfügen.</span><span class="sxs-lookup"><span data-stu-id="a746c-119">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="a746c-120">Sie können bis zu 250 Prioritätskonten überwachen.</span><span class="sxs-lookup"><span data-stu-id="a746c-120">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="a746c-121">Hinzufügen von Prioritätskonten von der Seite "Setup"</span><span class="sxs-lookup"><span data-stu-id="a746c-121">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="a746c-122">Hinzufügen von Prioritätskonten von der **Setupseite**.</span><span class="sxs-lookup"><span data-stu-id="a746c-122">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="a746c-123">Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="a746c-123">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a746c-124">Wechseln Sie zu **"Organisationswissen**  >  **einrichten",** und wählen **Sie "Ansicht"** unter **"Überwachen Ihrer wichtigsten Konten" aus.**</span><span class="sxs-lookup"><span data-stu-id="a746c-124">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="a746c-125">Wählen **Sie "Erste Schritte"** oder **"Verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="a746c-125">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="a746c-126">Geben Sie auf der Seite **"Prioritätskonten** hinzufügen" im Suchfeld den Namen oder die E-Mail-Adresse der Person ein, die Sie der Liste der Prioritätskonten hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="a746c-126">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="a746c-127">Sie können auch Ihren E-Mail-Schwellenwert für fehlgeschlagene oder verzögerte E-Mails festlegen und einen wöchentlichen Bericht über Probleme für Prioritätskonten erhalten.</span><span class="sxs-lookup"><span data-stu-id="a746c-127">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="a746c-128">Wählen Sie den Benutzer aus, und wählen Sie **"Speichern" aus.**</span><span class="sxs-lookup"><span data-stu-id="a746c-128">Select the user and choose **Save**.</span></span>

<span data-ttu-id="a746c-129">Sie können auch Prioritätskonten auf der Seite "Aktive Benutzer" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a746c-129">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="a746c-130">Hinzufügen von Prioritätskonten von der Seite "Aktive Benutzer"</span><span class="sxs-lookup"><span data-stu-id="a746c-130">Add priority accounts from Active users page</span></span>

<span data-ttu-id="a746c-131">Fügen Sie Prioritätskonten von der Seite "Aktive Benutzer" hinzu.</span><span class="sxs-lookup"><span data-stu-id="a746c-131">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="a746c-132">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="a746c-132">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a746c-133">Wechseln Sie **zu**  >  **"Aktive Benutzer",** und wählen Sie **...** am oberen Rand der Seite aus.</span><span class="sxs-lookup"><span data-stu-id="a746c-133">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="a746c-134">Wählen **Sie "Prioritätskonten verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="a746c-134">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="a746c-135">Wählen **Sie "Konten hinzufügen"** aus, und geben Sie auf der Seite "Prioritätskonten hinzufügen" im Suchfeld den Namen der Person ein, die Sie der Liste der Prioritätskonten hinzufügen möchten. </span><span class="sxs-lookup"><span data-stu-id="a746c-135">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="a746c-136">Wählen Sie den Benutzer aus, und wählen Sie **"Speichern" aus.**</span><span class="sxs-lookup"><span data-stu-id="a746c-136">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="a746c-137">Entfernen eines Benutzers aus der Liste der Prioritätskonten</span><span class="sxs-lookup"><span data-stu-id="a746c-137">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="a746c-138">Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="a746c-138">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a746c-139">Wechseln Sie zu **"Organisationswissen**  >  **einrichten",** und wählen **Sie "Ansicht"** unter **"Überwachen Ihrer wichtigsten Konten" aus.**</span><span class="sxs-lookup"><span data-stu-id="a746c-139">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="a746c-140">On the **Monitor your most accounts** page, choose Priority **accounts** under Manage **this feature**.</span><span class="sxs-lookup"><span data-stu-id="a746c-140">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="a746c-141">Wählen Sie **auf der** Seite "Prioritätskonten" die Benutzer aus, die Sie aus der Liste entfernen möchten, und wählen Sie **"Konten entfernen" aus.**</span><span class="sxs-lookup"><span data-stu-id="a746c-141">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a746c-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a746c-142">Related topics</span></span>

[<span data-ttu-id="a746c-143">Verwenden von Prioritätskonten in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a746c-143">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)