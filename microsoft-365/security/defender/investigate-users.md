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
ms.openlocfilehash: 2fd9b958cdbdaf22346f8171c789f2ca9a8336d1
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957607"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="6ec02-104">Analysieren von Benutzern im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="6ec02-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6ec02-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6ec02-105">**Applies to:**</span></span>

- <span data-ttu-id="6ec02-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ec02-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6ec02-107">Ein Teil ihrer Vorfallanalyse kann Benutzerkonten enthalten.</span><span class="sxs-lookup"><span data-stu-id="6ec02-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="6ec02-108">Beginnen Sie mit der **Registerkarte Benutzer** für einen Vorfall von & Warnungen **>** *Vorfall* **> Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="6ec02-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Beispiel einer Benutzerseite für einen Vorfall":::

<span data-ttu-id="6ec02-110">Um eine kurze Zusammenfassung eines Benutzerkontos für den Vorfall zu erhalten, aktivieren Sie das Kontrollkästchen neben dem Benutzernamen.</span><span class="sxs-lookup"><span data-stu-id="6ec02-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="6ec02-111">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6ec02-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Beispiel für den Zusammenfassungsbereich des Benutzerkontos für einen Vorfall im Microsoft 365 Security Center":::

> [!NOTE]
> <span data-ttu-id="6ec02-113">Auf der Seite Benutzer werden die Azure Active Directory (AD)-Organisation sowie Gruppen angezeigt, die Ihnen dabei helfen, die Gruppen und Berechtigungen zu verstehen, die einem Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6ec02-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="6ec02-114">Auf dieser Fly-Out-Seite können Sie Informationen zu Benutzerbedrohungen überprüfen, einschließlich aktueller Vorfälle, aktiver Warnungen und Risikostufe sowie benutzerexposition, Konten, Geräte und mehr.</span><span class="sxs-lookup"><span data-stu-id="6ec02-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="6ec02-115">Darüber hinaus können Sie direkt im Microsoft 365 Security Center Maßnahmen ergreifen, um einen gefährdeten Benutzer zu adressieren, um zu bestätigen, dass der Benutzer gefährdet ist oder dass er sich erneut anmelden muss.</span><span class="sxs-lookup"><span data-stu-id="6ec02-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="6ec02-116">Hier können Sie zur Benutzerseite wechseln **auswählen,** um die Details eines Benutzerkontos anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6ec02-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="6ec02-117">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6ec02-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Beispiel für die Benutzerkontoseite für einen Vorfall im Microsoft 365 Security Center":::

<span data-ttu-id="6ec02-119">Sie können diese Seite auch anzeigen, indem Sie den Namen des Benutzerkontos aus der Liste auf der Seite **Benutzer** auswählen.</span><span class="sxs-lookup"><span data-stu-id="6ec02-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="6ec02-120">Die Microsoft 365 Security Center-Benutzerseite kombiniert Informationen von Microsoft Defender for Endpoint, Microsoft Defender for Identity und Microsoft Cloud App Security (je nachdem, welche Lizenzen Sie besitzen).</span><span class="sxs-lookup"><span data-stu-id="6ec02-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="6ec02-121">Diese Seite enthält Informationen, die speziell für das Sicherheitsrisiko eines Benutzerkontos spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="6ec02-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="6ec02-122">Dies umfasst eine Bewertung, die bei der Bewertung von Risiken und aktuellen Ereignissen und Warnungen hilft, die zum Gesamtrisiko des Benutzers beigetragen haben.</span><span class="sxs-lookup"><span data-stu-id="6ec02-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="6ec02-123">Auf dieser Seite können Sie die folgenden zusätzlichen Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="6ec02-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="6ec02-124">Kennzeichnen des Benutzerkontos als gefährdet</span><span class="sxs-lookup"><span data-stu-id="6ec02-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="6ec02-125">Benutzer erneut anmelden</span><span class="sxs-lookup"><span data-stu-id="6ec02-125">Require the user to sign in again</span></span>
- <span data-ttu-id="6ec02-126">Anhalten des Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="6ec02-126">Suspend the user account</span></span>
- <span data-ttu-id="6ec02-127">Weitere Informationen finden Sie unter Azure Active Directory (Azure AD)-Benutzerkonteneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6ec02-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="6ec02-128">Anzeigen der Dateien im Besitz des Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="6ec02-128">View the files owned by the user account</span></span>
- <span data-ttu-id="6ec02-129">Anzeigen von Dateien, die für diesen Benutzer freigegeben sind.</span><span class="sxs-lookup"><span data-stu-id="6ec02-129">View files shared with this user.</span></span> 

<span data-ttu-id="6ec02-130">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6ec02-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Beispiel für die Aktionen für ein Benutzerkonto für einen Vorfall im Microsoft 365 Security Center":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="6ec02-132">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6ec02-132">Related topics</span></span>

- [<span data-ttu-id="6ec02-133">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="6ec02-133">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6ec02-134">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="6ec02-134">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="6ec02-135">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="6ec02-135">Manage incidents</span></span>](manage-incidents.md)