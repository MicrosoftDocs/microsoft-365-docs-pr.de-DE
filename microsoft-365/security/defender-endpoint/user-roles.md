---
title: Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung
description: Erstellen von Rollen und Definieren der Berechtigungen, die der Rolle als Teil der rollenbasierten Zugriffssteuerungsimplementierung im Microsoft Defender Security Center zugewiesen sind
keywords: Benutzerrollen, Rollen, Access rbac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065951"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a><span data-ttu-id="0eaa0-104">Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="0eaa0-104">Create and manage roles for role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0eaa0-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0eaa0-105">**Applies to:**</span></span>
- [<span data-ttu-id="0eaa0-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0eaa0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="0eaa0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0eaa0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0eaa0-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0eaa0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0eaa0-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a><span data-ttu-id="0eaa0-110">Erstellen von Rollen und Zuweisen der Rolle zu einer Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="0eaa0-110">Create roles and assign the role to an Azure Active Directory group</span></span>

<span data-ttu-id="0eaa0-111">In den folgenden Schritten erfahren Sie, wie Sie Rollen in Microsoft Defender Security Center erstellen.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-111">The following steps guide you on how to create roles in Microsoft Defender Security Center.</span></span> <span data-ttu-id="0eaa0-112">Es wird davon ausgegangen, dass Sie bereits Azure Active Directory-Benutzergruppen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-112">It assumes that you have already created Azure Active Directory user groups.</span></span>

1. <span data-ttu-id="0eaa0-113">Melden Sie sich [beim Microsoft Defender Security Center mit](https://securitycenter.windows.com/) einem Konto an, dem ein Sicherheitsadministrator oder eine globale Administratorrolle zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-113">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with a Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="0eaa0-114">Wählen Sie im Navigationsbereich Einstellungen **> Rollen aus.**</span><span class="sxs-lookup"><span data-stu-id="0eaa0-114">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="0eaa0-115">Wählen **Sie Element hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="0eaa0-115">Select **Add item**.</span></span>

4. <span data-ttu-id="0eaa0-116">Geben Sie den Rollennamen, die Beschreibung und die Berechtigungen ein, die Sie der Rolle zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-116">Enter the role name, description, and permissions you'd like to assign to the role.</span></span>

5. <span data-ttu-id="0eaa0-117">Wählen **Sie Weiter** aus, um die Rolle einer Azure AD-Sicherheitsgruppe zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-117">Select **Next** to assign the role to an Azure AD Security group.</span></span>

6. <span data-ttu-id="0eaa0-118">Verwenden Sie den Filter, um die Azure AD-Gruppe auszuwählen, die Sie dieser Rolle hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-118">Use the filter to select the Azure AD group that you'd like to add to this role to.</span></span>

7. <span data-ttu-id="0eaa0-119">**Speichern und schließen** Sie .</span><span class="sxs-lookup"><span data-stu-id="0eaa0-119">**Save and close**.</span></span>

8. <span data-ttu-id="0eaa0-120">Wenden Sie die Konfigurationseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-120">Apply the configuration settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0eaa0-121">Nach dem Erstellen von Rollen müssen Sie eine Gerätegruppe erstellen und zugriff auf die Gerätegruppe bereitstellen, indem Sie sie einer Rolle zuweisen, die Sie gerade erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-121">After creating roles, you'll need to create a device group and provide access to the device group by assigning it to a role that you just created.</span></span>

### <a name="permission-options"></a><span data-ttu-id="0eaa0-122">Berechtigungsoptionen</span><span class="sxs-lookup"><span data-stu-id="0eaa0-122">Permission options</span></span>

- <span data-ttu-id="0eaa0-123">**Anzeigen von Daten**</span><span class="sxs-lookup"><span data-stu-id="0eaa0-123">**View data**</span></span>
    - <span data-ttu-id="0eaa0-124">**Sicherheitsvorgänge** – Anzeigen aller Daten zu Sicherheitsvorgängen im Portal</span><span class="sxs-lookup"><span data-stu-id="0eaa0-124">**Security operations** - View all security operations data in the portal</span></span>
    - <span data-ttu-id="0eaa0-125">**Bedrohungs- und Sicherheitsrisikoverwaltung** – Anzeigen von Daten zur Verwaltung von Bedrohungen und Sicherheitslücken im Portal</span><span class="sxs-lookup"><span data-stu-id="0eaa0-125">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

- <span data-ttu-id="0eaa0-126">**Aktive Korrekturaktionen**</span><span class="sxs-lookup"><span data-stu-id="0eaa0-126">**Active remediation actions**</span></span>
    - <span data-ttu-id="0eaa0-127">**Sicherheitsvorgänge** – Ergreifen von Reaktionsaktionen, Genehmigen oder Schließen ausstehender Korrekturaktionen, Verwalten zulässiger/blockierter Listen für Automatisierung und Indikatoren</span><span class="sxs-lookup"><span data-stu-id="0eaa0-127">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
    - <span data-ttu-id="0eaa0-128">**Bedrohungs- und Sicherheitsrisikoverwaltung – Ausnahmebehandlung** – Erstellen neuer Ausnahmen und Verwalten aktiver Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="0eaa0-128">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
    - <span data-ttu-id="0eaa0-129">**Bedrohungs- und Sicherheitsrisikoverwaltung – Behandlung** von Abhilfemaßnahmen – Übermitteln neuer Behebungsanforderungen, Erstellen von Tickets und Verwalten vorhandener Abhilfemaßnahmen</span><span class="sxs-lookup"><span data-stu-id="0eaa0-129">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

- <span data-ttu-id="0eaa0-130">**Warnungsuntersuchung** : Verwalten von Warnungen, Initiieren automatisierter Untersuchungen, Ausführen von Scans, Sammeln von Untersuchungspaketen, Verwalten von Gerätetags und Herunterladen nur portabler ausführbarer Dateien (PE)</span><span class="sxs-lookup"><span data-stu-id="0eaa0-130">**Alerts investigation** - Manage alerts, initiate automated investigations, run scans, collect investigation packages, manage device tags, and download only portable executable (PE) files</span></span> 

- <span data-ttu-id="0eaa0-131">**Verwalten von Portalsystemeinstellungen** : Konfigurieren von Speichereinstellungen, SIEM- und Bedrohungs-INTEL-API-Einstellungen (gilt global), erweiterten Einstellungen, automatisierten Dateiuploads, Rollen und Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="0eaa0-131">**Manage portal system settings** - Configure storage settings, SIEM and threat intel API settings (applies globally), advanced settings, automated file uploads, roles and device groups</span></span>

    > [!NOTE]
    > <span data-ttu-id="0eaa0-132">Diese Einstellung ist nur in der Microsoft Defender for Endpoint-Administratorrolle (Standard) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-132">This setting is only available in the Microsoft Defender for Endpoint administrator (default) role.</span></span>

- <span data-ttu-id="0eaa0-133">**Verwalten von Sicherheitseinstellungen im Security Center** – Konfigurieren von Einstellungen für die Warnungsunterdrückung, Verwalten von Ordnerausschlüssen für Automatisierungs-, Onboard- und Offboardgeräte sowie Verwalten von E-Mail-Benachrichtigungen, Verwalten der Evaluierungsumgebung</span><span class="sxs-lookup"><span data-stu-id="0eaa0-133">**Manage security settings in Security Center** - Configure alert suppression settings, manage folder exclusions for automation, onboard and offboard devices, and manage email notifications, manage evaluation lab</span></span>

- <span data-ttu-id="0eaa0-134">**Liveantwortfunktionen**</span><span class="sxs-lookup"><span data-stu-id="0eaa0-134">**Live response capabilities**</span></span>
    - <span data-ttu-id="0eaa0-135">**Grundlegende** Befehle:</span><span class="sxs-lookup"><span data-stu-id="0eaa0-135">**Basic** commands:</span></span>
        - <span data-ttu-id="0eaa0-136">Starten einer Liveantwortsitzung</span><span class="sxs-lookup"><span data-stu-id="0eaa0-136">Start a live response session</span></span>
        - <span data-ttu-id="0eaa0-137">Ausführen von schreibgeschützten Liveantwortbefehlen auf einem Remotegerät (ohne Dateikopie und Ausführung)</span><span class="sxs-lookup"><span data-stu-id="0eaa0-137">Perform read only live response commands on remote device (excluding file copy and execution</span></span>
    - <span data-ttu-id="0eaa0-138">**Erweiterte** Befehle:</span><span class="sxs-lookup"><span data-stu-id="0eaa0-138">**Advanced** commands:</span></span>
        - <span data-ttu-id="0eaa0-139">Herunterladen einer Datei vom Remotegerät per Liveantwort</span><span class="sxs-lookup"><span data-stu-id="0eaa0-139">Download a file from the remote device via live response</span></span>
        - <span data-ttu-id="0eaa0-140">Herunterladen von PE- und Nicht-PE-Dateien von der Dateiseite</span><span class="sxs-lookup"><span data-stu-id="0eaa0-140">Download PE and non-PE files from the file page</span></span>
        - <span data-ttu-id="0eaa0-141">Hochladen einer Datei auf das Remotegerät</span><span class="sxs-lookup"><span data-stu-id="0eaa0-141">Upload a file to the remote device</span></span>
        - <span data-ttu-id="0eaa0-142">Anzeigen eines Skripts aus der Dateibibliothek</span><span class="sxs-lookup"><span data-stu-id="0eaa0-142">View a script from the files library</span></span>
        - <span data-ttu-id="0eaa0-143">Ausführen eines Skripts auf dem Remotegerät aus der Dateibibliothek</span><span class="sxs-lookup"><span data-stu-id="0eaa0-143">Execute a script on the remote device from the files library</span></span>

<span data-ttu-id="0eaa0-144">Weitere Informationen zu den verfügbaren Befehlen finden Sie unter [Untersuchen von Geräten mithilfe der Liveantwort](live-response.md).</span><span class="sxs-lookup"><span data-stu-id="0eaa0-144">For more information on the available commands, see [Investigate devices using Live response](live-response.md).</span></span>
  
## <a name="edit-roles"></a><span data-ttu-id="0eaa0-145">Bearbeiten von Rollen</span><span class="sxs-lookup"><span data-stu-id="0eaa0-145">Edit roles</span></span>

1. <span data-ttu-id="0eaa0-146">Melden Sie sich [beim Microsoft Defender Security Center mithilfe eines](https://securitycenter.windows.com/) Kontos an, dem der Sicherheitsadministrator oder die globale Administratorrolle zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-146">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="0eaa0-147">Wählen Sie im Navigationsbereich Einstellungen **> Rollen aus.**</span><span class="sxs-lookup"><span data-stu-id="0eaa0-147">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="0eaa0-148">Wählen Sie die Rolle aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-148">Select the role you'd like to edit.</span></span>

4. <span data-ttu-id="0eaa0-149">Klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-149">Click **Edit**.</span></span>

5. <span data-ttu-id="0eaa0-150">Ändern Sie die Details oder Gruppen, die der Rolle zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-150">Modify the details or the groups that are assigned to the role.</span></span> 

6. <span data-ttu-id="0eaa0-151">Klicken **Sie auf Speichern und schließen.**</span><span class="sxs-lookup"><span data-stu-id="0eaa0-151">Click **Save and close**.</span></span>

## <a name="delete-roles"></a><span data-ttu-id="0eaa0-152">Löschen von Rollen</span><span class="sxs-lookup"><span data-stu-id="0eaa0-152">Delete roles</span></span>

1. <span data-ttu-id="0eaa0-153">Melden Sie sich [beim Microsoft Defender Security Center mithilfe eines](https://securitycenter.windows.com/) Kontos an, dem der Sicherheitsadministrator oder die globale Administratorrolle zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-153">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="0eaa0-154">Wählen Sie im Navigationsbereich Einstellungen **> Rollen aus.**</span><span class="sxs-lookup"><span data-stu-id="0eaa0-154">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="0eaa0-155">Wählen Sie die Rolle aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="0eaa0-155">Select the role you'd like to delete.</span></span>

4. <span data-ttu-id="0eaa0-156">Klicken Sie auf die Dropdownschaltfläche, und wählen Sie **Rolle löschen aus.**</span><span class="sxs-lookup"><span data-stu-id="0eaa0-156">Click the drop-down button and select **Delete role**.</span></span>

## <a name="related-topic"></a><span data-ttu-id="0eaa0-157">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="0eaa0-157">Related topic</span></span>

- [<span data-ttu-id="0eaa0-158">Grundlegende Benutzerberechtigungen für den Zugriff auf das Portal</span><span class="sxs-lookup"><span data-stu-id="0eaa0-158">User basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="0eaa0-159">Erstellen und Verwalten von Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="0eaa0-159">Create and manage device groups</span></span>](machine-groups.md)
