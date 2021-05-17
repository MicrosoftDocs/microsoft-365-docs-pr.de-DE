---
title: Microsoft Teams
description: So wird Teams auf Geräten installiert und anschließend aktualisiert
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, Apps, Branchen-Apps, Branchen-Apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920656"
---
# <a name="microsoft-teams"></a><span data-ttu-id="e5ebd-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e5ebd-104">Microsoft Teams</span></span>

<span data-ttu-id="e5ebd-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) ist eine [Messaging-App](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) für Ihre Organisation, die auch einen Arbeitsbereich für Zusammenarbeit und Kommunikation in Echtzeit, Besprechungen sowie Datei- und App-Freigabe bietet.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="e5ebd-106">Erstbereitstellung</span><span class="sxs-lookup"><span data-stu-id="e5ebd-106">Initial deployment</span></span>

<span data-ttu-id="e5ebd-107">Die meisten Hardwareanbieter enthalten teams noch nicht als Teil ihrer Bilder, daher stellt Microsoft Managed Desktop Teams mithilfe von Microsoft Intune auf Ihren Geräten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="e5ebd-108">Auf allen verwalteten Geräten ist [das Teams .msi installiert,](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) um sicherzustellen, dass alle Benutzer, die sich bei einem Gerät anmelden, Microsoft Teams einsatzbereit sind.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-108">All managed devices have the [Teams .msi package](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="e5ebd-109">Wenn das Paket zum ersten Mal installiert ist, wird Teams automatisch gestartet und dem Desktop eine Verknüpfung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="e5ebd-110">Änderungen an Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e5ebd-110">Microsoft Intune changes</span></span>

<span data-ttu-id="e5ebd-111">Microsoft Managed Desktop fügt Ihrer Azure AD-Organisation für Microsoft Teams zwei Anwendungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="e5ebd-112">Sie werden auf 64-Bit- oder 32-Bit-Clients bereitgestellt, wie für das Gerät geeignet:</span><span class="sxs-lookup"><span data-stu-id="e5ebd-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="e5ebd-113">Moderner Arbeitsplatz – Teams Machine Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="e5ebd-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="e5ebd-114">Moderner Arbeitsplatz – Teams Machine Wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="e5ebd-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="e5ebd-115">Updates</span><span class="sxs-lookup"><span data-stu-id="e5ebd-115">Updates</span></span>

<span data-ttu-id="e5ebd-116">Teams folgt einem separaten Updatepfad von Microsoft 365 Apps for Enterprise, und der Desktopclient aktualisiert sich automatisch selbst.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="e5ebd-117">Teams sucht alle paar Stunden nach Updates, lädt sie herunter und wartet dann, bis sich der Computer im Leerlauf befindet, bevor das Update automatisch installiert wird.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="e5ebd-118">Die Microsoft Teams-Produktgruppe lässt Administratoren die Kontrolle über Updates nicht zu, sodass Microsoft Managed Desktop den standardmäßigen automatischen [Updatekanal verwendet.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)</span><span class="sxs-lookup"><span data-stu-id="e5ebd-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="e5ebd-119">Manuelles Aktualisieren von Teams</span><span class="sxs-lookup"><span data-stu-id="e5ebd-119">Manually updating Teams</span></span>

<span data-ttu-id="e5ebd-120">Einzelne Benutzer können updates auch herunterladen, indem Sie im Dropdownmenü Profil oben rechts in der App auf Updates   überprüfen \*\*\*\*   klicken.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="e5ebd-121">Wenn ein Update verfügbar ist, wird es heruntergeladen und automatisch installiert, wenn sich der Computer im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="e5ebd-122">Übermittlungsoptimierung von Updates</span><span class="sxs-lookup"><span data-stu-id="e5ebd-122">Delivery optimization of updates</span></span>

<span data-ttu-id="e5ebd-123">Die Übermittlungsoptimierung für Teams-Updates ist standardmäßig aktiviert und erfordert keine Aktion von Administratoren oder Benutzern.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span>