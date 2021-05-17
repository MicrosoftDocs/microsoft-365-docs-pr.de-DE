---
title: Schützen von vertraulichen Inhalten in E-Mails mit Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Neben dem Office 365 Trust Center, das Sicherheits-, Datenschutz- und Complianceinformationen für Microsoft 365 bietet, sollten Sie wissen, wie Microsoft beim Schutz von geheimen Schlüsseln hilft, die Sie in ihren Rechenzentren speichern. Wir verwenden eine Technologie namens Distributed Key Manager (DKM).
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906961"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="1a63d-104">Wie vertrauliche Daten in E-Mails in Exchange Online geschützt werden</span><span class="sxs-lookup"><span data-stu-id="1a63d-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="1a63d-105">In diesem Artikel wird beschrieben, wie Microsoft Ihre E-Mail-Schlüssel in ihren Rechenzentren sichert.</span><span class="sxs-lookup"><span data-stu-id="1a63d-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="1a63d-106">Wie sichern wir von Ihnen bereitgestellte geheime Informationen?</span><span class="sxs-lookup"><span data-stu-id="1a63d-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="1a63d-107">Neben dem Office 365 Trust Center, das Sicherheits-, Datenschutz- und Complianceinformationen für [Office 365](./get-started-with-service-trust-portal.md)bietet, möchten Sie vielleicht wissen, wie Microsoft beim Schutz von geheimen Daten unterstützt, die Sie in ihren Rechenzentren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1a63d-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](./get-started-with-service-trust-portal.md), you might want to know how Microsoft helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="1a63d-108">Wir verwenden eine Technologie namens Distributed Key Manager (DKM).</span><span class="sxs-lookup"><span data-stu-id="1a63d-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="1a63d-109">[Der verteilte Schlüssel-Manager (Distributed Key Manager,](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) DKM) ist eine clientseitige Funktionalität, die eine Reihe von geheimen Schlüsseln zum Verschlüsseln und Entschlüsseln von Informationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a63d-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="1a63d-110">Nur Mitglieder einer bestimmten Sicherheitsgruppe in Active Directory Domain Services können auf diese Schlüssel zugreifen, um die durch DKM verschlüsselten Daten zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1a63d-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="1a63d-111">In Exchange Online sind nur bestimmte Dienstkonten, unter denen die Exchange-Prozesse ausgeführt werden, Teil dieser Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="1a63d-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="1a63d-112">Im Rahmen der standardbetriebsprozedur im Datencenter erhalten keine Menschen Anmeldeinformationen, die Teil dieser Sicherheitsgruppe sind, und daher hat kein Mensch Zugriff auf die Schlüssel, die diese Geheimschlüssel entschlüsseln können.</span><span class="sxs-lookup"><span data-stu-id="1a63d-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="1a63d-113">Zum Debuggen, zur Problembehandlung oder zur Überwachung muss ein Rechenzentrumsadministrator erhöhten Zugriff anfordern, um temporäre Anmeldeinformationen zu erhalten, die Teil der Sicherheitsgruppe sind.</span><span class="sxs-lookup"><span data-stu-id="1a63d-113">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group.</span></span> <span data-ttu-id="1a63d-114">Dieser Prozess erfordert mehrere Ebenen der rechtlichen Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="1a63d-114">This process requires multiple levels of legal approval.</span></span> <span data-ttu-id="1a63d-115">Wenn der Zugriff gewährt wird, werden alle Aktivitäten protokolliert und überwacht.</span><span class="sxs-lookup"><span data-stu-id="1a63d-115">If access is granted, all activity is logged and audited.</span></span> <span data-ttu-id="1a63d-116">Darüber hinaus wird der Zugriff nur für einen festgelegten Zeitraum gewährt, nach dem er automatisch abläuft.</span><span class="sxs-lookup"><span data-stu-id="1a63d-116">In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="1a63d-117">Für zusätzlichen Schutz umfasst die DKM-Technologie das automatische Schlüsselrollover und die Archivierung.</span><span class="sxs-lookup"><span data-stu-id="1a63d-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="1a63d-118">Dadurch wird auch sichergestellt, dass Sie weiterhin auf Ihre älteren Inhalte zugreifen können, ohne sich auf unbestimmte Zeit auf denselben Schlüssel verlassen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="1a63d-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="1a63d-119">Wo nutzt Exchange Online DKM?</span><span class="sxs-lookup"><span data-stu-id="1a63d-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="1a63d-120">Microsoft verwendet [den Verteilten Schlüssel-Manager,](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) um Ihre Geheimschlüssel in Exchange Online-Rechenzentren zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1a63d-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="1a63d-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1a63d-121">For example:</span></span>
  
- <span data-ttu-id="1a63d-122">E-Mail-Kontoanmeldeinformationen für verbundene Konten.</span><span class="sxs-lookup"><span data-stu-id="1a63d-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="1a63d-123">Verbundene Konten sind Drittanbieterkonten wie Hotmail, Gmail und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1a63d-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="1a63d-124">E-Mail-Konten.</span><span class="sxs-lookup"><span data-stu-id="1a63d-124">mail accounts.</span></span>

- <span data-ttu-id="1a63d-125">Kundenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="1a63d-125">Customer key.</span></span> <span data-ttu-id="1a63d-126">Wenn Sie die [Dienstverschlüsselung mit dem Kundenschlüssel](customer-key-overview.md)verwenden, verwenden Sie [Azure Key Vault,](/azure/key-vault/key-vault-whatis) um Ihre Geheimschlüssel zu schützen.</span><span class="sxs-lookup"><span data-stu-id="1a63d-126">If you are using [Service encryption with Customer Key](customer-key-overview.md), you'll use [Azure Key Vault](/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1a63d-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1a63d-127">Related topics</span></span>

[<span data-ttu-id="1a63d-128">Verschlüsselung in Office 365</span><span class="sxs-lookup"><span data-stu-id="1a63d-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="1a63d-129">Technische Details zur Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="1a63d-129">Technical reference details about encryption</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="1a63d-130">Dienstsicherheit im Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1a63d-130">Service assurance in the Security &amp; Compliance Center</span></span>](./service-assurance.md)
