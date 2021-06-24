---
title: Überprüfung gemeldeter Nachrichten durch den Administrator
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
ms.openlocfilehash: a9fa6c890f0fa6098a2bb712f79ab82fc1edb68b
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108559"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="eda8f-103">Überprüfung gemeldeter Nachrichten durch den Administrator</span><span class="sxs-lookup"><span data-stu-id="eda8f-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="eda8f-104">Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das vor der kommerziellen Veröffentlichung erheblich geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="eda8f-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="eda8f-105">Dieses Dokument dient nur zu Evaluierungs- und Untersuchungszwecken.</span><span class="sxs-lookup"><span data-stu-id="eda8f-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="eda8f-106">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="eda8f-106">**Applies to**</span></span>
- [<span data-ttu-id="eda8f-107">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="eda8f-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eda8f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eda8f-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="eda8f-109">In Microsoft 365 Organisationen mit Exchange Online Postfächern und Microsoft Defender für Office 365 können Administratoren nun Nachrichten mit Vorlagen an Endbenutzer senden, nachdem sie gemeldete Nachrichten überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="eda8f-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="eda8f-110">Dies kann für Ihre Organisation angepasst werden und basiert auch auf der Bewertung Ihres Administrators.</span><span class="sxs-lookup"><span data-stu-id="eda8f-110">This can be customized for your organization and based on your admin's verdict as well.</span></span>

<span data-ttu-id="eda8f-111">Dieses Feature ist darauf ausgelegt, Ihren Benutzern Feedback zu geben, ändert jedoch nicht die Bewertung von Nachrichten im System.</span><span class="sxs-lookup"><span data-stu-id="eda8f-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="eda8f-112">Um Microsoft bei der Aktualisierung und Verbesserung seiner Filter zu unterstützen, müssen Sie Nachrichten mithilfe der [Administratorübermittlung](admin-submission.md)zur Analyse übermitteln.</span><span class="sxs-lookup"><span data-stu-id="eda8f-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="eda8f-113">Sie können Benutzer nur dann markieren und über Rezensionsergebnisse informieren, wenn die Nachricht als [falsch positive oder falsch negative](report-false-positives-and-false-negatives.md)Ergebnisse gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="eda8f-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eda8f-114">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="eda8f-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eda8f-115">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="eda8f-115">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="eda8f-116">Um direkt zur Seite **"Übermittlungen"** zu wechseln, verwenden Sie <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="eda8f-116">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="eda8f-117">Um die Konfiguration für Benutzerübermittlungen zu ändern, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="eda8f-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="eda8f-118">Organisationsverwaltung oder Sicherheitsadministrator im [Microsoft 365 Defender Portal.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="eda8f-118">Organization Management or Security Administrator in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="eda8f-119">Organisationsverwaltung in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="eda8f-119">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="eda8f-120">Sie benötigen auch Zugriff auf Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eda8f-120">You'll also need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="eda8f-121">Wenn das Konto, das Sie verwenden möchten, keinen Zugriff auf Exchange Online PowerShell hat, erhalten Sie einen Fehler, der besagt, dass *eine E-Mail-Adresse in Ihrer Domäne angegeben* wird.</span><span class="sxs-lookup"><span data-stu-id="eda8f-121">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="eda8f-122">Weitere Informationen zum Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="eda8f-122">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="eda8f-123">Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="eda8f-123">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="eda8f-124">Clientzugriffsregeln in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="eda8f-124">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="eda8f-125">Konfigurieren der Nachrichten, die zum Benachrichtigen von Benutzern verwendet werden</span><span class="sxs-lookup"><span data-stu-id="eda8f-125">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="eda8f-126">Wechseln Sie im portal Microsoft 365 Defender zu **E-Mail-& Zusammenarbeitsrichtlinien** & Seite \>  \> **"Richtlinien für Bedrohungsregeln"** im Abschnitt \>  \> **"Benutzer gemeldete Nachrichteneinstellungen".**</span><span class="sxs-lookup"><span data-stu-id="eda8f-126">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Others** section \> **User reported message settings**.</span></span>

2. <span data-ttu-id="eda8f-127">Wenn Sie auf der Seite **"Benutzerübermittlungen"** den Anzeigenamen des Absenders angeben möchten, aktivieren Sie das Kontrollkästchen für **"Angeben Office 365 E-Mail-Adresse als Absender"** unter dem Abschnitt **"E-Mail-Benachrichtigungen für Administratorüberprüfungsergebnisse",** und geben Sie den Namen ein, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="eda8f-127">On the **User submissions** page, if you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="eda8f-128">Dies ist die E-Mail-Adresse, die in Outlook angezeigt wird und an die Antworten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="eda8f-128">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="eda8f-129">Wenn Sie eine der Vorlagen anpassen möchten, klicken Sie auf **E-Mail-Benachrichtigung anpassen.**</span><span class="sxs-lookup"><span data-stu-id="eda8f-129">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="eda8f-130">In diesem Flyout können Sie nur Folgendes anpassen:</span><span class="sxs-lookup"><span data-stu-id="eda8f-130">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="eda8f-131">Phishing</span><span class="sxs-lookup"><span data-stu-id="eda8f-131">Phishing</span></span>
    - <span data-ttu-id="eda8f-132">Junk-E-Mail</span><span class="sxs-lookup"><span data-stu-id="eda8f-132">Junk</span></span>
    - <span data-ttu-id="eda8f-133">Keine Bedrohungen gefunden</span><span class="sxs-lookup"><span data-stu-id="eda8f-133">No threats found</span></span>
    - <span data-ttu-id="eda8f-134">Sensibilisierungsschulung</span><span class="sxs-lookup"><span data-stu-id="eda8f-134">Awareness training</span></span>
    - <span data-ttu-id="eda8f-135">Fußzeile</span><span class="sxs-lookup"><span data-stu-id="eda8f-135">Footer</span></span>

4. <span data-ttu-id="eda8f-136">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eda8f-136">When you're finished, click **Save**.</span></span> <span data-ttu-id="eda8f-137">Um diese Werte zu löschen, klicken Sie auf der Seite "Benutzerübermittlungen" auf **"Verwerfen".**</span><span class="sxs-lookup"><span data-stu-id="eda8f-137">To clear these values, click **Discard** on the User submissions page.</span></span>
