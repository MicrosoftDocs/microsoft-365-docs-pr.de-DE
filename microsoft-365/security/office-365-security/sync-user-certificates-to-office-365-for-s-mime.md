---
title: Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: Damit S/MIME-geschützte Nachrichten versendet werden können, müssen die entsprechenden Zertifikate eingerichtet werden. Zum Senden von verschlüsselten Nachrichten über Exchange Online verwendet das E-Mail-Programm das öffentliche Zertifikat des Empfängers, um die Nachricht zu verschlüsseln. Dieses öffentliche X.509-Zertifikat muss in Office 365 veröffentlicht werden.
ms.openlocfilehash: 7b42f757ade54e362afc65f920096252bf69eb31
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38030839"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="71d1b-105">Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME</span><span class="sxs-lookup"><span data-stu-id="71d1b-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="71d1b-106">Damit alle S/MIME-geschützten Nachrichten in Exchange Online gesendet werden können, müssen die entsprechenden Zertifikate eingerichtet sein.</span><span class="sxs-lookup"><span data-stu-id="71d1b-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="71d1b-107">Zum Senden von verschlüsselten Nachrichten über Exchange Online verwendet die e-Mail-App des Absenders das öffentliche Zertifikat des Empfängers zum Verschlüsseln der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="71d1b-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="71d1b-108">Dieses öffentliche X.509-Zertifikat muss in Office 365 veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="71d1b-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="71d1b-109">So synchronisieren Sie Zertifikate, die S/MIME unterstützen</span><span class="sxs-lookup"><span data-stu-id="71d1b-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="71d1b-110">Richten Sie S/MIME ein, indem Sie Zertifikate ausgeben und diese in Ihrem lokalen Active Directory-Domänendienst veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="71d1b-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="71d1b-111">Weitere Informationen zum Verwalten von Zertifikaten in Exchange Server finden Sie unter [digitale Zertifikate und SSL](https://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span><span class="sxs-lookup"><span data-stu-id="71d1b-111">For more information about managing certificates in Exchange Server, see [Digital Certificates and SSL](https://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>

<span data-ttu-id="71d1b-p104">Nachdem Ihre Zertifikate veröffentlicht wurden, verwenden Sie Azure Active Directory-Synchronisierungstool, um Benutzerdaten aus der lokalen Exchange-Umgebung mit Office 365 zu synchronisieren. Weitere Informationen zu diesem Prozess finden Sie unter [DirSync: Versionsverlauf für das Verzeichnissynchronisierungstool](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span><span class="sxs-lookup"><span data-stu-id="71d1b-p104">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365. For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>

<span data-ttu-id="71d1b-114">Zusammen mit dem Synchronisieren anderer Verzeichnisdaten für S/MIME-Zwecke synchronisiert das Tool die Attribute **userCertificate** und **userSMIMECertificate** für jedes Benutzerobjekt, damit die Daten zum Signieren und Verschlüsseln von Nachrichten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="71d1b-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="71d1b-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71d1b-115">More Information</span></span>

[<span data-ttu-id="71d1b-116">S/MIME für die Nachrichtensignierung und -verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="71d1b-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="71d1b-117">Azure Active Directory-Synchronisierungstool</span><span class="sxs-lookup"><span data-stu-id="71d1b-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)
