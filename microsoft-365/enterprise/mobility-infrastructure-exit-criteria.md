---
title: Mobiles Gerät Management Infrastructure abschlusskriterien
description: Microsoft 365 Enterprise umfasst die Verwaltung von mobilen Geräten mit Microsoft Intune. Überprüfen Sie die Anforderungen und Voraussetzungen, richten Sie Intune Ihrer Azure Active Directory-Ressource verwenden, registrieren iOS, Mac OS, Android und Windows-Geräten, erstellen Sie ein Profil konfigurieren, verwenden Sie eine Compliance-Richtlinie und Aktivieren des bedingten Zugriffs für Mobile Bereitstellen von apps Gerätemanagement mit Microsoft 365 Enterprise.
keywords: Microsoft 365 Microsoft 365 Enterprise Microsoft 365 Dokumentation, Verwaltung von mobilen Geräten, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.openlocfilehash: 48ee3bf52cdc11dc8a0215d954625899cd1e0224
ms.sourcegitcommit: 0221fa79642bc9ed5a052800fb2234facbb99731
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "22465629"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="11c3a-105">Mobiles Gerät Management Infrastructure abschlusskriterien</span><span class="sxs-lookup"><span data-stu-id="11c3a-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="11c3a-106">*Dies gilt für die E3 und E5 Versionen von Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="11c3a-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="11c3a-107">Bevor Sie mit der nächsten Phase des Bereitstellungsprozesses verschieben, stellen Sie sicher, dass Ihre Konfiguration für mobiles Gerät-Infrastruktur die folgenden Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="11c3a-107">Before you move on to the next phase in the deployment process, ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="11c3a-108">Intune wird eingerichtet, einschließlich der Erstellung von Azure Active Directory-Benutzer und Gruppen auf Regeln für die Geräte Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="11c3a-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="11c3a-109">Sie haben Geräte in Intune registriert, damit die Geräte die Richtlinien empfangen können, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="11c3a-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="11c3a-110">Apps werden Geräte hinzugefügt, damit Ihre Benutzer Zugriff auf Ihre Organisation 365 Microsoft Cloud Services wie Exchange Online und SharePoint Online zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="11c3a-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="11c3a-111">Features und Einstellungen sind konfiguriert und angewendet auf Geräte mit dem Azure Active Directory-Benutzer und Gruppen, die Sie erstellen, die Antivirus aktivieren und durch die Beschränkung auf bestimmte apps enthalten können.</span><span class="sxs-lookup"><span data-stu-id="11c3a-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="11c3a-p102">Richtlinien für die Kompatibilität sind eine Firewall oder eine Kennwortlänge auf einem Gerät erforderlich ist. Wenn Geräte nicht kompatibel sind, den Zugriff auf die Daten des Unternehmen bedingten Zugriff blockiert.</span><span class="sxs-lookup"><span data-stu-id="11c3a-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>

## <a name="next-phase"></a><span data-ttu-id="11c3a-114">Nächste Phase</span><span class="sxs-lookup"><span data-stu-id="11c3a-114">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="11c3a-115">Die nächste Phase im Prozess End-to-End-Bereitstellung für Microsoft 365 Enterprise ist [Schutz von Informationen](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="11c3a-115">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [information protection](infoprotect-infrastructure.md).</span></span> |
