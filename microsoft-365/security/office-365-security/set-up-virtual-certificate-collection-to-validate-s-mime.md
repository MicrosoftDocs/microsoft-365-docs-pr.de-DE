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
description: Administratoren können erfahren, wie Sie eine virtuelle Zertifikatsammlung erstellen, die zum Überprüfen von S/MIME-Zertifikaten in Exchange Online verwendet wird.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4537ecfa6d800294af9572e462ce18491ce2c441
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290477"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Einrichten der virtuellen Zertifikatsammlung in Exchange Online zur Überprüfung von S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Als Administrator müssen Sie eine virtuelle Zertifikatsammlung in Exchange Online konfigurieren, die zum Überprüfen von S/MIME-Zertifikaten verwendet wird. Diese virtuelle Zertifikatsammlung wird als Zertifikatspeicher mit der Dateinamenerweiterung SST eingerichtet. Die SST-Datei enthält alle Stamm- und Zwischenzertifikate, die bei der Überprüfung eines S/MIME-Zertifikats verwendet werden.

## <a name="create-and-save-an-sst"></a>Erstellen und Speichern einer SST-Datei

Sie können diese SST-Zertifikatspeicherdatei erstellen, indem Sie die Zertifikate von einem vertrauenswürdigen Computer mithilfe  des Cmdlets **"Export-Certificate"** in Windows PowerShell exportieren und den Typwert als SST angeben. Anweisungen finden Sie unter [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).

Sobald Sie über die #A0 verfügen, verwenden Sie die folgende Syntax in Exchange Online PowerShell, um die Inhalte der #A1 im virtuellen Exchange #A2 zu speichern. Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

In diesem Beispiel wird die #A0 "C:\My Documents\Exported Certificate Store.sst" importiert.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Sicherstellen der Gültigkeit eines Zertifikats

In Exchange Online wird nur die SST für die Zertifikatüberprüfung verwendet.

## <a name="more-information"></a>Weitere Informationen

[S/MIME für die Nachrichtensignierung und -verschlüsselung](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
