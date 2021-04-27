---
title: 'Schritt 4: Bereitstellen der Endpunktverwaltung für Ihre Geräte, PCs und andere Endpunkte'
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Verwenden Sie Microsoft Endpoint Manager zur Verwaltung Ihrer Geräte, PCs und anderen Endgeräte.
ms.openlocfilehash: 116f2a92ccae43a36a8a4ceafcd598c532a852c3
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028992"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="d08b7-104">Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="d08b7-104">Step 4.</span></span> <span data-ttu-id="d08b7-105">Bereitstellen der Endpunktverwaltung für Ihre Geräte, PCs und andere Endpunkte</span><span class="sxs-lookup"><span data-stu-id="d08b7-105">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="d08b7-106">Bei Remotemitarbeitern müssen Sie eine wachsende Anzahl von persönlichen Geräten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-106">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="d08b7-107">Die Endpunktverwaltung ist ein richtlinienbasierter Sicherheitsansatz, bei dem Geräte bestimmte Kriterien erfüllen müssen, bevor sie Zugriff auf Ressourcen erhalten.</span><span class="sxs-lookup"><span data-stu-id="d08b7-107">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="d08b7-108">Microsoft Endpoint Manager bietet moderne Verwaltungsfunktionen, um Ihre Daten in der Cloud und vor Ort sicher zu halten.</span><span class="sxs-lookup"><span data-stu-id="d08b7-108">Microsoft Endpoint Manager delivers modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="d08b7-109">[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) bietet Dienste und Tools für die Verwaltung von mobilen Geräten, Desktop-Computern, virtuellen Maschinen, eingebetteten Geräten und Servern durch die Kombination der folgenden Dienste, die Sie möglicherweise bereits kennen und nutzen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-109">[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![Die Komponenten der Endpunktverwaltung für Microsoft 365](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="d08b7-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d08b7-111">Microsoft Intune</span></span>

<span data-ttu-id="d08b7-112">Microsoft Intune ist ein Cloud-basierter Dienst, der sich auf die Verwaltung mobiler Geräte (MDM) und die mobile Anwendungsverwaltung (MAM) bezieht und ein Bestandteil von Microsoft 365 ist.</span><span class="sxs-lookup"><span data-stu-id="d08b7-112">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM) that is included with Microsoft 365.</span></span> 

- <span data-ttu-id="d08b7-113">**MDM:** Sie können über Geräte im Besitz der Organisation die vollständige Kontrolle ausüben, einschließlich der Einstellungen, Features und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="d08b7-113">**MDM:** For organization-owned devices, you can exercise full control including settings, features, and security.</span></span> <span data-ttu-id="d08b7-114">Geräte werden in Intune "registriert", wo Sie Intune-Richtlinien mit Regeln und Einstellungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="d08b7-114">Devices are "enrolled" in Intune where they receive Intune policies with rules and settings.</span></span> <span data-ttu-id="d08b7-115">Sie können z. b. die Anforderungen für Kennwort und PIN festlegen, eine VPN-Verbindung erstellen, den Bedrohungsschutz einrichten und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="d08b7-115">For example, you can set password and PIN requirements, create a VPN connection, set up threat protection, and more.</span></span>

- <span data-ttu-id="d08b7-116">**MAM:** Remotemitarbeiter möchten möglicherweise nicht, dass Sie die vollständige Kontrolle über ihre persönlichen Geräte haben, auch bekannt als BYOD-Geräte (Bring-your-own Device).</span><span class="sxs-lookup"><span data-stu-id="d08b7-116">**MAM:** Remote workers might not want you to have full control on their personal devices, also known as bring-your-own device (BYOD) devices.</span></span> <span data-ttu-id="d08b7-117">Sie können Ihren Remotemitarbeiter Optionen anbieten und Ihre Organisation trotzdem schützen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-117">You can give your remote workers options and still protect your organization.</span></span> <span data-ttu-id="d08b7-118">So können beispielsweise Remotemitarbeiter Ihre Geräte registrieren, wenn Sie Vollzugriff auf die Ressourcen Ihrer Organisation wünschen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-118">For example, remote workers can enroll their devices if they want full access to your organization resources.</span></span> <span data-ttu-id="d08b7-119">Wenn diese Benutzer jedoch nur Zugriff auf E-Mail oder Microsoft Teams haben möchten, verwenden Sie die APP-Schutzrichtlinien, bei denen die mehrstufige Authentifizierung (MFA) erforderlich ist, um diese Apps zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d08b7-119">Or, if these users only want access to email or Microsoft Teams, then use app protection policies that require multi-factor authentication (MFA) to use these apps.</span></span>

