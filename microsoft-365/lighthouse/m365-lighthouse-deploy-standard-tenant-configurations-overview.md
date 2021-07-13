---
title: Übersicht über die Verwendung von Basisplänen zum Bereitstellen von Standardmandantenkonfigurationen
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Informationen zur Verwendung von Basisplänen zum Bereitstellen von Standardmandantenkonfigurationen für verwaltete Dienstanbieter (Managed Service Providers, MSPs) mit Microsoft 365 Lighthouse.
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409179"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a><span data-ttu-id="915be-103">Übersicht über die Verwendung von Basisplänen zum Bereitstellen von Standardmandantenkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="915be-103">Overview of using baselines to deploy standard tenant configurations</span></span> 

> [!NOTE]
> <span data-ttu-id="915be-104">Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nur für Partner verfügbar, die die [Anforderungen](m365-lighthouse-requirements.md)erfüllen.</span><span class="sxs-lookup"><span data-stu-id="915be-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="915be-105">Wenn Ihre Organisation nicht über Microsoft 365 Lighthouse verfügt, lesen Sie ["Registrieren für Microsoft 365 Lighthouse".](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="915be-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="915be-106">Microsoft 365 Lighthouse Basispläne bieten eine wiederholbare und skalierbare Möglichkeit, Microsoft 365 Sicherheitseinstellungen über mehrere Mandanten hinweg zu bewerten und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="915be-106">Microsoft 365 Lighthouse baselines provide a repeatable and scalable way for you to assess and manage Microsoft 365 security settings across multiple tenants.</span></span> <span data-ttu-id="915be-107">Basispläne helfen auch bei der Überwachung der wichtigsten Sicherheitsrichtlinien und Mandantencompliancestandards mit Konfigurationen, die Benutzer, Geräte und Daten schützen.</span><span class="sxs-lookup"><span data-stu-id="915be-107">Baselines also help monitor core security policies and tenant compliance standards with configurations that secure users, devices, and data.</span></span>

<span data-ttu-id="915be-108">Microsoft 365 Lighthouse soll Partnern dabei helfen, die Einführung von Sicherheit durch Kunden in ihrem eigenen Tempo zu ermöglichen. Microsoft 365 Lighthouse bietet einen Standardsatz von Basisparametern und vordefinierte Konfigurationen für Microsoft 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="915be-108">Designed to help partners enable customer adoption of security at their own pace, Microsoft 365 Lighthouse provides a standard set of baseline parameters and pre-defined configurations for Microsoft 365 services.</span></span> <span data-ttu-id="915be-109">Diese Sicherheitskonfigurationen helfen bei der Messung der Microsoft 365 Sicherheits- und Compliance-Fortschritt Ihrer Mandanten.</span><span class="sxs-lookup"><span data-stu-id="915be-109">These security configurations help measure your tenants' Microsoft 365 security and compliance progress.</span></span>

<span data-ttu-id="915be-110">Sie können die Standardbasislinie und die zugehörigen Bereitstellungsschritte in Microsoft 365 Lighthouse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="915be-110">You can view the default baseline and its deployment steps from within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="915be-111">Wenn Sie Basispläne auf einen Mandanten anwenden möchten, wählen Sie im linken Navigationsbereich **Mandanten** aus, und wählen Sie dann einen Mandanten aus.</span><span class="sxs-lookup"><span data-stu-id="915be-111">To apply baselines to a tenant, select **Tenants** in the left navigation pane, and then select a tenant.</span></span> <span data-ttu-id="915be-112">Wechseln Sie als Nächstes zur Registerkarte **"Bereitstellungspläne",** und implementieren Sie den gewünschten Basisplan.</span><span class="sxs-lookup"><span data-stu-id="915be-112">Next, go to the **Deployment plans** tab and implement the desired baseline.</span></span>

## <a name="standard-baseline-security-templates"></a><span data-ttu-id="915be-113">Standard-Basisplansicherheitsvorlagen</span><span class="sxs-lookup"><span data-stu-id="915be-113">Standard baseline security templates</span></span>

<span data-ttu-id="915be-114">Microsoft 365 Lighthouse Standardbasiskonfigurationen für Sicherheitsworkloads sollen allen verwalteten Mandanten dabei helfen, einen akzeptablen Status der Sicherheitsabdeckung und Compliance zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="915be-114">Microsoft 365 Lighthouse standard baseline configurations for security workloads are designed to help all managed tenants reach an acceptable state of security coverage and compliance.</span></span>

