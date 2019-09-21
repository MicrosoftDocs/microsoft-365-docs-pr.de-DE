---
title: Festlegen eines Ablaufdatums für E-Mails, die mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden.
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Mit Office 365 erweiterten Nachrichten Verschlüsselungsfunktionen über Office 365-Nachrichtenverschlüsselung (OM) können Sie Ihre e-Mail-Sicherheit erweitern, indem Sie ein Ablaufdatum für e-Mails über eine benutzerdefinierte Marken Vorlage festlegen.
ms.openlocfilehash: 7c4ad1fb4a91bd62569edc5db9042dfbd2dbd9fe
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082249"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="8d14a-103">Festlegen eines Ablaufdatums für E-Mails, die mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="8d14a-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="8d14a-104">Office 365 erweiterte Nachrichtenverschlüsselung steht über Office 365 Nachrichtenverschlüsselung in bestimmten Abonnements zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8d14a-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="8d14a-105">Die erweiterte Nachrichtenverschlüsselung ist in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 und Office 365 Education A5 enthalten.</span><span class="sxs-lookup"><span data-stu-id="8d14a-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="8d14a-106">Wenn Ihre Organisation über ein Office 365es Abonnement verfügt, das nicht Office 365 erweiterte Nachrichtenverschlüsselung enthält, können Sie erweiterte Nachrichtenverschlüsselung als Add-on mit E5-Kompatibilität der Advanced Compliance-SKU erwerben.</span><span class="sxs-lookup"><span data-stu-id="8d14a-106">If your organization has an Office 365 subscription that doesn't include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="8d14a-107">Sie können Nachrichtenablauf bei e-Mails verwenden, die Ihre Benutzer an externe Empfänger senden, die das OM-Portal zum Zugriff auf verschlüsselte e-Mails verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d14a-107">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="8d14a-108">Sie erzwingen, dass Empfänger das OM-Portal verwenden, um verschlüsselte e-Mails anzuzeigen und zu beantworten, die von Ihrer Organisation gesendet werden, indem Sie eine benutzerdefinierte Marken Vorlage verwenden, die ein Ablaufdatum in Windows PowerShell angibt.</span><span class="sxs-lookup"><span data-stu-id="8d14a-108">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="8d14a-109">Wenn Sie als globaler O365-Administrator Ihre Unternehmensmarke anwenden, um das Aussehen der e-Mail-Nachrichten Ihrer Office 365 Organisation anzupassen, können Sie auch einen Ablauf für diese e-Mail-Nachrichten angeben.</span><span class="sxs-lookup"><span data-stu-id="8d14a-109">As an O365 global administrator, when you apply your company brand to customize the look of your Office 365 organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="8d14a-110">Mit Office 365 erweiterten Nachrichtenverschlüsselung können Sie mehrere Vorlagen für verschlüsselte e-Mails erstellen, die aus Ihrer Organisation stammen.</span><span class="sxs-lookup"><span data-stu-id="8d14a-110">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="8d14a-111">Mithilfe einer Vorlage können Sie steuern, wie lange Empfänger Zugriff auf von Ihren Benutzern gesendete e-Mails haben.</span><span class="sxs-lookup"><span data-stu-id="8d14a-111">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="8d14a-112">Wenn ein Endbenutzer e-Mails erhält, für die ein Ablaufdatum festgelegt wurde, sieht der Benutzer das Ablaufdatum in der Wrapper-e-Mail.</span><span class="sxs-lookup"><span data-stu-id="8d14a-112">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="8d14a-113">Wenn ein Benutzer versucht, eine abgelaufene e-Mail zu öffnen, wird im OM-Portal ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8d14a-113">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="8d14a-114">Sie können nur Ablaufdaten für e-Mails an externe Empfänger festlegen.</span><span class="sxs-lookup"><span data-stu-id="8d14a-114">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="8d14a-115">Bei Office 365 erweiterten Nachrichtenverschlüsselung wendet der Office 365 den Wrapper bei jeder Anwendung des benutzerdefinierten Branding auf e-Mail an, die der Nachrichtenfluss Regel entspricht, auf die die Vorlage angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8d14a-115">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="8d14a-116">Außerdem können Sie die Ablaufzeit nur verwenden, wenn Sie benutzerdefiniertes Branding verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d14a-116">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="8d14a-117">Erstellen einer benutzerdefinierten Branding-Vorlage zum Erzwingen des e-Mail-Ablaufs mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d14a-117">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="8d14a-118">Stellen Sie eine [Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) mit einem Konto her, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt.</span><span class="sxs-lookup"><span data-stu-id="8d14a-118">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your Office 365 organization.</span></span>

2. <span data-ttu-id="8d14a-119">Führen Sie das Cmdlet New-OMEConfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="8d14a-119">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="8d14a-120">Wobei Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="8d14a-120">Where:</span></span>

- <span data-ttu-id="8d14a-121">`Identity`ist der Name der benutzerdefinierten Vorlage.</span><span class="sxs-lookup"><span data-stu-id="8d14a-121">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="8d14a-122">`ExternalMailExpiryInDays`Gibt an, wie viele Tage e-Mails von Empfängern aufbewahrt werden können, bevor Sie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="8d14a-122">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="8d14a-123">Sie können einen beliebigen Wert zwischen 1 bis 730 Tagen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d14a-123">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="8d14a-124">Weitere Informationen zu Office 365 erweiterte Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="8d14a-124">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="8d14a-125">Erweiterte Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="8d14a-125">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="8d14a-126">Widerrufen von E-Mails, die von der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden</span><span class="sxs-lookup"><span data-stu-id="8d14a-126">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="8d14a-127">Beschreibung des Nachrichtenrichtlinien-und Kompatibilitätsdiensts</span><span class="sxs-lookup"><span data-stu-id="8d14a-127">Message policy and compliance service description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
