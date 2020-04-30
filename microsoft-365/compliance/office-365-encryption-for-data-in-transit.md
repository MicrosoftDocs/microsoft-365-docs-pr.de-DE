---
title: Verschlüsselung von Daten während der Übertragung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Eine kurze Erläuterung der Art und Weise, wie Microsoft Daten während der Übertragung in ihren Rechenzentren verschlüsselt.
ms.openlocfilehash: 645294522185a631012c1654fbad96ba0a21b33e
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943304"
---
# <a name="encryption-for-data-in-transit"></a><span data-ttu-id="e8cc3-103">Verschlüsselung von Daten während der Übertragung</span><span class="sxs-lookup"><span data-stu-id="e8cc3-103">Encryption for data in transit</span></span>

<span data-ttu-id="e8cc3-104">Neben dem Schutz von Kundendaten im Rest verwendet Microsoft Verschlüsselungstechnologien zum Schutz von Kundendaten während der Übertragung.</span><span class="sxs-lookup"><span data-stu-id="e8cc3-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect customer data in transit.</span></span> 

<span data-ttu-id="e8cc3-105">Die Daten werden in die Übertragung eingegangen:</span><span class="sxs-lookup"><span data-stu-id="e8cc3-105">Data is in transit:</span></span>

- <span data-ttu-id="e8cc3-106">Wenn ein Clientcomputer mit einem Microsoft-Server kommuniziert;</span><span class="sxs-lookup"><span data-stu-id="e8cc3-106">when a client machine communicates with a Microsoft server;</span></span>
- <span data-ttu-id="e8cc3-107">Wenn ein Microsoft-Server mit einem anderen Microsoft-Server kommuniziert; und</span><span class="sxs-lookup"><span data-stu-id="e8cc3-107">when a Microsoft server communicates with another Microsoft server; and</span></span>
- <span data-ttu-id="e8cc3-108">Wenn ein Microsoft-Server mit einem nicht-Microsoft-Server kommuniziert (beispielsweise Exchange Online Zustellung von e-Mails an einen e-Mail-Server eines Drittanbieters).</span><span class="sxs-lookup"><span data-stu-id="e8cc3-108">when a Microsoft server communicates with a non-Microsoft server (e.g., Exchange Online delivering email to a third-party email server).</span></span>

<span data-ttu-id="e8cc3-109">Die Kommunikation zwischen Datencentern zwischen Microsoft-Servern erfolgt über TLS oder IPSec, und alle kundenbezogenen Server verhandeln mit TLS mit Clientcomputern eine sichere Sitzung (beispielsweise wird Exchange Online TLS 1,2 mit 256-Bit-Verschlüsselungsstärke verwendet (FIPS 140-2 Level 2-validiert).</span><span class="sxs-lookup"><span data-stu-id="e8cc3-109">Inter-data center communications between Microsoft servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated).</span></span> <span data-ttu-id="e8cc3-110">(Weitere Informationen finden Sie unter [technische Referenzdetails zur Verschlüsselung](technical-reference-details-about-encryption.md) für eine Liste der TLS-Verschlüsselungs Pakete, die von Office 365 unterstützt werden.) Dies gilt für die Protokolle, die von Clients wie Outlook, Skype for Business, Microsoft Teams und Outlook im Internet (beispielsweise http, POP3 usw.) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8cc3-110">(See [Technical reference details about encryption](technical-reference-details-about-encryption.md) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, Microsoft Teams, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="e8cc3-111">Die öffentlichen Zertifikate werden von Microsoft IT SSL mit SSLAdmin, einem internen Microsoft-Tool zum Schutz der Vertraulichkeit von übermittelten Informationen, ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="e8cc3-111">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information.</span></span> <span data-ttu-id="e8cc3-112">Alle von Microsoft ausgestellten Zertifikate weisen mindestens 2048 Bits auf, und die WebTrust-Compliance erfordert SSLAdmin, um sicherzustellen, dass Zertifikate nur für öffentliche IP-Adressen ausgestellt werden, die Microsoft gehören.</span><span class="sxs-lookup"><span data-stu-id="e8cc3-112">All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and Webtrust compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft.</span></span> <span data-ttu-id="e8cc3-113">Alle IP-Adressen, die dieses Kriterium nicht erfüllen, werden durch einen Ausnahme Prozess weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="e8cc3-113">Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="e8cc3-114">Alle Implementierungsdetails wie die verwendete TLS-Version, ob das Forward-Geheimnis (FS) aktiviert ist, die Reihenfolge von Verschlüsselungs Paketen usw. sind öffentlich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e8cc3-114">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly.</span></span> <span data-ttu-id="e8cc3-115">Eine Möglichkeit, diese Details anzuzeigen, ist die Verwendung einer Drittanbieterwebsite wie [Qualys SSL Labs](https://www.ssllabs.com).</span><span class="sxs-lookup"><span data-stu-id="e8cc3-115">One way to see these details is to use a third-party website, such as [Qualys SSL Labs](https://www.ssllabs.com).</span></span> <span data-ttu-id="e8cc3-116">Im folgenden finden Sie Links zu automatisierten Testseiten von Qualys, die Informationen für die folgenden Dienste anzeigen:</span><span class="sxs-lookup"><span data-stu-id="e8cc3-116">Below are the links to automated test pages from Qualys that display information for the following services:</span></span>

- [<span data-ttu-id="e8cc3-117">Office 365 Portal</span><span class="sxs-lookup"><span data-stu-id="e8cc3-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="e8cc3-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e8cc3-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="e8cc3-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8cc3-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="e8cc3-120">Skype for Business (SIP)</span><span class="sxs-lookup"><span data-stu-id="e8cc3-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="e8cc3-121">Skype for Business (im Internet)</span><span class="sxs-lookup"><span data-stu-id="e8cc3-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="e8cc3-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e8cc3-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="e8cc3-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e8cc3-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="e8cc3-124">Für Exchange Online Schutz variieren URLs je nach Mandantennamen; Allerdings können alle Kunden Microsoft 365 mit **Microsoft-com.Mail.Protection.Outlook.com**testen.</span><span class="sxs-lookup"><span data-stu-id="e8cc3-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Microsoft 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
