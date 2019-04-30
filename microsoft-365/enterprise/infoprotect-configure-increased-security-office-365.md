---
title: 'Schritt 3: Konfigurieren der erhöhten Sicherheit für Microsoft 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren der erhöhten Sicherheit für Microsoft 365
ms.openlocfilehash: fcf023960679cf624f3ea7421ab92b1a450d2524
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400029"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="d5c3e-103">Schritt 3: Konfigurieren der erhöhten Sicherheit für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d5c3e-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="d5c3e-104">*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d5c3e-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="d5c3e-105">Um sicherzustellen, dass Ihr Microsoft-365-Abonnement und die zugehörigen Daten vor böswilligen Angriffen geschützt sind, konfigurieren Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d5c3e-105">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="d5c3e-106">Richtlinien zur Verwaltung von Bedrohungen optimieren</span><span class="sxs-lookup"><span data-stu-id="d5c3e-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [<span data-ttu-id="d5c3e-107">Zusätzliche mandantenweite Exchange Online-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d5c3e-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="d5c3e-108">Mandantenweite Freigaberichtlinien im SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="d5c3e-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="d5c3e-109">Azure Active Directory-Einstellungen (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d5c3e-109">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="d5c3e-110">Nachdem Sie diese konfiguriert haben, können Sie Informationen zu Ihrem Sicherheitsstatus abrufen von:</span><span class="sxs-lookup"><span data-stu-id="d5c3e-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="d5c3e-111">Dashboards und Berichte im Microsoft Security Center</span><span class="sxs-lookup"><span data-stu-id="d5c3e-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [<span data-ttu-id="d5c3e-112">Microsoft-Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="d5c3e-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="d5c3e-113">Ein zusätzliches Sicherheitsfeature ist [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), mit dem Ihre Organisation sicherer zusammenarbeiten kann, indem:</span><span class="sxs-lookup"><span data-stu-id="d5c3e-113">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="d5c3e-114">[Links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) und [Anlagen](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in E-Mails geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="d5c3e-114">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="d5c3e-115">Spoofintelligenz und Anti-Phishing-Funktionen für E-Mails in Exchange Online und [Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams) bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d5c3e-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="d5c3e-116">Office 365 ATP ist nur mit Microsoft 365 Enterprise E5 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d5c3e-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d5c3e-118">Testumgebungsanleitung: Konfigurieren der erhöhten Sicherheit von Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d5c3e-118">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="d5c3e-119">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step3) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="d5c3e-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d5c3e-120">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d5c3e-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|<span data-ttu-id="d5c3e-121">[Konfigurieren der Windows Information Protection](infoprotect-deploy-windows-information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="d5c3e-121">[](infoprotect-deploy-windows-information-protection.md)Configure Azure Information Protection</span></span>|


