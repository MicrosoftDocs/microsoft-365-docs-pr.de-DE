---
title: Einrichten der virtuellen Zertifikat Sammlung in Exchange Online zur Überprüfung von S/MIME
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Administratoren können erfahren, wie Sie eine virtuelle Zertifikat Sammlung erstellen, die zum Validieren von S/MIME-Zertifikaten in Exchange Online verwendet wird.
ms.openlocfilehash: 0848fc974c48b442f9106125b847db5f8ec0d0c3
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37306099"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Einrichten der virtuellen Zertifikat Sammlung in Exchange Online zur Überprüfung von S/MIME

Als Administrator müssen Sie eine virtuelle Zertifikat Sammlung in Exchange Online konfigurieren, die zum Validieren von S/MIME-Zertifikaten verwendet wird. Diese virtuelle Zertifikat Sammlung ist als Zertifikatspeicher mit einer Dateinamenerweiterung "SST" eingerichtet. Die SST-Datei enthält alle Stamm- und Zwischenzertifikate, die bei der Überprüfung eines S/MIME-Zertifikats verwendet werden.

## <a name="create-and-save-an-sst"></a>Erstellen und Speichern einer SST-Datei

Sie können diese SST-Zertifikatspeicher Datei erstellen, indem Sie die Zertifikate von einem vertrauenswürdigen Computer mithilfe des **Export-Certificate-** Cmdlets in Windows PowerShell exportieren und den _Type_ -Wert als sst angeben. Anweisungen finden Sie unter [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).

Nachdem Sie die SST-Zertifikatspeicher Datei verwendet haben, verwenden Sie die folgende Syntax in Exchange Online PowerShell, um die SST-Dateiinhalte im Exchange Online virtuellen Zertifikatspeicher zu speichern. Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

In diesem Beispiel wird die SST-Datei C:\My Documents\Exported Certificate Store. sst importiert.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SmimeConfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Sicherstellen der Gültigkeit eines Zertifikats

In Exchange Online wird nur der SST für die Zertifikatüberprüfung verwendet.

## <a name="more-information"></a>Weitere Informationen

[S/MIME für die Nachrichtensignierung und -verschlüsselung](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
