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
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867730"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="664ec-105">Mobiles Gerät Management Infrastructure abschlusskriterien</span><span class="sxs-lookup"><span data-stu-id="664ec-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="664ec-106">*Dies gilt für die E3 und E5 Versionen von Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="664ec-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="664ec-107">Bevor Sie mit der nächsten Phase des Bereitstellungsprozesses verschieben, stellen Sie sicher, dass Ihre Konfiguration für mobiles Gerät-Infrastruktur die folgenden Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="664ec-107">Before you move on to the next phase in the deployment process, ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="664ec-108">Intune ist so eingerichtet (einschließlich der Erstellung von Azure AD-Benutzern und -Gruppen), dass die Regeln Ihrer Organisation für Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="664ec-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="664ec-109">Sie haben Geräte in Intune registriert, damit die Geräte die von Ihnen erstellten Richtlinien empfangen können.</span><span class="sxs-lookup"><span data-stu-id="664ec-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="664ec-110">Apps werden Geräten hinzugefügt, damit Ihre Benutzer Zugriff auf die Microsoft 365-Clouddienste Ihrer Organisation erhalten, z. B. Exchange Online und SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="664ec-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="664ec-111">Features und Einstellungen werden konfiguriert und mithilfe der erstellten Azure AD-Benutzer und -Gruppen auf Ihre Geräte angewendet. Dazu gehört möglicherweise das Aktivieren von Antiviren-Apps sowie das Einschränken bestimmter Apps.</span><span class="sxs-lookup"><span data-stu-id="664ec-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="664ec-p102">Es sind Compliancerichtlinien vorhanden, damit für ein Gerät eine Firewall oder eine Kennwortlänge erforderlich ist. Wenn Geräte diese Richtlinien nicht erfüllen, greifen bedingte Zugriffsblöcke auf die Daten Ihrer Organisation zu.</span><span class="sxs-lookup"><span data-stu-id="664ec-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>

## <a name="next-phase"></a><span data-ttu-id="664ec-114">Nächste Phase</span><span class="sxs-lookup"><span data-stu-id="664ec-114">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="664ec-115">Die nächste Phase im Prozess End-to-End-Bereitstellung für Microsoft 365 Enterprise ist [Schutz von Informationen](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="664ec-115">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [information protection](infoprotect-infrastructure.md).</span></span> |
