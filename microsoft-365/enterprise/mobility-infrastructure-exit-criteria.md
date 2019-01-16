---
title: Mobiles Gerät Management Infrastructure abschlusskriterien
description: Microsoft 365 Enterprise umfasst die Verwaltung von mobilen Geräten mit Microsoft Intune. Überprüfen Sie die Anforderungen und Voraussetzungen, richten Sie Intune Ihrer Azure Active Directory-Ressource verwenden, registrieren iOS, Mac OS, Android und Windows-Geräten, erstellen Sie ein Profil konfigurieren, verwenden Sie eine Compliance-Richtlinie und Aktivieren des bedingten Zugriffs für Mobile Bereitstellen von apps Gerätemanagement mit Microsoft 365 Enterprise.
keywords: Microsoft 365 Microsoft 365 Enterprise Microsoft 365 Dokumentation, Verwaltung von mobilen Geräten, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867730"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Mobiles Gerät Management Infrastructure abschlusskriterien

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Dies gilt für die E3 und E5 Versionen von Microsoft 365 Enterprise*

Bevor Sie mit der nächsten Phase des Bereitstellungsprozesses verschieben, stellen Sie sicher, dass Ihre Konfiguration für mobiles Gerät-Infrastruktur die folgenden Anforderungen erfüllt.

- Intune ist so eingerichtet (einschließlich der Erstellung von Azure AD-Benutzern und -Gruppen), dass die Regeln Ihrer Organisation für Geräte angewendet werden.
- Sie haben Geräte in Intune registriert, damit die Geräte die von Ihnen erstellten Richtlinien empfangen können.
- Apps werden Geräten hinzugefügt, damit Ihre Benutzer Zugriff auf die Microsoft 365-Clouddienste Ihrer Organisation erhalten, z. B. Exchange Online und SharePoint Online.
- Features und Einstellungen werden konfiguriert und mithilfe der erstellten Azure AD-Benutzer und -Gruppen auf Ihre Geräte angewendet. Dazu gehört möglicherweise das Aktivieren von Antiviren-Apps sowie das Einschränken bestimmter Apps.
- Es sind Compliancerichtlinien vorhanden, damit für ein Gerät eine Firewall oder eine Kennwortlänge erforderlich ist. Wenn Geräte diese Richtlinien nicht erfüllen, greifen bedingte Zugriffsblöcke auf die Daten Ihrer Organisation zu.

## <a name="next-phase"></a>Nächste Phase

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Die nächste Phase im Prozess End-to-End-Bereitstellung für Microsoft 365 Enterprise ist [Schutz von Informationen](infoprotect-infrastructure.md). |
