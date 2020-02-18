---
title: Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: 12/13/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie eine Bezeichnung automatisch einem Dokument oder einer E-Mail zuweisen oder die Benutzer dazu auffordern, die von Ihnen empfohlene Bezeichnung auszuwählen.
ms.openlocfilehash: b2b78c6b028dc34040019f5087f1f8773eed768d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079692"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="613a7-103">Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte</span><span class="sxs-lookup"><span data-stu-id="613a7-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="613a7-104">Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie diese Bezeichnung automatisch Inhalten mit vertraulichen Informationen zuweisen oder die Benutzer dazu auffordern, die von Ihnen empfohlene Bezeichnung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="613a7-104">When you create a sensitivity label, you can automatically assign that label to content containing sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="613a7-105">Die Möglichkeit, Vertraulichkeitsbezeichnungen automatisch auf Inhalte anzuwenden, ist aus den folgenden Gründen wichtig:</span><span class="sxs-lookup"><span data-stu-id="613a7-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="613a7-106">Sie müssen die Benutzer nicht schulen, damit sie alle Ihre Klassifizierungen kennen.</span><span class="sxs-lookup"><span data-stu-id="613a7-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="613a7-107">Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="613a7-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="613a7-108">Benutzer müssen nicht mehr über Ihre Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="613a7-108">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="613a7-109">Informationen zu Lizenzanforderungen finden Sie unter [Abonnements- und Lizenzierungsanforderungen für Vertraulichkeitsbezeichnungen](sensitivity-labels-office-apps.md#subscription-and-licensing-requirements-for-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="613a7-109">For information about license requirements, see [Subscription and licensing requirements for sensitivity labels](sensitivity-labels-office-apps.md#subscription-and-licensing-requirements-for-sensitivity-labels).</span></span>

<span data-ttu-id="613a7-110">Die Bezeichnungseinstellungen sind verfügbar, wenn Sie eine Vertraulichkeitzbezeichnung im Microsoft 365 Compliance Center, Microsoft 365 Security Center oder Office 365 Security & Compliance Center unter **Klassifizierung** > **Vertraulichkeitsbezeichnungen** erstellen.</span><span class="sxs-lookup"><span data-stu-id="613a7-110">The auto-labeling settings are available when you create a sensitivity label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center under **Classification** > **Sensitivity labels**.</span></span>

![Automatische Bezeichnungsoptionen für Vertraulichkeitsbezeichnungen](../media/Sensitivity-labels-Auto-labeling-options.png)

## <a name="apply-a-sensitivity-label-automatically-based-on-conditions"></a><span data-ttu-id="613a7-112">Automatisches Anwenden einer Vertraulichkeitsbezeichnung basierend auf Kriterien</span><span class="sxs-lookup"><span data-stu-id="613a7-112">Apply a sensitivity label automatically based on conditions</span></span>

<span data-ttu-id="613a7-113">Eines der leistungsstärksten Features von Vertraulichkeitsbezeichnungen ist die Möglichkeit, sie automatisch auf Inhalte anzuwenden, die bestimmte Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="613a7-113">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="613a7-114">In diesem Fall müssen die Personen in Ihrer Organisation die Vertraulichkeitsbezeichnungen nicht selber anwenden – dies erledigt Office 365 automatisch.</span><span class="sxs-lookup"><span data-stu-id="613a7-114">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="613a7-p102">Sie können festlegen, dass Vertraulichkeitsbezeichnungen automatisch auf Inhalte angewendet werden, wenn bestimmte Typen vertraulicher Informationen enthalten sind. Wenn Se festlegen, dass eine Vertraulichkeitsbezeichnung automatisch angewendet werden soll, wird dieselbe Liste mit Typen vertraulicher Informationen angezeigt wie beim Erstellen einer DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust). So können Sie z. B. automatisch die Bezeichnung „Streng vertraulich“ auf Inhalte anwenden, die personenbezogene Kundendaten wie Kreditkartennummern oder Sozialversicherungsnummern enthalten.</span><span class="sxs-lookup"><span data-stu-id="613a7-p102">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information. When you configure a sensitivity label to be applied automatically, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy. So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers.</span></span>

![Optionen für Instanzenanzahl und Übereinstimmungsgenauigkeit](../media/Sensitivity-labels-instance-count-match-accuracy.png)

