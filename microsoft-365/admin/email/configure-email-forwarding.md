---
title: Konfigurieren der E-Mail-Weiterleitung
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Richten Sie die E-Mail-Weiterleitung für ein oder mehrere E-Mail-Konten ein, die Office 365 verwenden.
ms.openlocfilehash: b5612a915fce21e9e9865fca6cb2275d8af17bd2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242408"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="ab78d-103">Konfigurieren der E-Mail-Weiterleitung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab78d-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="ab78d-104">Als Administrator einer Organisation haben Sie möglicherweise Unternehmensanforderungen, was die Einrichtung der E-Mail-Weiterleitung für das Postfach eines Benutzers betrifft.</span><span class="sxs-lookup"><span data-stu-id="ab78d-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="ab78d-105">Mit einer E-Mail-Weiterleitung können Sie E-Mails, die an das Postfach eines Benutzers gesendet wurden, an das Postfach eines anderen Benutzers innerhalb oder außerhalb Ihrer Organisation weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="ab78d-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab78d-106">Sie können ausgehende Spamfilter-Richtlinien verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern.</span><span class="sxs-lookup"><span data-stu-id="ab78d-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="ab78d-107">Weitere Informationen finden Sie unter [Steuerung der automatischen externen E-Mail-Weiterleitung in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="ab78d-107">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="ab78d-108">Konfigurieren der E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="ab78d-108">Configure email forwarding</span></span>

<span data-ttu-id="ab78d-109">Bedenken Sie vor dem Einrichten der E-Mail-Weiterleitung Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ab78d-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="ab78d-110">Nach dem Einrichten der E-Mail-Weiterleitung werden nur **neue** E-Mails weitergeleitet, die an das *„Von“*-Postfach gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="ab78d-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="ab78d-111">Für die E-Mail-Weiterleitung muss das *„Von“*-Konto über eine Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="ab78d-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="ab78d-112">Wenn ein Benutzer Ihre Organisation verlassen hat, ist [das Umwandeln seines Postfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) eine alternative Option zum Einrichten der E-Mail-Weiterleitung.</span><span class="sxs-lookup"><span data-stu-id="ab78d-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="ab78d-113">Auf diese Art und Weise können mehrere Personen darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ab78d-113">This way several people can access it.</span></span> <span data-ttu-id="ab78d-114">Ein freigegebenes Postfach kann jedoch 50 GB nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="ab78d-114">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="ab78d-115">Um dies durchzuführen, müssen Sie ein Exchange-Administrator oder ein globaler Administrator in Microsoft 365 sein.</span><span class="sxs-lookup"><span data-stu-id="ab78d-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="ab78d-116">Weitere Informationen finden Sie im Thema [Info zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ab78d-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="ab78d-117">Wechseln Sie im Admin Center zur Seite **Benutzer** \> **[Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=834822)**.</span><span class="sxs-lookup"><span data-stu-id="ab78d-117">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="ab78d-118">Wählen Sie zum Öffnen der Eigenschaften-Seite den Namen des Benutzers aus, dessen E-Mails Sie weiterleiten wollen.</span><span class="sxs-lookup"><span data-stu-id="ab78d-118">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="ab78d-119">Wählen Sie auf der Registerkarte **E-Mail** die Option **E-Mail-Weiterleitung verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="ab78d-119">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="ab78d-120">Wählen Sie auf der Seite zum Weiterleiten von E-Mails die Option **Alle an dieses Postfach gesendeten E-Mails weiterleiten** aus, geben Sie die Weiterleitungsadresse ein, und wählen Sie, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="ab78d-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="ab78d-121">Wenn Sie diese Option nicht sehen, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ab78d-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="ab78d-122">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="ab78d-122">Select **Save changes**.</span></span>

    <span data-ttu-id="ab78d-123">**Um an mehrere E-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Outlook-Regel zum Weiterleiten an diese Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ab78d-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="ab78d-124">Weiter Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="ab78d-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="ab78d-125">Alternativ können Sie im Admin Center [eine Verteilergruppe erstellen](../setup/create-distribution-lists.md), [die Adressen hinzufügen](add-user-or-contact-to-distribution-list.md), und dann die Weiterleitung an die Verteilergruppe einrichten, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab78d-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="ab78d-126">Löschen Sie nicht das Konto des Benutzers, dessen E-Mail Sie weiterleiten, und löschen Sie auch nicht dessen Lizenz!</span><span class="sxs-lookup"><span data-stu-id="ab78d-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="ab78d-127">Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.</span><span class="sxs-lookup"><span data-stu-id="ab78d-127">If you do, email forwarding will stop.</span></span>