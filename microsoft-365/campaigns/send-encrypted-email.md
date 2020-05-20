---
title: Senden verschlüsselter E-Mail-Nachrichten
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Erfahren Sie, wie Sie verschlüsselte e-Mails mit Outlook senden.
ms.openlocfilehash: 5318fbe045c909e3b7f81d195a8e6b4d5eb96dc1
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322147"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="5f8aa-103">Verschlüsseln oder bezeichnen von vertraulichen e-Mails</span><span class="sxs-lookup"><span data-stu-id="5f8aa-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="5f8aa-104">Ihre Daten und Kampagneninformationen sind wichtig und werden häufig vertraulich behandelt.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="5f8aa-105">Schützen Sie diese vertraulichen Informationen mithilfe von Verschlüsselungs-und Sensitivitäts Bezeichnungen, damit Sie und Ihre e-Mail-Empfänger die Informationen mit der für Sie erforderlichen Empfindlichkeit behandeln können.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>


## <a name="best-practices"></a><span data-ttu-id="5f8aa-106">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="5f8aa-106">Best practices</span></span>

<span data-ttu-id="5f8aa-107">Bevor Sie e-Mails mit vertraulichen oder vertraulichen Informationen senden, sollten Sie Folgendes einschalten:</span><span class="sxs-lookup"><span data-stu-id="5f8aa-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="5f8aa-108">**Verschlüsselung:** Sie können Ihre e-Mails verschlüsseln, um die Vertraulichkeit der Informationen in der e-Mail zu schützen.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="5f8aa-109">Wenn Sie eine e-Mail-Nachricht verschlüsseln, wird Sie von lesbarem Nur-Text in verschlüsselten Cypher-Text konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="5f8aa-110">Nur der Empfänger mit dem privaten Schlüssel, der mit dem zum Verschlüsseln der Nachricht verwendeten öffentlichen Schlüssel übereinstimmt, kann die Nachricht zum Lesen entziffern.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="5f8aa-111">Jeder Empfänger ohne den entsprechenden privaten Schlüssel sieht jedoch unlesbaren Text.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="5f8aa-112">Ihr Administrator kann Regeln definieren, um Nachrichten automatisch zu verschlüsseln, die bestimmte Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="5f8aa-113">Beispielsweise kann Ihr Administrator eine Regel erstellen, die alle Nachrichten verschlüsselt, die außerhalb Ihrer Organisation gesendet werden, oder alle Nachrichten, die bestimmte Wörter oder Phrasen erwähnen.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="5f8aa-114">Alle Verschlüsselungsregeln werden automatisch angewendet.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="5f8aa-115">**Vertraulichkeits Bezeichnungen:** Ihre Kampagne kann auch Sensitivitäts Bezeichnungen einrichten, die Sie auf Ihre Dateien und e-Mails anwenden können, damit Sie mit den Informationsschutz Richtlinien Ihrer Kampagne konform bleiben.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="5f8aa-116">Wenn Sie eine Bezeichnung festlegen, bleibt die Bezeichnung mit Ihrer e-Mail erhalten, auch wenn Sie gesendet wird, beispielsweise indem Sie als Kopfzeile für Ihre Nachricht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagramm einer e-Mail mit Beschriftungen für Bezeichnungen und Verschlüsselung](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a><span data-ttu-id="5f8aa-118">Einrichtung</span><span class="sxs-lookup"><span data-stu-id="5f8aa-118">Set it up</span></span>

