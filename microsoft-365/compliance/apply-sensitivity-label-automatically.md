---
title: Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie eine Bezeichnung automatisch einem Dokument oder einer E-Mail zuweisen oder die Benutzer dazu auffordern, die von Ihnen empfohlene Bezeichnung auszuwählen.
ms.openlocfilehash: a1ea81bf8c65d3f54d26b19eae3b590f11283c30
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277212"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="cd968-103">Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte</span><span class="sxs-lookup"><span data-stu-id="cd968-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="cd968-104">Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie diese Bezeichnung automatisch Inhalten mit vertraulichen Informationen zuweisen oder die Benutzer dazu auffordern, die von Ihnen empfohlene Bezeichnung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="cd968-104">When you create a sensitivity label, you can automatically assign that label to content when it contains sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="cd968-105">Die Möglichkeit, Vertraulichkeitsbezeichnungen automatisch auf Inhalte anzuwenden, ist aus den folgenden Gründen wichtig:</span><span class="sxs-lookup"><span data-stu-id="cd968-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="cd968-106">Sie müssen die Benutzer nicht schulen, damit sie alle Ihre Klassifizierungen kennen.</span><span class="sxs-lookup"><span data-stu-id="cd968-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="cd968-107">Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="cd968-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="cd968-108">Benutzer müssen nicht mehr über Ihre Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="cd968-108">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="cd968-109">Die automatische Zuweisung von Bezeichnungen in Office-Apps für Windows wird durch den Client mit einheitlichen Bezeichnungen von Azure Information Protection unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cd968-109">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="cd968-110">Für integrierte Bezeichnungen in Office-Apps befindet sich diese Funktion [für einigen Apps in der Vorschau](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span><span class="sxs-lookup"><span data-stu-id="cd968-110">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="cd968-111">Die Einstellungen für automatische Zuweisung von Bezeichnungen für Office-Apps sind verfügbar, wenn Sie [eine Vertraulichkeitsbezeichnung erstellen oder bearbeiten](create-sensitivity-labels.md):</span><span class="sxs-lookup"><span data-stu-id="cd968-111">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![Optionen der automatischen Zuweisung von Bezeichnungen für Vertraulichkeitsbezeichnungen](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="cd968-113">Konfigurieren der automatischen Zuweisung von Bezeichnungen für Office-Apps</span><span class="sxs-lookup"><span data-stu-id="cd968-113">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="cd968-114">Eines der leistungsstärksten Features von Vertraulichkeitsbezeichnungen ist die Möglichkeit, sie automatisch auf Inhalte anzuwenden, die bestimmte Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="cd968-114">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="cd968-115">In diesem Fall müssen die Personen in Ihrer Organisation die Vertraulichkeitsbezeichnungen nicht selber anwenden – dies erledigt Office 365 automatisch.</span><span class="sxs-lookup"><span data-stu-id="cd968-115">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="cd968-116">Sie können sich dafür entscheiden, Inhalten automatisch Vertraulichkeitsbezeichnungen zuzuordnen, wenn diese Inhalte bestimmte Arten von sensiblen Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd968-116">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="cd968-117">Wählen Sie aus einer Liste von Arten von sensiblen Informationen oder Klassifizierungen:</span><span class="sxs-lookup"><span data-stu-id="cd968-117">Choose from a list of sensitive info types or classifers:</span></span>

![Bezeichnungsbedingungen für die automatische Zuweisung von Bezeichnungen in Office-Apps](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="cd968-119">Derzeit befindet sich die Option für **Klassifizierungen** in einer begrenzten Vorschau und erfordert, dass Sie ein Formular an Microsoft senden, um diese Funktion für Ihren Mandanten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cd968-119">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="cd968-120">Weitere Informationen finden Sie im Blogbeitrag [Announcing automatic labeling in Office Apps using built-in classifiers – Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889) (Ankündigung der automatischen Zuweisung von Bezeichnungen in Office-Apps mit integrierten Klassifizierungen – begrenzte Vorschau).</span><span class="sxs-lookup"><span data-stu-id="cd968-120">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="cd968-121">Wenn eine Vertraulichkeitsbezeichnung automatisch angewendet wird, wird dem Benutzer eine Benachrichtigung in der Office-App angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd968-121">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="cd968-122">Sie können **OK** auswählen, um die Benachrichtigung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="cd968-122">They can choose **OK** to dismiss the notification.</span></span>

![Benachrichtigung darüber, dass ein Dokument automatisch mit einer Bezeichnung versehen wurde](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="cd968-124">Konfigurieren von Typen vertraulicher Informationen für eine Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="cd968-124">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="cd968-125">Wenn Sie die Option **Typen vertraulicher Informationen** auswählen, wird dieselbe Liste von vertraulichen Informationen wie beim Erstellen einer DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd968-125">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="cd968-126">So können Sie z. B. auf alle Inhalte, die persönlich identifizierbare Informationen (PII) von Kunden enthalten, wie z. B. Kreditkartennummern oder Sozialversicherungsnummern, automatisch die Bezeichnung "Streng vertraulich" anwenden:</span><span class="sxs-lookup"><span data-stu-id="cd968-126">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Typen vertraulicher Informationen für die automatische Zuweisung von Bezeichnungen in Office-Apps](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="cd968-128">Nachdem Sie die Typen vertraulicher Informationen ausgewählt haben, können Sie die Kriterien eingrenzen, indem Sie die Instanzenanzahl oder Übereinstimmungsgenauigkeit ändern.</span><span class="sxs-lookup"><span data-stu-id="cd968-128">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="cd968-129">Weitere Informationen finden Sie unter [Optimieren von Regeln, um die Übereinstimmung zu vereinfachen oder zu erschweren](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="cd968-129">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="cd968-130">Darüber hinaus können Sie auswählen, ob eine Bedingung alle vertraulichen Informationstypen oder nur einen dieser Typen erkennen muss.</span><span class="sxs-lookup"><span data-stu-id="cd968-130">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="cd968-131">Und um Ihre Bedingungen flexibler oder komplexer zu gestalten, können Sie Gruppen hinzufügen und logische Operatoren zwischen den Gruppen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd968-131">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="cd968-132">Weitere Informationen finden Sie unter [Gruppieren und logische Operatoren](data-loss-prevention-policies.md#grouping-and-logical-operators).</span><span class="sxs-lookup"><span data-stu-id="cd968-132">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![Optionen für Instanzenanzahl und Übereinstimmungsgenauigkeit](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="cd968-134">Konfigurieren von Klassifizierungen für eine Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="cd968-134">Configuring classifers for a label</span></span>

<span data-ttu-id="cd968-135">Wenn Sie die Option **Klassifizierungen** auswählen, wählen Sie eine oder mehrere der integrierten Klassifizierungen aus:</span><span class="sxs-lookup"><span data-stu-id="cd968-135">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![Optionen für Klassifizierungen und Vertraulichkeitsbezeichnungen](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="cd968-137">Weitere Informationen zu diesen Klassifizierungen finden Sie unter [Erste Schritte mit trainierbaren Klassifizierungen (Vorschau)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="cd968-137">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="cd968-138">Während des Vorschauzeitraums unterstützen die folgenden Apps Klassifizierungen für Vertraulichkeitsbezeichnungen:</span><span class="sxs-lookup"><span data-stu-id="cd968-138">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="cd968-139">Office 365 ProPlus-Desktop-Apps für Windows, von [Office Insider](https://office.com/insider):</span><span class="sxs-lookup"><span data-stu-id="cd968-139">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="cd968-140">Word</span><span class="sxs-lookup"><span data-stu-id="cd968-140">Word</span></span>
    - <span data-ttu-id="cd968-141">Excel</span><span class="sxs-lookup"><span data-stu-id="cd968-141">Excel</span></span>
    - <span data-ttu-id="cd968-142">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cd968-142">PowerPoint</span></span>

- <span data-ttu-id="cd968-143">Office für das Web-Apps, wenn Sie über [aktivierte Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive (öffentliche Vorschau)](sensitivity-labels-sharepoint-onedrive-files.md) verfügen:</span><span class="sxs-lookup"><span data-stu-id="cd968-143">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="cd968-144">Word</span><span class="sxs-lookup"><span data-stu-id="cd968-144">Word</span></span>
    - <span data-ttu-id="cd968-145">Excel</span><span class="sxs-lookup"><span data-stu-id="cd968-145">Excel</span></span>
    - <span data-ttu-id="cd968-146">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cd968-146">PowerPoint</span></span>
    - <span data-ttu-id="cd968-147">Outlook</span><span class="sxs-lookup"><span data-stu-id="cd968-147">Outlook</span></span>

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="cd968-148">Empfehlen des Anwendens einer Vertraulichkeitsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="cd968-148">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="cd968-149">Wenn Sie es vorziehen, können Sie Ihren Benutzern empfehlen, die Bezeichnung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="cd968-149">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="cd968-150">Mithilfe dieser Option können Ihre Benutzer die Klassifizierung und alle zugehörigen Schutzmaßnahmen akzeptieren oder die Empfehlung zurückweisen, wenn die Bezeichnung für ihre Inhalte ungeeignet ist.</span><span class="sxs-lookup"><span data-stu-id="cd968-150">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

<span data-ttu-id="cd968-151">Empfohlene Bezeichnungen werden für Word, PowerPoint und Excel unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cd968-151">Recommended labels are supported for Word, PowerPoint, and Excel.</span></span>

![Option zum Empfehlen einer Vertraulichkeitsbezeichnung](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="cd968-p110">Im Folgenden finden Sie ein Beispiel für eine Aufforderung, wenn Sie Kriterien zum Anwenden einer Bezeichnung als empfohlene Aktion, und einen benutzerdefinierten Richtlinientipp. Sie können den Text festlegen, der im Richtlinientipp angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cd968-p110">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![Aufforderung zum Anwenden einer empfohlene Bezeichnung](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="cd968-156">Anwenden automatischer oder empfohlener Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="cd968-156">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="cd968-157">Die automatische Zuweisung von Bezeichnungen gilt für Word, Excel und PowerPoint beim Speichern eines Dokuments, und für Outlook beim Senden einer E-Mail.</span><span class="sxs-lookup"><span data-stu-id="cd968-157">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="cd968-158">Diese Bedingungen erkennen vertrauliche Informationen im Text in Dokumenten und E-Mails sowie in Kopf- und Fußzeilen, aber nicht in der Betreffzeile oder E-Mail-Anlagen.</span><span class="sxs-lookup"><span data-stu-id="cd968-158">These conditions detect sensitive information in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="cd968-159">Sie können keine automatische Zuweisung von Bezeichnungen für Dokumente und E-Mails verwenden, die zuvor manuell bezeichnet oder automatisch mit einer höheren Vertraulichkeit gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="cd968-159">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="cd968-160">Denken Sie daran, dass Sie einem Dokument oder einer E-Mail-Nachricht nur eine einzige Vertraulichkeitsbezeichnung zuweisen können (zusätzlich zu einer einzigen Aufbewahrungsbezeichnung).</span><span class="sxs-lookup"><span data-stu-id="cd968-160">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="cd968-161">Die empfohlene Bezeichnungen gelten für Word, Excel und PowerPoint beim Speichern von Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="cd968-161">Recommended labeling applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="cd968-162">Sie können die empfohlenen Bezeichnungen für Dokumente, die zuvor mit einer höheren Vertraulichkeit gekennzeichnet wurden, nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd968-162">You can't use recommended labeling for documents that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="cd968-163">Wenn der Inhalt bereits mit einer höheren Vertraulichkeit gekennzeichnet ist, wird dem Benutzer die Eingabeaufforderung mit der Empfehlung und dem Richtlinientipp nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd968-163">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="cd968-164">Auswerten mehrerer Kriterien, wenn sie für mehr als eine Bezeichnung zutreffen</span><span class="sxs-lookup"><span data-stu-id="cd968-164">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="cd968-p114">Die Bezeichnungen werden je nach Position, die Sie in der Richtlinie festlegen, sortiert: die Bezeichnung an erster Stelle hat die niedrigste Position (am wenigsten vertraulich) und die Bezeichnung an letzter Stelle hat die höchste Position (am meisten vertraulich). Weitere Informationen zur Priorität finden Sie unter [Priorität der Bezeichnungen (Reihenfolge wesentlich)](sensitivity-labels.md#label-priority-order-matters).</span><span class="sxs-lookup"><span data-stu-id="cd968-p114">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="cd968-167">Konfigurieren Sie keine übergeordnete Bezeichnung, die automatisch angewendet oder empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="cd968-167">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="cd968-168">Denken Sie daran, dass Sie eine übergeordnete Bezeichnung (eine Bezeichnung mit Unterbezeichnungen) nicht auf Inhalt anwenden können.</span><span class="sxs-lookup"><span data-stu-id="cd968-168">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="cd968-169">Stellen Sie sicher, dass Sie eine übergeordnete Bezeichnung nicht so konfigurieren, dass sie automatisch angewendet oder empfohlen wird, da die übergeordnete Bezeichnung nicht auf Inhalt in Office-Apps angewendet wird, die den Azure Information Protection-Client mit einheitlichen Bezeichnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd968-169">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="cd968-170">Weitere Informationen zu übergeordneten Bezeichnungen und Unterbezeichnungen finden Sie unter [Unterbezeichnungen (Gruppierungsbezeichnungen)](sensitivity-labels.md#sublabels-grouping-labels).</span><span class="sxs-lookup"><span data-stu-id="cd968-170">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
