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
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Zusammenfassung: Grundlegendes zur Datenverschlüsselung auf der Dienstebene in Microsoft Office 365.'
ms.openlocfilehash: fb6bf87fbd51bcb4383e9eb595ef11f081989d86
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211942"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="360a8-103">Office 365-Dienstverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="360a8-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="360a8-104">Zusätzlich zur Verwendung von BitLocker für die Verschlüsselung auf Volumen Ebene verwenden Exchange Online, Skype for Business, SharePoint Online, OneDrive für Unternehmen und Teams auch die Dienst Verschlüsselung zum Verschlüsseln von Kundendaten.</span><span class="sxs-lookup"><span data-stu-id="360a8-104">In addition to using BitLocker for volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="360a8-105">Die Dienst Verschlüsselung ermöglicht zwei wichtige Verwaltungsoptionen:</span><span class="sxs-lookup"><span data-stu-id="360a8-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="360a8-106">Microsoft verwaltet alle kryptografischen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="360a8-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="360a8-107">Diese Option ist derzeit in SharePoint Online-, OneDrive für Unternehmen-, Skype for Business-und Microsoft Teams-Chats verfügbar.</span><span class="sxs-lookup"><span data-stu-id="360a8-107">This option is currently available in SharePoint Online, OneDrive for Business, Skype for Business, and Teams chats.</span></span> <span data-ttu-id="360a8-108">Ihre Daten werden standardmäßig mit von Microsoft verwalteten Schlüsseln verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="360a8-108">Your data is encrypted by default with Microsoft-managed keys.</span></span>

- <span data-ttu-id="360a8-109">Ihre Organisation stellt die Stammschlüssel zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="360a8-109">Your organization supplies the root keys.</span></span> <span data-ttu-id="360a8-110">Sie verwalten diese Schlüssel mithilfe von Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="360a8-110">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="360a8-111">Diese Option wird als Kundenschlüssel bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="360a8-111">This option is called Customer Key.</span></span> <span data-ttu-id="360a8-112">Der Kundenschlüssel steht derzeit für Exchange Online-, SharePoint Online-, OneDrive für Unternehmen-, Skype for Business-und Microsoft Teams-Dateien zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="360a8-112">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="360a8-113">Wenn Sie den Kundenschlüssel verwenden, ersetzen diese Tasten die von Microsoft verwalteten Schlüssel, um Ihre Daten zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="360a8-113">If you use Customer Key, these keys replace Microsoft-managed keys to encrypt your data.</span></span>

<span data-ttu-id="360a8-114">Unabhängig von der gewählten Option bietet die Dienst Verschlüsselung mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="360a8-114">Whatever option you choose, service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="360a8-115">Erzwingt die Benutzerauthentifizierung zum Abrufen und Entschlüsseln von Daten, die von einem autorisierten Benutzer angefordert wurden.</span><span class="sxs-lookup"><span data-stu-id="360a8-115">Enforces user authentication to retrieve and decrypt data requested by an authorized user.</span></span>

- <span data-ttu-id="360a8-116">Ermöglicht die Trennung von Administratoren des Windows-Betriebssystems vom Zugriff auf Kundendaten, die vom Betriebssystem gespeichert oder verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="360a8-116">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="360a8-117">Erhöht die Fähigkeit von Office 365, die Anforderungen von Kunden zu erfüllen, die Compliance-Anforderungen bezüglich Verschlüsselung haben.</span><span class="sxs-lookup"><span data-stu-id="360a8-117">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="360a8-118">Informationen zum Einrichten des Kunden Schlüssels für Office 365 für Exchange Online-, Skype for Business-, SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="360a8-118">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files, see these articles:</span></span>

- [<span data-ttu-id="360a8-119">Dienst Verschlüsselung mit Kundenschlüssel in Office 365</span><span class="sxs-lookup"><span data-stu-id="360a8-119">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="360a8-120">Einrichten des Kunden Schlüssels für Office 365</span><span class="sxs-lookup"><span data-stu-id="360a8-120">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="360a8-121">Verwalten des Kunden Schlüssels für Office 365</span><span class="sxs-lookup"><span data-stu-id="360a8-121">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="360a8-122">Rollen oder Drehen eines Kunden Schlüssels oder eines Verfügbarkeits Schlüssels</span><span class="sxs-lookup"><span data-stu-id="360a8-122">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="360a8-123">Grundlegendes zum Verfügbarkeits Schlüssel</span><span class="sxs-lookup"><span data-stu-id="360a8-123">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
