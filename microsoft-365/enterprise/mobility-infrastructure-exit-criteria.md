---
title: Beendigungskriterien für die Infrastruktur der mobilen Geräteverwaltung
description: Microsoft 365 Enterprise umfasst die Verwaltung mobiler Geräte mithilfe von Microsoft InTune. Überprüfen Sie die Anforderungen und Voraussetzungen, richten Sie InTune mithilfe ihrer Azure Active Directory-Ressource ein, registrieren Sie IOS-, macOS-, Android-und Windows-Geräte, stellen Sie apps bereit, erstellen Sie ein configure-Profil, verwenden Sie eine Konformitätsrichtlinie, und aktivieren Sie den bedingten Zugriff für Mobile Geräteverwaltung mit Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-Dokumentation, Verwaltung mobiler Geräte, InTune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: e8f8f53224b334f92142e2c03ed05eaa9e38787a
ms.sourcegitcommit: d4aa94716b33e6c270ae7adfbdc4c19cf4a0087d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "37385722"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="27ad9-105">Beendigungskriterien für die Infrastruktur der mobilen Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="27ad9-105">Mobile device management infrastructure exit criteria</span></span>

![Phase 5: Verwaltung mobiler Geräte](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="27ad9-107">*Dies gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="27ad9-107">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="27ad9-108">Stellen Sie sicher, dass Ihre Konfiguration die folgenden Anforderungen für die Infrastruktur zur Verwaltung mobiler Geräte erfüllt.</span><span class="sxs-lookup"><span data-stu-id="27ad9-108">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="27ad9-109">InTune ist eingerichtet, einschließlich der Erstellung von Azure Active Directory (Azure AD)-Benutzern und-Gruppen, um die Regeln Ihrer Organisation für Geräte anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="27ad9-109">Intune is set up, including the creation of Azure Active Directory (Azure AD) users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="27ad9-110">Sie haben Geräte in Intune registriert, damit die Geräte die von Ihnen erstellten Richtlinien empfangen können.</span><span class="sxs-lookup"><span data-stu-id="27ad9-110">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="27ad9-111">Apps werden Geräten hinzugefügt, damit Ihre Benutzer Zugriff auf die Microsoft 365-Clouddienste Ihrer Organisation erhalten, z. B. Exchange Online und SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="27ad9-111">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="27ad9-112">Features und Einstellungen werden konfiguriert und mithilfe der erstellten Azure AD-Benutzer und -Gruppen auf Ihre Geräte angewendet. Dazu gehört möglicherweise das Aktivieren von Antiviren-Apps sowie das Einschränken bestimmter Apps.</span><span class="sxs-lookup"><span data-stu-id="27ad9-112">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="27ad9-113">Compliance-Richtlinien sind vorhanden, um eine Firewall oder eine Kennwortlänge auf einem Gerät zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="27ad9-113">Compliance policies are in place to require a firewall or a password length on a device.</span></span> <span data-ttu-id="27ad9-114">Wenn Geräte nicht kompatibel sind, blockiert der bedingte Zugriff den Zugriff auf die Daten Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="27ad9-114">If devices aren't compliant, Conditional Access blocks access to your organization's data.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="27ad9-115">Ergebnisse und nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="27ad9-115">Results and next steps</span></span>

<span data-ttu-id="27ad9-116">Ihre Geräte sind in InTune registriert und mit den entsprechenden Richtlinien konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="27ad9-116">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![Phase 6: Schutz von Daten](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="27ad9-118">Wenn Sie die Phasen für die End-to-End-Bereitstellung von Microsoft 365 Enterprise ausführen, ist Ihre nächste Phase der [Informationsschutz](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="27ad9-118">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
