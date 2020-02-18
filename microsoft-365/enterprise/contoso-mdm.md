---
title: Verwaltung mobiler Geräte bei Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen Sie, wie Contoso Microsoft Intune in Microsoft 365 Enterprise verwendet, um seine Geräte und die Apps zu verwalten, die darauf ausgeführt werden.
ms.openlocfilehash: 7232c89cc105525cc57facd5a1b9de06426adbca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068366"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="b79b7-103">Verwaltung mobiler Geräte bei Contoso</span><span class="sxs-lookup"><span data-stu-id="b79b7-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="b79b7-104">Microsoft 365 Enterprise enthält Intune und eine Reihe von Azure-Diensten zur Unterstützung der Verwaltung und Sicherheit mobiler Geräte und Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b79b7-104">Microsoft 365 Enterprise includes Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="b79b7-p101">Bei Contoso arbeiten viele Mitarbeiter mit Mobilunterstützung, von denen einige Büros an Contoso-Standorten haben und einige nicht in Büros arbeiten. Das Unternehmen benötigte eine Möglichkeit, die Mitarbeiterproduktivität zu steigern und dabei gleichzeitig die auf diesen Geräten gespeicherten Contoso-Daten sowie das Anwendungsverhalten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="b79b7-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="b79b7-107">Planen</span><span class="sxs-lookup"><span data-stu-id="b79b7-107">Plan</span></span>

<span data-ttu-id="b79b7-108">Bei der Analyse der Verwaltung mobiler Geräte für Microsoft 365 Enterprise identifizierte Contoso frühzeitig die folgenden Intune-Anwendungsfälle:</span><span class="sxs-lookup"><span data-stu-id="b79b7-108">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="b79b7-109">Schützen von Exchange Online-E-Mails und -Daten, damit von mobilen Geräten sicher auf diese zugegriffen werden kann</span><span class="sxs-lookup"><span data-stu-id="b79b7-109">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="b79b7-110">Implementieren eines BYOD-Programms (Bring Your Own Device) für Contoso-Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="b79b7-110">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="b79b7-111">Verteilen von Telefonen im Besitz der Organisation und gemeinsam genutzten Tablets mit beschränkter Nutzung an Contoso-Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="b79b7-111">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="b79b7-112">Contoso verwendet Intune nicht für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b79b7-112">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="b79b7-113">Zulassen, dass Mitarbeiter von einem nicht verwalteten öffentlichen Kiosk sicher auf Office 365 zugreifen</span><span class="sxs-lookup"><span data-stu-id="b79b7-113">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="b79b7-114">Schützen von lokalen E-Mails und Daten, damit von mobilen Geräten sicher darauf zugegriffen werden kann, da es keine lokalen Microsoft Exchange-Server mehr gibt</span><span class="sxs-lookup"><span data-stu-id="b79b7-114">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="b79b7-115">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b79b7-115">Deploy</span></span>

