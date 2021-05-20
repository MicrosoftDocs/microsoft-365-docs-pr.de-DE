---
title: Untersuchen von Benutzern in Microsoft 365 Defender
description: Untersuchen Sie Benutzer auf einen Vorfall im Microsoft 365 Sicherheitscenter.
keywords: Sicherheit, Malware, Microsoft 365, M365, Sicherheitscenter, Monitor, Bericht, Identitäten, Daten, Geräte, Apps, Vorfall, Analysieren, Reagieren
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
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572801"
---
# <a name="investigate-users-in-microsoft-365-defender"></a><span data-ttu-id="370d7-104">Untersuchen von Benutzern in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="370d7-104">Investigate users in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="370d7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="370d7-105">**Applies to:**</span></span>

- <span data-ttu-id="370d7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="370d7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="370d7-107">Ein Teil Ihrer Vorfalluntersuchung kann Benutzerkonten umfassen.</span><span class="sxs-lookup"><span data-stu-id="370d7-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="370d7-108">Beginnen Sie mit der Registerkarte **Benutzer** für einen Vorfall aus **Vorfällen & Warnungen >** *>* **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="370d7-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Beispiel für eine Benutzerseite für einen Vorfall":::

<span data-ttu-id="370d7-110">Um eine kurze Zusammenfassung eines Benutzerkontos für den Vorfall zu erhalten, wählen Sie das Häkchen neben dem Benutzernamen aus.</span><span class="sxs-lookup"><span data-stu-id="370d7-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="370d7-111">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="370d7-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Beispiel für den Zusammenfassungsbereich des Benutzerkontos für einen Vorfall im Microsoft 365 Sicherheitscenter":::

> [!NOTE]
> <span data-ttu-id="370d7-113">Auf der Seite Benutzer werden Azure Active Directory (Azure AD)-Organisation sowie Gruppen angezeigt, die Ihnen helfen, die Gruppen und Berechtigungen zu verstehen, die einem Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="370d7-113">The User page shows Azure Active Directory (Azure AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="370d7-114">Auf dieser Fly-Out-Seite können Sie Informationen zu Benutzerbedrohungen überprüfen, einschließlich aktueller Vorfälle, aktiver Warnungen und Risikostufen sowie Benutzerexposition, Konten, Geräte und mehr.</span><span class="sxs-lookup"><span data-stu-id="370d7-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="370d7-115">Darüber hinaus können Sie direkt im Microsoft 365 Sicherheitscenter Maßnahmen ergreifen, um einen kompromittierten Benutzer zu adressieren, zu bestätigen, dass der Benutzer kompromittiert ist, oder dass er sich erneut anmelden muss.</span><span class="sxs-lookup"><span data-stu-id="370d7-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="370d7-116">Von hier aus können Sie die **Seite Zur Benutzerseite** wechseln auswählen, um die Details eines Benutzerkontos anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="370d7-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="370d7-117">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="370d7-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Beispiel für die Benutzerkontoseite für einen Vorfall im Microsoft 365 Sicherheitscenter":::

<span data-ttu-id="370d7-119">Sie können diese Seite auch anzeigen, indem Sie den Namen des Benutzerkontos aus der Liste auf der Seite **Benutzer** auswählen.</span><span class="sxs-lookup"><span data-stu-id="370d7-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="370d7-120">Die Benutzerseite Microsoft 365 Security Center kombiniert Informationen von Microsoft Defender for Endpoint, Microsoft Defender for Identity und Microsoft Cloud App Security (je nachdem, welche Lizenzen Sie haben).</span><span class="sxs-lookup"><span data-stu-id="370d7-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="370d7-121">Auf dieser Seite werden Informationen angezeigt, die speziell auf das Sicherheitsrisiko eines Benutzerkontos zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="370d7-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="370d7-122">Dazu gehört eine Bewertung, mit der Risiken und aktuelle Ereignisse und Warnungen bewertet werden, die zum Gesamtrisiko des Benutzers beigetragen haben.</span><span class="sxs-lookup"><span data-stu-id="370d7-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="370d7-123">Auf dieser Seite können Sie die folgenden zusätzlichen Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="370d7-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="370d7-124">Das Benutzerkonto als kompromittiert markieren</span><span class="sxs-lookup"><span data-stu-id="370d7-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="370d7-125">Den Benutzer zur erneuten Anmeldung auffordern, sich anzumelden</span><span class="sxs-lookup"><span data-stu-id="370d7-125">Require the user to sign in again</span></span>
- <span data-ttu-id="370d7-126">Sperren des Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="370d7-126">Suspend the user account</span></span>
- <span data-ttu-id="370d7-127">Informationen zu den Azure Active Directory-Benutzerkontoeinstellungen (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="370d7-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="370d7-128">Anzeigen der Dateien, die im Besitz des Benutzerkontos sind</span><span class="sxs-lookup"><span data-stu-id="370d7-128">View the files owned by the user account</span></span>
- <span data-ttu-id="370d7-129">Zeigen Sie Dateien an, die für diesen Benutzer freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="370d7-129">View files shared with this user.</span></span> 

<span data-ttu-id="370d7-130">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="370d7-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Beispiel für aktionen in einem Benutzerkonto für einen Vorfall im Microsoft 365 Sicherheitscenter":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="370d7-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="370d7-132">Next steps</span></span>

<span data-ttu-id="370d7-133">Setzen Sie die [Untersuchung](investigate-incidents.md)bei Bedarf für Prozessvorfälle fort.</span><span class="sxs-lookup"><span data-stu-id="370d7-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="370d7-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="370d7-134">See also</span></span>

- [<span data-ttu-id="370d7-135">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="370d7-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="370d7-136">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="370d7-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="370d7-137">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="370d7-137">Manage incidents</span></span>](manage-incidents.md)