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
ms.openlocfilehash: 217f5ebb1692d68b5dc70988888bf78d4bd36a0c
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893728"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="872ae-103">Überprüfung gemeldeter Nachrichten durch den Administrator</span><span class="sxs-lookup"><span data-stu-id="872ae-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="872ae-104">Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das vor der kommerziellen Veröffentlichung erheblich geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="872ae-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="872ae-105">Dieses Dokument dient nur zu Evaluierungs- und Untersuchungszwecken.</span><span class="sxs-lookup"><span data-stu-id="872ae-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="872ae-106">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="872ae-106">**Applies to**</span></span>
- [<span data-ttu-id="872ae-107">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="872ae-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="872ae-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="872ae-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="872ae-109">In Microsoft 365 Organisationen mit Exchange Online Postfächern und Microsoft Defender für Office 365 können Administratoren nun Nachrichten mit Vorlagen an Endbenutzer senden, nachdem sie die gemeldeten Nachrichten überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="872ae-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="872ae-110">Dies kann für Ihre Organisation angepasst werden und basiert auch auf der Bewertung Ihres Administrators.</span><span class="sxs-lookup"><span data-stu-id="872ae-110">This can be customized for your organization and based on your admin's verdict as well.</span></span>

<span data-ttu-id="872ae-111">Dieses Feature ist darauf ausgelegt, Ihren Benutzern Feedback zu geben, ändert aber nicht die Bewertung von Nachrichten im System.</span><span class="sxs-lookup"><span data-stu-id="872ae-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="872ae-112">Um Microsoft bei der Aktualisierung und Verbesserung seiner Filter zu unterstützen, müssen Sie Nachrichten mithilfe der [Administratorübermittlung](admin-submission.md)zur Analyse übermitteln.</span><span class="sxs-lookup"><span data-stu-id="872ae-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="872ae-113">Sie können Benutzer nur dann markieren und über Rezensionsergebnisse informieren, wenn die Nachricht als [falsch positive oder falsch negative](report-false-positives-and-false-negatives.md)Ergebnisse gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="872ae-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="872ae-114">Wissenswertes, bevor Sie anfangen</span><span class="sxs-lookup"><span data-stu-id="872ae-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="872ae-115">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="872ae-115">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="872ae-116">Um direkt zur Seite **"Übermittlungen"** zu wechseln, verwenden Sie <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="872ae-116">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="872ae-117">Um die Konfiguration für Benutzerübermittlungen zu ändern, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="872ae-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="872ae-118">Organisationsverwaltung oder Sicherheitsadministrator im [Microsoft 365 Defender-Portal.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="872ae-118">Organization Management or Security Administrator in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="872ae-119">Organisationsverwaltung in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="872ae-119">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="872ae-120">Sie benötigen auch Zugriff auf Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="872ae-120">You'll also need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="872ae-121">Wenn das Konto, das Sie verwenden möchten, keinen Zugriff auf Exchange Online PowerShell hat, erhalten Sie eine Fehlermeldung, die besagt, dass *eine E-Mail-Adresse in Ihrer Domäne angegeben* wird.</span><span class="sxs-lookup"><span data-stu-id="872ae-121">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="872ae-122">Weitere Informationen zum Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="872ae-122">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="872ae-123">Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="872ae-123">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="872ae-124">Clientzugriffsregeln in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="872ae-124">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="872ae-125">Konfigurieren der Nachrichten, die zum Benachrichtigen von Benutzern verwendet werden</span><span class="sxs-lookup"><span data-stu-id="872ae-125">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="872ae-126">Wechseln Sie im Microsoft 365 **Defender-Portal zu E-Mail-& Richtlinien** für die Zusammenarbeit \> **& Regeln** \> **Bedrohungsrichtlinien** \> **Andere** Abschnitt Nachrichteneinstellungen des \> **Benutzers gemeldet.**</span><span class="sxs-lookup"><span data-stu-id="872ae-126">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Others** section \> **User reported message settings**.</span></span>

2. <span data-ttu-id="872ae-127">Wenn Sie auf der Seite **"Benutzerübermittlungen"** den Anzeigenamen des Absenders angeben möchten, aktivieren Sie das Kontrollkästchen für **"Angeben Office 365 E-Mail-Adresse als Absender"** im Abschnitt **"E-Mail-Benachrichtigungen für Administratorüberprüfungsergebnisse",** und geben Sie den Namen ein, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="872ae-127">On the **User submissions** page, if you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="872ae-128">Dies ist die E-Mail-Adresse, die in Outlook angezeigt wird und an die Antworten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="872ae-128">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="872ae-129">Wenn Sie eine der Vorlagen anpassen möchten, klicken Sie auf **E-Mail-Benachrichtigung anpassen.**</span><span class="sxs-lookup"><span data-stu-id="872ae-129">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="872ae-130">In diesem Flyout können Sie nur Folgendes anpassen:</span><span class="sxs-lookup"><span data-stu-id="872ae-130">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="872ae-131">Phishing</span><span class="sxs-lookup"><span data-stu-id="872ae-131">Phishing</span></span>
    - <span data-ttu-id="872ae-132">Junk-E-Mail</span><span class="sxs-lookup"><span data-stu-id="872ae-132">Junk</span></span>
    - <span data-ttu-id="872ae-133">Keine Bedrohungen gefunden</span><span class="sxs-lookup"><span data-stu-id="872ae-133">No threats found</span></span>
    - <span data-ttu-id="872ae-134">Sensibilisierungsschulung</span><span class="sxs-lookup"><span data-stu-id="872ae-134">Awareness training</span></span>
    - <span data-ttu-id="872ae-135">Fußzeile</span><span class="sxs-lookup"><span data-stu-id="872ae-135">Footer</span></span>

4. <span data-ttu-id="872ae-136">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="872ae-136">When you're finished, click **Save**.</span></span> <span data-ttu-id="872ae-137">Um diese Werte zu löschen, klicken Sie auf der Seite "Benutzerübermittlungen" auf **"Verwerfen".**</span><span class="sxs-lookup"><span data-stu-id="872ae-137">To clear these values, click **Discard** on the User submissions page.</span></span>
