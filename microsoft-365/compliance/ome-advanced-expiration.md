---
title: Festlegen eines Ablaufdatums für E-Mails, die mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden.
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Verwenden Office 365 Advanced Message Encryption, um Ihre E-Mail-Sicherheit zu erhöhen, indem Sie ein Ablaufdatum für E-Mails über eine benutzerdefinierte Markenvorlage festlegen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927785"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="2fe37-103">Festlegen eines Ablaufdatums für E-Mails, die mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="2fe37-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="2fe37-104">Office 365 Advanced Message Encryption ist in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Preis für gemeinnützige Mitarbeiter), Office 365 Enterprise E5 (Preis für gemeinnützige Mitarbeiter) und Office 365 Education A5 enthalten.</span><span class="sxs-lookup"><span data-stu-id="2fe37-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="2fe37-105">Wenn Ihre Organisation über ein Abonnement verfügt, das Office 365 Advanced Message Encryption nicht enthält, können Sie es mit dem Microsoft 365 E5 Compliance SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preis für gemeinnützige Mitarbeiter) oder das Office 365 Advanced Compliance SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preis für gemeinnützige Mitarbeiter) oder Office 365 SKUs erwerben.</span><span class="sxs-lookup"><span data-stu-id="2fe37-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="2fe37-106">Sie können den Nachrichtenablauf für E-Mails verwenden, die Ihre Benutzer an externe Empfänger senden, die das OME-Portal für den Zugriff auf verschlüsselte E-Mails verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fe37-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="2fe37-107">Sie erzwingen, dass Empfänger das OME-Portal verwenden, um verschlüsselte E-Mails, die von Ihrer Organisation gesendet werden, mithilfe einer benutzerdefinierten Markenvorlage anzeigen und beantworten zu können, die ein Ablaufdatum in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2fe37-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows PowerShell.</span></span>

<span data-ttu-id="2fe37-108">Als globaler Office 365 können Sie auch einen Ablauf für diese E-Mail-Nachrichten angeben, wenn Sie Ihre Unternehmensmarke anwenden, um das Erscheinungsbild der E-Mail-Nachrichten Ihrer Organisation anzupassen.</span><span class="sxs-lookup"><span data-stu-id="2fe37-108">As an Office 365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="2fe37-109">Mit Office 365 Advanced Message Encryption können Sie mehrere Vorlagen für verschlüsselte E-Mails erstellen, die aus Ihrer Organisation stammen.</span><span class="sxs-lookup"><span data-stu-id="2fe37-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="2fe37-110">Mithilfe einer Vorlage können Sie steuern, wie lange Empfänger Zugriff auf von Ihren Benutzern gesendete E-Mails haben.</span><span class="sxs-lookup"><span data-stu-id="2fe37-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="2fe37-111">Wenn ein Endbenutzer E-Mails empfängt, für die ein Ablaufdatum festgelegt ist, wird dem Benutzer das Ablaufdatum in der Wrapper-E-Mail angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fe37-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="2fe37-112">Wenn ein Benutzer versucht, eine abgelaufene E-Mail zu öffnen, wird im OME-Portal ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fe37-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="2fe37-113">Sie können nur Ablaufdaten für E-Mails an externe Empfänger festlegen.</span><span class="sxs-lookup"><span data-stu-id="2fe37-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="2fe37-114">Mit Office 365 Advanced Message Encryption wendet das Office 365 den Wrapper auf E-Mails an, die der Nachrichtenflussregel entspricht, auf die Sie die Vorlage anwenden.</span><span class="sxs-lookup"><span data-stu-id="2fe37-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="2fe37-115">Darüber hinaus können Sie den Ablauf nur verwenden, wenn Sie benutzerdefiniertes Branding verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fe37-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="2fe37-116">Erstellen einer benutzerdefinierten Brandingvorlage zum Erzwingen des Ablaufs von E-Mails mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fe37-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="2fe37-117">[Verbinden, Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) mit einem Konto zu erstellen, das über globale Administratorberechtigungen in Ihrer Organisation verfügt.</span><span class="sxs-lookup"><span data-stu-id="2fe37-117">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="2fe37-118">Führen Sie New-OMEConfiguration cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="2fe37-118">Run the New-OMEConfiguration cmdlet.</span></span>

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

<span data-ttu-id="2fe37-119">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="2fe37-119">Where:</span></span>

- <span data-ttu-id="2fe37-120">`Identity` ist der Name der benutzerdefinierten Vorlage.</span><span class="sxs-lookup"><span data-stu-id="2fe37-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="2fe37-121">`ExternalMailExpiryInDays` gibt an, wie viele Tage Empfänger E-Mails behalten können, bevor sie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="2fe37-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="2fe37-122">Sie können einen beliebigen Wert zwischen 1 und 730 Tagen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fe37-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="2fe37-123">Weitere Informationen zu Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="2fe37-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="2fe37-124">Erweiterte Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="2fe37-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="2fe37-125">Widerrufen von E-Mails, die von der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden</span><span class="sxs-lookup"><span data-stu-id="2fe37-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="2fe37-126">Beschreibung des Nachrichtenrichtlinien- und Compliancediensts</span><span class="sxs-lookup"><span data-stu-id="2fe37-126">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)