<span data-ttu-id="b79b7-116">Contoso hat seine Infrastruktur für die Verwaltung mobiler Geräte folgendermaßen eingerichtet:</span><span class="sxs-lookup"><span data-stu-id="b79b7-116">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="b79b7-117">Intune wurde als MDM-Autorität (Mobile Geräteverwaltung) eingerichtet, und Intune wird auf Azure verwendet, um Inhalte und Geräte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b79b7-117">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="b79b7-118">Es wurden Azure AD-Gruppen für Geräte zur Registrierung und Intune-Einstellungen sowie gerätebasierte Richtlinien für bedingten Zugriff erstellt.</span><span class="sxs-lookup"><span data-stu-id="b79b7-118">Created Azure AD groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="b79b7-119">Weitere Informationen finden Sie unter [Richtlinien für den bedingten Zugriff von Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="b79b7-119">See [Contoso's Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="b79b7-120">Die Apple-Geräteplattform wurde aktiviert, um Mitarbeiter mit iPads, iMacs, iPhones und iPhone-basierten Telefonen im Besitz des Unternehmens zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b79b7-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="b79b7-121">Es wurden Contoso-spezifische Nutzungsbedingungen erstellt, die während der Installation des Unternehmensportals für Contoso auf mobilen Geräten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b79b7-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="b79b7-122">Für Geräte, die nicht registriert sind, wurde eine Reihe von MAM-Richtlinien (für mobile Anwendungsverwaltung) erstellt, die eine Authentifizierung für den Zugriff auf Office 365-Dienste erfordern.</span><span class="sxs-lookup"><span data-stu-id="b79b7-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="b79b7-123">Es wurden Intune-Richtlinien erstellt, die Folgendes erzwingen:</span><span class="sxs-lookup"><span data-stu-id="b79b7-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="b79b7-124">Zulässige Apps</span><span class="sxs-lookup"><span data-stu-id="b79b7-124">Allowed apps</span></span>
  - <span data-ttu-id="b79b7-125">Geräteverschlüsselung, um nicht autorisierten Zugriff zu verhindern</span><span class="sxs-lookup"><span data-stu-id="b79b7-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="b79b7-126">Eine sechsstellige PIN oder ein Kennwort</span><span class="sxs-lookup"><span data-stu-id="b79b7-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="b79b7-127">Ein Zeitlimit für Inaktivität</span><span class="sxs-lookup"><span data-stu-id="b79b7-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="b79b7-128">Schutz vor Viren und Schadsoftware und Signaturupdates mit Windows Defender auf Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="b79b7-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="b79b7-129">Automatische Updates für Windows 10-Geräte, die die neuesten Sicherheitsupdates enthalten</span><span class="sxs-lookup"><span data-stu-id="b79b7-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="b79b7-130">Verschieben von Zertifikaten auf verwaltete Geräte</span><span class="sxs-lookup"><span data-stu-id="b79b7-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="b79b7-p102">Eine klare Trennung der geschäftlichen und persönlichen Daten. Benutzer oder Administratoren können Unternehmensdaten selektiv vom Gerät löschen, aber persönliche Daten wie Bilder, persönliche E-Mail-Konten und persönliche Dateien unberührt lassen.</span><span class="sxs-lookup"><span data-stu-id="b79b7-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="b79b7-p103">Nach der Bereitstellung hat Contoso PCs sowie Smartphones und Tablets im Besitz des Unternehmens registriert, indem diese zu den entsprechenden Intune-Gerätegruppe hinzugefügt wurden, und es wurde ein BYOD-Programm eingeführt, im Rahmen dessen Mitarbeiter ihre persönlichen Geräte registrieren können. Registrierte Geräte erhielten Intune-Richtlinien, die zu verwalteten und geschützten Geräten und Anwendungen führten. Geräte, die nicht registriert wurden, weisen MAM-Richtlinien auf, in denen zulässige Anwendungen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b79b7-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="b79b7-136">Hier ist Contosos Bereitstellungsarchitektur für die Verwaltung mobiler Geräte.</span><span class="sxs-lookup"><span data-stu-id="b79b7-136">Here is Contoso's mobile device management deployment architecture.</span></span>

![Contosos Bereitstellungsarchitektur für die Verwaltung mobiler Geräte](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="b79b7-138">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b79b7-138">Next step</span></span>

<span data-ttu-id="b79b7-139">[Erfahren Sie](contoso-info-protect.md), wie Contoso die Funktionen zum Schutz von Informationen von Microsoft 365 Enterprise verwendet, um wichtige digitale Ressourcen in der gesamten Organisation zu klassifizieren, zu identifizieren und zu schützen.</span><span class="sxs-lookup"><span data-stu-id="b79b7-139">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="b79b7-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b79b7-140">See also</span></span>

[<span data-ttu-id="b79b7-141">Verwaltung mobiler Geräte für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b79b7-141">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="b79b7-142">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="b79b7-142">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b79b7-143">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="b79b7-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

