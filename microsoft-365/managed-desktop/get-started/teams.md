---
title: Microsoft Teams
description: Wie Teams auf Geräten installiert und anschließend aktualisiert werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, apps, Branchenanwendungen, Lob-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950939"
---
# <a name="microsoft-teams"></a><span data-ttu-id="ce287-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce287-104">Microsoft Teams</span></span>

<span data-ttu-id="ce287-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) ist eine [Messaging-App](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) für Ihre Organisation, die auch einen Arbeitsbereich für die Zusammenarbeit und Kommunikation in Echtzeit, Besprechungen sowie die Datei-und App-Freigabe bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ce287-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="ce287-106">Erstbereitstellung</span><span class="sxs-lookup"><span data-stu-id="ce287-106">Initial deployment</span></span>

<span data-ttu-id="ce287-107">Die meisten Hardwareanbieter enthalten noch keine Teams als Bestandteil ihrer Images, sodass Microsoft Managed Desktop Teams auf Ihren Geräten mithilfe von Microsoft InTune bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ce287-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="ce287-108">Auf allen verwalteten Geräten ist das [Paket "Teams. msi](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) " installiert, um sicherzustellen, dass alle Benutzer, die sich bei einem Gerät anmelden, Microsoft Teams für die Verwendung bereit haben.</span><span class="sxs-lookup"><span data-stu-id="ce287-108">All managed devices have the [Teams .msi package](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="ce287-109">Wenn das Paket zuerst die Installation abgeschlossen hat, werden die Teams automatisch gestartet und eine Verknüpfung zum Desktop hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ce287-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="ce287-110">Änderungen an Microsoft InTune</span><span class="sxs-lookup"><span data-stu-id="ce287-110">Microsoft Intune changes</span></span>

<span data-ttu-id="ce287-111">Microsoft Managed Desktop fügt Ihrer Azure AD Organisation für Microsoft Teams zwei Anwendungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="ce287-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="ce287-112">Sie werden entweder auf 64-Bit-oder 32-Bit-Clients bereitgestellt, je nach Bedarf des Geräts:</span><span class="sxs-lookup"><span data-stu-id="ce287-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="ce287-113">Moderner Arbeitsplatz – Teams Machine Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="ce287-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="ce287-114">Moderner Arbeitsplatz – Teams Machine Wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="ce287-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="ce287-115">Updates</span><span class="sxs-lookup"><span data-stu-id="ce287-115">Updates</span></span>

<span data-ttu-id="ce287-116">Teams folgt einem separaten Aktualisierungspfad von Microsoft 365 apps for Enterprise, und der Desktop Client aktualisiert sich automatisch.</span><span class="sxs-lookup"><span data-stu-id="ce287-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="ce287-117">Microsoft Teams überprüft alle paar Stunden nach Updates, lädt Sie herunter und wartet dann darauf, dass der Computer im Leerlauf ist, bevor das Update automatisch installiert wird.</span><span class="sxs-lookup"><span data-stu-id="ce287-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="ce287-118">Die Teams-Produktgruppe erlaubt Administratoren nicht, Updates zu steuern, sodass der [standardmäßige automatische Update Kanal](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)von Microsoft Managed Desktop verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ce287-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="ce287-119">Manuelles Aktualisieren von Teams</span><span class="sxs-lookup"><span data-stu-id="ce287-119">Manually updating Teams</span></span>

<span data-ttu-id="ce287-120">Einzelne Benutzer können Updates auch herunterladen, indem **Sie**im   Dropdownmenü **Profil**auf der   rechten oberen Ecke der APP nach Updates suchen auswählen.</span><span class="sxs-lookup"><span data-stu-id="ce287-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="ce287-121">Wenn ein Update verfügbar ist, wird es heruntergeladen und automatisch installiert, wenn sich der Computer im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="ce287-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="ce287-122">Zustellungsoptimierung von Updates</span><span class="sxs-lookup"><span data-stu-id="ce287-122">Delivery optimization of updates</span></span>

<span data-ttu-id="ce287-123">Die Zustellungsoptimierung für Microsoft Teams-Updates ist standardmäßig aktiviert und erfordert keine Aktion von Administratoren oder Benutzern.</span><span class="sxs-lookup"><span data-stu-id="ce287-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span> 