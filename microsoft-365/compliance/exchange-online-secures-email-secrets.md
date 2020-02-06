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
description: Neben dem Office 365 Trust Center, das Informationen zu Sicherheit, Datenschutz und Compliance für Office 365 bereitstellt, sollten Sie wissen, wie Office 365 zum Schutz von in den Rechenzentren bereitgestellten Geheimnissen beiträgt. Wir verwenden eine Technologie namens Distributed Key Manager (DKM).
ms.openlocfilehash: 6ba60616ee72a4457d81f3f9c2049007afdcbb1d
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800075"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="5fbaa-104">Schützen von vertraulichen Inhalten in E-Mails mit Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5fbaa-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="5fbaa-105">In diesem Artikel wird beschrieben, wie Microsoft Ihre e-Mail-Geheimnisse in ihren Rechenzentren sichert.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="5fbaa-106">Wie sichern wir geheime Informationen, die von Ihnen bereitgestellt werden?</span><span class="sxs-lookup"><span data-stu-id="5fbaa-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="5fbaa-107">Neben dem Office 365 Trust Center, das Informationen zu [Sicherheit, Datenschutz und Compliance für Office 365](https://go.microsoft.com/fwlink/?linkid=874644)bereitstellt, sollten Sie wissen, wie Office 365 zum Schutz von in den Rechenzentren bereitgestellten Geheimnissen beiträgt.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](https://go.microsoft.com/fwlink/?linkid=874644), you might want to know how Office 365 helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="5fbaa-108">Wir verwenden eine Technologie namens Distributed Key Manager (DKM).</span><span class="sxs-lookup"><span data-stu-id="5fbaa-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="5fbaa-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) ist eine clientseitige Funktionalität, die eine Reihe von geheimen Schlüsseln zum Verschlüsseln und Entschlüsseln von Informationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="5fbaa-110">Nur Mitglieder einer bestimmten Sicherheitsgruppe in Active Directory-Domänendienste können auf diese Schlüssel zugreifen, um die von DKM verschlüsselten Daten zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="5fbaa-111">In Exchange Online sind nur bestimmte Dienstkonten, unter denen die Exchange-Prozesse ausgeführt werden, Teil dieser Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="5fbaa-112">Im Rahmen des standardmäßigen betriebsverfahrens im Rechenzentrum werden keinem Menschen Anmeldeinformationen zugewiesen, die Teil dieser Sicherheitsgruppe sind, und daher hat kein Mensch Zugriff auf die Schlüssel, die diese Geheimnisse entschlüsseln können.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="5fbaa-113">Zum Debuggen, zur Problembehandlung oder zu Überwachungszwecken muss ein Rechenzentrums Administrator erhöhten Zugriff anfordern, um temporäre Anmeldeinformationen zu erhalten, die Teil der Sicherheitsgruppe sind.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-113">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group.</span></span> <span data-ttu-id="5fbaa-114">Für diesen Prozess sind mehrere Ebenen der rechtlichen Genehmigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-114">This process requires multiple levels of legal approval.</span></span> <span data-ttu-id="5fbaa-115">Wenn der Zugriff gewährt wird, werden alle Aktivitäten protokolliert und überwacht.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-115">If access is granted, all activity is logged and audited.</span></span> <span data-ttu-id="5fbaa-116">Darüber hinaus wird der Zugriff nur für ein festgelegtes Zeitintervall gewährt, nach dem es automatisch abläuft.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-116">In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="5fbaa-117">Für zusätzlichen Schutz umfasst die DKM-Technologie einen automatisierten Schlüssel Rollover und eine Archivierung.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="5fbaa-118">Dadurch wird auch sichergestellt, dass Sie weiterhin auf Ihre älteren Inhalte zugreifen können, ohne sich auf unbestimmte Zeit auf denselben Schlüssel verlassen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="5fbaa-119">Wo verwendet Exchange Online DKM?</span><span class="sxs-lookup"><span data-stu-id="5fbaa-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="5fbaa-120">Microsoft verwendet den [verteilten Schlüssel-Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) , um ihre Geheimnisse in Exchange Online-Rechenzentren zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="5fbaa-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5fbaa-121">For example:</span></span>
  
- <span data-ttu-id="5fbaa-122">E-Mail-Kontoanmeldeinformationen für verbundene Konten.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="5fbaa-123">Verbundene Konten sind Drittanbieter Konten wie Hotmail, Gmail und Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="5fbaa-124">e-Mail-Konten.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-124">mail accounts.</span></span>

- <span data-ttu-id="5fbaa-125">Kundenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-125">Customer key.</span></span> <span data-ttu-id="5fbaa-126">Wenn Sie die [Dienst Verschlüsselung mit dem Kundenschlüssel in Office 365](customer-key-overview.md)verwenden, verwenden Sie [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) , um ihre Geheimnisse zu schützen.</span><span class="sxs-lookup"><span data-stu-id="5fbaa-126">If you are using [Service encryption with Customer Key in Office 365](customer-key-overview.md), you'll use [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5fbaa-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5fbaa-127">Related topics</span></span>

[<span data-ttu-id="5fbaa-128">Verschlüsselung in Office 365</span><span class="sxs-lookup"><span data-stu-id="5fbaa-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="5fbaa-129">Technische Details zur Verschlüsselung in Office 365</span><span class="sxs-lookup"><span data-stu-id="5fbaa-129">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="5fbaa-130">Dienst Assurance im Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="5fbaa-130">Service assurance in the Office 365 Security &amp; Compliance Center</span></span>](https://go.microsoft.com/fwlink/?linkid=874645)
  

