---
title: 'Schritt 6: Konfigurieren der E-Mail-Verschlüsselung'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Verstehen und Konfigurieren von Privileged Access Management für Office 365.
ms.openlocfilehash: 252a5f76197deb1034d200553308a281ef079957
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600922"
---
# <a name="step-6-configure-email-encryption"></a><span data-ttu-id="696df-103">Schritt 6: Konfigurieren der E-Mail-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="696df-103">Step 6: Configure email encryption</span></span>

<span data-ttu-id="696df-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="696df-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Phase 6: Schutz von Daten](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="696df-106">Es gibt drei Arten von e-Mail-Verschlüsselung in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="696df-106">There are three types of email encryption in Microsoft 365.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="696df-107">Office-Nachrichtenverschlüsselung (Office Message Encryption, OME)</span><span class="sxs-lookup"><span data-stu-id="696df-107">Office Message Encryption (OME)</span></span> | <span data-ttu-id="696df-108">Verschlüsselung für Exchange Online e-Mails, die außerhalb Ihrer Organisation gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="696df-108">Encryption for Exchange Online email sent outside your organization.</span></span> |
| <span data-ttu-id="696df-109">Verwaltung von Informationsrechten (Information Rights Management, IRM)</span><span class="sxs-lookup"><span data-stu-id="696df-109">Information Rights Management (IRM)</span></span> | <span data-ttu-id="696df-110">Verschlüsselung und Berechtigungen, die mit der e-Mail Reisen.</span><span class="sxs-lookup"><span data-stu-id="696df-110">Encryption and permissions that travel with the email.</span></span> |
| <span data-ttu-id="696df-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="696df-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="696df-112">E-Mail-Schutz mit Verschlüsselung und digitaler Signatur.</span><span class="sxs-lookup"><span data-stu-id="696df-112">Email protection with encryption and digital signatures.</span></span> |
|||

## <a name="office-365-message-encryption"></a><span data-ttu-id="696df-113">Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="696df-113">Office 365 Message Encryption</span></span>

<span data-ttu-id="696df-114">Mit OM kann Ihre Organisation verschlüsselte e-Mail-Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="696df-114">With OME, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="696df-115">OM kann mit Outlook.com, Yahoo!, Gmail und anderen e-Mail-Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="696df-115">OME works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="696df-116">Die e-Mail-Nachrichtenverschlüsselung hilft sicherzustellen, dass nur vorgesehene Empfänger die Nachricht anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="696df-116">Email message encryption helps ensure that only intended recipients can view the message.</span></span>

![OM-Verschlüsselung von e-Mail-Nachrichten](./media/infoprotect-email-encryption/ome-encryption.png)

<span data-ttu-id="696df-118">Sie richten Transportregeln ein, die die Bedingungen für die Verschlüsselung definieren.</span><span class="sxs-lookup"><span data-stu-id="696df-118">You set up transport rules that define the conditions for encryption.</span></span> <span data-ttu-id="696df-119">Wenn ein Benutzer eine Nachricht sendet, die mit einer Regel übereinstimmt, wird die Verschlüsselung automatisch angewendet.</span><span class="sxs-lookup"><span data-stu-id="696df-119">When a user sends a message that matches a rule, encryption is applied automatically.</span></span>

<span data-ttu-id="696df-120">Um verschlüsselte Nachrichten anzuzeigen, können Empfänger entweder einen einmaligen Zugangscode erhalten, sich mit einem Microsoft-Konto anmelden oder sich mit einem Arbeits-oder Schulkonto anmelden, das Microsoft 365 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="696df-120">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Microsoft 365.</span></span> <span data-ttu-id="696df-121">Empfänger können auch verschlüsselte Antworten senden.</span><span class="sxs-lookup"><span data-stu-id="696df-121">Recipients can also send encrypted replies.</span></span> <span data-ttu-id="696df-122">Sie benötigen kein eigenes Microsoft 365-Abonnement, um verschlüsselte Nachrichten anzuzeigen oder verschlüsselte Antworten zu senden.</span><span class="sxs-lookup"><span data-stu-id="696df-122">They don't need their own Microsoft 365 subscription to view encrypted messages or send encrypted replies.</span></span>

<span data-ttu-id="696df-123">Weitere Informationen finden Sie unter [Verschlüsselung in Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span><span class="sxs-lookup"><span data-stu-id="696df-123">For more information, see [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span></span>

## <a name="irm"></a><span data-ttu-id="696df-124">IRM</span><span class="sxs-lookup"><span data-stu-id="696df-124">IRM</span></span>

<span data-ttu-id="696df-125">IRM in Microsoft 365 hilft Ihnen bei der Sicherung Ihrer Informationen mit zusätzlicher Verschlüsselung und durch Anwendung einer intelligenten Richtlinie, die angibt, wer Zugriff hat, was Sie tun können.</span><span class="sxs-lookup"><span data-stu-id="696df-125">IRM in Microsoft 365 helps you secure your information with additional encryption and by applying an intelligent policy that specifies who has access what they can do.</span></span> <span data-ttu-id="696df-126">Bei e-Mail-Nachrichten können Sie IRM für die Verschlüsselung verwenden und Nutzungseinschränkungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="696df-126">For email messages, you can use IRM for encryption and to apply usage restrictions.</span></span> <span data-ttu-id="696df-127">Sie können beispielsweise angeben, dass einige Empfänger über alle Möglichkeiten zum Verwalten der e-Mail verfügen und andere nicht die Möglichkeit haben, die e-Mail zu drucken oder weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="696df-127">For example, you can specify that some recipients have all abilities to manage the email and some do not have the ability to print or forward the email.</span></span> 

<span data-ttu-id="696df-128">IRM-Richtlinien werden in Microsoft 365 konfiguriert und können auf Dokumente in SharePoint Online und e-Mail-Nachrichten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="696df-128">IRM policies are configured within Microsoft 365 and can apply to documents in SharePoint Online and email messages.</span></span> <span data-ttu-id="696df-129">Eine durch IRM geschützte e-Mail enthält die angewendeten Richtlinieneinstellungen, die angewendet werden und mit der Sie Reisen.</span><span class="sxs-lookup"><span data-stu-id="696df-129">An IRM-protected email includes the applied policy settings applied and travel with it.</span></span> 

![IRM-Schutz für e-Mail-Nachrichten](./media/infoprotect-email-encryption/irm-protection.png)

<span data-ttu-id="696df-131">Wenn der Empfänger die e-Mail mit der eingeschlossenen Richtlinie öffnet, werden die Richtlinieneinstellungen verwendet, um die Nachricht zu entschlüsseln und festzulegen, was der Empfänger damit tun kann.</span><span class="sxs-lookup"><span data-stu-id="696df-131">When the recipient opens the email with the included policy, the policy settings are used to decrypt the message and determine what the recipient can do with it.</span></span> 

<span data-ttu-id="696df-132">Weitere Informationen finden Sie unter [Verwaltung von Informationsrechten in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="696df-132">For more information, see [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span></span>

## <a name="smime"></a><span data-ttu-id="696df-133">S/MIME</span><span class="sxs-lookup"><span data-stu-id="696df-133">S/MIME</span></span>

<span data-ttu-id="696df-134">S/MIME ist eine digitale zertifikatbasierte e-Mail-basierte Schutzlösung, mit der Sie eine Nachricht sowohl verschlüsseln als auch digital signieren können.</span><span class="sxs-lookup"><span data-stu-id="696df-134">S/MIME is a digital certificate-based email-based protection solution that allows you to both encrypt and digitally sign a message.</span></span> <span data-ttu-id="696df-135">Die Nachrichtenverschlüsselung hilft Ihnen bei der Sicherstellung, dass nur der beabsichtigte Empfänger die Nachricht öffnen und lesen kann.</span><span class="sxs-lookup"><span data-stu-id="696df-135">The message encryption helps ensure that only the intended recipient can open and read the message.</span></span> <span data-ttu-id="696df-136">Eine digitale Signatur hilft dem Empfänger, die Identität des Absenders zu überprüfen und festzustellen, ob der Absender ihn nur gesendet hätte.</span><span class="sxs-lookup"><span data-stu-id="696df-136">A digital signature helps the recipient validate the identity of the sender and determine that only the sender could have sent it.</span></span>

![S/MIME-Schutz für e-Mail-Nachrichten](./media/infoprotect-email-encryption/smime-protection.png)

<span data-ttu-id="696df-138">S/MIME kann für e-Mails an andere Postfächer in Ihrem Microsoft 365-Abonnement oder für externe Benutzer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="696df-138">S/MIME can be used for email to other mailboxes in your Microsoft 365 subscription or to external users.</span></span>
<span data-ttu-id="696df-139">Sowohl Nachrichtenverschlüsselung als auch digitale Signaturen werden mithilfe digitaler Zertifikate ermöglicht, die die öffentlichen und privaten Schlüssel zum Verschlüsseln oder Entschlüsseln von Nachrichten sowie zum Erstellen und Überprüfen digitaler Signaturen enthalten.</span><span class="sxs-lookup"><span data-stu-id="696df-139">Both message encryption and digital signatures are made possible through the use of digital certificates that contain the public and private keys for encrypting or decrypting messages and creating and verifying digital signatures.</span></span>
<span data-ttu-id="696df-140">Damit S/MIME verwendet werden kann, müssen Sie über die öffentlichen Schlüssel für jeden Empfänger verfügen.</span><span class="sxs-lookup"><span data-stu-id="696df-140">To use S/MIME, you must have the public keys for each recipient.</span></span> <span data-ttu-id="696df-141">Empfänger verwalten ihre eigenen privaten Schlüssel, die sicher bleiben müssen.</span><span class="sxs-lookup"><span data-stu-id="696df-141">Recipients maintain their own private keys, which must remain secure.</span></span> <span data-ttu-id="696df-142">Wenn Ihr privater Schlüssel kompromittiert ist, müssen Sie ein neues digitales Zertifikat erhalten und öffentliche Schlüssel auf alle potenziellen Absender verteilen.</span><span class="sxs-lookup"><span data-stu-id="696df-142">If your private key is compromised, you need to get a new digital certificate and redistribute public keys to all potential senders.</span></span>

<span data-ttu-id="696df-143">Weitere Informationen finden Sie unter [S/MIME für die Nachrichtensignierung und -verschlüsselung](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span><span class="sxs-lookup"><span data-stu-id="696df-143">For more information, see [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span></span>


<span data-ttu-id="696df-144">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step6) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="696df-144">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="696df-145">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="696df-145">Next step</span></span>

|||
|:-------|:-----|
|![Schritt 7](./media/stepnumbers/Step7.png)|[<span data-ttu-id="696df-147">Konfigurieren von Privileged Access Management für Office 365</span><span class="sxs-lookup"><span data-stu-id="696df-147">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
