---
title: Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Erfahren Sie, wie Sie Registrierungsschlüssel festlegen, um die moderne Authentifizierung für Geräte zu aktivieren, auf denen Microsoft Office 2013 installiert ist.
ms.openlocfilehash: 8bfe515fefed9d58f140a67e53ce0d078457aa72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393655"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten

[] Wenn Sie moderne Authentifizierung bei Windows-Geräten aktivieren möchten, auf denen Office 2013 installiert ist, müssen Sie spezielle Registrierungsschlüssel festlegen.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Aktivieren von moderner Authentifizierung bei Office 2013-Clients

> [!NOTE]
> Die moderne Authentifizierung ist für Office 2016-Clients bereits aktiviert, daher müssen Sie für Office 2016 keine Registrierungsschlüssel festlegen. 
  
Um moderne Authentifizierung bei Geräten unter Windows (beispielsweise auf Laptops und Tablets) zu aktivieren, auf denen Microsoft Office 2013 installiert ist, müssen Sie die nachstehenden Registrierungsschlüssel festlegen. Die Schlüssel müssen auf jedem Gerät festgelegt werden, das Sie für moderne Authentifizierung aktivieren möchten:
  
|**Registrierungsschlüssel**|**Type**|**Wert** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
Nachdem Sie die Registrierungsschlüssel festgelegt haben, können Sie Office 2013-Geräte-Apps so festlegen, dass die [mehrstufige Authentifizierung (MFA)](set-up-multi-factor-authentication.md) mit Microsoft 365 verwendet wird. 
  
Wenn Sie aktuell bei einer der Client-Apps angemeldet sind, müssen Sie sich abmelden und wieder anmelden, damit die Änderung wirksam wird. Andernfalls werden die MRU- und Roamingeinstellungen erst wieder verfügbar, wenn die ADAL-Identität eingerichtet ist.
  
## <a name="disable-modern-authentication-on-devices"></a>Deaktivieren von moderner Authentifizierung auf Geräten

Wenn Sie moderne Authentifizierung auf einem Gerät deaktivieren möchten, legen Sie dort die folgenden Registrierungsschlüssel fest:
  
|**Registrierungsschlüssel**|**Type**|**Wert**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-content"></a>Verwandte Inhalte

[Melden Sie sich bei Office 2013 mit einer zweiten Überprüfungsmethode](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) an (Artikel)\
[Outlook Eingabeaufforderungen für Kennwörter und verwendet keine moderne Authentifizierung, um eine Verbindung mit Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) herzustellen (Artikel)

