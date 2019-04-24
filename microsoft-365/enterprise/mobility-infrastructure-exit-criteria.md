---
title: Infrastruktur-Exit-Kriterien für die Verwaltung mobiler Geräte
description: Microsoft 365 Enterprise umfasst die Verwaltung mobiler Geräte mit Microsoft InTune. Überprüfung der Anforderungen und Voraussetzungen, Einrichten von InTune mithilfe ihrer Azure Active Directory-Ressource, Registrieren von iOS-, macOS-, Android-und Windows-Geräten, Bereitstellen von apps, Erstellen eines Konfigurationsprofils, verwenden einer Konformitätsrichtlinie und Aktivieren des bedingten Zugriffs für Mobilgeräte Geräteverwaltung mit Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Mobile Device Management, InTune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291232"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Infrastruktur-Exit-Kriterien für die Verwaltung mobiler Geräte

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Dies gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

Stellen Sie sicher, dass Ihre Konfiguration die folgenden Anforderungen für die Verwaltung mobiler Geräte erfüllt.

- Intune ist so eingerichtet (einschließlich der Erstellung von Azure AD-Benutzern und -Gruppen), dass die Regeln Ihrer Organisation für Geräte angewendet werden.
- Sie haben Geräte in Intune registriert, damit die Geräte die von Ihnen erstellten Richtlinien empfangen können.
- Apps werden Geräten hinzugefügt, damit Ihre Benutzer Zugriff auf die Microsoft 365-Clouddienste Ihrer Organisation erhalten, z. B. Exchange Online und SharePoint Online.
- Features und Einstellungen werden konfiguriert und mithilfe der erstellten Azure AD-Benutzer und -Gruppen auf Ihre Geräte angewendet. Dazu gehört möglicherweise das Aktivieren von Antiviren-Apps sowie das Einschränken bestimmter Apps.
- Es sind Compliancerichtlinien vorhanden, damit für ein Gerät eine Firewall oder eine Kennwortlänge erforderlich ist. Wenn Geräte diese Richtlinien nicht erfüllen, greifen bedingte Zugriffsblöcke auf die Daten Ihrer Organisation zu.



## <a name="results-and-next-steps"></a>Ergebnisse und nächste Schritte

Ihre Geräte sind in InTune registriert und mit den entsprechenden Richtlinien konfiguriert.

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Wenn Sie die Phasen für die End-to-End-Bereitstellung von Microsoft 365 Enterprise verfolgen, ist der [Informationsschutz](infoprotect-infrastructure.md)die nächste Phase. |
