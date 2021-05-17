---
title: Einrichten der virtuellen Zertifikatsammlung – Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Administratoren erfahren, wie Sie eine virtuelle Zertifikatsammlung erstellen, die zum Überprüfen von S/MIME-Zertifikaten in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a5dad897ce58b8496551535cc28e03c7a1fa964
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206804"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="ace50-103">Einrichten der virtuellen Zertifikatsammlung in Exchange Online zur Überprüfung von S/MIME</span><span class="sxs-lookup"><span data-stu-id="ace50-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ace50-104">Als Administrator müssen Sie eine virtuelle Zertifikatsammlung in Exchange Online konfigurieren, die zum Überprüfen von S/MIME-Zertifikaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ace50-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="ace50-105">Diese virtuelle Zertifikatsammlung wird als Zertifikatspeicher mit einer SST-Dateinamenerweiterung eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="ace50-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="ace50-106">Die SST-Datei enthält alle Stamm- und Zwischenzertifikate, die bei der Überprüfung eines S/MIME-Zertifikats verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ace50-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="ace50-107">Erstellen und Speichern einer SST-Datei</span><span class="sxs-lookup"><span data-stu-id="ace50-107">Create and save an SST</span></span>

<span data-ttu-id="ace50-108">Sie können diese SST-Zertifikatspeicherdatei erstellen, indem Sie die Zertifikate mithilfe des **Cmdlets Export-Certificate** in Windows PowerShell von einem vertrauenswürdigen Computer exportieren und den _Type-Wert_ als SST angeben.</span><span class="sxs-lookup"><span data-stu-id="ace50-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="ace50-109">Anweisungen finden Sie unter [Export-Certificate](/powershell/module/pkiclient/export-certificate).</span><span class="sxs-lookup"><span data-stu-id="ace50-109">For instructions, see [Export-Certificate](/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="ace50-110">Nachdem Sie über die #A0 verfügen, verwenden Sie die folgende Syntax in Exchange Online PowerShell, um die #A1 im virtuellen Exchange Online zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ace50-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="ace50-111">Wie Sie eine Verbindung mit Exchange Online-PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ace50-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="ace50-112">In diesem Beispiel wird die #A0 C:\My Documents\Exported Certificate Store.sst importiert.</span><span class="sxs-lookup"><span data-stu-id="ace50-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="ace50-113">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="ace50-113">For detailed syntax and parameter information, see [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="ace50-114">Sicherstellen der Gültigkeit eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="ace50-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="ace50-115">In Exchange Online wird nur der SST für die Zertifikatüberprüfung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ace50-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="ace50-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ace50-116">More Information</span></span>

[<span data-ttu-id="ace50-117">S/MIME für die Nachrichtensignierung und -verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="ace50-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="ace50-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="ace50-118">Get-SmimeConfig</span></span>](/powershell/module/exchange/get-smimeconfig)