---
title: Entfernen von Geräten
description: Entfernen von Geräten aus Microsoft Managed Desktop Verwaltung
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893815"
---
# <a name="remove-devices"></a><span data-ttu-id="d5501-103">Entfernen von Geräten</span><span class="sxs-lookup"><span data-stu-id="d5501-103">Remove devices</span></span>

<span data-ttu-id="d5501-104">Sie können Geräte aus Microsoft Managed Desktop Verwaltung entfernen, indem Sie das Administratorportal verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5501-104">You can remove devices from Microsoft Managed Desktop management by using the Admin portal.</span></span> <span data-ttu-id="d5501-105">Diese Aktion ist dauerhaft, Sie können sie jedoch erneut Microsoft Managed Desktop registrieren, indem Sie die [Registrierungsschritte ausführen.](../get-started/register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="d5501-105">This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [registration steps](../get-started/register-devices-self.md).</span></span>

<span data-ttu-id="d5501-106">Wenn Sie ein Gerät entfernen, treten alle folgenden Schritte auf:</span><span class="sxs-lookup"><span data-stu-id="d5501-106">When you remove a device, all of the following occur:</span></span>

- <span data-ttu-id="d5501-107">Wir entfernen das Gerät aus Autopilot.</span><span class="sxs-lookup"><span data-stu-id="d5501-107">We remove the device from Autopilot.</span></span>
- <span data-ttu-id="d5501-108">Wir entfernen das Gerät aus allen "Modern Workplace"-Gerätegruppen.</span><span class="sxs-lookup"><span data-stu-id="d5501-108">We remove the device from  all "Modern Workplace" device groups.</span></span>
- <span data-ttu-id="d5501-109">Wir entfernen das Gerät aus dem **Blatt Geräte** im Administratorportal.</span><span class="sxs-lookup"><span data-stu-id="d5501-109">We remove the device from the **Devices** blade in the Admin portal.</span></span>

<span data-ttu-id="d5501-110">Wenn Sie ein Gerät entfernen, haben Sie die Möglichkeit, es auch aus Azure Active Directory (Azure AD) und Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d5501-110">When you remove a device, you have the option to also remove it from Azure Active Directory (Azure AD) and Microsoft Intune.</span></span>
 
> [!CAUTION]
> <span data-ttu-id="d5501-111">Das Entfernen der Objekte im Zusammenhang mit einem Gerät aus Azure AD und Microsoft Intune ist dauerhaft.</span><span class="sxs-lookup"><span data-stu-id="d5501-111">Removing the objects related to a device from Azure AD and Microsoft Intune is permanent.</span></span> <span data-ttu-id="d5501-112">Wenn Sie die Objekte entfernen, können Sie die Geräte nicht in den Intune- und Azure-Portalen anzeigen oder verwalten.</span><span class="sxs-lookup"><span data-stu-id="d5501-112">If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals.</span></span> <span data-ttu-id="d5501-113">Die Geräte können nicht auf die Unternehmensressourcen ihres Unternehmens zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d5501-113">The devices won't be able to access their company's corporate resources.</span></span> <span data-ttu-id="d5501-114">Unternehmensdaten werden möglicherweise aus ihnen gelöscht, wenn die Geräte versuchen, sich nach dem Löschen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d5501-114">Company data might be deleted from them if the devices try to sign in after they're deleted.</span></span>

1. <span data-ttu-id="d5501-115">Wählen [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)im linken **Navigationsbereich** Geräte aus.</span><span class="sxs-lookup"><span data-stu-id="d5501-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span>
2. <span data-ttu-id="d5501-116">Suchen Sie nach **Microsoft Managed Desktop** im Menü, und wählen Sie **Geräte aus.**</span><span class="sxs-lookup"><span data-stu-id="d5501-116">Look for the **Microsoft Managed Desktop** section of the menu and select **Devices**.</span></span>
3. <span data-ttu-id="d5501-117">Wählen Sie im Microsoft Managed Desktop Arbeitsbereich Geräte die Geräte aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="d5501-117">In the Microsoft Managed Desktop Devices workspace, select the devices you want to delete.</span></span>
4. <span data-ttu-id="d5501-118">Wählen **Sie Geräteaktionen** aus, und wählen Sie dann **Gerät löschen aus,** das ein Fly-In öffnet, um die Geräte zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d5501-118">Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.</span></span>
5. <span data-ttu-id="d5501-119">Überprüfen Sie im Fly-In die ausgewählten Geräte, und wählen Sie **dann Geräte entfernen aus.**</span><span class="sxs-lookup"><span data-stu-id="d5501-119">In the fly-in, review the selected devices and then select **Remove devices**.</span></span> <span data-ttu-id="d5501-120">Wenn Sie gleichzeitig auch die Azure AD- und Intune-Objekte entfernen möchten, aktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="d5501-120">If you want to also remove the Azure AD and Intune objects at the same time, select the check box.</span></span> <span data-ttu-id="d5501-121">Die Geräteentfernung kann einige Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="d5501-121">Device removal can take a few minutes to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="d5501-122">Geräte, die sich in einem ausstehenden Registrierungsstatus befinden, können **nicht** entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d5501-122">You can't remove devices that are in a **pending** registration state.</span></span>