<span data-ttu-id="613a7-119">Nachdem Sie die Typen vertraulicher Informationen ausgewählt haben, können Sie die Kriterien eingrenzen, indem Sie die Instanzenanzahl oder Übereinstimmungsgenauigkeit ändern.</span><span class="sxs-lookup"><span data-stu-id="613a7-119">After you choose your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="613a7-120">Weitere Informationen finden Sie unter [Optimieren von Regeln, um die Übereinstimmung zu vereinfachen oder zu erschweren](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="613a7-120">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="613a7-121">Darüber hinaus können Sie auswählen, ob eine Bedingung alle vertraulichen Informationstypen oder nur einen dieser Typen erkennen muss.</span><span class="sxs-lookup"><span data-stu-id="613a7-121">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="613a7-122">Und um Ihre Bedingungen flexibler oder komplexer zu gestalten, können Sie Gruppen hinzufügen und logische Operatoren zwischen den Gruppen verwenden.</span><span class="sxs-lookup"><span data-stu-id="613a7-122">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="613a7-123">Weitere Informationen finden Sie unter [Gruppieren und logische Operatoren](data-loss-prevention-policies.md#grouping-and-logical-operators).</span><span class="sxs-lookup"><span data-stu-id="613a7-123">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

<span data-ttu-id="613a7-p105">Wenn eine Vertraulichkeitsbezeichnung automatisch angewendet wird, wird dem Benutzer eine Benachrichtigung in der Office-App angezeigt. Sie können **OK** auswählen, um die Benachrichtigung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="613a7-p105">When a sensitivity label is automatically applied, the user sees a notification in their Office app. They can choose **OK** to dismiss the notification.</span></span>

![Benachrichtigung darüber, dass ein Dokument automatisch mit einer Bezeichnung versehen wurde](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="613a7-127">Empfehlen des Anwendens einer Vertraulichkeitsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="613a7-127">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="613a7-128">Wenn Sie es vorziehen, können Sie Ihren Benutzern empfehlen, die Bezeichnung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="613a7-128">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="613a7-129">Mithilfe dieser Option können Ihre Benutzer die Klassifizierung und alle zugehörigen Schutzmaßnahmen akzeptieren oder die Empfehlung zurückweisen, wenn die Bezeichnung für ihr Dokument oder ihre E-Mail ungeeignet ist.</span><span class="sxs-lookup"><span data-stu-id="613a7-129">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their document or email.</span></span>

<span data-ttu-id="613a7-130">Empfohlene Bezeichnungen werden in Word, PowerPoint und Excel unterstützt (Azure Information Protection-Client für einheitliche Bezeichnungen muss installiert sein).</span><span class="sxs-lookup"><span data-stu-id="613a7-130">Recommended labels are supported in Word, PowerPoint, and Excel (and require that the Azure Information Protection unified labeling client is installed).</span></span>

![Option zum Empfehlen einer Vertraulichkeitsbezeichnung](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="613a7-p107">Im Folgenden finden Sie ein Beispiel für eine Aufforderung, wenn Sie Kriterien zum Anwenden einer Bezeichnung als empfohlene Aktion, und einen benutzerdefinierten Richtlinientipp. Sie können den Text festlegen, der im Richtlinientipp angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="613a7-p107">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![Aufforderung zum Anwenden einer empfohlene Bezeichnung](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="613a7-135">Anwenden automatischer oder empfohlener Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="613a7-135">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="613a7-136">Die automatische Zuweisung von Bezeichnungen gilt für Word, Excel und PowerPoint beim Speichern eines Dokuments, und für Outlook beim Senden einer E-Mail.</span><span class="sxs-lookup"><span data-stu-id="613a7-136">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="613a7-137">Diese Bedingungen erkennen vertrauliche Informationen im Text in Dokumenten und E-Mails sowie in Kopf- und Fußzeilen, aber nicht in der Betreffzeile oder E-Mail-Anlagen.</span><span class="sxs-lookup"><span data-stu-id="613a7-137">These conditions detect sensitive information in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="613a7-138">Sie können keine automatische Klassifizierung für Dokumente und E-Mails verwenden, die zuvor manuell bezeichnet oder automatisch mit einer höheren Klassifizierung gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="613a7-138">You can't use automatic classification for documents and emails that were previously manually labeled, or previously automatically labeled with a higher classification.</span></span> <span data-ttu-id="613a7-139">Denken Sie daran, dass Sie einem Dokument oder einer E-Mail-Nachricht nur eine einzige Vertraulichkeitsbezeichnung zuweisen können (zusätzlich zu einer einzigen Aufbewahrungsbezeichnung).</span><span class="sxs-lookup"><span data-stu-id="613a7-139">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="613a7-140">Die empfohlene Klassifizierung gilt für Word, Excel und PowerPoint beim Speichern von Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="613a7-140">Recommended classification applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="613a7-141">Sie können die empfohlene Klassifizierung für Dokumente, die zuvor mit einer höheren Klassifizierung gekennzeichnet wurden, nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="613a7-141">You can't use recommended classification for documents that were previously labeled with a higher classification.</span></span> <span data-ttu-id="613a7-142">Wenn der Inhalt bereits mit einer höheren Klassifizierung gekennzeichnet ist, wird dem Benutzer die Eingabeaufforderung mit der Empfehlung und dem Richtlinientipp nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="613a7-142">When the content's already labeled with a higher classification, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="613a7-143">Auswerten mehrerer Kriterien, wenn sie für mehr als eine Bezeichnung zutreffen</span><span class="sxs-lookup"><span data-stu-id="613a7-143">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="613a7-p111">Die Bezeichnungen werden je nach Position, die Sie in der Richtlinie festlegen, sortiert: die Bezeichnung an erster Stelle hat die niedrigste Position (am wenigsten vertraulich) und die Bezeichnung an letzter Stelle hat die höchste Position (am meisten vertraulich). Weitere Informationen zur Priorität finden Sie unter [Priorität der Bezeichnungen (Reihenfolge wesentlich)](sensitivity-labels.md#label-priority-order-matters).</span><span class="sxs-lookup"><span data-stu-id="613a7-p111">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="613a7-146">Konfigurieren Sie keine übergeordnete Bezeichnung, die automatisch angewendet oder empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="613a7-146">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="613a7-147">Denken Sie daran, dass Sie eine übergeordnete Bezeichnung (eine Bezeichnung mit Unterbezeichnungen) nicht auf Inhalt anwenden können.</span><span class="sxs-lookup"><span data-stu-id="613a7-147">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="613a7-148">Stellen Sie sicher, dass Sie eine übergeordnete Bezeichnung nicht so konfigurieren, dass sie automatisch angewendet oder empfohlen wird, da die übergeordnete Bezeichnung nicht auf Inhalt in Office-Apps angewendet wird, die den Azure Information Protection-Client mit einheitlichen Bezeichnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="613a7-148">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="613a7-149">Weitere Informationen zu übergeordneten Bezeichnungen und Unterbezeichnungen finden Sie unter [Unterbezeichnungen (Gruppierungsbezeichnungen)](sensitivity-labels.md#sublabels-grouping-labels).</span><span class="sxs-lookup"><span data-stu-id="613a7-149">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
