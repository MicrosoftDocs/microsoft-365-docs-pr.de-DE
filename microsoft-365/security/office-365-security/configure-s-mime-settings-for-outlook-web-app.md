---
title: Konfigurieren von S/MIME-Einstellungen – Exchange Online für Outlook Im Web
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
description: Eine kurze Beschreibung der Exchange Online administratoren zum Anzeigen und Konfigurieren der S/MIME-Einstellungen in Outlook im Web in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6eacc6a264682474054d0d3546b831039bee9a0c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203940"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Konfigurieren von S/MIME-Einstellungen in Exchange Online für Outlook im Web

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Als Administrator für Exchange Online können Sie Outlook im Web (früher als Outlook Web App bezeichnet) einrichten, um das Senden und Empfangen von S/MIME-geschützten Nachrichten zu ermöglichen. Verwenden Sie **die Cmdlets Get-SmimeConfig** und **Set-SmimeConfig** zum Anzeigen und Verwalten dieses Features in Exchange Online PowerShell. Wie Sie eine Verbindung mit Exchange Online-PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) und [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Überlegungen zu neuen Microsoft Edge (Chromium)

Um S/MIME in Outlook im Web im neuen [Microsoft Edge-Webbrowser](https://www.microsoft.com/windows/microsoft-edge) zu verwenden, müssen Sie (oder ein anderer Administrator) die Microsoft Edge-Browserrichtlinie **namens ExtensionInstallForcelist** festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung in der neuen Microsoft Edge zu installieren. Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Und beachten Sie, dass für die Anwendung dieser Richtlinie Geräte erforderlich sind, die der Domäne oder Azure AD beigetreten sind. Daher erfordert die Verwendung von S/MIME im neuen Microsoft Edge-Browser effektiv Geräte, die der Domäne oder Azure AD beigetreten sind.

Weitere Informationen zur **ExtensionInstallForcelist-Richtlinie** finden Sie unter [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Dieser Schritt ist eine Voraussetzung für die Verwendung neuer Microsoft Edge; Es ersetzt nicht das von Benutzern installierte S/MIME-Steuerelement. Benutzer werden aufgefordert, das S/MIME-Steuerelement Outlook der ersten Verwendung von S/MIME im Web herunterzuladen und zu installieren. Oder Benutzer können proaktiv zu **S/MIME** in ihren Outlook in den Webeinstellungen wechseln, um den Downloadlink für das Steuerelement zu erhalten.

## <a name="considerations-for-chrome"></a>Überlegungen zu Chrome

Um S/MIME in Outlook im Web im Google Chrome-Webbrowser zu verwenden, müssen Sie (oder ein anderer Administrator) die Chromium-Richtlinie namens **ExtensionInstallForcelist** festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung in Chrome zu installieren. Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Beachten Sie außerdem, dass für die Anwendung dieser Richtlinie Computer mit Domänen verbunden sind, sodass die Verwendung von S/MIME in Chrome effektiv Computer erfordert, die der Domäne beigetreten sind.

Weitere Informationen zur **ExtensionInstallForcelist-Richtlinie** finden Sie unter [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Dieser Schritt ist eine Voraussetzung für die Verwendung von Chrome. Es ersetzt nicht das von Benutzern installierte S/MIME-Steuerelement. Benutzer werden aufgefordert, das S/MIME-Steuerelement Outlook der ersten Verwendung von S/MIME im Web herunterzuladen und zu installieren. Oder Benutzer können proaktiv zu **S/MIME** in ihren Outlook in den Webeinstellungen wechseln, um den Downloadlink für das Steuerelement zu erhalten.

## <a name="for-more-information"></a>Weitere Informationen

[S/MIME für die Nachrichtensignierung und -verschlüsselung](s-mime-for-message-signing-and-encryption.md)