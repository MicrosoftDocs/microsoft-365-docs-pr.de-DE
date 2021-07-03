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
ms.openlocfilehash: 86e01e591823c94d8279f975ed7de24cc65776dc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286141"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="c6111-103">Verwalten und Überwachen von Prioritätskonten</span><span class="sxs-lookup"><span data-stu-id="c6111-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="c6111-104">In jeder Microsoft 365 Organisation gibt es Personen, die wichtig sind, z. B. Führungskräfte, Führungskräfte, Manager oder andere Benutzer, die Zugriff auf vertrauliche, proprietäre oder Informationen mit hoher Priorität haben.</span><span class="sxs-lookup"><span data-stu-id="c6111-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="c6111-105">Um Ihre Organisation beim Schutz dieser Konten zu unterstützen, können Sie jetzt bestimmte Benutzer als Prioritätskonten festlegen und app-spezifische Features nutzen, die ihnen zusätzlichen Schutz bieten.</span><span class="sxs-lookup"><span data-stu-id="c6111-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="c6111-106">In Zukunft werden weitere Apps und Features Prioritätskonten unterstützen. Zunächst haben wir zwei Funktionen angekündigt: **den Schutz von Prioritätskonten** und die Überwachung des **Premium-E-Mail-Flusses.**</span><span class="sxs-lookup"><span data-stu-id="c6111-106">In the future, more apps and features will support priority accounts, and to start with, we've announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="c6111-107">**Prioritätskontoschutz** – Microsoft Defender für Office 365 (früher Office 365 Advanced Threat Protection) unterstützt Prioritätskonten als Tags, die in Filtern in Warnungen, Berichten und Untersuchungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c6111-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="c6111-108">Weitere Informationen finden Sie [unter "Benutzertags" in Microsoft Defender für Office 365.](../../security/office-365-security/user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="c6111-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>

  <span data-ttu-id="c6111-109">Eine natürliche Frage lautet: "Haben nicht alle Benutzer Priorität?</span><span class="sxs-lookup"><span data-stu-id="c6111-109">A natural question is, "Aren't all users a priority?</span></span> <span data-ttu-id="c6111-110">Warum nicht alle Benutzer als Prioritätskonten festlegen?"</span><span class="sxs-lookup"><span data-stu-id="c6111-110">Why not designate all users as priority accounts?"</span></span> <span data-ttu-id="c6111-111">Ja, alle Benutzer haben Priorität, aber der Prioritätskontoschutz bietet die folgenden zusätzlichen Vorteile:</span><span class="sxs-lookup"><span data-stu-id="c6111-111">Yes, all users are a priority, but priority account protection offers the following additional benefits:</span></span>

  - <span data-ttu-id="c6111-112">**Zusätzliche Heuristiken:** Unsere Analyse des Nachrichtenflusses in den Microsoft-Rechenzentren weist darauf hin, dass sich die Nachrichtenflussmuster für Führungskräfte in Unternehmen von den durchschnittlichen Mitarbeitern unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c6111-112">**Additional heuristics**: Our analysis of mail flow in the Microsoft datacenters indicates that mail flow patterns for company executives are different than the average employee.</span></span> <span data-ttu-id="c6111-113">Der Schutz vor Prioritätskonten bietet zusätzliche Heuristiken, die speziell auf Führungskräfte des Unternehmens zugeschnitten sind, die keinem regulären Mitarbeiter vorteilen.</span><span class="sxs-lookup"><span data-stu-id="c6111-113">Priority account protection offers additional heuristics that are specifically tailored to company executives that wouldn't benefit a regular employee.</span></span>
  - <span data-ttu-id="c6111-114">**Zusätzliche Sichtbarkeit in der Berichterstellung:** Tatsächlich sind Informationen für alle Benutzer (oder alle betroffenen Benutzer) bereits in Warnungen, Berichten und Untersuchungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c6111-114">**Additional visibility in reporting**: In effect, information for all users (or all affected users) is already available in alerts, reports, and investigations.</span></span> <span data-ttu-id="c6111-115">Mit dem Tag "Prioritätskonten" als Filter können Sie ihre Untersuchungen gezielt ausrichten.</span><span class="sxs-lookup"><span data-stu-id="c6111-115">The priority accounts tag as a filter allows you to specifically target your investigations.</span></span>

