---
title: Administratorüberprüfung für gemeldete Nachrichten
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie gemeldete Nachrichten überprüfen und Ihren Benutzern Feedback geben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 619cd35b6a60f0d50aa6c13e4cad2b8d7ae947a8
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730964"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="a65dc-103">Administratorüberprüfung für gemeldete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="a65dc-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="a65dc-104">Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das möglicherweise erheblich geändert wird, bevor es kommerziell veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="a65dc-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a65dc-105">Dieses Dokument wird nur zu Evaluierungs- und Explorationszwecken bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a65dc-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="a65dc-106">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="a65dc-106">**Applies to**</span></span>
- [<span data-ttu-id="a65dc-107">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="a65dc-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a65dc-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a65dc-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a65dc-109">In Microsoft 365 Organisationen mit Exchange Online Postfächern und Microsoft Defender für Office 365 können Administratoren nun vorlagenierte Nachrichten zurück an Endbenutzer senden, nachdem sie die gemeldeten Nachrichten überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="a65dc-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="a65dc-110">Dies kann für Ihre Organisation und auch basierend auf dem Urteil Ihres Admins angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="a65dc-110">This can be customized for your organization and based on your admin’s verdict as well.</span></span>

<span data-ttu-id="a65dc-111">Dieses Feature dient dazu, Ihren Benutzern Feedback zu geben, ändert jedoch nicht die Bewertungen von Nachrichten im System.</span><span class="sxs-lookup"><span data-stu-id="a65dc-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="a65dc-112">Um Microsoft dabei zu unterstützen, seine Filter zu aktualisieren und zu verbessern, müssen Sie Nachrichten mithilfe der Admin-Übermittlung zur [Analyse übermitteln.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a65dc-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="a65dc-113">Sie können Die Benutzer nur dann über Die Ergebnisse der Überprüfung markieren und benachrichtigen, wenn die Nachricht als falsch positive oder falsch negative Ergebnisse [gemeldet wurde.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="a65dc-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a65dc-114">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="a65dc-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a65dc-115">Zum Ändern der Konfiguration für Benutzerübermittlungen müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="a65dc-115">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
    - <span data-ttu-id="a65dc-116">Organisationsverwaltung oder Sicherheitsadministrator im [Security Center](permissions-microsoft-365-compliance-security.md).</span><span class="sxs-lookup"><span data-stu-id="a65dc-116">Organization Management or Security Administrator in the [Security center](permissions-microsoft-365-compliance-security.md).</span></span>
    - <span data-ttu-id="a65dc-117">Organisationsverwaltung in [Exchange Online](/Exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="a65dc-117">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo).</span></span>

- <span data-ttu-id="a65dc-118">Sie benötigen auch Zugriff auf die Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a65dc-118">You'll also need access to the Exchange Online PowerShell.</span></span> <span data-ttu-id="a65dc-119">Wenn das Konto, das Sie verwenden möchten, keinen Zugriff auf Exchange Online PowerShell hat, wird eine Fehlermeldung mit der Angabe einer E-Mail-Adresse in Ihrer Domäne *angezeigt.*</span><span class="sxs-lookup"><span data-stu-id="a65dc-119">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="a65dc-120">Weitere Informationen zum Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="a65dc-120">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
    - [<span data-ttu-id="a65dc-121">Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a65dc-121">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
    - [<span data-ttu-id="a65dc-122">Clientzugriffsregeln in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a65dc-122">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="a65dc-123">Konfigurieren der Nachrichten, die zum Benachrichtigen von Benutzern verwendet werden</span><span class="sxs-lookup"><span data-stu-id="a65dc-123">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="a65dc-124">Wechseln Sie [Microsoft 365 Security Center](../defender/overview-security-center.md)zu Richtlinien **&** Regeln \> **Bedrohungsrichtlinien** Vom Benutzer \> **gemeldete Nachrichteneinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="a65dc-124">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Policies & rules** \> **Threat policies** \> **User reported message settings**.</span></span>

2. <span data-ttu-id="a65dc-125">Wenn Sie den Anzeigenamen des Absenders angeben möchten, aktivieren Sie das Kontrollkästchen **Office 365** E-Mail-Adresse angeben, die als Absender verwendet werden soll, im Abschnitt **E-Mail-Benachrichtigungen** für Administratorüberprüfungsergebnisse, und geben Sie den Namen ein, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a65dc-125">If you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="a65dc-126">Dies ist die E-Mail-Adresse, die in Outlook angezeigt wird und an die Antworten gehen.</span><span class="sxs-lookup"><span data-stu-id="a65dc-126">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="a65dc-127">Wenn Sie eine der Vorlagen anpassen möchten, klicken Sie auf **E-Mail-Benachrichtigung anpassen.**</span><span class="sxs-lookup"><span data-stu-id="a65dc-127">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="a65dc-128">In diesem Flyout können Sie nur Folgendes anpassen:</span><span class="sxs-lookup"><span data-stu-id="a65dc-128">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="a65dc-129">Phishing</span><span class="sxs-lookup"><span data-stu-id="a65dc-129">Phishing</span></span>
    - <span data-ttu-id="a65dc-130">Junk-E-Mail</span><span class="sxs-lookup"><span data-stu-id="a65dc-130">Junk</span></span>
    - <span data-ttu-id="a65dc-131">Keine Bedrohungen gefunden</span><span class="sxs-lookup"><span data-stu-id="a65dc-131">No threats found</span></span>
    - <span data-ttu-id="a65dc-132">Sensibilisierungstraining</span><span class="sxs-lookup"><span data-stu-id="a65dc-132">Awareness training</span></span>
    - <span data-ttu-id="a65dc-133">Fußzeile</span><span class="sxs-lookup"><span data-stu-id="a65dc-133">Footer</span></span>

4. <span data-ttu-id="a65dc-134">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a65dc-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="a65dc-135">Klicken Sie auf der Seite Benutzerübermittlungen **auf Verwerfen,** um diese Werte zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a65dc-135">To clear these values, click **Discard** on the User submissions page.</span></span>