<span data-ttu-id="d08b7-120">Weitere Informationen finden Sie in dieser [Übersicht über Microsoft Intune](/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="d08b7-120">For more information, see this [overview of Microsoft Intune](/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="d08b7-121">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d08b7-121">Configuration Manager</span></span>

<span data-ttu-id="d08b7-122">Configuration Manager ist eine lokale Verwaltungslösung zur Verwaltung von Desktops, Servern und Laptops, die sich in Ihrem Netzwerk oder internetbasiert befinden.</span><span class="sxs-lookup"><span data-stu-id="d08b7-122">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="d08b7-123">Verwenden Sie Configuration Manager zur Bereitstellung von Anwendungen, Software-Updates und Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-123">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="d08b7-124">Sie können auch die Einhaltung von Vorschriften überwachen, Kunden in Echtzeit abfragen und auf sie einwirken und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="d08b7-124">You can also monitor compliance, query and act on clients in real time, and much more.</span></span> <span data-ttu-id="d08b7-125">Sie können es für die Integration mit Intune, Azure AD, Microsoft Defender für Endpunkt und anderen Cloud-Diensten in der Cloud aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d08b7-125">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender for Endpoint, and other cloud services.</span></span> 

<span data-ttu-id="d08b7-126">Weitere Informationen finden Sie in dieser [Übersicht über Configuration Manager](/mem/configmgr/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="d08b7-126">For more information, see this [overview of Configuration Manager](/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="d08b7-127">Co-Management</span><span class="sxs-lookup"><span data-stu-id="d08b7-127">Co-management</span></span>

<span data-ttu-id="d08b7-128">Co-Management kombiniert Ihre vorhandenen Investitionen in Configuration Manager vor Ort mit der Cloud unter Verwendung von Intune und anderen Microsoft 365 Cloud-Diensten.</span><span class="sxs-lookup"><span data-stu-id="d08b7-128">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="d08b7-129">Sie wählen, ob Configuration Manager oder Intune die Verwaltungsautorität für verschiedenen Arbeitslasten ist.</span><span class="sxs-lookup"><span data-stu-id="d08b7-129">You choose whether Configuration Manager or Intune is the management authority for different workload.</span></span> 

<span data-ttu-id="d08b7-130">Das Co-Management verwendet Intune-basierte Cloud-Funktionen, einschließlich bedingtem Zugriff und erzwingen der Gerätekompatibilität.</span><span class="sxs-lookup"><span data-stu-id="d08b7-130">Co-management uses Intune-based cloud features, including Conditional Access and enforcing device compliance.</span></span> <span data-ttu-id="d08b7-131">Sie behalten einige Aufgaben lokal, während Sie andere Aufgaben in der Cloud ausführen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-131">You keep some tasks on-premises, while running other tasks in the cloud.</span></span>

<span data-ttu-id="d08b7-132">Weitere Informationen finden Sie in dieser [Übersicht über Co-Management](/mem/configmgr/comanage/overview).</span><span class="sxs-lookup"><span data-stu-id="d08b7-132">For more information, see this [overview of co-management](/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="d08b7-133">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="d08b7-133">Desktop Analytics</span></span>

<span data-ttu-id="d08b7-134">Desktop Analytics ist ein Cloud-basierter Dienst, der in Configuration Manager integriert ist und Ihnen Einblicke und Informationen liefert, damit Sie fundierte Entscheidungen über Ihre Windows-Clients treffen können.</span><span class="sxs-lookup"><span data-stu-id="d08b7-134">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="d08b7-135">Es kombiniert Daten aus Ihrem Unternehmen mit Daten, die aus Millionen von anderen Geräten aggregiert wurden, die mit Microsoft Cloud Services verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="d08b7-135">It combines data from your organization with data aggregated from millions of other devices connected to Microsoft cloud services.</span></span> 

<span data-ttu-id="d08b7-136">Mithilfe von Desktop Analytics können Sie:</span><span class="sxs-lookup"><span data-stu-id="d08b7-136">With Desktop Analytics, you can:</span></span>

- <span data-ttu-id="d08b7-137">ein Inventar der in Ihrem Unternehmen ausgeführten Anwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-137">Create an inventory of apps running in your organization.</span></span>
- <span data-ttu-id="d08b7-138">die Kompatibilität von Anwendungen mit den neuesten Windows 10-Feature-Updates bewerten.</span><span class="sxs-lookup"><span data-stu-id="d08b7-138">Assess app compatibility with the latest Windows 10 feature updates.</span></span>
- <span data-ttu-id="d08b7-139">Kompatibilitätsprobleme identifizieren und auf der Grundlage von Einblicken in Cloud-fähige Daten Vorschläge zur Risikominderung erhalten.</span><span class="sxs-lookup"><span data-stu-id="d08b7-139">Identify compatibility issues and receive mitigation suggestions based on cloud-enabled data insights.</span></span>
- <span data-ttu-id="d08b7-140">Pilotgruppen erstellen, welche die gesamte Anwendungs- und Treiberkombination auf einem minimalen Satz von Geräten repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="d08b7-140">Create pilot groups that represent the entire application and driver estate across a minimal set of devices.</span></span>
- <span data-ttu-id="d08b7-141">Windows 10 auf pilot- und produktionsverwalteten Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-141">Deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="d08b7-142">Weitere Informationen finden Sie in dieser [Übersicht über Desktop Analytics](/mem/configmgr/desktop-analytics/overview).</span><span class="sxs-lookup"><span data-stu-id="d08b7-142">For more information, see this [overview of Desktop Analytics](/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="d08b7-143">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="d08b7-143">Windows Autopilot</span></span>

<span data-ttu-id="d08b7-144">Windows Autopilot ist eine Self-Service-Plattform für die Bereitstellung von Windows ohne manuelles Eingreifen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-144">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="d08b7-145">Es ist eine Sammlung von Technologien, mit denen Sie neue Geräte eingerichtet und vorkonfiguriert können, damit sie für die Nutzung in der Produktion bereit stehen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-145">It includes a collection of technologies you use to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="d08b7-146">Sie können Windows Autopilot auch zum Zurücksetzen, Ändern des Zwecks und Wiederherstellen von Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="d08b7-146">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> 

<span data-ttu-id="d08b7-147">Windows Autopilot versetzt eine IT-Abteilung in die Lage, Geräte mithilfe einer geringen bis gar keiner zu verwaltenden Infrastruktur vorzukonfigurieren, und das über einen einfachen und schnellen Vorgang.</span><span class="sxs-lookup"><span data-stu-id="d08b7-147">Windows Autopilot enables an IT department to pre-configure devices with little to no infrastructure to manage, with a process that's easy and simple.</span></span> 

- <span data-ttu-id="d08b7-148">Aus der Sicht des Benutzers sind nur ein paar einfache Vorgänge nötig, um sein Gerät einsatzbereit zu machen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-148">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> 
- <span data-ttu-id="d08b7-149">Aus der Sicht der IT-Profis besteht die einzige Interaktion, die vom Endbenutzer verlangt wird, darin, sich mit einem Netzwerk zu verbinden und seine Anmeldeinformationen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d08b7-149">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="d08b7-150">Weitere Informationen finden Sie in dieser [Übersicht über Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot).</span><span class="sxs-lookup"><span data-stu-id="d08b7-150">For more information, see this [overview of Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="d08b7-151">Verwaltung technischer Ressourcen für die Endpunktverwaltung</span><span class="sxs-lookup"><span data-stu-id="d08b7-151">Admin technical resources for endpoint management</span></span>

- [<span data-ttu-id="d08b7-152">Roadmap für die Verwaltung mobiler Geräte für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d08b7-152">Device management roadmap for Microsoft 365</span></span>](../enterprise/device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="d08b7-153">Registrieren verschiedener Gerätetypen für die mobile Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="d08b7-153">How to enroll different types of devices for mobile device management</span></span>](/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="d08b7-154">Informieren Ihrer Endbenutzer über Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d08b7-154">How to educate your end users about Microsoft Intune</span></span>](/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-4"></a><span data-ttu-id="d08b7-155">Ergebnisse von Schritt 4</span><span class="sxs-lookup"><span data-stu-id="d08b7-155">Results of Step 4</span></span>

<span data-ttu-id="d08b7-156">Sie verwenden die Suite der Funktionen und Möglichkeiten von Endpoint Manager, um mobile Geräte, Desktop-Computer, virtuelle Maschinen, eingebettete Geräte und Server zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="d08b7-156">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="d08b7-157">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d08b7-157">Next step</span></span>

<span data-ttu-id="d08b7-158">[![Schritt 5: Bereitstellen von Produktivitätsanwendungen und -diensten für Remotemitarbeiter](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)</span><span class="sxs-lookup"><span data-stu-id="d08b7-158">[![Step 5: Deploy remote worker productivity apps and services](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)</span></span>

<span data-ttu-id="d08b7-159">Fahren Sie mit [Schritt 5](empower-people-to-work-remotely-teams-productivity-apps.md) fort, um Ihre Remotemitarbeiter mit Microsoft 365 Produktivitäts-Apps wie Microsoft Teams auszustatten.</span><span class="sxs-lookup"><span data-stu-id="d08b7-159">Continue with [Step 5](empower-people-to-work-remotely-teams-productivity-apps.md) to get your remote workers using Microsoft 365 productivity apps such as Microsoft Teams.</span></span>