- <span data-ttu-id="c6111-116">**Premium E-Mail-Flow-Überwachung** : Ein fehlerfreier Nachrichtenfluss kann für den Geschäftserfolg von entscheidender Bedeutung sein, und Übermittlungsverzögerungen oder -fehler können sich negativ auf das Unternehmen auswirken.</span><span class="sxs-lookup"><span data-stu-id="c6111-116">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="c6111-117">Sie können einen Schwellenwert für fehlgeschlagene oder verzögerte E-Mails auswählen, Benachrichtigungen empfangen, wenn dieser Schwellenwert überschritten wird, und einen Bericht über E-Mail-Probleme für Prioritätskonten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6111-117">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="c6111-118">Weitere Informationen finden Sie [im Bericht "E-Mail-Probleme bei Prioritätskonten" im modernen EAC.](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="c6111-118">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="c6111-119">Bewährte Methoden für die Sicherheit von Prioritätskonten finden Sie unter ["Sicherheitsempfehlungen für Prioritätskonten".](../../security/office-365-security/security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="c6111-119">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c6111-120">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="c6111-120">Before you begin</span></span>

<span data-ttu-id="c6111-121">Das in diesem Thema beschriebene Feature zum Schutz von **Prioritätskonten** ist nur für Organisationen verfügbar, die die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="c6111-121">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="c6111-122">Microsoft Defender für Office 365 Plan 2, einschließlich derjenigen mit Office 365 E3, Office 365 E5, Microsoft 365 E5 oder Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="c6111-122">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="c6111-123">Das in diesem Thema beschriebene Feature Premium Überwachung von **E-Mail-Flow** ist nur für Organisationen verfügbar, die die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="c6111-123">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="c6111-124">Ihre Organisation muss über eine Lizenzanzahl von mindestens 5.000 aus einem der folgenden Produkte oder einer Kombination der folgenden Produkte verfügen: Office 365 E3, Microsoft 365 E3, Office 365 E5 Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c6111-124">Your organization needs to have a license count of at least 5,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="c6111-125">So kann Ihre Organisation beispielsweise über 3000 Office 365 E3-Lizenzen und 2500 Microsoft 365 E5-Lizenzen verfügen, die insgesamt 5500 Lizenzen für berechtigende Produkte ergeben.</span><span class="sxs-lookup"><span data-stu-id="c6111-125">For example, your organization can have 3,000 Office 365 E3 licenses and 2,500 Microsoft 365 E5, for a total of 5,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="c6111-126">Ihre Organisation muss über mindestens 50 monatlich aktive Exchange Online-Benutzer verfügen.</span><span class="sxs-lookup"><span data-stu-id="c6111-126">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="c6111-127">Sie können bis zu 250 Prioritätskonten überwachen.</span><span class="sxs-lookup"><span data-stu-id="c6111-127">You can monitor up to 250 priority accounts.</span></span>

