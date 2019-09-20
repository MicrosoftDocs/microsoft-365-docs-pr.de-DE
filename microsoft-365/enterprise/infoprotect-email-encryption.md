---
title: 'Schritt 6: Konfigurieren der e-Mail-Verschlüsselung'
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
ms.openlocfilehash: 7747f5a0905a9477e9d3fd17b00eae740d76f640
ms.sourcegitcommit: 78fa107271252d902e600196a75cfa746bca73e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "37050296"
---
# <a name="step-6-configure-email-encryption"></a><span data-ttu-id="93375-103">Schritt 6: Konfigurieren der e-Mail-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="93375-103">Step 6: Configure email encryption</span></span>

<span data-ttu-id="93375-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="93375-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="93375-105">Es gibt drei Arten von e-Mail-Verschlüsselung in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93375-105">There are three types of email encryption in Microsoft 365.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="93375-106">Office-Nachrichtenverschlüsselung (Office Message Encryption, OME)</span><span class="sxs-lookup"><span data-stu-id="93375-106">Office Message Encryption (OME)</span></span> | <span data-ttu-id="93375-107">Verschlüsselung für Exchange Online e-Mails, die außerhalb Ihrer Organisation gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="93375-107">Encryption for Exchange Online email sent outside your organization.</span></span> |
| <span data-ttu-id="93375-108">Verwaltung von Informationsrechten (Information Rights Management, IRM)</span><span class="sxs-lookup"><span data-stu-id="93375-108">Information Rights Management (IRM)</span></span> | <span data-ttu-id="93375-109">Verschlüsselung und Berechtigungen, die mit der e-Mail Reisen.</span><span class="sxs-lookup"><span data-stu-id="93375-109">Encryption and permissions that travel with the email.</span></span> |
| <span data-ttu-id="93375-110">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="93375-110">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="93375-111">E-Mail-Schutz mit Verschlüsselung und digitaler Signatur.</span><span class="sxs-lookup"><span data-stu-id="93375-111">Email protection with encryption and digital signatures.</span></span> |
|||

## <a name="office-365-message-encryption"></a><span data-ttu-id="93375-112">Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="93375-112">Office 365 Message Encryption</span></span>

<span data-ttu-id="93375-113">Mit OM kann Ihre Organisation verschlüsselte e-Mail-Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="93375-113">With OME, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="93375-114">OM kann mit Outlook.com, Yahoo!, Gmail und anderen e-Mail-Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="93375-114">OME works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="93375-115">Die e-Mail-Nachrichtenverschlüsselung hilft sicherzustellen, dass nur vorgesehene Empfänger die Nachricht anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="93375-115">Email message encryption helps ensure that only intended recipients can view the message.</span></span>

![OM-Verschlüsselung von e-Mail-Nachrichten](./media/infoprotect-email-encryption/ome-encryption.png)

<span data-ttu-id="93375-117">Sie richten Transportregeln ein, die die Bedingungen für die Verschlüsselung definieren.</span><span class="sxs-lookup"><span data-stu-id="93375-117">You set up transport rules that define the conditions for encryption.</span></span> <span data-ttu-id="93375-118">Wenn ein Benutzer eine Nachricht sendet, die mit einer Regel übereinstimmt, wird die Verschlüsselung automatisch angewendet.</span><span class="sxs-lookup"><span data-stu-id="93375-118">When a user sends a message that matches a rule, encryption is applied automatically.</span></span>

<span data-ttu-id="93375-119">Um verschlüsselte Nachrichten anzuzeigen, können Empfänger entweder einen einmaligen Zugangscode erhalten, sich mit einem Microsoft-Konto anmelden oder sich mit einem Arbeits-oder Schulkonto anmelden, das Microsoft 365 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="93375-119">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Microsoft 365.</span></span> <span data-ttu-id="93375-120">Empfänger können auch verschlüsselte Antworten senden.</span><span class="sxs-lookup"><span data-stu-id="93375-120">Recipients can also send encrypted replies.</span></span> <span data-ttu-id="93375-121">Sie benötigen kein eigenes Microsoft 365-Abonnement, um verschlüsselte Nachrichten anzuzeigen oder verschlüsselte Antworten zu senden.</span><span class="sxs-lookup"><span data-stu-id="93375-121">They don't need their own Microsoft 365 subscription to view encrypted messages or send encrypted replies.</span></span>

