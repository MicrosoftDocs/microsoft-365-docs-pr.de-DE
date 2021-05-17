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
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Einrichten der virtuellen Zertifikatsammlung in Exchange Online zur Überprüfung von S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Als Administrator müssen Sie eine virtuelle Zertifikatsammlung in Exchange Online konfigurieren, die zum Überprüfen von S/MIME-Zertifikaten verwendet wird. Diese virtuelle Zertifikatsammlung wird als Zertifikatspeicher mit einer SST-Dateinamenerweiterung eingerichtet. Die SST-Datei enthält alle Stamm- und Zwischenzertifikate, die bei der Überprüfung eines S/MIME-Zertifikats verwendet werden.

## <a name="create-and-save-an-sst"></a>Erstellen und Speichern einer SST-Datei

Sie können diese SST-Zertifikatspeicherdatei erstellen, indem Sie die Zertifikate mithilfe des **Cmdlets Export-Certificate** in Windows PowerShell von einem vertrauenswürdigen Computer exportieren und den _Type-Wert_ als SST angeben. Anweisungen finden Sie unter [Export-Certificate](/powershell/module/pkiclient/export-certificate).

Nachdem Sie über die #A0 verfügen, verwenden Sie die folgende Syntax in Exchange Online PowerShell, um die #A1 im virtuellen Exchange Online zu speichern. Wie Sie eine Verbindung mit Exchange Online-PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

In diesem Beispiel wird die #A0 C:\My Documents\Exported Certificate Store.sst importiert.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Sicherstellen der Gültigkeit eines Zertifikats

In Exchange Online wird nur der SST für die Zertifikatüberprüfung verwendet.

## <a name="more-information"></a>Weitere Informationen

[S/MIME für die Nachrichtensignierung und -verschlüsselung](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig)