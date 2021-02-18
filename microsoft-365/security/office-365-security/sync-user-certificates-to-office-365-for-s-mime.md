---
title: Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie geeignete Zertifikate in Office 365 veröffentlichen, bevor Sie S/MIME-geschützte Nachrichten in Exchange Online senden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8c6d3968d617bcb503057c47567182091010c726
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290201"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="e8d33-103">Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME</span><span class="sxs-lookup"><span data-stu-id="e8d33-103">Sync user certificates to Office 365 for S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e8d33-104">Bevor jemand S/MIME-geschützte Nachrichten in Exchange Online senden kann, müssen die entsprechenden Zertifikate eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="e8d33-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="e8d33-105">Um verschlüsselte Nachrichten über Exchange Online zu senden, verwendet die E-Mail-App des Absenders das öffentliche Zertifikat des Empfängers, um die Nachricht zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="e8d33-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="e8d33-106">Dieses öffentliche X.509-Zertifikat muss in Office 365 veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="e8d33-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="e8d33-107">So synchronisieren Sie Zertifikate, die S/MIME unterstützen</span><span class="sxs-lookup"><span data-stu-id="e8d33-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="e8d33-108">Richten Sie S/MIME ein, indem Sie Zertifikate ausgeben und diese in Ihrem lokalen Active Directory-Domänendienst veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e8d33-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="e8d33-109">Weitere Informationen finden Sie unter [Active Directory-Zertifikatdienste: Übersicht](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="e8d33-109">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="e8d33-110">Nachdem Ihre Zertifikate veröffentlicht wurden, verwenden Sie das Azure AD Connect-Tool, um Benutzerdaten aus Ihrer lokalen Exchange-Umgebung mit Office 365 zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="e8d33-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="e8d33-111">Weitere Informationen zu diesem Prozess finden Sie unter [Azure AD Connect-Synchronisierung: Verstehen und Anpassen der Synchronisierung.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)</span><span class="sxs-lookup"><span data-stu-id="e8d33-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="e8d33-112">Neben der Synchronisierung anderer Verzeichnisdaten synchronisiert das Tool für S/MIME-Zwecke die  **Attribute userCertificate** und **userSMIMECertificate** für jedes Benutzerobjekt, sodass die Daten zum Signieren und Verschlüsseln von Nachrichten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e8d33-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="e8d33-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8d33-113">More Information</span></span>

[<span data-ttu-id="e8d33-114">S/MIME für die Nachrichtensignierung und -verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="e8d33-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="e8d33-115">Was ist Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="e8d33-115">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
