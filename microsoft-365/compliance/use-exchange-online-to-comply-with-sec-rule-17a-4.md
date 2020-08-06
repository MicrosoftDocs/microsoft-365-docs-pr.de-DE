---
title: Verwenden Sie Exchange Online und das Security & Compliance Center, um die SEC-Richtlinie 17a-4 einzuhalten
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Konfigurieren Sie Exchange Online & Compliance Center, um den behördlichen Bestimmungen von CFTC Regel 1.31(c)-(d), FINRA Regel 4511 und SEC Regel 17a-4 gerecht zu werden.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: bba51bed4409bfb933b577419f48ab6963d4f7d6
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577115"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="dffd6-103">Verwenden Sie Exchange Online und das Security & Compliance Center, um die SEC-Richtlinie 17a-4 einzuhalten</span><span class="sxs-lookup"><span data-stu-id="dffd6-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="dffd6-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="dffd6-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="dffd6-p101">Wenn Ihre Organisation gesetzliche Standards für die Aufbewahrung von Daten einhalten muss, bietet das Security & Compliance Center Features zur Verwaltung des Lebenszyklus Ihrer Daten in Exchange Online. Dazu gehört auch die Möglichkeit zum Aufbewahren, Überwachen, Durchsuchen und Exportieren der Daten. Diese Funktionen reichen aus, um die Anforderungen der meisten Organisationen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="dffd6-p101">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online. This includes the ability to retain, audit, search, and export your data. These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="dffd6-p102">Einige Organisationen in stark regulierten Branchen unterliegen jedoch stringenteren aufsichtsrechtlichen Anforderungen. Finanzinstitute wie Banken oder Broker-Händler unterliegen beispielsweise der Richtlinie 17a-4 der Securities and Exchange Commission (SEC). Die Richtlinie 17a-4 enthält spezielle Anforderungen an die elektronische Datenspeicherung, darunter einige Aspekte der Aufzeichnungsverwaltung wie z. B. Dauer, Format, Qualität, Verfügbarkeit und Haftung für die Datenaufbewahrung.</span><span class="sxs-lookup"><span data-stu-id="dffd6-p102">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements. For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC). Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="dffd6-111">Damit diese Organisationen besser verstehen, wie das Security & Compliance Center genutzt werden kann, um ihre gesetzlichen Auflagen für Exchange Online einzuhalten, insbesondere in Bezug auf die Anforderungen der Richtlinie 17a-4, haben wir in Zusammenarbeit mit Cohasset Associates eine Bewertung veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="dffd6-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="dffd6-p103">Cohasset Associates bestätigt, dass Exchange Online und das Security & Compliance Center bei der empfohlenen Konfiguration die relevanten Speicheranforderungen der CFTC-Richtlinie 1.31(c)-(d), der FINRA-Richtlinie 4511 und der SEC-Richtlinie 17a-4 erfüllen. Diese Richtlinien wurden ausgewählt, da sie die ausführlichsten globalen Anleitungen für die Datenaufbewahrung für Finanzinstitute darstellen.</span><span class="sxs-lookup"><span data-stu-id="dffd6-p103">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4. We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="dffd6-114">Die Bewertung von Cohasset herunterladen</span><span class="sxs-lookup"><span data-stu-id="dffd6-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="dffd6-115">Sie können [hier die Bewertung von Cohasset herunterladen](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span><span class="sxs-lookup"><span data-stu-id="dffd6-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![Titelseite für die Bewertung von Cohasset Associates zum Herunterladen](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="dffd6-117">Diese Bewertung ist beschränkt auf Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dffd6-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="dffd6-p104">Beachten Sie, dass diese Bewertung auf Exchange Online beschränkt ist. Die Bewertung umfasst keine anderen Microsoft 365-Dienste wie SharePoint Online oder OneDrive for Business, obwohl in Zukunft der Support für diese Dienste unter Einhaltung der SEC 17a-4 geplant ist.</span><span class="sxs-lookup"><span data-stu-id="dffd6-p104">Note that this assessment is specific to Exchange Online. The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="dffd6-p105">Es ist wichtig zu verstehen, dass Skype for Business und Teams auch Daten in Exchange Online speichern. Daher deckt die Bewertung Nachrichten von Skype for Business sowie Kanal- und Chatnachrichten von Teams ab.</span><span class="sxs-lookup"><span data-stu-id="dffd6-p105">It's important to understand that Skype for Business and Teams also store data in Exchange Online. Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="dffd6-122">Die Verwendung der Erhaltungssperre ist für die empfohlene Konfiguration essentiell</span><span class="sxs-lookup"><span data-stu-id="dffd6-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="dffd6-p106">In hochgradig regulierten Branchen müssen oft elektronische Kommunikationsdaten gespeichert werden, um die sogenannte WORM-Anforderung (write onde, read many) zu erfüllen. Die WORM-Anforderung schreibt eine Speicherlösung vor, in der folgende Voraussetzungen in Bezug auf Datensätze erfüllt werden müssen:</span><span class="sxs-lookup"><span data-stu-id="dffd6-p106">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement. The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="dffd6-125">Sie müssen über einen erforderlichen Aufbewahrungszeitraum gespeichert werden, der nicht verkürzt sondern nur verlängert werden kann.</span><span class="sxs-lookup"><span data-stu-id="dffd6-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="dffd6-126">Sie müssen unveränderlich sein, d. h. Datensätze können während des erforderlichen Aufbewahrungszeitraums nicht überschrieben, gelöscht oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dffd6-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="dffd6-p107">Wenn in Exchange Online eine [Aufbewahrungsrichtlinie](retention.md) auf das Postfach eines Benutzers angewendet wird, werden alle Inhalte des Benutzers basierend auf den Kriterien der Richtlinie aufbewahrt. Dis bedeutet, dass, sobald ein Benutzer versucht, eine E-Mail zu löschen oder zu ändern, eine Kopie der E-Mail im unveränderten Zustand an einem sicheren, versteckten Speicherort im Postfach des Benutzers abgelegt wird. Durch Aufbewahrungsrichtlinien kann sichergestellt werden, dass eine Organisation elektronische Kommunikationsdaten aufbewahrt, allerdings können derartige Richtlinien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dffd6-p107">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy. In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox. Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="dffd6-p108">Durch das Anwenden einer Erhaltungssperre auf eine Aufbewahrungsrichtlinie kann eine Organisation sicherstellen, dass die Richtlinie nicht geändert werden kann. Nach dem Anwenden einer Erhaltungssperre auf eine Aufbewahrungsrichtlinie sind folgende Aktionen eingeschränkt:</span><span class="sxs-lookup"><span data-stu-id="dffd6-p108">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified. In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="dffd6-132">Die in der Richtlinie enthaltene Aufbewahrungsdauer kann nur verlängert, nicht gekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="dffd6-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="dffd6-133">Benutzer können der Richtlinie hinzugefügt werden, jedoch können keine Benutzer entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="dffd6-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="dffd6-134">Die Aufbewahrungsrichtlinie kann nicht von einem Administrator gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="dffd6-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="dffd6-135">Eine Erhaltungssperre kann Sie bei der Einhaltung der gesetzlichen Bestimmungen der SEC 17a-4 unterstützen.</span><span class="sxs-lookup"><span data-stu-id="dffd6-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="dffd6-136">So richten Sie eine Erhaltungssperre ein</span><span class="sxs-lookup"><span data-stu-id="dffd6-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="dffd6-137">Sie können eine Aufbewahrungsrichtlinie nur mithilfe von PowerShell sperren.</span><span class="sxs-lookup"><span data-stu-id="dffd6-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="dffd6-138">Weitere Informationen hierzu finden Sie unter [Verwenden der Erhaltungssperre zur Einhaltung gesetzlicher Vorschriften](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span><span class="sxs-lookup"><span data-stu-id="dffd6-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

