---
title: Konfigurieren von S/MIME-Einstellungen in Exchange Online für Outlook im Internet
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Eine kurze Beschreibung, was Exchange Online Administratoren tun müssen, um die S/MIME-Einstellungen in Outlook im Internet in Exchange Online anzuzeigen und zu konfigurieren.
ms.openlocfilehash: 354b247c2b0e0e610e6cb0626f4a404b582db717
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960321"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Konfigurieren von S/MIME-Einstellungen in Exchange Online für Outlook im Internet

Als Administrator für Exchange Online können Sie Outlook im Internet (früher als Outlook Web App bezeichnet) einrichten, um das Senden und empfangen von S/MIME-geschützten Nachrichten zu ermöglichen. Verwenden Sie die Cmdlets **Get-SmimeConfig** und **SmimeConfig** , um dieses Feature in Exchange Online PowerShell anzuzeigen und zu verwalten. Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) und [Sets-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Überlegungen für neue Microsoft Edge (Chrom basiert)

Um s/MIME in Outlook im Internet im neuen [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) -Webbrowser zu verwenden, müssen Sie (oder ein anderer Administrator) die Microsoft-Edge-Browser-Richtlinie " **ExtensionInstallForcelist** " festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung in New Microsoft Edge zu installieren. Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`. Beachten Sie, dass die Anwendung dieser Richtlinie Computer mit Domänenbeitritt erfordert, sodass die Verwendung von S/MIME im neuen Microsoft Edge-Browser effektiv Domänen verbundene Computer erfordert.

Ausführliche Informationen zur **ExtensionInstallForcelist** -Richtlinie finden Sie unter [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Dieser Schritt ist eine Voraussetzung für die Verwendung von New Microsoft Edge; das von Benutzern installierte S/MIME-Steuerelement wird nicht ersetzt. Benutzer werden aufgefordert, das s/MIME-Steuerelement in Outlook im Internet während der ersten Verwendung von s/MIME herunterzuladen und zu installieren. Oder können Benutzer proaktiv zu **S/MIME** in Ihren Outlook im Webeinstellungen wechseln, um den Download-Link für das Steuerelement abzurufen.

## <a name="considerations-for-chrome"></a>Überlegungen für Chrome

Um s/MIME in Outlook im Internet im Webbrowser von Google Chrome zu verwenden, müssen Sie (oder ein anderer Administrator) die Chrom Richtlinie mit dem Namen **ExtensionInstallForcelist** festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung in Chrome zu installieren. Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`. Beachten Sie, dass die Anwendung dieser Richtlinie Computer mit Domänenbeitritt erfordert, sodass die Verwendung von S/MIME in Chrome effektiv mit der Domäne verbundener Computer erforderlich ist.

Ausführliche Informationen zur **ExtensionInstallForcelist** -Richtlinie finden Sie unter [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Dieser Schritt ist eine Voraussetzung für die Verwendung von Chrome; das von Benutzern installierte S/MIME-Steuerelement wird nicht ersetzt. Benutzer werden aufgefordert, das s/MIME-Steuerelement in Outlook im Internet während der ersten Verwendung von s/MIME herunterzuladen und zu installieren. Oder können Benutzer proaktiv zu **S/MIME** in Ihren Outlook im Webeinstellungen wechseln, um den Download-Link für das Steuerelement abzurufen.

## <a name="for-more-information"></a>Weitere Informationen

[S/MIME für die Nachrichtensignierung und -verschlüsselung](s-mime-for-message-signing-and-encryption.md)