<span data-ttu-id="5f8aa-119">Wenn Sie eine Nachricht verschlüsseln möchten, die keine vordefinierte Regel erfüllt oder Ihr Administrator keine Regeln eingerichtet hat, können Sie vor dem Senden einer Nachricht eine Vielzahl unterschiedlicher Verschlüsselungsregeln anwenden.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="5f8aa-120">Wenn Sie eine verschlüsselte Nachricht von Outlook 2013 oder 2016 oder Outlook 2016 für Mac senden möchten, wählen Sie **Optionen > Berechtigungen**aus, und wählen Sie dann die benötigte Schutzoption aus.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="5f8aa-121">Sie können eine verschlüsselte Nachricht auch senden, indem Sie die Schaltfläche **schützen** in Outlook im Internet auswählen.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="5f8aa-122">Weitere Informationen finden Sie unter [senden, anzeigen und Antworten auf verschlüsselte Nachrichten in Outlook für PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span><span class="sxs-lookup"><span data-stu-id="5f8aa-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="5f8aa-123">Administratoreinstellungen</span><span class="sxs-lookup"><span data-stu-id="5f8aa-123">Admin settings</span></span>

<span data-ttu-id="5f8aa-124">Weitere Informationen zum Einrichten der e-Mail-Verschlüsselung finden Sie unter [e-Mail-Verschlüsselung in Office 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span><span class="sxs-lookup"><span data-stu-id="5f8aa-124">You can learn all about setting up email encryption at [Email encryption in Office 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="5f8aa-125">E-Mail-Nachrichten automatisch verschlüsseln</span><span class="sxs-lookup"><span data-stu-id="5f8aa-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="5f8aa-126">Administratoren können e-Mail-Flussregeln erstellen, um automatisch e-Mail-Nachrichten zu schützen, die von Ihrer Kampagne gesendet und empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="5f8aa-127">Richten Sie Regeln zum Verschlüsseln von ausgehenden e-Mail-Nachrichten ein, und entfernen Sie die Verschlüsselung aus verschlüsselten Nachrichten, die innerhalb Ihrer Organisation oder aus Antworten auf verschlüsselte Nachrichten von Ihrer Organisation gesendet</span><span class="sxs-lookup"><span data-stu-id="5f8aa-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> 

<span data-ttu-id="5f8aa-128">Sie erstellen Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail-Nachrichten mit den neuen Funktionen für die Office 365 Nachrichtenverschlüsselung (OM).</span><span class="sxs-lookup"><span data-stu-id="5f8aa-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="5f8aa-129">Definieren Sie Nachrichtenfluss Regeln für die Auslösung der Nachrichtenverschlüsselung mit den neuen OM-Funktionen mithilfe des Exchange Admin Centers (EAC).</span><span class="sxs-lookup"><span data-stu-id="5f8aa-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="5f8aa-130">Melden Sie sich in einem Webbrowser mit einem Arbeits-oder Schulkonto, dem globale Administratorberechtigungen erteilt wurden, bei Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in to Office 365.</span></span> 
2. <span data-ttu-id="5f8aa-131">Wählen Sie die Kachel admin aus.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-131">Choose the Admin tile.</span></span> 
3. <span data-ttu-id="5f8aa-132">Wählen Sie im Admin Center die Option admin Centers **> Exchange**aus.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-132">In the admin center, choose **Admin centers > Exchange**.</span></span> 

<span data-ttu-id="5f8aa-133">Weitere Informationen finden Sie unter [Definieren von Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail-Nachrichten in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span><span class="sxs-lookup"><span data-stu-id="5f8aa-133">For more information, see [Define mail flow rules to encrypt email messages in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="5f8aa-134">Branding Ihrer Verschlüsselungs Nachrichten</span><span class="sxs-lookup"><span data-stu-id="5f8aa-134">Brand your encryption messages</span></span>

<span data-ttu-id="5f8aa-135">Sie können auch Ihr Kampagnen Branding anwenden, um das Aussehen und den Text in den e-Mail-Nachrichten anzupassen.</span><span class="sxs-lookup"><span data-stu-id="5f8aa-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="5f8aa-136">Weitere Informationen finden Sie unter [Hinzufügen der Marke Ihrer Organisation zu ihren verschlüsselten Nachrichten](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span><span class="sxs-lookup"><span data-stu-id="5f8aa-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

