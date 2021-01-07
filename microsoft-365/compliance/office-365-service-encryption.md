---
title: Dienst Verschlüsselung
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
description: 'Zusammenfassung: Grundlegendes zur Ausfallsicherheit von Daten in Microsoft Office 365.'
ms.openlocfilehash: fbd2672986046a4f6d25c47b011eaef0a87d90e1
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777049"
---
# <a name="service-encryption"></a><span data-ttu-id="b128b-103">Dienst Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="b128b-103">Service Encryption</span></span>

<span data-ttu-id="b128b-104">Zusätzlich zur Verschlüsselung auf Volumen Ebene verwenden Exchange Online, Skype for Business, SharePoint Online und OneDrive für Unternehmen auch die Dienst Verschlüsselung zum Verschlüsseln von Kundendaten.</span><span class="sxs-lookup"><span data-stu-id="b128b-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="b128b-105">Die Dienst Verschlüsselung ermöglicht zwei wichtige Verwaltungsoptionen:</span><span class="sxs-lookup"><span data-stu-id="b128b-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="b128b-106">Von Microsoft verwaltete Schlüssel</span><span class="sxs-lookup"><span data-stu-id="b128b-106">Microsoft-managed keys</span></span>
<span data-ttu-id="b128b-107">Microsoft verwaltet alle kryptografischen Schlüssel einschließlich der Stammschlüssel für die Dienst Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="b128b-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="b128b-108">Diese Option ist derzeit standardmäßig für Exchange Online, SharePoint Online OneDrive für Unternehmen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b128b-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="b128b-109">Von Microsoft verwaltete Schlüssel wird die Standarddienst Verschlüsselung bereitgestellt, es sei denn, Sie verwenden den Kundenschlüssel an Bord.</span><span class="sxs-lookup"><span data-stu-id="b128b-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="b128b-110">Wenn Sie zu einem späteren Zeitpunkt beschließen, die Verwendung des Kunden Schlüssels zu beenden, ohne den Pfad der Datenbereinigung zu befolgen, bleiben Ihre Daten mit den von Microsoft verwalteten Schlüsseln verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="b128b-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="b128b-111">Ihre Daten werden immer mindestens auf dieser Standardstufe verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="b128b-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="b128b-112">Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="b128b-112">Customer Key</span></span>
<span data-ttu-id="b128b-113">Sie geben die mit der Dienst Verschlüsselung verwendeten Stammschlüssel an und verwalten diese Schlüssel mithilfe von Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="b128b-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="b128b-114">Microsoft verwaltet alle anderen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="b128b-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="b128b-115">Diese Option wird als Kundenschlüssel bezeichnet und steht derzeit für Exchange Online, SharePoint Online und OneDrive für Unternehmen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b128b-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="b128b-116">(Zuvor als erweiterte Verschlüsselung mit BYOK bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b128b-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="b128b-117">Weitere Informationen finden Sie unter [Enhancing transparency and Control for Office 365 Customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the Original Announcement.)</span><span class="sxs-lookup"><span data-stu-id="b128b-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="b128b-118">Die Dienst Verschlüsselung bietet mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="b128b-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="b128b-119">Bietet eine zusätzliche Schutzebene auf BitLocker.</span><span class="sxs-lookup"><span data-stu-id="b128b-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="b128b-120">Ermöglicht die Trennung von Administratoren des Windows-Betriebssystems vom Zugriff auf Anwendungsdaten, die vom Betriebssystem gespeichert oder verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b128b-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="b128b-121">Enthält eine Option für Kundenschlüssel, mit der mehrere mandantenfähige Dienste für eine mandantenorientierte Schlüsselverwaltung bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="b128b-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="b128b-122">Verbessert die Fähigkeit von Microsoft 365, die Anforderungen von Kunden zu erfüllen, die bestimmte Compliance-Anforderungen hinsichtlich der Verschlüsselung haben.</span><span class="sxs-lookup"><span data-stu-id="b128b-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="b128b-123">Mit dem Kundenschlüssel können Sie eigene kryptografische Schlüssel generieren, indem Sie entweder ein lokales Hardware-Service Modul (HSM) oder ein Azure Key Vault (AKV) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b128b-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="b128b-124">Unabhängig davon, wie Sie den Schlüssel generieren, verwenden Sie AKV, um die von Office 365 verwendeten kryptografischen Schlüssel zu steuern und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b128b-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="b128b-125">Nachdem Ihre Schlüssel in AKV gespeichert wurden, können Sie als Stamm einer der keychains verwendet werden, die ihre Postfachdaten oder-Dateien verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="b128b-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="b128b-126">Ein weiterer Vorteil von Customer Key ist die Kontrolle, die Sie über die Fähigkeit von Microsoft haben, Ihre Daten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b128b-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="b128b-127">Wenn Sie Daten aus Office 365 entfernen möchten, beispielsweise wenn Sie den Dienst mit Microsoft beenden oder einen Teil der in der Cloud gespeicherten Daten entfernen möchten, können Sie dies tun und den Kundenschlüssel als technische Steuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b128b-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="b128b-128">Durch das Entfernen von Daten wird sichergestellt, dass niemand, einschließlich Microsoft, auf die Daten zugreifen oder diese verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b128b-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="b128b-129">Kundenschlüssel wird zusätzlich zu den Kunden-Lockbox ergänzt, die Sie zum Steuern des Zugriffs auf Ihre Daten durch Microsoft-Mitarbeiter verwenden.</span><span class="sxs-lookup"><span data-stu-id="b128b-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="b128b-130">Informationen zum Einrichten des Kunden Schlüssels für Microsoft 365 für Exchange Online, Skype for Business, SharePoint Online, einschließlich Team Websites und OneDrive für Unternehmen, finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="b128b-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="b128b-131">Dienstverschlüsselung mit Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="b128b-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="b128b-132">Einrichten des Kunden Schlüssels</span><span class="sxs-lookup"><span data-stu-id="b128b-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="b128b-133">Verwalten des Kunden Schlüssels</span><span class="sxs-lookup"><span data-stu-id="b128b-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="b128b-134">Rollen oder Drehen eines Kunden Schlüssels oder eines Verfügbarkeits Schlüssels</span><span class="sxs-lookup"><span data-stu-id="b128b-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="b128b-135">Grundlegendes zum Verfügbarkeits Schlüssel</span><span class="sxs-lookup"><span data-stu-id="b128b-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

