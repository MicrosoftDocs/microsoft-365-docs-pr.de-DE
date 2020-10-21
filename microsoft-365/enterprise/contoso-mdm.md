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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erfahren Sie, wie Contoso Microsoft InTune in Microsoft 365 für Unternehmen verwendet, um die Geräte und die darauf ausgeführten apps zu verwalten.
ms.openlocfilehash: d3f973827a9b05a415efe9225a2bdb3d83ccaf38
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649645"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="b654a-103">Verwaltung mobiler Geräte bei Contoso</span><span class="sxs-lookup"><span data-stu-id="b654a-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="b654a-104">Microsoft 365 für Unternehmen umfasst InTune und eine Gruppe von Azure-Diensten, die die Verwaltung mobiler Geräte und Anwendungen sowie die Sicherheit unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b654a-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="b654a-p101">Contoso verfügt über viele Mobil aktivierte Mitarbeiter. Einige haben Niederlassungen an Contoso-Standorten und einige haben keine Büros. Contoso benötigte eine Möglichkeit, die Mitarbeiterproduktivität zu ermöglichen, aber die Geräte, die auf diesen Geräten gespeicherten Contoso-Daten und das Anwendungsverhalten sicher zu halten.</span><span class="sxs-lookup"><span data-stu-id="b654a-p101">Contoso has many mobile-enabled employees. Some have offices in Contoso locations, and some have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="b654a-108">Plan</span><span class="sxs-lookup"><span data-stu-id="b654a-108">Plan</span></span>

<span data-ttu-id="b654a-109">Contoso hat die folgenden InTune-Anwendungsfälle für die Verwaltung mobiler Geräte für Microsoft 365 für Unternehmen identifiziert:</span><span class="sxs-lookup"><span data-stu-id="b654a-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="b654a-110">Schützen Sie Exchange Online e-Mails und Daten, damit Sie auf mobilen Geräten sicher zugänglich sind.</span><span class="sxs-lookup"><span data-stu-id="b654a-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="b654a-111">Implementieren Sie ein BYOD-Programm ("Holen Sie Ihr eigenes Gerät") für Contoso-Mitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="b654a-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="b654a-112">Stellen Sie die unternehmenseigenen Telefone und die Limited-use Shared Tablets für Contoso-Mitarbeiter aus.</span><span class="sxs-lookup"><span data-stu-id="b654a-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="b654a-113">Contoso verwendet InTune nicht für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b654a-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="b654a-114">Ermöglichen Sie Mitarbeitern den sicheren Zugriff auf Microsoft 365 von einem nicht verwalteten öffentlichen Kiosk aus.</span><span class="sxs-lookup"><span data-stu-id="b654a-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="b654a-115">Schützen Sie lokale e-Mails und Daten, damit Sie auf mobilen Geräten sicher zugegriffen werden kann, da keine lokalen Microsoft Exchange Server vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b654a-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="b654a-116">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b654a-116">Deploy</span></span>

<span data-ttu-id="b654a-117">Contoso hat seine Infrastruktur für die Verwaltung mobiler Geräte folgendermaßen eingerichtet:</span><span class="sxs-lookup"><span data-stu-id="b654a-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="b654a-118">Festlegen von InTune als MDM-Autorität (Mobile Device Management) und Verwenden von InTune in Azure zum Verwalten von Inhalten und Verwalten der Geräte</span><span class="sxs-lookup"><span data-stu-id="b654a-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="b654a-119">Erstellt Azure Active Directory (Azure AD) Gruppen für Geräte für die Registrierung und InTune-Einstellungen und gerätebasierte Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="b654a-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="b654a-120">Weitere Informationen finden Sie unter [bedingte Zugriffsrichtlinien für Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="b654a-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="b654a-121">Die Apple-Geräteplattform wurde aktiviert, um Mitarbeiter mit iPads, iMacs und iPhones sowie unternehmenseigenen iPhones zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b654a-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="b654a-122">Es wurden Contoso-spezifische Nutzungsbedingungen erstellt, die während der Installation des Unternehmensportals für Contoso auf mobilen Geräten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b654a-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="b654a-123">Für Geräte, die nicht registriert sind, wurde eine Reihe von MAM-Richtlinien (Mobile Application Management) implementiert, um die Authentifizierung für den Zugriff auf Microsoft 365-Dienste zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="b654a-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="b654a-124">Es wurden Intune-Richtlinien erstellt, die Folgendes erzwingen:</span><span class="sxs-lookup"><span data-stu-id="b654a-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="b654a-125">Zugelassene apps.</span><span class="sxs-lookup"><span data-stu-id="b654a-125">Allowed apps.</span></span>
  - <span data-ttu-id="b654a-126">Geräteverschlüsselung zur Verhinderung von nicht autorisiertem Zugriff.</span><span class="sxs-lookup"><span data-stu-id="b654a-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="b654a-127">Eine sechsstellige PIN oder ein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="b654a-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="b654a-128">Ein Timeoutzeitraum für Inaktivität.</span><span class="sxs-lookup"><span data-stu-id="b654a-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="b654a-129">Antiviren-und Malware Schutz sowie Signaturupdates mit Windows Defender auf Windows 10-Geräten.</span><span class="sxs-lookup"><span data-stu-id="b654a-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="b654a-130">Automatische Updates auf Windows 10-Geräten, die die neuesten Sicherheitsupdates enthalten.</span><span class="sxs-lookup"><span data-stu-id="b654a-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="b654a-131">Pushing Certificates to Managed Devices.</span><span class="sxs-lookup"><span data-stu-id="b654a-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="b654a-p102">Eine klare Trennung der geschäftlichen und persönlichen Daten. Benutzer oder Administratoren können Unternehmensdaten selektiv vom Gerät löschen, aber persönliche Daten wie Bilder, persönliche E-Mail-Konten und persönliche Dateien unberührt lassen.</span><span class="sxs-lookup"><span data-stu-id="b654a-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="b654a-134">Contoso hat bereitgestellte PCs und unternehmenseigene Smartphones und Tablets registriert, indem Sie Sie den entsprechenden InTune-Gerätegruppen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="b654a-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="b654a-135">Sie haben außerdem ein BYOD-Programm für Mitarbeiter eingerichtet, die Ihre persönlichen Geräte registrieren.</span><span class="sxs-lookup"><span data-stu-id="b654a-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="b654a-136">Für registriertes Gerät werden InTune-Richtlinien empfangen, die verwaltete und gesicherte Geräte und deren Anwendungen zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="b654a-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="b654a-137">Für Geräte, die nicht registriert sind, gibt es Richtlinien für Mobile Anwendungsverwaltung (MAM), die zugelassene Anwendungen angeben.</span><span class="sxs-lookup"><span data-stu-id="b654a-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="b654a-138">Hier ist die Bereitstellungsarchitektur für die Mobile Geräteverwaltung von contoso.</span><span class="sxs-lookup"><span data-stu-id="b654a-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Bereitstellungsinfrastruktur für die Mobile Geräteverwaltung von Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="b654a-140">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b654a-140">Next step</span></span>

<span data-ttu-id="b654a-141">[Erfahren Sie](contoso-info-protect.md) , wie Contoso die Informationen Schutzfunktionen von Microsoft 365 für Unternehmen verwendet, um wichtige digitale Objekte in Ihrer Organisation zu klassifizieren, zu identifizieren und zu schützen.</span><span class="sxs-lookup"><span data-stu-id="b654a-141">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="b654a-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b654a-142">See also</span></span>

[<span data-ttu-id="b654a-143">Geräteverwaltung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b654a-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="b654a-144">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b654a-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b654a-145">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="b654a-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

