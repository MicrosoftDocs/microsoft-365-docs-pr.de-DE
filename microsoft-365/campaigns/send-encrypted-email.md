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
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Erfahren Sie, wie Sie verschlüsselte E-Mails mithilfe von Outlook senden.
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044216"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="b2f7a-103">Verschlüsseln oder beschriften Sie Ihre vertraulichen E-Mails</span><span class="sxs-lookup"><span data-stu-id="b2f7a-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="b2f7a-104">Ihre Daten und Kampagneninformationen sind wichtig und häufig vertraulich.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="b2f7a-105">Schützen Sie diese vertraulichen Informationen mithilfe von Verschlüsselungs- und Vertraulichkeitsbezeichnungen, damit Sie und Ihre E-Mail-Empfänger die Informationen mit der benötigten Vertraulichkeit behandeln.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="b2f7a-106">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="b2f7a-106">Best practices</span></span>

<span data-ttu-id="b2f7a-107">Bevor Sie E-Mails mit vertraulichen oder vertraulichen Informationen senden, sollten Sie dies aktivieren:</span><span class="sxs-lookup"><span data-stu-id="b2f7a-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="b2f7a-108">**Verschlüsselung:** Sie können Ihre E-Mails verschlüsseln, um den Datenschutz der Informationen in der E-Mail zu schützen.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="b2f7a-109">Wenn Sie eine E-Mail-Nachricht verschlüsseln, wird sie von lesbarem nur-Text in scrambled -Text konvertiert.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="b2f7a-110">Nur der Empfänger, der über den privaten Schlüssel verfügt, der dem zum Verschlüsseln der Nachricht verwendeten öffentlichen Schlüssel entspricht, kann die Nachricht zum Lesen entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="b2f7a-111">Jeder Empfänger ohne den entsprechenden privaten Schlüssel sieht jedoch unentschlüsselten Text.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="b2f7a-112">Ihr Administrator kann Regeln definieren, um Nachrichten, die bestimmte Kriterien erfüllen, automatisch zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="b2f7a-113">Beispielsweise kann Ihr Administrator eine Regel erstellen, die alle nachrichten verschlüsselt, die außerhalb Ihrer Organisation gesendet werden, oder alle Nachrichten, die bestimmte Wörter oder Ausdrücke erwähnen.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="b2f7a-114">Verschlüsselungsregeln werden automatisch angewendet.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="b2f7a-115">**Vertraulichkeitsbezeichnungen:** Ihre Kampagne kann auch Vertraulichkeitsbezeichnungen einrichten, die Sie auf Ihre Dateien und E-Mails anwenden können, um sie mit den Informationsschutzrichtlinien Ihrer Kampagne kompatibel zu halten.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="b2f7a-116">Wenn Sie eine Bezeichnung festlegen, bleibt die Bezeichnung auch dann bei Ihrer E-Mail erhalten, wenn sie gesendet wird, z. B. indem sie als Kopfzeile ihrer Nachricht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagramm einer E-Mail mit Beschriftungen und Verschlüsselung](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="b2f7a-118">Einrichtung</span><span class="sxs-lookup"><span data-stu-id="b2f7a-118">Set it up</span></span>

<span data-ttu-id="b2f7a-119">Wenn Sie eine Nachricht verschlüsseln möchten, die keine vordefinierte Regel erfüllt, oder Wenn Ihr Administrator keine Regeln eingerichtet hat, können Sie eine Vielzahl verschiedener Verschlüsselungsregeln anwenden, bevor Sie die Nachricht senden.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="b2f7a-120">Wenn Sie eine verschlüsselte Nachricht aus Outlook 2013 oder 2016 oder Outlook 2016 für Mac senden möchten, wählen Sie Optionen **>** Berechtigungen aus, und wählen Sie dann die schutzoption aus, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="b2f7a-121">Sie können auch eine verschlüsselte  Nachricht senden, indem Sie in Outlook im Web auf die Schaltfläche "Schützen" klicken.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="b2f7a-122">Weitere Informationen finden Sie unter Senden, Anzeigen und Antworten auf verschlüsselte [Nachrichten in Outlook für PC.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)</span><span class="sxs-lookup"><span data-stu-id="b2f7a-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="b2f7a-123">Administratoreinstellungen</span><span class="sxs-lookup"><span data-stu-id="b2f7a-123">Admin settings</span></span>

<span data-ttu-id="b2f7a-124">Weitere Informationen zum Einrichten der E-Mail-Verschlüsselung finden Sie bei [der E-Mail-Verschlüsselung in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)</span><span class="sxs-lookup"><span data-stu-id="b2f7a-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="b2f7a-125">Automatisches Verschlüsseln von E-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="b2f7a-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="b2f7a-126">Administratoren können Nachrichtenflussregeln erstellen, um automatisch E-Mail-Nachrichten zu schützen, die von Ihrer Kampagne gesendet und empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="b2f7a-127">Richten Sie Regeln ein, um alle ausgehenden E-Mail-Nachrichten zu verschlüsseln und die Verschlüsselung von verschlüsselten Nachrichten zu entfernen, die von innerhalb Ihrer Organisation oder aus Antworten auf verschlüsselte Nachrichten von Ihrer Organisation gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="b2f7a-128">Sie erstellen Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten mit den neuen Funktionen der Office 365-Nachrichtenverschlüsselung (Office 365 Message Encryption, OME).</span><span class="sxs-lookup"><span data-stu-id="b2f7a-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="b2f7a-129">Definieren von Nachrichtenflussregeln zum Auslösen der Nachrichtenverschlüsselung mit den neuen OME-Funktionen mithilfe der Exchange Admin Center (EAC).</span><span class="sxs-lookup"><span data-stu-id="b2f7a-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="b2f7a-130">Melden Sie sich in einem Webbrowser mit einem Arbeits- oder Schulkonto an, dem globale Administratorberechtigungen erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="b2f7a-131">Wählen Sie die Kachel "Admin" aus.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="b2f7a-132">Wählen Sie im Admin Center admin **center > Exchange aus.**</span><span class="sxs-lookup"><span data-stu-id="b2f7a-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="b2f7a-133">Weitere Informationen finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten.](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)</span><span class="sxs-lookup"><span data-stu-id="b2f7a-133">For more information, see [Define mail flow rules to encrypt email messages](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="b2f7a-134">Ihre Verschlüsselungsnachrichten mit einem Markenbranding bebranden</span><span class="sxs-lookup"><span data-stu-id="b2f7a-134">Brand your encryption messages</span></span>

<span data-ttu-id="b2f7a-135">Sie können Ihr Kampagnenbranding auch anwenden, um das Aussehen und den Text in den E-Mail-Nachrichten anzupassen.</span><span class="sxs-lookup"><span data-stu-id="b2f7a-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="b2f7a-136">Weitere Informationen finden Sie unter "Hinzufügen der Marke Ihrer [Organisation zu Ihren verschlüsselten Nachrichten".](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)</span><span class="sxs-lookup"><span data-stu-id="b2f7a-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>