<span data-ttu-id="93375-122">Weitere Informationen finden Sie unter [Verschlüsselung in Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span><span class="sxs-lookup"><span data-stu-id="93375-122">For more information, see [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span></span>

## <a name="irm"></a><span data-ttu-id="93375-123">IRM</span><span class="sxs-lookup"><span data-stu-id="93375-123">IRM</span></span>

<span data-ttu-id="93375-124">IRM in Microsoft 365 hilft Ihnen bei der Sicherung Ihrer Informationen mit zusätzlicher Verschlüsselung und durch Anwendung einer intelligenten Richtlinie, die angibt, wer Zugriff hat, was Sie tun können.</span><span class="sxs-lookup"><span data-stu-id="93375-124">IRM in Microsoft 365 helps you secure your information with additional encryption and by applying an intelligent policy that specifies who has access what they can do.</span></span> <span data-ttu-id="93375-125">Bei e-Mail-Nachrichten können Sie IRM für die Verschlüsselung verwenden und Nutzungseinschränkungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="93375-125">For email messages, you can use IRM for encryption and to apply usage restrictions.</span></span> <span data-ttu-id="93375-126">Sie können beispielsweise angeben, dass einige Empfänger über alle Möglichkeiten zum Verwalten der e-Mail verfügen und andere nicht die Möglichkeit haben, die e-Mail zu drucken oder weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="93375-126">For example, you can specify that some recipients have all abilities to manage the email and some do not have the ability to print or forward the email.</span></span> 

<span data-ttu-id="93375-127">IRM-Richtlinien werden in Microsoft 365 konfiguriert und können auf Dokumente in SharePoint Online und e-Mail-Nachrichten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="93375-127">IRM policies are configured within Microsoft 365 and can apply to documents in SharePoint Online and email messages.</span></span> <span data-ttu-id="93375-128">Eine durch IRM geschützte e-Mail enthält die angewendeten Richtlinieneinstellungen, die angewendet werden und mit der Sie Reisen.</span><span class="sxs-lookup"><span data-stu-id="93375-128">An IRM-protected email includes the applied policy settings applied and travel with it.</span></span> 

![IRM-Schutz für e-Mail-Nachrichten](./media/infoprotect-email-encryption/irm-protection.png)

<span data-ttu-id="93375-130">Wenn der Empfänger die e-Mail mit der eingeschlossenen Richtlinie öffnet, werden die Richtlinieneinstellungen verwendet, um die Nachricht zu entschlüsseln und festzulegen, was der Empfänger damit tun kann.</span><span class="sxs-lookup"><span data-stu-id="93375-130">When the recipient opens the email with the included policy, the policy settings are used to decrypt the message and determine what the recipient can do with it.</span></span> 

<span data-ttu-id="93375-131">Weitere Informationen finden Sie unter [Verwaltung von Informationsrechten in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="93375-131">For more information, see [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span></span>

## <a name="smime"></a><span data-ttu-id="93375-132">S/MIME</span><span class="sxs-lookup"><span data-stu-id="93375-132">S/MIME</span></span>

<span data-ttu-id="93375-133">S/MIME ist eine digitale zertifikatbasierte e-Mail-basierte Schutzlösung, mit der Sie eine Nachricht sowohl verschlüsseln als auch digital signieren können.</span><span class="sxs-lookup"><span data-stu-id="93375-133">S/MIME is a digital certificate-based email-based protection solution that allows you to both encrypt and digitally sign a message.</span></span> <span data-ttu-id="93375-134">Durch die Nachrichtenverschlüsselung kann sichergestellt werden, dass nur der vorgesehene Empfänger die Nachricht öffnen und lesen kann.</span><span class="sxs-lookup"><span data-stu-id="93375-134">The message encryption helps ensure that only the intended recipient can open and read the message.</span></span> <span data-ttu-id="93375-135">Eine digitale Signatur hilft dem Empfänger, die Identität des Absenders zu überprüfen und festzustellen, ob der Absender ihn nur gesendet hätte.</span><span class="sxs-lookup"><span data-stu-id="93375-135">A digital signature helps the recipient validate the identity of the sender and determine that only the sender could have sent it.</span></span>

![S/MIME-Schutz für e-Mail-Nachrichten](./media/infoprotect-email-encryption/smime-protection.png)

<span data-ttu-id="93375-137">S/MIME kann für e-Mails an andere Postfächer in Ihrem Microsoft 365-Abonnement oder für externe Benutzer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="93375-137">S/MIME can be used for email to other mailboxes in your Microsoft 365 subscription or to external users.</span></span>
<span data-ttu-id="93375-138">Sowohl Nachrichtenverschlüsselung als auch digitale Signaturen werden mithilfe digitaler Zertifikate ermöglicht, die die öffentlichen und privaten Schlüssel zum Verschlüsseln oder Entschlüsseln von Nachrichten sowie zum Erstellen und Überprüfen digitaler Signaturen enthalten.</span><span class="sxs-lookup"><span data-stu-id="93375-138">Both message encryption and digital signatures are made possible through the use of digital certificates that contain the public and private keys for encrypting or decrypting messages and creating and verifying digital signatures.</span></span>
<span data-ttu-id="93375-139">Damit S/MIME verwendet werden kann, müssen Sie über die öffentlichen Schlüssel für jeden Empfänger verfügen.</span><span class="sxs-lookup"><span data-stu-id="93375-139">To use S/MIME, you must have the public keys for each recipient.</span></span> <span data-ttu-id="93375-140">Empfänger verwalten ihre eigenen privaten Schlüssel, die sicher bleiben müssen.</span><span class="sxs-lookup"><span data-stu-id="93375-140">Recipients maintain their own private keys, which must remain secure.</span></span> <span data-ttu-id="93375-141">Wenn Ihr privater Schlüssel kompromittiert ist, müssen Sie ein neues digitales Zertifikat erhalten und öffentliche Schlüssel auf alle potenziellen Absender verteilen.</span><span class="sxs-lookup"><span data-stu-id="93375-141">If your private key is compromised, you need to get a new digital certificate and redistribute public keys to all potential senders.</span></span>

<span data-ttu-id="93375-142">Weitere Informationen finden Sie unter [S/MIME für die Nachrichtensignierung und -verschlüsselung](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span><span class="sxs-lookup"><span data-stu-id="93375-142">For more information, see [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span></span>


<span data-ttu-id="93375-143">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step6) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="93375-143">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="93375-144">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="93375-144">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)|[<span data-ttu-id="93375-145">Konfigurieren von Privileged Access Management für Office 365</span><span class="sxs-lookup"><span data-stu-id="93375-145">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
