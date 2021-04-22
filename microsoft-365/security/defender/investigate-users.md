---
title: Analysieren von Benutzern im Microsoft 365 Security Center
description: Analysieren von Benutzern im Microsoft 365 Security Center
keywords: Security, Malware, Microsoft 365, M365, Security Center, monitor, report, identities, data, devices, apps, incident, analyze, response
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 1fb5a4eee41384ef1afc9b46e5bf538344718fe9
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939730"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="7bdd8-104">Analysieren von Benutzern im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="7bdd8-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7bdd8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7bdd8-105">**Applies to:**</span></span>

- <span data-ttu-id="7bdd8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bdd8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7bdd8-107">Ein Teil ihrer Vorfallanalyse kann Benutzerkonten enthalten.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="7bdd8-108">Beginnen Sie mit der **Registerkarte Benutzer** für einen Vorfall von & Warnungen **>** *Vorfall* **> Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Beispiel einer Benutzerseite für einen Vorfall":::

<span data-ttu-id="7bdd8-110">Um eine kurze Zusammenfassung eines Benutzerkontos für den Vorfall zu erhalten, aktivieren Sie das Kontrollkästchen neben dem Benutzernamen.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="7bdd8-111">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Beispiel für den Zusammenfassungsbereich des Benutzerkontos für einen Vorfall im Microsoft 365 Security Center":::

<span data-ttu-id="7bdd8-113">Hier können Sie zur Benutzerseite wechseln **auswählen,** um die Details eines Benutzerkontos anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="7bdd8-114">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Beispiel für die Benutzerkontoseite für einen Vorfall im Microsoft 365 Security Center":::

<span data-ttu-id="7bdd8-116">Sie können diese Seite auch anzeigen, indem Sie den Namen des Benutzerkontos aus der Liste auf der Seite **Benutzer** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="7bdd8-117">Die Microsoft 365 Security Center-Benutzerseite kombiniert Informationen von Microsoft Defender for Endpoint, Microsoft Defender for Identity und Microsoft Cloud App Security (je nachdem, welche Lizenzen Sie besitzen).</span><span class="sxs-lookup"><span data-stu-id="7bdd8-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="7bdd8-118">Diese Seite enthält Informationen, die speziell für das Sicherheitsrisiko eines Benutzerkontos spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="7bdd8-119">Dies umfasst eine Bewertung, die bei der Bewertung von Risiken und aktuellen Ereignissen und Warnungen hilft, die zum Gesamtrisiko des Benutzers beigetragen haben.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="7bdd8-120">Auf dieser Seite können Sie die folgenden zusätzlichen Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="7bdd8-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="7bdd8-121">Kennzeichnen des Benutzerkontos als gefährdet</span><span class="sxs-lookup"><span data-stu-id="7bdd8-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="7bdd8-122">Benutzer erneut anmelden</span><span class="sxs-lookup"><span data-stu-id="7bdd8-122">Require the user to sign in again</span></span>
- <span data-ttu-id="7bdd8-123">Anhalten des Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="7bdd8-123">Suspend the user account</span></span>
- <span data-ttu-id="7bdd8-124">Weitere Informationen finden Sie unter Azure Active Directory (Azure AD)-Benutzerkonteneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="7bdd8-125">Anzeigen der Dateien im Besitz des Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="7bdd8-125">View the files owned by the user account</span></span>
- <span data-ttu-id="7bdd8-126">Anzeigen von Dateien, die für diesen Benutzer freigegeben sind.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-126">View files shared with this user.</span></span> 

<span data-ttu-id="7bdd8-127">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="7bdd8-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Beispiel für die Aktionen für ein Benutzerkonto für einen Vorfall im Microsoft 365 Security Center":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="7bdd8-129">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7bdd8-129">Related topics</span></span>

- [<span data-ttu-id="7bdd8-130">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="7bdd8-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="7bdd8-131">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="7bdd8-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="7bdd8-132">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="7bdd8-132">Manage incidents</span></span>](manage-incidents.md)