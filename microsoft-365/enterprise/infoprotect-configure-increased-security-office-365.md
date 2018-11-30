---
title: 'Schritt 3: Konfigurieren der erhöhten Sicherheit für Office 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren der erhöhten Sicherheit für Office 365, einschließlich Office 365 ATP.
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868085"
---
# <a name="step-3-configure-increased-security-for-office-365"></a><span data-ttu-id="33fd4-103">Schritt 3: Konfigurieren der erhöhten Sicherheit für Office 365</span><span class="sxs-lookup"><span data-stu-id="33fd4-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="33fd4-104">*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="33fd4-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="33fd4-105">Um sicherzustellen, dass Ihr Office 365-Abonnement und die darin enthaltenen Daten vor böswilligen Angriffen geschützt sind, lesen Sie die Informationen unter [Konfigurieren Ihres Office 365-Mandanten für erhöhte Sicherheit](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355), und konfigurieren Sie die folgende zusätzliche Sicherheit:</span><span class="sxs-lookup"><span data-stu-id="33fd4-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) and configure the following additional security:</span></span>

- <span data-ttu-id="33fd4-106">Richtlinien für die Bedrohungsverwaltung im Office 365 Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="33fd4-106">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="33fd4-107">Zusätzliche mandantenweite Exchange Online-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="33fd4-107">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="33fd4-108">Mandantenweite Freigaberichtlinien im SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="33fd4-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>
- <span data-ttu-id="33fd4-109">Azure Active Directory-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="33fd4-109">Settings in Azure Active Directory</span></span>

<span data-ttu-id="33fd4-110">Nachdem Sie diese konfiguriert haben, können Sie Informationen zu Ihrem Sicherheitsstatus abrufen von:</span><span class="sxs-lookup"><span data-stu-id="33fd4-110">Once configured, you can obtain information about your security status from:</span></span>

- <span data-ttu-id="33fd4-111">Dashboards und Berichte im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="33fd4-111">Dashboards and reports in the Security & Compliance Center</span></span>
- [<span data-ttu-id="33fd4-112">Office 365 Secure Score</span><span class="sxs-lookup"><span data-stu-id="33fd4-112">Office 365 Secure Score</span></span>](https://securescore.office.com/)
 
  <span data-ttu-id="33fd4-113">Um auf diese Seite zugreifen zu können, müssen Sie als Office 365-Mandantenadministrator angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="33fd4-113">To access this page, you must be signed in as an Office 365 tenant admin.</span></span>

<span data-ttu-id="33fd4-114">Sie können Cloud App Security oder Office 365 Cloud App Security auch zur Überwachung von Sicherheitsvorfällen verwenden. Weitere Informationen finden Sie unter [Übersicht über Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span><span class="sxs-lookup"><span data-stu-id="33fd4-114">You can also use Cloud App Security or Office 365 Cloud App Security to monitor for security events and act. For more information, see [Overview of Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span></span>

<span data-ttu-id="33fd4-115">Ein zusätzliches Sicherheitsfeature ist Office 365 Advanced Threat Protection (ATP), mit dem Ihre Organisation sicherer zusammenarbeiten kann, indem:</span><span class="sxs-lookup"><span data-stu-id="33fd4-115">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="33fd4-116">Links und Anlagen in E-Mails geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="33fd4-116">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="33fd4-117">Spoofintelligenz und Anti-Phishing-Funktionen für E-Mails in Exchange Online und Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="33fd4-117">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

>[!Note]
><span data-ttu-id="33fd4-p101">Office 365 ATP ist im Lieferumfang von Microsoft 365 Enterprise E5 enthalten. Wenn Sie über Microsoft 365 Enterprise E3 verfügen, können Sie einzelne Lizenzen für ATP erwerben.</span><span class="sxs-lookup"><span data-stu-id="33fd4-p101">Office 365 ATP is included with Microsoft 365 Enterprise E5. If you have Microsoft 365 Enterprise E3, you can purchase individual licenses for ATP.</span></span>
>

<span data-ttu-id="33fd4-120">Informationen zum Aktivieren von Office 365 ATP finden Sie unter [Aktivieren](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span><span class="sxs-lookup"><span data-stu-id="33fd4-120">To enable Office 365 ATP, see [Turn it on](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="33fd4-121">Weitere Informationen finden Sie unter [Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span><span class="sxs-lookup"><span data-stu-id="33fd4-121">For more information, see [Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span></span>


|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="33fd4-123">Testumgebungsanleitung: Konfigurieren der erhöhten Sicherheit von Office 365</span><span class="sxs-lookup"><span data-stu-id="33fd4-123">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="33fd4-124">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step4) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="33fd4-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="33fd4-125">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="33fd4-125">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="33fd4-126">Konfigurieren von Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="33fd4-126">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


