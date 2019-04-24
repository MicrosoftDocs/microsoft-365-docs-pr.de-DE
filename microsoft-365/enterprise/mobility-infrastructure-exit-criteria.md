---
title: Infrastruktur-Exit-Kriterien für die Verwaltung mobiler Geräte
description: Microsoft 365 Enterprise umfasst die Verwaltung mobiler Geräte mit Microsoft InTune. Überprüfung der Anforderungen und Voraussetzungen, Einrichten von InTune mithilfe ihrer Azure Active Directory-Ressource, Registrieren von iOS-, macOS-, Android-und Windows-Geräten, Bereitstellen von apps, Erstellen eines Konfigurationsprofils, verwenden einer Konformitätsrichtlinie und Aktivieren des bedingten Zugriffs für Mobilgeräte Geräteverwaltung mit Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Mobile Device Management, InTune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291232"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="63b8b-105">Infrastruktur-Exit-Kriterien für die Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="63b8b-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="63b8b-106">*Dies gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="63b8b-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="63b8b-107">Stellen Sie sicher, dass Ihre Konfiguration die folgenden Anforderungen für die Verwaltung mobiler Geräte erfüllt.</span><span class="sxs-lookup"><span data-stu-id="63b8b-107">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="63b8b-108">Intune ist so eingerichtet (einschließlich der Erstellung von Azure AD-Benutzern und -Gruppen), dass die Regeln Ihrer Organisation für Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="63b8b-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="63b8b-109">Sie haben Geräte in Intune registriert, damit die Geräte die von Ihnen erstellten Richtlinien empfangen können.</span><span class="sxs-lookup"><span data-stu-id="63b8b-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="63b8b-110">Apps werden Geräten hinzugefügt, damit Ihre Benutzer Zugriff auf die Microsoft 365-Clouddienste Ihrer Organisation erhalten, z. B. Exchange Online und SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="63b8b-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="63b8b-111">Features und Einstellungen werden konfiguriert und mithilfe der erstellten Azure AD-Benutzer und -Gruppen auf Ihre Geräte angewendet. Dazu gehört möglicherweise das Aktivieren von Antiviren-Apps sowie das Einschränken bestimmter Apps.</span><span class="sxs-lookup"><span data-stu-id="63b8b-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="63b8b-p102">Es sind Compliancerichtlinien vorhanden, damit für ein Gerät eine Firewall oder eine Kennwortlänge erforderlich ist. Wenn Geräte diese Richtlinien nicht erfüllen, greifen bedingte Zugriffsblöcke auf die Daten Ihrer Organisation zu.</span><span class="sxs-lookup"><span data-stu-id="63b8b-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>



## <a name="results-and-next-steps"></a><span data-ttu-id="63b8b-114">Ergebnisse und nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="63b8b-114">Results and next steps</span></span>

<span data-ttu-id="63b8b-115">Ihre Geräte sind in InTune registriert und mit den entsprechenden Richtlinien konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="63b8b-115">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="63b8b-116">Wenn Sie die Phasen für die End-to-End-Bereitstellung von Microsoft 365 Enterprise verfolgen, ist der [Informationsschutz](infoprotect-infrastructure.md)die nächste Phase.</span><span class="sxs-lookup"><span data-stu-id="63b8b-116">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
