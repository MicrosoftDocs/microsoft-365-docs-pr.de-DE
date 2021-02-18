---
title: Konfigurieren von S/MIME-Einstellungen – Exchange Online für Outlook im Web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Eine kurze Beschreibung, was Exchange Online-Administratoren tun müssen, um die S/MIME-Einstellungen in Outlook im Web in Exchange Online anzeigen und konfigurieren zu können.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ccadfc46e42713601b115c18a119e48dcfdcbf4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290033"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Konfigurieren von S/MIME-Einstellungen in Exchange Online für Outlook im Web

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Als Administrator für Exchange Online können Sie Outlook im Web (früher als Outlook Web App bezeichnet) einrichten, um das Senden und Empfangen von S/MIME-geschützten Nachrichten zu ermöglichen. Verwenden Sie **die Cmdlets "Get-SmimeConfig"** und **"Set-SmimeConfig",** um dieses Feature in Exchange Online PowerShell anzeigen und verwalten zu können. Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) und [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Überlegungen für das neue Microsoft Edge (Chromium-basiert)

Um S/MIME in Outlook im Web im neuen [Microsoft Edge-Webbrowser](https://www.microsoft.com/windows/microsoft-edge) zu verwenden, müssen Sie (oder ein anderer Administrator) die Microsoft Edge-Browserrichtlinie namens **ExtensionInstallForcelist** so festlegen und konfigurieren, dass die Microsoft S/MIME-Erweiterung im neuen Microsoft Edge installiert wird. Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Und beachten Sie, dass für die Anwendung dieser Richtlinie Geräte erforderlich sind, die einer Domäne oder Azure AD beigetreten sind. Daher sind für die Verwendung von S/MIME im neuen Microsoft Edge-Browser effektiv Geräte erforderlich, die in die Domäne oder in Azure AD eingetreten sind.

Details zur **Richtlinie ExtensionInstallForcelist** finden Sie unter [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Dieser Schritt ist eine Voraussetzung für die Verwendung des neuen Microsoft Edge. Das S/MIME-Steuerelement, das von Benutzern installiert wird, wird nicht ersetzt. Benutzer werden aufgefordert, das S/MIME-Steuerelement bei der ersten Verwendung von S/MIME in Outlook im Web herunterzuladen und zu installieren. Oder Benutzer können proaktiv zu **S/MIME** in ihren Outlook im Web-Einstellungen wechseln, um den Downloadlink für das Steuerelement zu erhalten.

## <a name="considerations-for-chrome"></a>Überlegungen zu Chrome

Um S/MIME in Outlook im Web im Google Chrome-Webbrowser zu verwenden, müssen Sie (oder ein anderer Administrator) die Chromium-Richtlinie namens **ExtensionInstallForcelist** festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung in Chrome zu installieren. Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Und beachten Sie, dass für die Anwendung dieser Richtlinie Computer erforderlich sind, die der Domäne beigetreten sind. Daher sind für die Verwendung von S/MIME in Chrome effektiv Computer erforderlich, die der Domäne beigetreten sind.

Details zur **Richtlinie ExtensionInstallForcelist** finden Sie unter [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Dieser Schritt ist eine Voraussetzung für die Verwendung von Chrome. Das S/MIME-Steuerelement, das von Benutzern installiert wird, wird nicht ersetzt. Benutzer werden aufgefordert, das S/MIME-Steuerelement bei der ersten Verwendung von S/MIME in Outlook im Web herunterzuladen und zu installieren. Oder Benutzer können proaktiv zu **S/MIME** in ihren Outlook im Web-Einstellungen wechseln, um den Downloadlink für das Steuerelement zu erhalten.

## <a name="for-more-information"></a>Weitere Informationen

[S/MIME für die Nachrichtensignierung und -verschlüsselung](s-mime-for-message-signing-and-encryption.md)
