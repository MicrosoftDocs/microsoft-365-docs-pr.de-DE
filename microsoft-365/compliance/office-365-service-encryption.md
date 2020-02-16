---
title: Office 365-Dienstverschlüsselung
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
ms.openlocfilehash: ec7f794a62a910fadaece890cf73451644d44109
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071112"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="63bac-103">Office 365-Dienstverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="63bac-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="63bac-104">Zusätzlich zur Verschlüsselung auf Volumen Ebene verwenden Exchange Online, Skype for Business, SharePoint Online und OneDrive für Unternehmen auch die Dienst Verschlüsselung zum Verschlüsseln von Kundendaten.</span><span class="sxs-lookup"><span data-stu-id="63bac-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="63bac-105">Die Dienst Verschlüsselung ermöglicht zwei wichtige Verwaltungsoptionen:</span><span class="sxs-lookup"><span data-stu-id="63bac-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="63bac-106">Microsoft verwaltet alle kryptografischen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="63bac-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="63bac-107">(Diese Option ist derzeit in SharePoint Online, OneDrive für Unternehmen und Skype for Business verfügbar.)</span><span class="sxs-lookup"><span data-stu-id="63bac-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="63bac-108">Der Kunde stellt Stammschlüssel bereit, die mit der Dienst Verschlüsselung verwendet werden, und der Kunde verwaltet diese Schlüssel mithilfe von Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="63bac-108">The customer supplies root keys used with service encryption and the customer manages these keys using Azure Key Vault.</span></span> <span data-ttu-id="63bac-109">Microsoft verwaltet alle anderen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="63bac-109">Microsoft manages all other keys.</span></span> <span data-ttu-id="63bac-110">Diese Option wird als Kundenschlüssel bezeichnet und steht derzeit für Exchange Online, SharePoint Online und OneDrive für Unternehmen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="63bac-110">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="63bac-111">(Zuvor als erweiterte Verschlüsselung mit BYOK bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="63bac-111">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="63bac-112">Weitere Informationen finden Sie unter [Enhancing transparency and Control for Office 365 Customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the Original Announcement.)</span><span class="sxs-lookup"><span data-stu-id="63bac-112">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="63bac-113">Die Dienst Verschlüsselung bietet mehrere Vorteile.</span><span class="sxs-lookup"><span data-stu-id="63bac-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="63bac-114">Beispiel: Kundenschlüssel:</span><span class="sxs-lookup"><span data-stu-id="63bac-114">For example, Customer Key:</span></span>

- <span data-ttu-id="63bac-115">Bietet Rechtsschutz-und Verwaltungsfunktionen über einen starken Verschlüsselungsschutz hinaus.</span><span class="sxs-lookup"><span data-stu-id="63bac-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="63bac-116">Enthält eine Option für Kundenschlüssel, mit der mehrere mandantenfähige Dienste für eine mandantenorientierte Schlüsselverwaltung bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="63bac-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="63bac-117">Ermöglicht die Trennung von Administratoren des Windows-Betriebssystems vom Zugriff auf Kundendaten, die vom Betriebssystem gespeichert oder verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="63bac-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="63bac-118">Erhöht die Fähigkeit von Office 365, die Anforderungen von Kunden zu erfüllen, die Compliance-Anforderungen bezüglich Verschlüsselung haben.</span><span class="sxs-lookup"><span data-stu-id="63bac-118">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="63bac-119">Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="63bac-119">Customer Key</span></span>

<span data-ttu-id="63bac-120">Mit dem Kundenschlüssel können Sie eigene kryptografische Schlüssel generieren, indem Sie entweder ein lokales Hardware-Service Modul (HSM) oder ein Azure Key Vault (AKV) verwenden.</span><span class="sxs-lookup"><span data-stu-id="63bac-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="63bac-121">Unabhängig davon, wie Sie den Schlüssel generieren, verwenden Sie AKV, um die von Office 365 verwendeten kryptografischen Schlüssel zu steuern und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="63bac-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="63bac-122">Nachdem Ihre Schlüssel in AKV gespeichert wurden, können Sie als Stamm einer der keychains verwendet werden, die ihre Postfachdaten oder-Dateien verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="63bac-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="63bac-123">Ein weiterer Vorteil von Customer Key ist die Kontrolle, die Sie über die Fähigkeit von Microsoft haben, Ihre Daten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="63bac-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="63bac-124">Wenn Sie Daten aus Office 365 entfernen möchten, beispielsweise wenn Sie den Dienst mit Microsoft beenden oder einen Teil der in der Cloud gespeicherten Daten entfernen möchten, können Sie dies tun und den Kundenschlüssel als technische Steuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="63bac-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="63bac-125">Dadurch wird sichergestellt, dass niemand, einschließlich Microsoft, auf die Daten zugreifen oder diese verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="63bac-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="63bac-126">Kundenschlüssel wird zusätzlich zu den Kunden-Lockbox ergänzt, die Sie zum Steuern des Zugriffs auf Ihre Daten durch Microsoft-Mitarbeiter verwenden.</span><span class="sxs-lookup"><span data-stu-id="63bac-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="63bac-127">Informationen zum Einrichten des Kunden Schlüssels für Office 365 für Exchange Online, Skype for Business, SharePoint Online, einschließlich Team Websites und OneDrive für Unternehmen, finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="63bac-127">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="63bac-128">Dienst Verschlüsselung mit Kundenschlüssel in Office 365</span><span class="sxs-lookup"><span data-stu-id="63bac-128">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="63bac-129">Einrichten des Kunden Schlüssels für Office 365</span><span class="sxs-lookup"><span data-stu-id="63bac-129">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="63bac-130">Verwalten des Kunden Schlüssels für Office 365</span><span class="sxs-lookup"><span data-stu-id="63bac-130">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="63bac-131">Rollen oder Drehen eines Kunden Schlüssels oder eines Verfügbarkeits Schlüssels</span><span class="sxs-lookup"><span data-stu-id="63bac-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="63bac-132">Grundlegendes zum Verfügbarkeits Schlüssel</span><span class="sxs-lookup"><span data-stu-id="63bac-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 
