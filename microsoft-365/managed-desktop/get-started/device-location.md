---
title: Standortdienst für Windows 10
description: So können Sie Windows Standortdienste für Ihre Geräte aktiviert haben
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
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
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929499"
---
# <a name="windows-10-location-service"></a><span data-ttu-id="5b696-104">Standortdienst für Windows 10</span><span class="sxs-lookup"><span data-stu-id="5b696-104">Windows 10 location service</span></span>

<span data-ttu-id="5b696-105">Geräte in Microsoft Managed Desktop werden mithilfe von autopilot Windows registriert.</span><span class="sxs-lookup"><span data-stu-id="5b696-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="5b696-106">Bei diesem Prozess können wir sie mit Azure Active Directory und Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5b696-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="5b696-107">Standardmäßig ist Windows 10 Standortdienst deaktiviert, wenn ein Gerät zum ersten Mal aktiviert ist, es sei denn, dieses Feature ist während der "out-of-box"-Erfahrung in den Datenschutzeinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5b696-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="5b696-108">Diese Einstellungen werden während der Autopilot-Registrierung in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5b696-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="5b696-109">Weitere Informationen zum Einrichten von Autopilot finden Sie unter [First-run experience with Autopilot und the Enrollment Status Page](esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="5b696-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="5b696-110">Aus diesem Grund Microsoft Managed Desktop Geräte ihren Gerätespeicherort nicht abrufen, was die Funktionalität mehrerer Windows, z. B. Zeitzonen, einschränkt.</span><span class="sxs-lookup"><span data-stu-id="5b696-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="5b696-111">Weitere Informationen zum Standortdienst Windows 10 finden Sie [unter Windows 10 Standortdienst und Datenschutz](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span><span class="sxs-lookup"><span data-stu-id="5b696-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="5b696-112">Sie müssen den Standortdienst nicht verwenden, um an Microsoft Managed Desktop teilzunehmen, aber die Benutzeroberfläche wird eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="5b696-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="5b696-113">Beispielsweise können Geräte nicht automatisch die Zeitzone bestimmen, in der sie sich befinden, wenn Ihre Benutzer in einer anderen Zeitzone arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5b696-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="5b696-114">Aktivieren des Standortdiensts</span><span class="sxs-lookup"><span data-stu-id="5b696-114">Enable the location service</span></span>

<span data-ttu-id="5b696-115">Sie können sich entweder für die Verwendung des Standortdiensts entscheiden, wenn Sie Geräte beim Microsoft Managed Desktop registrieren, oder Sie können den Dienst nach der Registrierung aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b696-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="5b696-116">Anmeldung während der Registrierung</span><span class="sxs-lookup"><span data-stu-id="5b696-116">Opt in during enrollment</span></span>

<span data-ttu-id="5b696-117">Sie können den Microsoft Managed Desktop Standortdienst aktivieren lassen.</span><span class="sxs-lookup"><span data-stu-id="5b696-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="5b696-118">Während der Registrierungssequenz werden Sie aufgefordert, auszuwählen, ob Sie zulassen möchten, dass Windows 10 Standortdienst auf Geräten aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="5b696-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="5b696-119">Steuern des Standortdiensts nach der Registrierung</span><span class="sxs-lookup"><span data-stu-id="5b696-119">Control the location service after enrollment</span></span>

<span data-ttu-id="5b696-120">Sie können den Standortdienst jederzeit aktiviert (oder deaktiviert) [](../working-with-managed-desktop/admin-support.md) haben, indem Sie eine Supportanfrage über das [Administratorportal übermitteln.](access-admin-portal.md)</span><span class="sxs-lookup"><span data-stu-id="5b696-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="5b696-121">Konfigurieren Microsoft Managed Desktop standortdiensts Windows 10</span><span class="sxs-lookup"><span data-stu-id="5b696-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="5b696-122">Wenn Sie sich für die Verwendung des Standortdiensts entscheiden, verwenden wir die erforderlichen Mindesteinstellungen, ohne den Datenschutz der Benutzer zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="5b696-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="5b696-123">Weitere Informationen finden Sie unter [Windows 10 Standortdienst und Datenschutz](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span><span class="sxs-lookup"><span data-stu-id="5b696-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="5b696-124">Microsoft Managed Desktop aktiviert die Einstellung **Standortdatenschutz** in **den Windows,** um den Zugriff auf den Standort **auf diesem Gerät zu ermöglichen.**</span><span class="sxs-lookup"><span data-stu-id="5b696-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="5b696-125">Die Benutzeroberfläche sieht wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="5b696-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Standorteinstellungen in Windows Einstellungen":::

> [!NOTE]
> <span data-ttu-id="5b696-127">Wenn Sie sich für die Verwendung des Standortdiensts entscheiden, gilt dies nur für Windows Betriebssystem selbst.</span><span class="sxs-lookup"><span data-stu-id="5b696-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="5b696-128">Apps dürfen keine Standortdienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b696-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="5b696-129">Jeder Benutzer kann auswählen, ob Apps auf seinen Standort zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="5b696-129">Each user can choose whether to allow apps to access their location.</span></span>