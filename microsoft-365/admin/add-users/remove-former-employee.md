---
title: Entfernen eines ehemaligen Mitarbeiters – Übersicht
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Führen Sie die Schritte in dieser Lösung aus, um einen ehemaligen Mitarbeiter aus Microsoft 365 zu entfernen und die Daten Ihrer Organisation zu schützen.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241736"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="96975-103">Übersicht: Entfernen eines ehemaligen Mitarbeiters und Sichern von Daten</span><span class="sxs-lookup"><span data-stu-id="96975-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="96975-104">Eine Häufig gestellte Frage lautet: "Was soll ich tun, um Daten zu schützen und den Zugriff zu schützen, wenn ein Mitarbeiter meine Organisation verlässt?"</span><span class="sxs-lookup"><span data-stu-id="96975-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="96975-105">In dieser Artikelreihe wird erläutert, wie Sie den Zugriff auf Microsoft 365 blockieren, welche Schritte Sie zum Sichern Ihrer Daten ausführen sollten, und wie anderen Mitarbeitern der Zugriff auf die Daten ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="96975-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

<span data-ttu-id="96975-106">Sehen Sie sich ein kurzes Video zum Entfernen eines Mitarbeiters an.</span><span class="sxs-lookup"><span data-stu-id="96975-106">Watch a short video about removing an employee.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

<span data-ttu-id="96975-107">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../../business-video/index.yml) an.</span><span class="sxs-lookup"><span data-stu-id="96975-107">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

<span data-ttu-id="96975-108">So verhindern Sie, dass sich ein Mitarbeiter anmelden kann:</span><span class="sxs-lookup"><span data-stu-id="96975-108">To prevent an employee from logging in:</span></span>

1. <span data-ttu-id="96975-109">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="96975-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="96975-110">Wählen Sie das Feld neben dem Namen des Benutzers aus, und wählen Sie dann **Kennwort zurücksetzen aus.**</span><span class="sxs-lookup"><span data-stu-id="96975-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="96975-111">Geben Sie ein neues Kennwort ein, und wählen Sie dann **Zurücksetzen aus.**</span><span class="sxs-lookup"><span data-stu-id="96975-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="96975-112">(Senden Sie es nicht an sie.)</span><span class="sxs-lookup"><span data-stu-id="96975-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="96975-113">Wählen Sie den Namen des Benutzers aus, um  zum Eigenschaftenbereich zu wechseln, und wählen Sie auf der Registerkarte Konto die Option **Abmelden initiieren aus.**</span><span class="sxs-lookup"><span data-stu-id="96975-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

> [!NOTE]
> <span data-ttu-id="96975-114">Sie müssen ein globaler Administrator sein, um das Abmelden zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="96975-114">You need to be a global administrator to initiate sign-out.</span></span>

<span data-ttu-id="96975-115">Innerhalb einer Stunde – oder nachdem sie die aktuelle Seite Microsoft 365 verlassen, auf der sie sich befinden – werden sie aufgefordert, sich erneut zu melden.</span><span class="sxs-lookup"><span data-stu-id="96975-115">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="96975-116">Ein Zugriffstoken ist für eine Stunde gut, daher hängt die Zeitachse davon ab, wie viel Zeit auf diesem Token noch bleibt und ob sie aus ihrer aktuellen Webseite navigieren.</span><span class="sxs-lookup"><span data-stu-id="96975-116">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96975-117">Obwohl wir die Schritte in dieser Lösung nummeriert haben und Sie die Lösung nicht in der genauen Reihenfolge abschließen müssen, wird empfohlen, die Schritte auf diese Weise zu tun.</span><span class="sxs-lookup"><span data-stu-id="96975-117">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="96975-118">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="96975-118">Before you begin</span></span>

