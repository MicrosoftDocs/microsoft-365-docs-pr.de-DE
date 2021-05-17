---
title: Verwaltung mobiler Geräte bei Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erfahren Sie, wie Contoso Microsoft Intune in Microsoft 365 Für Unternehmen verwendet, um seine Geräte und die Apps zu verwalten, die auf ihnen ausgeführt werden.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753993"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="2a556-103">Verwaltung mobiler Geräte bei Contoso</span><span class="sxs-lookup"><span data-stu-id="2a556-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="2a556-104">Microsoft 365 für Unternehmen umfasst Intune und eine Reihe von Azure-Diensten, die die Verwaltung und Sicherheit mobiler Geräte und Anwendungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2a556-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="2a556-105">Contoso verfügt über viele mobile fähige Mitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="2a556-105">Contoso has many mobile-enabled employees.</span></span> <span data-ttu-id="2a556-106">Einige verfügen über Büros an Contoso-Standorten, andere über keine Büros.</span><span class="sxs-lookup"><span data-stu-id="2a556-106">Some have offices in Contoso locations, and some have no offices.</span></span> <span data-ttu-id="2a556-107">Contoso benötigte eine Möglichkeit, um die Produktivität der Mitarbeiter zu ermöglichen, aber die Geräte, die Auf diesen Geräten gespeicherten Contoso-Daten und das Anwendungsverhalten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="2a556-107">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="2a556-108">Planen</span><span class="sxs-lookup"><span data-stu-id="2a556-108">Plan</span></span>

<span data-ttu-id="2a556-109">Contoso hat die folgenden Intune-Verwendungsfälle für die Verwaltung mobiler Geräte für unternehmen Microsoft 365 identifiziert:</span><span class="sxs-lookup"><span data-stu-id="2a556-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="2a556-110">Schützen Exchange Online E-Mails und Daten, damit sie von mobilen Geräten sicher zugegriffen werden können.</span><span class="sxs-lookup"><span data-stu-id="2a556-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="2a556-111">Implementieren Sie ein Bring-your-own-device (BYOD)-Programm für Contoso-Mitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="2a556-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="2a556-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span><span class="sxs-lookup"><span data-stu-id="2a556-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="2a556-113">Contoso verwendet Intune nicht für:</span><span class="sxs-lookup"><span data-stu-id="2a556-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="2a556-114">Ermöglichen Sie Mitarbeitern den sicheren Zugriff Microsoft 365 von einem nicht verwalteten öffentlichen Kiosk aus.</span><span class="sxs-lookup"><span data-stu-id="2a556-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="2a556-115">Schützen Sie lokale E-Mails und Daten, damit sie von mobilen Geräten sicher zugegriffen werden können, da es keine lokalen Microsoft-Exchange gibt.</span><span class="sxs-lookup"><span data-stu-id="2a556-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="2a556-116">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="2a556-116">Deploy</span></span>

<span data-ttu-id="2a556-117">Contoso hat seine Infrastruktur für die Verwaltung mobiler Geräte folgendermaßen eingerichtet:</span><span class="sxs-lookup"><span data-stu-id="2a556-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="2a556-118">Festlegen von Intune als Autorität für die Mobile Geräteverwaltung (Mobile Device Management, MDM) und Verwenden von Intune in Azure zum Verwalten von Inhalten und Verwalten der Geräte</span><span class="sxs-lookup"><span data-stu-id="2a556-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="2a556-119">Erstellt Azure Active Directory (Azure AD)-Gruppen für Geräte für die Registrierung und Intune-Einstellungen und gerätebasierte Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="2a556-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="2a556-120">Weitere Informationen finden Sie unter [Richtlinien für den bedingten Zugriff von Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="2a556-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="2a556-121">Aktivieren der Apple-Geräteplattform zur Unterstützung von Mitarbeitern mit iPads, iMacs und iPhones sowie unternehmenseigenen iPhones</span><span class="sxs-lookup"><span data-stu-id="2a556-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="2a556-122">Es wurden Contoso-spezifische Nutzungsbedingungen erstellt, die während der Installation des Unternehmensportals für Contoso auf mobilen Geräten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2a556-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="2a556-123">Für Geräte, die nicht registriert sind, implementierten Sie eine Reihe von Mobile Application Management (MAM)-Richtlinien, um die Authentifizierung für den Zugriff auf Microsoft 365 erfordern.</span><span class="sxs-lookup"><span data-stu-id="2a556-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="2a556-124">Es wurden Intune-Richtlinien erstellt, die Folgendes erzwingen:</span><span class="sxs-lookup"><span data-stu-id="2a556-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="2a556-125">Zugelassene Apps.</span><span class="sxs-lookup"><span data-stu-id="2a556-125">Allowed apps.</span></span>
  - <span data-ttu-id="2a556-126">Geräteverschlüsselung, um nicht autorisierten Zugriff zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="2a556-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="2a556-127">Eine sechsstellige PIN oder ein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="2a556-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="2a556-128">Ein Inaktivitätstimeoutzeitraum.</span><span class="sxs-lookup"><span data-stu-id="2a556-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="2a556-129">Antivirus- und Schadsoftwareschutz sowie Signaturupdates mit Windows Defender auf Windows 10 Geräten.</span><span class="sxs-lookup"><span data-stu-id="2a556-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="2a556-130">Automatische Updates auf Windows 10, die die neuesten Sicherheitsupdates enthalten.</span><span class="sxs-lookup"><span data-stu-id="2a556-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="2a556-131">Übertragen von Zertifikaten auf verwaltete Geräte.</span><span class="sxs-lookup"><span data-stu-id="2a556-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="2a556-p102">Eine klare Trennung der geschäftlichen und persönlichen Daten. Benutzer oder Administratoren können Unternehmensdaten selektiv vom Gerät löschen, aber persönliche Daten wie Bilder, persönliche E-Mail-Konten und persönliche Dateien unberührt lassen.</span><span class="sxs-lookup"><span data-stu-id="2a556-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="2a556-134">Contoso registrierte bereitgestellte PCs und unternehmenseigene Smartphones und Tablets, indem diese den entsprechenden Intune-Gerätegruppen hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="2a556-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="2a556-135">Außerdem haben sie ein BYOD-Programm für Mitarbeiter eingerichtet, um ihre persönlichen Geräte zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="2a556-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="2a556-136">Registrierte Geräte erhalten Intune-Richtlinien, was zu verwalteten und gesicherten Geräten und ihren Anwendungen führt.</span><span class="sxs-lookup"><span data-stu-id="2a556-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="2a556-137">Geräte, die nicht registriert sind, verfügen über Mammutrichtlinien (Mobile Application Management), die zulässige Anwendungen angeben.</span><span class="sxs-lookup"><span data-stu-id="2a556-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="2a556-138">Hier ist die Bereitstellungsarchitektur für die Mobile Device Management von Contoso.</span><span class="sxs-lookup"><span data-stu-id="2a556-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Bereitstellungsinfrastruktur für mobile Geräteverwaltung von Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="2a556-140">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="2a556-140">Next step</span></span>

<span data-ttu-id="2a556-141">Erfahren Sie, [](contoso-info-protect.md) wie Contoso die Informationsschutzfunktionen von Microsoft 365 Unternehmen verwendet, um wichtige digitale Ressourcen in der gesamten Organisation zu klassifizieren, zu identifizieren und zu schützen.</span><span class="sxs-lookup"><span data-stu-id="2a556-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a556-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a556-142">See also</span></span>

[<span data-ttu-id="2a556-143">Geräteverwaltung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2a556-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="2a556-144">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2a556-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2a556-145">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="2a556-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

