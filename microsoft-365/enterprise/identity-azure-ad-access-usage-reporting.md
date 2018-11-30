---
title: 'Schritt 13: Überwachen der Mandanten- und Anmeldeaktivität'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren von Azure AD-Zugriffs- und Verwendungsberichten.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867545"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="7402b-103">Schritt 13: Überwachen der Mandanten- und Anmeldeaktivität</span><span class="sxs-lookup"><span data-stu-id="7402b-103">Step 13: Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="7402b-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="7402b-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="7402b-p101">In diesem Schritt überprüfen Sie Überwachungsprotokolle und Anmeldeaktivitäten mithilfe von Azure AD-Berichten. Es stehen zwei Arten von Berichten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7402b-p101">In Step 13, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="7402b-p102">Der **Aktivitätsbericht „Überwachungsprotokolle“** verzeichnet den Verlauf jeder in Ihrem Azure AD-Mandanten ausgeführten Aufgabe. In diesem Bericht finden Sie Antworten auf Fragen wie:</span><span class="sxs-lookup"><span data-stu-id="7402b-p102">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="7402b-109">Wer hat eine Person zu einer Administratorengruppe hinzugefügt?</span><span class="sxs-lookup"><span data-stu-id="7402b-109">Who added someone to an admin group?</span></span>
- <span data-ttu-id="7402b-110">Welche Benutzer melden sich bei einer bestimmten App an?</span><span class="sxs-lookup"><span data-stu-id="7402b-110">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="7402b-111">Wie viele Kennwortzurücksetzungen werden ausgeführt?</span><span class="sxs-lookup"><span data-stu-id="7402b-111">How many password resets are happening?</span></span>

<span data-ttu-id="7402b-p103">Der **Aktivitätsbericht „Anmeldungen“** verzeichnet, wer die im Überwachungsprotokollbericht gemeldeten Aufgaben ausgeführt hat. In diesem Bericht finden Sie Antworten auf Fragen wie:</span><span class="sxs-lookup"><span data-stu-id="7402b-p103">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="7402b-114">Welches Anmeldemuster gilt für einen bestimmten untersuchten Benutzer?</span><span class="sxs-lookup"><span data-stu-id="7402b-114">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="7402b-115">Wie groß ist das Volumen von Anmeldungen über einen Tag, eine Woche oder einen Monat?</span><span class="sxs-lookup"><span data-stu-id="7402b-115">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="7402b-116">Wie viele dieser Anmeldeversuche waren nicht erfolgreich und für welche Konten?</span><span class="sxs-lookup"><span data-stu-id="7402b-116">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="7402b-117">Weitere Informationen zu den Berichten und den Zugriffsmöglichkeiten auf diese finden Sie unter [Azure Active Directory-Berichterstellung](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="7402b-117">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="7402b-118">In diesem Schritt lernen Sie die Berichte kennen und erfahren, wie Sie sie verwenden können, um zu Planungs- und Sicherheitszwecken Informationen über Azure AD-Ereignisse und -Aktivitäten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7402b-118">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="7402b-119">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="7402b-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="7402b-120">Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="7402b-120">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
