---
title: 'Schritt 5: Konfigurieren von Office 365 Data Loss Prevention'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Bereitstellen von Office 365 Data Loss Prevention in Microsoft 365.
ms.openlocfilehash: 43ebfb39202e407fe6dc7bb4c8e0fe8f906f7a6d
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370162"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a><span data-ttu-id="11aa6-103">Schritt 5: Konfigurieren von Office 365 Data Loss Prevention</span><span class="sxs-lookup"><span data-stu-id="11aa6-103">Step 5: Configure Office 365 Data Loss Prevention</span></span>

<span data-ttu-id="11aa6-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="11aa6-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Phase 6: Schutz von Daten](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="11aa6-106">Mithilfe von Data Loss Prevention-Richtlinien (DLP) im Office 365 Security & Compliance Center können Sie vertrauliche Informationen in Microsoft 365 identifizieren, überwachen und automatisch schützen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-106">With data loss prevention (DLP) policies in the Office 365 Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="11aa6-107">Mit DLP-Richtlinien können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="11aa6-107">With DLP policies, you can:</span></span>

- <span data-ttu-id="11aa6-108">Identifizieren vertraulicher Informationen an vielen Orten, zum Beispiel Exchange Online, SharePoint Online, OneDrive for Business und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="11aa6-108">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="11aa6-109">Verhindern der versehentlichen Freigabe von vertraulichen Informationen durch das Sperren des Zugriffs auf ein Dokument oder durch das Blockieren der E-Mail, die es enthält.</span><span class="sxs-lookup"><span data-stu-id="11aa6-109">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="11aa6-110">Überwachen und Schützen von vertraulichen Informationen in den Desktopversionen von Excel, PowerPoint und Word.</span><span class="sxs-lookup"><span data-stu-id="11aa6-110">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="11aa6-111">Unterstützen von Benutzern mit E-Mail-Benachrichtigungen und Richtlinientipps, die erfahren, wie sie die Anforderungen erfüllen, ohne dabei ihren Arbeitsablauf unterbrechen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-111">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="11aa6-112">Anzeigen von DLP-Berichten mit Inhalten, die mit den DLP-Richtlinien Ihrer Organisation übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-112">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="11aa6-113">Eine DLP-Richtlinie gibt Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="11aa6-113">A DLP policy specifies:</span></span>

- <span data-ttu-id="11aa6-114">**Wo:** Orte, zum Beispiel Exchange Online-, SharePoint Online- und OneDrive for Business-Websites sowie Microsoft Teams-Chats und -Kanäle.</span><span class="sxs-lookup"><span data-stu-id="11aa6-114">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="11aa6-115">**Wann:** Bedingungen, die der Inhalt innerhalb einer bestimmten Richtlinienregel erfüllen muss.</span><span class="sxs-lookup"><span data-stu-id="11aa6-115">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="11aa6-116">**Wie:** Aktionen in dieser Abgleichsrichtlinienregel, die automatisch für die übereinstimmenden Bedingungen durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="11aa6-116">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="11aa6-117">Anders ausgedrückt:</span><span class="sxs-lookup"><span data-stu-id="11aa6-117">In other words:</span></span>

- <span data-ttu-id="11aa6-118">Wenn für ein Dokument an diesem Ort (wo) der Inhalt die Kriterien einer Regel erfüllt (wenn), dann werden automatisch die Aktionen in der Regel durchgeführt (wie).</span><span class="sxs-lookup"><span data-stu-id="11aa6-118">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="11aa6-119">Um die Gruppe von DLP-Richtlinien zu ermitteln, die Sie benötigen, müssen Sie Ihre Dokumente und die Arten von Daten in ihnen analysieren, die vor Datenverlust geschützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-119">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="11aa6-120">Eine Finanzorganisation in den Vereinigten Staaten von Amerika würde beispielsweise eine DLP-Richtlinie erstellen, die verhindert, dass Dokumente mit Sozialversicherungsnummern nach außen gelangen oder per E-Mail an Orte außerhalb des Unternehmens gesendet. werden.</span><span class="sxs-lookup"><span data-stu-id="11aa6-120">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="11aa6-121">Als Nächstes konfigurieren und testen Sie die Richtlinien mit Testorten, um das richtige DLP-Verhalten sicherzustellen und falsch positive Ergebnisse zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="11aa6-121">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="11aa6-122">Zum Schluss implementieren Sie sie für Ihre Organisation, indem Sie die Mitarbeiter über die neuen Richtlinien und das gewünschte Verhalten informieren und den Umfang der Orte erweitern.</span><span class="sxs-lookup"><span data-stu-id="11aa6-122">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="11aa6-123">Weitere Informationen erhalten Sie unter [Empfohlene erste Schritte mit DLP-Richtlinienvorlagen](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span><span class="sxs-lookup"><span data-stu-id="11aa6-123">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="11aa6-124">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step5) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="11aa6-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="11aa6-125">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="11aa6-125">Next step</span></span>

|||
|:-------|:-----|
|![Schritt 6](./media/stepnumbers/Step6.png)|[<span data-ttu-id="11aa6-127">Konfigurieren der E-Mail-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="11aa6-127">Configure email encryption</span></span>](infoprotect-email-encryption.md)|


