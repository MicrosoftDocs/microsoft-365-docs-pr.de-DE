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
ms.openlocfilehash: 4759cfda13ab5044ddf5980d7e61004e9e7626fa
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024775"
---
# <a name="service-encryption"></a><span data-ttu-id="5a434-103">Dienst Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="5a434-103">Service Encryption</span></span>

<span data-ttu-id="5a434-104">Zusätzlich zur Verschlüsselung auf Volumen Ebene verwenden Exchange Online, Skype for Business, SharePoint Online und OneDrive für Unternehmen auch die Dienst Verschlüsselung zum Verschlüsseln von Kundendaten.</span><span class="sxs-lookup"><span data-stu-id="5a434-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="5a434-105">Die Dienst Verschlüsselung ermöglicht zwei wichtige Verwaltungsoptionen:</span><span class="sxs-lookup"><span data-stu-id="5a434-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="5a434-106">Verwaltete Schlüssel von Microsoft</span><span class="sxs-lookup"><span data-stu-id="5a434-106">Microsoft managed keys</span></span>
<span data-ttu-id="5a434-107">Microsoft verwaltet alle kryptografischen Schlüssel einschließlich der Stammschlüssel für die Dienst Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="5a434-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="5a434-108">Diese Option ist derzeit in SharePoint Online und OneDrive für Unternehmen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5a434-108">This option is currently available in SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="5a434-109">Diese Option wird derzeit für Exchange Online eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5a434-109">This option is currently being rolled out for Exchange Online.</span></span> <span data-ttu-id="5a434-110">Microsoft-verwaltete Schlüssel bieten standardmäßige Dienst Verschlüsselung, es sei denn, Sie möchten mit dem Kundenschlüssel an Bord wählen.</span><span class="sxs-lookup"><span data-stu-id="5a434-110">Microsoft managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="5a434-111">Wenn Sie zu einem späteren Zeitpunkt beschließen, die Verwendung des Kunden Schlüssels zu beenden, ohne den Pfad der Datenbereinigung zu befolgen, bleiben Ihre Daten mit den verwalteten Microsoft-Schlüsseln verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="5a434-111">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft managed keys.</span></span> <span data-ttu-id="5a434-112">Ihre Daten werden immer mindestens auf dieser Standardstufe verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="5a434-112">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="5a434-113">Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="5a434-113">Customer Key</span></span>
<span data-ttu-id="5a434-114">Sie geben die mit der Dienst Verschlüsselung verwendeten Stammschlüssel an und verwalten diese Schlüssel mithilfe von Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5a434-114">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="5a434-115">Microsoft verwaltet alle anderen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="5a434-115">Microsoft manages all other keys.</span></span> <span data-ttu-id="5a434-116">Diese Option wird als Kundenschlüssel bezeichnet und steht derzeit für Exchange Online, SharePoint Online und OneDrive für Unternehmen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5a434-116">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="5a434-117">(Zuvor als erweiterte Verschlüsselung mit BYOK bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5a434-117">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="5a434-118">Weitere Informationen finden Sie unter [Enhancing transparency and Control for Office 365 Customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the Original Announcement.)</span><span class="sxs-lookup"><span data-stu-id="5a434-118">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="5a434-119">Die Dienst Verschlüsselung bietet mehrere Vorteile.</span><span class="sxs-lookup"><span data-stu-id="5a434-119">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="5a434-120">Beispiel: Kundenschlüssel:</span><span class="sxs-lookup"><span data-stu-id="5a434-120">For example, Customer Key:</span></span>

- <span data-ttu-id="5a434-121">Bietet Rechtsschutz-und Verwaltungsfunktionen über einen starken Verschlüsselungsschutz hinaus.</span><span class="sxs-lookup"><span data-stu-id="5a434-121">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="5a434-122">Enthält eine Option für Kundenschlüssel, mit der mehrere mandantenfähige Dienste für eine mandantenorientierte Schlüsselverwaltung bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="5a434-122">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="5a434-123">Ermöglicht die Trennung von Administratoren des Windows-Betriebssystems vom Zugriff auf Kundendaten, die vom Betriebssystem gespeichert oder verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5a434-123">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="5a434-124">Verbessert die Fähigkeit von Microsoft 365, die Anforderungen von Kunden zu erfüllen, die Compliance-Anforderungen bezüglich Verschlüsselung haben.</span><span class="sxs-lookup"><span data-stu-id="5a434-124">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="5a434-125">Mit dem Kundenschlüssel können Sie eigene kryptografische Schlüssel generieren, indem Sie entweder ein lokales Hardware-Service Modul (HSM) oder ein Azure Key Vault (AKV) verwenden.</span><span class="sxs-lookup"><span data-stu-id="5a434-125">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="5a434-126">Unabhängig davon, wie Sie den Schlüssel generieren, verwenden Sie AKV, um die von Office 365 verwendeten kryptografischen Schlüssel zu steuern und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="5a434-126">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="5a434-127">Nachdem Ihre Schlüssel in AKV gespeichert wurden, können Sie als Stamm einer der keychains verwendet werden, die ihre Postfachdaten oder-Dateien verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="5a434-127">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="5a434-128">Ein weiterer Vorteil von Customer Key ist die Kontrolle, die Sie über die Fähigkeit von Microsoft haben, Ihre Daten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a434-128">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="5a434-129">Wenn Sie Daten aus Office 365 entfernen möchten, beispielsweise wenn Sie den Dienst mit Microsoft beenden oder einen Teil der in der Cloud gespeicherten Daten entfernen möchten, können Sie dies tun und den Kundenschlüssel als technische Steuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="5a434-129">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="5a434-130">Dadurch wird sichergestellt, dass niemand, einschließlich Microsoft, auf die Daten zugreifen oder diese verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5a434-130">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="5a434-131">Kundenschlüssel wird zusätzlich zu den Kunden-Lockbox ergänzt, die Sie zum Steuern des Zugriffs auf Ihre Daten durch Microsoft-Mitarbeiter verwenden.</span><span class="sxs-lookup"><span data-stu-id="5a434-131">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="5a434-132">Informationen zum Einrichten des Kunden Schlüssels für Microsoft 365 für Exchange Online, Skype for Business, SharePoint Online, einschließlich Team Websites und OneDrive für Unternehmen, finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="5a434-132">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="5a434-133">Dienst Verschlüsselung mit Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="5a434-133">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="5a434-134">Einrichten des Kunden Schlüssels</span><span class="sxs-lookup"><span data-stu-id="5a434-134">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="5a434-135">Verwalten des Kunden Schlüssels</span><span class="sxs-lookup"><span data-stu-id="5a434-135">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="5a434-136">Rollen oder Drehen eines Kunden Schlüssels oder eines Verfügbarkeits Schlüssels</span><span class="sxs-lookup"><span data-stu-id="5a434-136">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="5a434-137">Grundlegendes zum Verfügbarkeits Schlüssel</span><span class="sxs-lookup"><span data-stu-id="5a434-137">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

