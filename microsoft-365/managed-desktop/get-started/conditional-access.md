---
title: Bedingten Zugriff anpassen
description: Ausschließen bestimmter Microsoft-Konten
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1bc5d937616cba60c5af43fe22a7c4dccf89a55e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085805"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="2f83a-104">Bedingten Zugriff anpassen</span><span class="sxs-lookup"><span data-stu-id="2f83a-104">Adjust conditional access</span></span>

<span data-ttu-id="2f83a-105">Wenn Sie Richtlinien für [bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) in Ihrer Organisation verwenden, müssen Sie diese so festlegen, dass bestimmte Konten ausgeschlossen werden, damit Microsoft Managed Desktop ordnungsgemäß ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2f83a-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="2f83a-106">Führen Sie hierzu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2f83a-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="2f83a-107">Weitere Informationen finden Sie im Abschnitt "Rollback Steps" unter [Vorgehensweise: Planen der Bereitstellung des bedingten Zugriffs in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span><span class="sxs-lookup"><span data-stu-id="2f83a-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="2f83a-108">Führen Sie die folgenden Schritte aus, um die Gruppe der *modernen Arbeitsplatz-Dienstkonten* für alle Richtlinien auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="2f83a-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="2f83a-109">Wenn Sie Probleme mit dem bedingten Zugriff haben, wenden Sie sich an den Administrator [Support](../working-with-managed-desktop/admin-support.md).</span><span class="sxs-lookup"><span data-stu-id="2f83a-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="2f83a-110">Schritte zum Einstieg in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2f83a-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="2f83a-111">Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal</span><span class="sxs-lookup"><span data-stu-id="2f83a-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="2f83a-112">Anpassen des bedingten Zugriffs (dieses Thema)</span><span class="sxs-lookup"><span data-stu-id="2f83a-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="2f83a-113">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="2f83a-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="2f83a-114">Intune-Unternehmensportal bereitstellen</span><span class="sxs-lookup"><span data-stu-id="2f83a-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="2f83a-115">Aktivieren von Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="2f83a-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="2f83a-116">Einrichten von Geräten</span><span class="sxs-lookup"><span data-stu-id="2f83a-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="2f83a-117">Vorbereiten Ihrer Benutzer für die Verwendung von Geräten</span><span class="sxs-lookup"><span data-stu-id="2f83a-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="2f83a-118">Bereitstellen von Apps</span><span class="sxs-lookup"><span data-stu-id="2f83a-118">Deploy apps</span></span>](deploy-apps.md)