<span data-ttu-id="c6111-128">Wenn Sie den Prioritätskontoschutz auf ein Postfach anwenden, sollten Sie den Prioritätskontoschutz auch auf Benutzer anwenden, die Zugriff auf das Postfach haben (z. B. der CEO und der Assistent des CEO, der den Kalender des CEO verwaltet).</span><span class="sxs-lookup"><span data-stu-id="c6111-128">When you apply priority account protection to a mailbox, you should also apply priority account protection to users who have access to the mailbox (for example, the CEO and the CEO's executive assistant who manages the CEO's calendar).</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="c6111-129">Hinzufügen von Prioritätskonten von der Setupseite</span><span class="sxs-lookup"><span data-stu-id="c6111-129">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="c6111-130">Hinzufügen von Prioritätskonten von der **Setupseite.**</span><span class="sxs-lookup"><span data-stu-id="c6111-130">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="c6111-131">Wechseln Sie zu der Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="c6111-131">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c6111-132">Wechseln Sie zu   >  **"Organisationswissen** einrichten", und wählen Sie **"Anzeigen"** unter **"Ihre wichtigsten Konten überwachen"** aus.</span><span class="sxs-lookup"><span data-stu-id="c6111-132">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="c6111-133">Wählen Sie **Erste Schritte** oder **verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="c6111-133">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="c6111-134">Geben Sie auf der Seite **"Prioritätskonten hinzufügen"** im Suchfeld den Namen oder die E-Mail-Adresse der Person ein, die Sie der Liste der Prioritätskonten hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="c6111-134">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="c6111-135">Sie können auch Ihren E-Mail-Schwellenwert für fehlgeschlagene oder verzögerte E-Mails festlegen und einen wöchentlichen Bericht über Probleme für Prioritätskonten erhalten.</span><span class="sxs-lookup"><span data-stu-id="c6111-135">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="c6111-136">Wählen Sie den Benutzer aus, und wählen Sie **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="c6111-136">Select the user and choose **Save**.</span></span>

<span data-ttu-id="c6111-137">Sie können auch Prioritätskonten auf der Seite "Aktive Benutzer" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c6111-137">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="c6111-138">Hinzufügen von Prioritätskonten von der Seite "Aktive Benutzer"</span><span class="sxs-lookup"><span data-stu-id="c6111-138">Add priority accounts from Active users page</span></span>

<span data-ttu-id="c6111-139">Hinzufügen von Prioritätskonten auf der Seite "Aktive Benutzer".</span><span class="sxs-lookup"><span data-stu-id="c6111-139">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="c6111-140">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="c6111-140">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c6111-141">Wechseln Sie zu   >  **"Aktive Benutzer",** und wählen Sie die drei Punkte (weitere Aktionen) oben auf der Seite aus.</span><span class="sxs-lookup"><span data-stu-id="c6111-141">Go to **Users** > **Active users** and select the three dots (more actions) at the top of the page.</span></span> <span data-ttu-id="c6111-142">Wählen Sie **"Prioritätskonten verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="c6111-142">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="c6111-143">Wählen Sie **"Konten hinzufügen"** aus, und geben Sie auf der Seite **"Prioritätskonten hinzufügen"** im Suchfeld den Namen der Person ein, die Sie der Liste der Prioritätskonten hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="c6111-143">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="c6111-144">Wählen Sie den Benutzer aus, und wählen Sie **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="c6111-144">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="c6111-145">Entfernen eines Benutzers aus der Liste der Prioritätskonten</span><span class="sxs-lookup"><span data-stu-id="c6111-145">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="c6111-146">Wechseln Sie zu der Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="c6111-146">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c6111-147">Wechseln Sie zu   >  **"Organisationswissen** einrichten", und wählen Sie **"Anzeigen"** unter **"Ihre wichtigsten Konten überwachen"** aus.</span><span class="sxs-lookup"><span data-stu-id="c6111-147">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="c6111-148">Wählen Sie auf der Seite **"Ihre meisten Konten überwachen"** unter **"Dieses Feature verwalten"** die Option **"Prioritätskonten"** aus.</span><span class="sxs-lookup"><span data-stu-id="c6111-148">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="c6111-149">Wählen Sie auf der Seite **"Prioritätskonten"** den Benutzer aus, den Sie aus der Liste entfernen möchten, und wählen Sie **"Konten entfernen"** aus.</span><span class="sxs-lookup"><span data-stu-id="c6111-149">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c6111-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c6111-150">Related topics</span></span>

[<span data-ttu-id="c6111-151">Verwenden von Prioritätskonten in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c6111-151">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
