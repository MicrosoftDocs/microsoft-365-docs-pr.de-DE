---
title: 'Schritt 3 : Weiterleiten der E-Mail eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter oder Konvertieren in ein freigegebenes Postfach'
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
description: Führen Sie die folgenden Schritte aus, um die E-Mails eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter weiter zu senden oder in ein freigegebenes Postfach zu konvertieren.
ms.openlocfilehash: 5ab66cf9d71a597a7f33c9a5e3a180738592faca
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244243"
---
# <a name="step-3---forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a><span data-ttu-id="18688-103">Schritt 3 : Weiterleiten der E-Mail eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter oder Konvertieren in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="18688-103">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>

<span data-ttu-id="18688-104">In diesem Schritt weisen Sie die E-Mail-Adresse des ehemaligen Mitarbeiters einem anderen Mitarbeiter zu oder konvertieren das Postfach des Benutzers in ein freigegebenes Postfach.</span><span class="sxs-lookup"><span data-stu-id="18688-104">In this step, you assign the former employee's email address to another employee, or convert the user's mailbox to a shared mailbox.</span></span>

## <a name="convert-former-employees-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="18688-105">Konvertieren des Postfachs eines ehemaligen Mitarbeiters in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="18688-105">Convert former employee's mailbox to a shared mailbox</span></span>

<span data-ttu-id="18688-106">Wenn Sie das Postfach eines Benutzers in ein freigegebenes Postfach konvertieren, werden alle vorhandenen E-Mails und Kalender beibehalten.</span><span class="sxs-lookup"><span data-stu-id="18688-106">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="18688-107">Sie befinden sich nun nur in einem freigegebenen Postfach, auf das mehrere Personen (nicht nur eine Person) zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="18688-107">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="18688-108">Sie können ein freigegebenes Postfach zu einem späteren Zeitpunkt wieder in ein (privates) Benutzerpostfach konvertieren.</span><span class="sxs-lookup"><span data-stu-id="18688-108">You can convert a shared mailbox back to a user (private) mailbox at a later date if you want.</span></span>

- <span data-ttu-id="18688-p102">Das Erstellen eines freigegebenen Postfachs ist die kostengünstigere Methode, weil Sie für keine Lizenz bezahlen müssen, **solange das Postfach kleiner als 50 GB ist**. Bei über 50 GB müssen Sie dem Postfach eine Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="18688-p102">Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it.</span></span>
- <span data-ttu-id="18688-p103">Wenn Sie das Postfach in ein freigegebenes Postfach konvertieren, stehen auch alle alten E-Mails zur Verfügung. Dadurch kann eine Menge an Speicherplatz belegt werden.</span><span class="sxs-lookup"><span data-stu-id="18688-p103">If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.</span></span>
- <span data-ttu-id="18688-113">Wenn Sie die E-Mail-Weiterleitung einrichten, werden nur neue E-Mails an den ehemaligen Mitarbeiter gesendet. </span><span class="sxs-lookup"><span data-stu-id="18688-113">If you set up email forwarding, only *new* emails sent to the former employee will now be sent to the current employee.</span></span>

<span data-ttu-id="18688-114">Führen Sie die folgenden Schritte aus, um das Postfach des Benutzers in ein [freigegebenes Postfach zu konvertieren.](../email/convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="18688-114">Follow these steps on how to [convert the user's mailbox to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md).</span></span>

## <a name="forward-a-former-employees-email-to-another-employee"></a><span data-ttu-id="18688-115">Weiterleiten der E-Mail eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="18688-115">Forward a former employee's email to another employee</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="18688-116">Wenn Sie die E-Mail-Weiterleitung oder ein freigegebenes Postfach einrichten, löschen Sie am Ende nicht das Konto des ehemaligen Mitarbeiters.</span><span class="sxs-lookup"><span data-stu-id="18688-116">If you're setting up email forwarding or a shared mailbox, at the end, don't delete the former employee's account.</span></span> <span data-ttu-id="18688-117">Es muss nämlich vorhanden sein, damit die E-Mail-Weiterleitung oder das freigegebene Postfach funktionieren.</span><span class="sxs-lookup"><span data-stu-id="18688-117">The account needs to be there to anchor the email forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="18688-118">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="18688-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="18688-119">Wählen Sie den Namen des Mitarbeiters aus, den Sie blockieren möchten, und wählen Sie dann die Registerkarte **E-Mail** aus.</span><span class="sxs-lookup"><span data-stu-id="18688-119">Select the name of the employee that you want to block, and then select the **Mail** tab.</span></span>
3. <span data-ttu-id="18688-120">Wählen **Sie unter E-Mail-Weiterleitung** die Option **E-Mail-Weiterleitung verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="18688-120">Under **Email Forwarding**, select **Manage email forwarding**.</span></span>
4. <span data-ttu-id="18688-121">Aktivieren Sie **Alle an dieses Postfach gesendeten E-Mails weiterleiten**.</span><span class="sxs-lookup"><span data-stu-id="18688-121">Turn on **Forward all email sent to this mailbox**.</span></span> <span data-ttu-id="18688-122">Geben Sie **im Feld** Weiterleitungsadresse die E-Mail-Adresse des aktuellen Mitarbeiters ein, der die E-Mail erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="18688-122">In the **Forwarding address** box, type the email address of the current employee who's going to get the email.</span></span>
5. <span data-ttu-id="18688-123">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="18688-123">Select **Save**.</span></span>
6. <span data-ttu-id="18688-124">Denken Sie daran, dass das Konto des ehemaligen Mitarbeiters nicht gelöscht werden sollte.</span><span class="sxs-lookup"><span data-stu-id="18688-124">Remember, don't delete the former employee's account.</span></span>
