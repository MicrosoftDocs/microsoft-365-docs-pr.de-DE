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
description: Mit Office 365 erweiterten Nachrichten Verschlüsselungsfunktionen über Office 365-Nachrichtenverschlüsselung (OM) können Sie Ihre e-Mail-Sicherheit erweitern, indem Sie ein Ablaufdatum für e-Mails über eine benutzerdefinierte Marken Vorlage festlegen.
ms.openlocfilehash: c9b639c016e86c3883191b04d4c7480625745e91
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626903"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="283c0-103">Festlegen eines Ablaufdatums für E-Mails, die mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="283c0-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="283c0-104">Office 365 erweiterte Nachrichtenverschlüsselung ist in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Non-Profit-Mitarbeiter Preise), Office 365 Enterprise E5 (Nonprofit-Mitarbeiter Preise) und Office 365 Education A5 enthalten.</span><span class="sxs-lookup"><span data-stu-id="283c0-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="283c0-105">Wenn Ihre Organisation über ein Abonnement verfügt, das Office 365 erweiterte Nachrichtenverschlüsselung nicht enthält, können Sie Sie mit dem Microsoft 365 E5 Compliance-SKU-Add-on für Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Pricing) oder mit dem Office 365 Advanced Compliance SKU-Add-on für Microsoft 365 E3, Microsoft 365 E3 (Preise für gemeinnützige Mitarbeiter) oder Office 365-SKUs erwerben.</span><span class="sxs-lookup"><span data-stu-id="283c0-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="283c0-106">Sie können Nachrichtenablauf bei e-Mails verwenden, die Ihre Benutzer an externe Empfänger senden, die das OM-Portal zum Zugriff auf verschlüsselte e-Mails verwenden.</span><span class="sxs-lookup"><span data-stu-id="283c0-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="283c0-107">Sie erzwingen, dass Empfänger das OM-Portal verwenden, um verschlüsselte e-Mails anzuzeigen und zu beantworten, die von Ihrer Organisation gesendet werden, indem Sie eine benutzerdefinierte Marken Vorlage verwenden, die ein Ablaufdatum in Windows PowerShell angibt.</span><span class="sxs-lookup"><span data-stu-id="283c0-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="283c0-108">Wenn Sie als globaler O365-Administrator Ihre Unternehmensmarke anwenden, um das Aussehen der e-Mail-Nachrichten Ihrer Organisation anzupassen, können Sie auch einen Ablauf für diese e-Mail-Nachrichten angeben.</span><span class="sxs-lookup"><span data-stu-id="283c0-108">As an O365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="283c0-109">Mit Office 365 erweiterten Nachrichtenverschlüsselung können Sie mehrere Vorlagen für verschlüsselte e-Mails erstellen, die aus Ihrer Organisation stammen.</span><span class="sxs-lookup"><span data-stu-id="283c0-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="283c0-110">Mithilfe einer Vorlage können Sie steuern, wie lange Empfänger Zugriff auf von Ihren Benutzern gesendete e-Mails haben.</span><span class="sxs-lookup"><span data-stu-id="283c0-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="283c0-111">Wenn ein Endbenutzer e-Mails erhält, für die ein Ablaufdatum festgelegt wurde, sieht der Benutzer das Ablaufdatum in der Wrapper-e-Mail.</span><span class="sxs-lookup"><span data-stu-id="283c0-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="283c0-112">Wenn ein Benutzer versucht, eine abgelaufene e-Mail zu öffnen, wird im OM-Portal ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="283c0-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="283c0-113">Sie können nur Ablaufdaten für e-Mails an externe Empfänger festlegen.</span><span class="sxs-lookup"><span data-stu-id="283c0-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="283c0-114">Bei Office 365 erweiterten Nachrichtenverschlüsselung wendet der Office 365 den Wrapper bei jeder Anwendung des benutzerdefinierten Branding auf e-Mail an, die der Nachrichtenfluss Regel entspricht, auf die die Vorlage angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="283c0-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="283c0-115">Außerdem können Sie die Ablaufzeit nur verwenden, wenn Sie benutzerdefiniertes Branding verwenden.</span><span class="sxs-lookup"><span data-stu-id="283c0-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="283c0-116">Erstellen einer benutzerdefinierten Branding-Vorlage zum Erzwingen des e-Mail-Ablaufs mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="283c0-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="283c0-117">Stellen Sie eine [Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) mit einem Konto her, das über globale Administratorberechtigungen in Ihrer Organisation verfügt.</span><span class="sxs-lookup"><span data-stu-id="283c0-117">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="283c0-118">Führen Sie das Cmdlet New-OMEConfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="283c0-118">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="283c0-119">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="283c0-119">Where:</span></span>

- <span data-ttu-id="283c0-120">`Identity`ist der Name der benutzerdefinierten Vorlage.</span><span class="sxs-lookup"><span data-stu-id="283c0-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="283c0-121">`ExternalMailExpiryInDays`Gibt an, wie viele Tage e-Mails von Empfängern aufbewahrt werden können, bevor Sie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="283c0-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="283c0-122">Sie können einen beliebigen Wert zwischen 1 bis 730 Tagen verwenden.</span><span class="sxs-lookup"><span data-stu-id="283c0-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="283c0-123">Weitere Informationen zu Office 365 erweiterte Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="283c0-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="283c0-124">Erweiterte Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="283c0-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="283c0-125">Widerrufen von E-Mails, die von der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden</span><span class="sxs-lookup"><span data-stu-id="283c0-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="283c0-126">Beschreibung des Nachrichtenrichtlinien-und Kompatibilitätsdiensts</span><span class="sxs-lookup"><span data-stu-id="283c0-126">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