<span data-ttu-id="96975-119">Sie müssen ein globaler Administrator sein, um die Schritte in dieser Lösung ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="96975-119">You need to be a global administrator to complete the steps in this solution.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="96975-120">**Schritt**</span><span class="sxs-lookup"><span data-stu-id="96975-120">**Step**</span></span> <br/> |<span data-ttu-id="96975-121">**Zweck**</span><span class="sxs-lookup"><span data-stu-id="96975-121">**Why do this**</span></span> <br/> |
|[<span data-ttu-id="96975-122">Schritt 1 – Verhindern, dass sich ein ehemaliger Mitarbeiter an einem Dienst anmelden und den Zugriff auf Microsoft 365 blockieren</span><span class="sxs-lookup"><span data-stu-id="96975-122">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md) <br/> |<span data-ttu-id="96975-123">Dadurch wird verhindert, dass sich Ihr ehemaliger Mitarbeiter bei Microsoft 365 anmelden und verhindert, dass die Person auf Microsoft 365 zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="96975-123">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span> <br/> |
|[<span data-ttu-id="96975-124">Schritt 2 : Speichern des Inhalts des Postfachs eines ehemaligen Mitarbeiters</span><span class="sxs-lookup"><span data-stu-id="96975-124">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md) <br/> |<span data-ttu-id="96975-125">Dies ist nützlich für die Person, die die Arbeit des Mitarbeiters übernimmt, oder wenn ein Rechtsstreit besteht.</span><span class="sxs-lookup"><span data-stu-id="96975-125">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span> <br/> |
|[<span data-ttu-id="96975-126">Schritt 3 : Weiterleiten der E-Mail eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter oder Konvertieren in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="96975-126">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md) <br/> |<span data-ttu-id="96975-p104">Damit sorgen Sie dafür, dass die E-Mail-Adresse des ehemaligen Mitarbeiters aktiv bleibt. Wenn Kunden oder Partner E-Mails weiterhin an diese Adresse senden, werden sie hierdurch an die Person geleitet, die dessen Arbeit übernimmt.</span><span class="sxs-lookup"><span data-stu-id="96975-p104">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span> <br/> |
|[<span data-ttu-id="96975-129">Schritt 4: Geben Sie einem anderen Mitarbeiter Zugriff auf OneDrive und Outlook Daten</span><span class="sxs-lookup"><span data-stu-id="96975-129">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-6.md) <br/> |<span data-ttu-id="96975-130">Wenn Sie nur die Lizenz eines Benutzers entfernen, aber das Konto nicht löschen, können Sie auch nach mehr als 30 Tagen auf den OneDrive-Inhalt des Benutzers zugreifen.</span><span class="sxs-lookup"><span data-stu-id="96975-130">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <br/><br/> <span data-ttu-id="96975-131">Bevor Sie das Konto löschen, sollten Sie einem anderen Benutzer OneDrive und Outlook zugriffen.</span><span class="sxs-lookup"><span data-stu-id="96975-131">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="96975-132">Nachdem Sie das Konto eines Mitarbeiters gelöscht haben, werden die Inhalte in OneDrive und Outlook **30 Tage aufbewahrt.**</span><span class="sxs-lookup"><span data-stu-id="96975-132">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="96975-133">Während dieser 30 Tage können Sie jedoch das Konto des Benutzers wiederherstellen und Zugriff auf deren Inhalte erhalten.</span><span class="sxs-lookup"><span data-stu-id="96975-133">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="96975-134">Wenn Sie das Konto des Benutzers wiederherstellen, bleiben OneDrive und Outlook auch nach 30 Tagen für Sie zugänglich.</span><span class="sxs-lookup"><span data-stu-id="96975-134">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span> <br/> |
|[<span data-ttu-id="96975-135">Schritt 5: Löschen und Blockieren des mobilen Geräts eines ehemaligen Mitarbeiters</span><span class="sxs-lookup"><span data-stu-id="96975-135">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-4.md) <br/> |<span data-ttu-id="96975-136">Entfernt die Geschäftsdaten vom Smartphone oder Tablet.</span><span class="sxs-lookup"><span data-stu-id="96975-136">Removes your business data from the phone or tablet.</span></span>  <br/> |
|[<span data-ttu-id="96975-137">Schritt 6 – Entfernen und Löschen Microsoft 365 Lizenz eines ehemaligen Mitarbeiters</span><span class="sxs-lookup"><span data-stu-id="96975-137">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="96975-p106">Wenn Sie eine Lizenz entfernen, können Sie sie einem anderen Benutzer zuweisen. Sie können die Lizenz auch löschen, damit Sie erst dann wieder dafür bezahlen, wenn Sie eine andere Person einstellen.  </span><span class="sxs-lookup"><span data-stu-id="96975-p106">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><br/><br/> <span data-ttu-id="96975-p107">Wenn Sie eine Lizenz entfernen oder löschen, werden die alten E-Mails, Kontakte und Kalender des Benutzers für **30 Tage** gespeichert und anschließend dauerhaft gelöscht. Wenn Sie eine Lizenz entfernen oder löschen, aber das Konto nicht löschen, können Sie auch nach mehr als 30 Tagen auf den OneDrive-Inhalt des Benutzers zugreifen.  </span><span class="sxs-lookup"><span data-stu-id="96975-p107">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  </span></span><br/> |
|[<span data-ttu-id="96975-142">Schritt 7 : Löschen des Benutzerkontos eines ehemaligen Mitarbeiters</span><span class="sxs-lookup"><span data-stu-id="96975-142">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="96975-143">Dadurch wird das Konto aus Ihrem Admin Center entfernt.</span><span class="sxs-lookup"><span data-stu-id="96975-143">This removes the account from your admin center.</span></span> <span data-ttu-id="96975-144">So behalten Sie die Übersicht.</span><span class="sxs-lookup"><span data-stu-id="96975-144">Keeps things clean.</span></span> <br/> |

## <a name="related-articles"></a><span data-ttu-id="96975-145">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="96975-145">Related articles</span></span>

[<span data-ttu-id="96975-146">Wiederherstellen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="96975-146">Restore a user</span></span>](restore-user.md)