<span data-ttu-id="915be-115">Die Basislinienkonfigurationen in der folgenden Tabelle weisen standardmäßig die Microsoft 365 Lighthouse Standardbasislinie auf.</span><span class="sxs-lookup"><span data-stu-id="915be-115">The baseline configurations in the following table come standard with the Microsoft 365 Lighthouse default baseline.</span></span><br><br>

| <span data-ttu-id="915be-116">Basiskonfiguration</span><span class="sxs-lookup"><span data-stu-id="915be-116">Baseline configuration</span></span> | <span data-ttu-id="915be-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="915be-117">Description</span></span> |
|--|--|
| <span data-ttu-id="915be-118">MFA für Administratoren anfordern</span><span class="sxs-lookup"><span data-stu-id="915be-118">Require MFA for admins</span></span> | <span data-ttu-id="915be-119">Eine nur berichtsbasierte Richtlinie für bedingten Zugriff, die eine mehrstufige Authentifizierung für Administratoren erfordert.</span><span class="sxs-lookup"><span data-stu-id="915be-119">A report-only Conditional Access policy requiring multifactor authentication for admins.</span></span> <span data-ttu-id="915be-120">Sie ist für alle Cloudanwendungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="915be-120">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="915be-121">MFA für Endbenutzer anfordern</span><span class="sxs-lookup"><span data-stu-id="915be-121">Require MFA for end users</span></span> | <span data-ttu-id="915be-122">Eine berichtbasierte Richtlinie für bedingten Zugriff, die eine mehrstufige Authentifizierung für Benutzer erfordert.</span><span class="sxs-lookup"><span data-stu-id="915be-122">A report-only Conditional Access policy that requires multifactor authentication for users.</span></span> <span data-ttu-id="915be-123">Sie ist für alle Cloudanwendungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="915be-123">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="915be-124">Blockieren von Legacy-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="915be-124">Block legacy authentication</span></span> | <span data-ttu-id="915be-125">Eine berichtbasierte Richtlinie für bedingten Zugriff zum Blockieren der älteren Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="915be-125">A report-only Conditional Access policy to block legacy client authentication.</span></span> |
| <span data-ttu-id="915be-126">Registrieren von Geräten in Microsoft Endpoint Manager – Azure AD-Beitritt</span><span class="sxs-lookup"><span data-stu-id="915be-126">Enroll devices in Microsoft Endpoint Manager – Azure AD Join</span></span> | <span data-ttu-id="915be-127">Geräteregistrierung, damit sich Ihre Mandantengeräte bei Microsoft Endpoint Manager registrieren können.</span><span class="sxs-lookup"><span data-stu-id="915be-127">Device enrollment to allow your tenant devices to enroll in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="915be-128">Dazu wird die automatische Registrierung zwischen Azure Active Directory und Microsoft Endpoint Manager eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="915be-128">This is done by setting up Auto Enrollment between Azure Active Directory and Microsoft Endpoint Manager.</span></span> |
| <span data-ttu-id="915be-129">Av-Richtlinienkonfiguration (Antivirus)</span><span class="sxs-lookup"><span data-stu-id="915be-129">Antivirus (AV) policy configuration</span></span> | <span data-ttu-id="915be-130">Ein Gerätekonfigurationsprofil für Windows Geräte mit vorkonfigurierten Microsoft Defender Antivirus Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="915be-130">A Device Configuration profile for Windows devices with pre-configured Microsoft Defender Antivirus settings.</span></span> |
| <span data-ttu-id="915be-131">Windows 10 Compliance-Richtlinie eingerichtet</span><span class="sxs-lookup"><span data-stu-id="915be-131">Window 10 Compliance policy set up</span></span> | <span data-ttu-id="915be-132">Eine Windows Geräterichtlinie mit vorkonfigurierten Einstellungen, um grundlegende Complianceanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="915be-132">A Windows device policy with pre-configured settings to meet basic compliance requirements.</span></span> |

## <a name="related-content"></a><span data-ttu-id="915be-133">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="915be-133">Related content</span></span>

<span data-ttu-id="915be-134">[Bereitstellen Microsoft 365 Lighthouse Baselines](m365-lighthouse-deploy-baselines.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="915be-134">[Deploy Microsoft 365 Lighthouse baselines](m365-lighthouse-deploy-baselines.md) (article)</span></span>\
<span data-ttu-id="915be-135">[faq zu Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="915be-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
