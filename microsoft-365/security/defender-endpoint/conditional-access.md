---
title: Aktivieren des bedingten Zugriffs zum besseren Schutz von Benutzern, Geräten und Daten
description: Aktivieren Sie bedingten Zugriff, um zu verhindern, dass Anwendungen ausgeführt werden, wenn ein Gerät als gefährdet betrachtet wird und eine Anwendung als nicht kompatibel gilt.
keywords: bedingter Zugriff, Blockieren von Anwendungen, Sicherheitsstufe, Intune,
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
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166197"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a><span data-ttu-id="af0d4-104">Aktivieren des bedingten Zugriffs zum besseren Schutz von Benutzern, Geräten und Daten</span><span class="sxs-lookup"><span data-stu-id="af0d4-104">Enable Conditional Access to better protect users, devices, and data</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af0d4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="af0d4-105">**Applies to:**</span></span>
- [<span data-ttu-id="af0d4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="af0d4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="af0d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af0d4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="af0d4-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="af0d4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="af0d4-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="af0d4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

<span data-ttu-id="af0d4-110">Bedingter Zugriff ist eine Funktion, mit der Sie Ihre Benutzer und Unternehmensinformationen besser schützen können, indem sichergestellt wird, dass nur sichere Geräte Zugriff auf Anwendungen haben.</span><span class="sxs-lookup"><span data-stu-id="af0d4-110">Conditional Access is a capability that helps you better protect your users and enterprise information by making sure that only secure devices have access to applications.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

<span data-ttu-id="af0d4-111">Mit bedingten Zugriff können Sie den Zugriff auf Unternehmensinformationen basierend auf der Risikostufe eines Geräts steuern.</span><span class="sxs-lookup"><span data-stu-id="af0d4-111">With Conditional Access, you can control access to enterprise information based on the risk level of a device.</span></span> <span data-ttu-id="af0d4-112">Dadurch können vertrauenswürdige Benutzer auf vertrauenswürdigen Geräten mit vertrauenswürdigen Anwendungen bleiben.</span><span class="sxs-lookup"><span data-stu-id="af0d4-112">This helps keep trusted users on trusted devices using trusted applications.</span></span>

<span data-ttu-id="af0d4-113">Sie können Sicherheitsbedingungen definieren, unter denen Geräte und Anwendungen ausgeführt werden können und auf Informationen aus Ihrem Netzwerk zugreifen können, indem Sie Richtlinien erzwingen, um die Ausführung von Anwendungen zu verhindern, bis ein Gerät in einen kompatiblen Zustand zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="af0d4-113">You can define security conditions under which devices and applications can run and access information from your network by enforcing policies to stop applications from running until a device returns to a compliant state.</span></span> 

<span data-ttu-id="af0d4-114">Die Implementierung von Bedingter Zugriff in Defender for Endpoint basiert auf Microsoft Intune (Intune) Geräte-Compliance-Richtlinien und Azure Active Directory (Azure AD)-Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="af0d4-114">The implementation of Conditional Access in Defender for Endpoint is based on Microsoft Intune (Intune) device compliance policies and Azure Active Directory (Azure AD) conditional access policies.</span></span> 

<span data-ttu-id="af0d4-115">Die Compliancerichtlinie wird zusammen mit bedingten Zugriff verwendet, um nur Geräten, die eine oder mehrere Richtlinienregeln für die Gerätekonformität erfüllen, den Zugriff auf Anwendungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="af0d4-115">The compliance policy is used with Conditional Access to allow only devices that fulfill one or more device compliance policy rules to access applications.</span></span> 

## <a name="understand-the-conditional-access-flow"></a><span data-ttu-id="af0d4-116">Verstehen des Bedingten Zugriffsflusses</span><span class="sxs-lookup"><span data-stu-id="af0d4-116">Understand the Conditional Access flow</span></span>
<span data-ttu-id="af0d4-117">Bedingter Zugriff wird so installiert, dass der Zugriff auf vertrauliche Inhalte blockiert wird, wenn eine Bedrohung auf einem Gerät angezeigt wird, bis die Bedrohung behoben ist.</span><span class="sxs-lookup"><span data-stu-id="af0d4-117">Conditional Access is put in place so that when a threat is seen on a device, access to sensitive content is blocked until the threat is remediated.</span></span> 

<span data-ttu-id="af0d4-118">Der Fluss beginnt damit, dass Geräte ein niedriges, mittleres oder hohes Risiko haben.</span><span class="sxs-lookup"><span data-stu-id="af0d4-118">The flow begins with devices being seen to have a low, medium, or high risk.</span></span> <span data-ttu-id="af0d4-119">Diese Risikoermittlungen werden dann an Intune gesendet.</span><span class="sxs-lookup"><span data-stu-id="af0d4-119">These risk determinations are then sent to Intune.</span></span> 

<span data-ttu-id="af0d4-120">Je nachdem, wie Sie Richtlinien in Intune konfigurieren, kann bedingter Zugriff so eingerichtet werden, dass die Richtlinie angewendet wird, wenn bestimmte Bedingungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="af0d4-120">Depending on how you configure policies in Intune, Conditional Access can be set up so that when certain conditions are met, the policy is applied.</span></span>

<span data-ttu-id="af0d4-121">Beispielsweise können Sie Intune so konfigurieren, dass bedingter Zugriff auf Geräte mit hohem Risiko angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="af0d4-121">For example, you can configure Intune to apply Conditional Access on devices that have a high risk.</span></span>

<span data-ttu-id="af0d4-122">In Intune wird eine Gerätekonformitätsrichtlinie in Verbindung mit dem bedingten Azure AD-Zugriff verwendet, um den Zugriff auf Anwendungen zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="af0d4-122">In Intune, a device compliance policy is used in conjunction with Azure AD Conditional Access to block access to applications.</span></span> <span data-ttu-id="af0d4-123">Parallel dazu wird ein automatisierter Untersuchungs- und Behebungsprozess gestartet.</span><span class="sxs-lookup"><span data-stu-id="af0d4-123">In parallel, an automated investigation and remediation process is launched.</span></span>

 <span data-ttu-id="af0d4-124">Ein Benutzer kann das Gerät weiterhin verwenden, während die automatisierte Untersuchung und Behebung stattfindet, aber der Zugriff auf Unternehmensdaten wird blockiert, bis die Bedrohung vollständig behoben ist.</span><span class="sxs-lookup"><span data-stu-id="af0d4-124">A user can still use the device while the automated investigation and remediation is taking place, but access to enterprise data is blocked until the threat is fully remediated.</span></span> 

<span data-ttu-id="af0d4-125">Um das auf einem Gerät gefundene Risiko zu beheben, müssen Sie das Gerät in einen kompatiblen Zustand zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="af0d4-125">To resolve the risk found on a device, you'll need to return the device to a compliant state.</span></span> <span data-ttu-id="af0d4-126">Ein Gerät kehrt in einen kompatiblen Zustand zurück, wenn kein Risiko auf dem Gerät besteht.</span><span class="sxs-lookup"><span data-stu-id="af0d4-126">A device returns to a compliant state when there is no risk seen on it.</span></span> 

<span data-ttu-id="af0d4-127">Es gibt drei Möglichkeiten, um ein Risiko zu adressieren:</span><span class="sxs-lookup"><span data-stu-id="af0d4-127">There are three ways to address a risk:</span></span>
1. <span data-ttu-id="af0d4-128">Verwenden Sie manuelle oder automatisierte Korrekturen.</span><span class="sxs-lookup"><span data-stu-id="af0d4-128">Use Manual or automated remediation.</span></span>
2. <span data-ttu-id="af0d4-129">Lösen Sie aktive Warnungen auf dem Gerät auf.</span><span class="sxs-lookup"><span data-stu-id="af0d4-129">Resolve active alerts on the device.</span></span> <span data-ttu-id="af0d4-130">Dadurch wird das Risiko vom Gerät entfernt.</span><span class="sxs-lookup"><span data-stu-id="af0d4-130">This will remove the risk from the device.</span></span>
3. <span data-ttu-id="af0d4-131">Sie können das Gerät aus den aktiven Richtlinien entfernen, und daher wird bedingter Zugriff nicht auf das Gerät angewendet.</span><span class="sxs-lookup"><span data-stu-id="af0d4-131">You can remove the device from the active policies and consequently, Conditional Access will not be applied on the device.</span></span> 

<span data-ttu-id="af0d4-132">Bei der manuellen Korrektur muss ein Secops-Administrator eine Warnung untersuchen und das auf dem Gerät angezeigte Risiko eingehen.</span><span class="sxs-lookup"><span data-stu-id="af0d4-132">Manual remediation requires a secops admin to investigate an alert and address the risk seen on the device.</span></span> <span data-ttu-id="af0d4-133">Die automatische Korrektur wird über konfigurationseinstellungen konfiguriert, die im folgenden Abschnitt [Configure Conditional Access bereitgestellt werden.](configure-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="af0d4-133">The automated remediation is configured through configuration settings provided in the following section, [Configure Conditional Access](configure-conditional-access.md).</span></span>

<span data-ttu-id="af0d4-134">Wenn das Risiko entweder durch manuelle oder automatisierte Korrekturen entfernt wird, kehrt das Gerät in einen kompatiblen Zustand zurück, und der Zugriff auf Anwendungen wird gewährt.</span><span class="sxs-lookup"><span data-stu-id="af0d4-134">When the risk is removed either through manual or automated remediation, the device returns to a compliant state and access to applications is granted.</span></span>

<span data-ttu-id="af0d4-135">In der folgenden Beispielsequenz von Ereignissen wird bedingter Zugriff in Aktion erläutert:</span><span class="sxs-lookup"><span data-stu-id="af0d4-135">The following example sequence of events explains Conditional Access in action:</span></span>

1. <span data-ttu-id="af0d4-136">Ein Benutzer öffnet eine schädliche Datei, und Defender for Endpoint kennzeichnet das Gerät als hohes Risiko.</span><span class="sxs-lookup"><span data-stu-id="af0d4-136">A user opens a malicious file and Defender for Endpoint flags the device as high risk.</span></span>
2. <span data-ttu-id="af0d4-137">Die Bewertung mit hohem Risiko wird an Intune übergeben.</span><span class="sxs-lookup"><span data-stu-id="af0d4-137">The high risk assessment is passed along to Intune.</span></span> <span data-ttu-id="af0d4-138">Parallel dazu wird eine automatisierte Untersuchung initiiert, um die identifizierte Bedrohung zu begleichen.</span><span class="sxs-lookup"><span data-stu-id="af0d4-138">In parallel, an automated investigation is initiated to remediate the identified threat.</span></span> <span data-ttu-id="af0d4-139">Eine manuelle Korrektur kann auch zur Behebung der identifizierten Bedrohung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="af0d4-139">A manual remediation can also be done to remediate the identified threat.</span></span>
3. <span data-ttu-id="af0d4-140">Basierend auf der in Intune erstellten Richtlinie wird das Gerät als nicht kompatibel gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="af0d4-140">Based on the policy created in Intune, the device is marked as not compliant.</span></span> <span data-ttu-id="af0d4-141">Die Bewertung wird dann von der Intune-Richtlinie für bedingten Zugriff an Azure AD übermittelt.</span><span class="sxs-lookup"><span data-stu-id="af0d4-141">The assessment is then communicated to Azure AD by the Intune Conditional Access policy.</span></span> <span data-ttu-id="af0d4-142">In Azure AD wird die entsprechende Richtlinie angewendet, um den Zugriff auf Anwendungen zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="af0d4-142">In Azure AD, the corresponding policy is applied to block access to applications.</span></span>
4. <span data-ttu-id="af0d4-143">Die manuelle oder automatisierte Untersuchung und Behebung ist abgeschlossen, und die Bedrohung wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="af0d4-143">The manual or automated investigation and remediation is completed and the threat is removed.</span></span> <span data-ttu-id="af0d4-144">Defender for Endpoint sieht, dass auf dem Gerät kein Risiko besteht, und Intune bewertet das Gerät als konform.</span><span class="sxs-lookup"><span data-stu-id="af0d4-144">Defender for Endpoint sees that there is no risk on the device and Intune assesses the device to be in a compliant state.</span></span> <span data-ttu-id="af0d4-145">Azure AD wendet die Richtlinie an, die den Zugriff auf Anwendungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="af0d4-145">Azure AD applies the policy which allows access to applications.</span></span>
5. <span data-ttu-id="af0d4-146">Benutzer können jetzt auf Anwendungen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="af0d4-146">Users can now access applications.</span></span>

 
## <a name="related-topic"></a><span data-ttu-id="af0d4-147">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="af0d4-147">Related topic</span></span>
- [<span data-ttu-id="af0d4-148">Konfigurieren des bedingten Zugriffs in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af0d4-148">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>](configure-conditional-access.md)
