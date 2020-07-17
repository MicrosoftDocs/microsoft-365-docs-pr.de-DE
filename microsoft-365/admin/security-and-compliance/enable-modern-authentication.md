---
title: Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Hier erfahren Sie, wie Sie Registrierungsschlüssel festlegen, um moderne Authentifizierung für Geräte zu aktivieren, auf denen Microsoft Office 2013 installiert ist.
ms.openlocfilehash: 8edcedefc04d5018b8b61022c26cbe027f7c24a9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779965"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten

[] Wenn Sie moderne Authentifizierung bei Windows-Geräten aktivieren möchten, auf denen Office 2013 installiert ist, müssen Sie spezielle Registrierungsschlüssel festlegen.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Aktivieren von moderner Authentifizierung bei Office 2013-Clients

> [!NOTE]
> Die moderne Authentifizierung ist für Office 2016-Clients bereits aktiviert, daher müssen Sie für Office 2016 keine Registrierungsschlüssel festlegen. 
  
Um moderne Authentifizierung bei Geräten unter Windows (beispielsweise auf Laptops und Tablets) zu aktivieren, auf denen Microsoft Office 2013 installiert ist, müssen Sie die nachstehenden Registrierungsschlüssel festlegen. Die Schlüssel müssen auf jedem Gerät festgelegt werden, das Sie für moderne Authentifizierung aktivieren möchten:
  
|**Registrierungsschlüssel**|**Typ**|**Wert** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1   |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1  |
   
Nachdem Sie die Registrierungsschlüssel festgelegt haben, können Sie Office 2013 Geräte-Apps für die Verwendung von mehrstufiger [Authentifizierung (MFA)](set-up-multi-factor-authentication.md) mit Microsoft 365 festlegen. 
  
Wenn Sie aktuell bei einer der Client-Apps angemeldet sind, müssen Sie sich abmelden und wieder anmelden, damit die Änderung wirksam wird. Andernfalls werden die MRU- und Roamingeinstellungen erst wieder verfügbar, wenn die ADAL-Identität eingerichtet ist.
  
## <a name="disable-modern-authentication-on-devices"></a>Deaktivieren von moderner Authentifizierung auf Geräten

Wenn Sie moderne Authentifizierung auf einem Gerät deaktivieren möchten, legen Sie dort die folgenden Registrierungsschlüssel fest:
  
|**Registrierungsschlüssel**|**Typ**|**Wert**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-articles"></a>Verwandte Artikel
[Anmelden bei Office 2013 mit einer zweiten Überprüfungsmethode](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

  

