---
title: Dienstverschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Zusammenfassung: Verstehen der Datenresilienz in Microsoft Office 365.'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058548"
---
# <a name="service-encryption"></a><span data-ttu-id="e6734-103">Dienstverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="e6734-103">Service Encryption</span></span>

<span data-ttu-id="e6734-104">Neben der Verwendung der Verschlüsselung auf Volumeebene verwenden Exchange Online, Microsoft Teams, SharePoint Online und OneDrive for Business auch die Dienstverschlüsselung, um Kundendaten zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="e6734-104">In addition to using volume-level encryption, Exchange Online, Microsoft Teams, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="e6734-105">Die Dienstverschlüsselung ermöglicht zwei wichtige Verwaltungsoptionen:</span><span class="sxs-lookup"><span data-stu-id="e6734-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="e6734-106">Von Microsoft verwaltete Schlüssel</span><span class="sxs-lookup"><span data-stu-id="e6734-106">Microsoft-managed keys</span></span>
<span data-ttu-id="e6734-107">Microsoft verwaltet alle kryptografischen Schlüssel, einschließlich der Stammschlüssel für die Dienstverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="e6734-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="e6734-108">Diese Option ist derzeit standardmäßig für Exchange Online, SharePoint Online, OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="e6734-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="e6734-109">Von Microsoft verwaltete Schlüssel bieten standardmäßige Dienstverschlüsselung, es sei denn, Sie entscheiden sich für das Onboarding mithilfe des Kundenschlüssels.</span><span class="sxs-lookup"><span data-stu-id="e6734-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="e6734-110">Wenn Sie zu einem späteren Zeitpunkt die Verwendung des Kundenschlüssels beenden möchten, ohne den Datenbereinigungspfad zu folgen, bleiben Ihre Daten mit den von Microsoft verwalteten Schlüsseln verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e6734-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="e6734-111">Ihre Daten werden auf dieser Standardebene immer mindestens verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e6734-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="e6734-112">Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="e6734-112">Customer Key</span></span>
<span data-ttu-id="e6734-113">Sie liefern Stammschlüssel, die mit der Dienstverschlüsselung verwendet werden, und Sie verwalten diese Schlüssel mithilfe von Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="e6734-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="e6734-114">Microsoft verwaltet alle anderen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="e6734-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="e6734-115">Diese Option heißt Customer Key und ist derzeit für Exchange Online, SharePoint Online und OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="e6734-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="e6734-116">(Wird zuvor als Erweiterte Verschlüsselung mit BYOK bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e6734-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="e6734-117">Informationen [zur ursprünglichen](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) Ankündigung finden Sie unter Verbessern der Transparenz und Kontrolle für Office 365 Kunden.)</span><span class="sxs-lookup"><span data-stu-id="e6734-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="e6734-118">Die Dienstverschlüsselung bietet mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="e6734-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="e6734-119">Bietet eine zusätzliche Schutzebene auf der BitLocker.</span><span class="sxs-lookup"><span data-stu-id="e6734-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="e6734-120">Ermöglicht die Trennung Windows Betriebssystemadministratoren vom Zugriff auf vom Betriebssystem gespeicherte oder verarbeitete Anwendungsdaten.</span><span class="sxs-lookup"><span data-stu-id="e6734-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="e6734-121">Enthält eine Customer Key-Option, mit der dienste mit mehreren Mandanten die Verwaltung von Schlüsseln pro Mandant bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="e6734-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="e6734-122">Verbessert die Fähigkeit der Microsoft 365, die Anforderungen von Kunden zu erfüllen, die bestimmte Complianceanforderungen hinsichtlich der Verschlüsselung haben.</span><span class="sxs-lookup"><span data-stu-id="e6734-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="e6734-123">Mithilfe des Kundenschlüssels können Sie eigene Kryptografieschlüssel mithilfe eines lokalen Hardwaredienstmoduls (Hardware Service Module, HSM) oder eines Azure Key Vault (AKV) generieren.</span><span class="sxs-lookup"><span data-stu-id="e6734-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="e6734-124">Unabhängig davon, wie Sie den Schlüssel generieren, verwenden Sie AKV zum Steuern und Verwalten der kryptografischen Schlüssel, die von Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6734-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="e6734-125">Sobald Ihre Schlüssel in AKV gespeichert sind, können sie als Stamm einer der Schlüsselbunde verwendet werden, die Ihre Postfachdaten oder -dateien verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="e6734-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="e6734-126">Ein weiterer Vorteil von Customer Key ist das Steuerelement, das Sie über die Möglichkeit von Microsoft zum Verarbeiten Ihrer Daten verfügen.</span><span class="sxs-lookup"><span data-stu-id="e6734-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="e6734-127">Wenn Sie Daten aus Office 365 entfernen möchten, z. B. wenn Sie den Dienst bei Microsoft beenden oder einen Teil Ihrer in der Cloud gespeicherten Daten entfernen möchten, können Sie dies tun und den Kundenschlüssel als technische Steuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6734-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="e6734-128">Durch das Entfernen von Daten wird sichergestellt, dass niemand, einschließlich Microsoft, auf die Daten zugreifen oder diese verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e6734-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="e6734-129">Der Kundenschlüssel ist zusätzlich und ergänzt kundenspezifische Lockbox, die Sie zum Steuern des Zugriffs auf Ihre Daten durch Microsoft-Mitarbeiter verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6734-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="e6734-130">Informationen zum Einrichten des Kundenschlüssels für Microsoft 365 für Exchange Online, Microsoft Teams, SharePoint Online, einschließlich Teamwebsites und OneDrive for Business finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="e6734-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Microsoft Teams, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="e6734-131">Dienstverschlüsselung mit Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="e6734-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="e6734-132">Einrichten des Kundenschlüssels</span><span class="sxs-lookup"><span data-stu-id="e6734-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="e6734-133">Verwalten des Kundenschlüssels</span><span class="sxs-lookup"><span data-stu-id="e6734-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="e6734-134">Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels</span><span class="sxs-lookup"><span data-stu-id="e6734-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="e6734-135">Verstehen des Verfügbarkeitsschlüssels</span><span class="sxs-lookup"><span data-stu-id="e6734-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
