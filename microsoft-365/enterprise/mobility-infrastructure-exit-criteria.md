---
title: Beendigungskriterien für die Infrastruktur der mobilen Geräteverwaltung
description: Microsoft 365 Enterprise umfasst die Verwaltung mobiler Geräte mithilfe von Microsoft InTune. Überprüfen Sie die Anforderungen und Voraussetzungen, richten Sie InTune mithilfe ihrer Azure Active Directory-Ressource ein, registrieren Sie IOS-, macOS-, Android-und Windows-Geräte, stellen Sie apps bereit, erstellen Sie ein configure-Profil, verwenden Sie eine Konformitätsrichtlinie, und aktivieren Sie den bedingten Zugriff für Mobile Geräteverwaltung mit Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-Dokumentation, Verwaltung mobiler Geräte, InTune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 3e8013426983584783488e6f937f8ba5b02d7a1a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066786"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Beendigungskriterien für die Infrastruktur der mobilen Geräteverwaltung

![Phase 5: Verwaltung mobiler Geräte](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Dies gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

Stellen Sie sicher, dass Ihre Konfiguration die folgenden Anforderungen für die Infrastruktur zur Verwaltung mobiler Geräte erfüllt.

- InTune ist eingerichtet, einschließlich der Erstellung von Azure Active Directory (Azure AD)-Benutzern und-Gruppen, um die Regeln Ihrer Organisation für Geräte anzuwenden.
- Sie haben Geräte in Intune registriert, damit die Geräte die von Ihnen erstellten Richtlinien empfangen können.
- Apps werden Geräten hinzugefügt, damit Ihre Benutzer Zugriff auf die Microsoft 365-Clouddienste Ihrer Organisation erhalten, z. B. Exchange Online und SharePoint Online.
- Features und Einstellungen werden konfiguriert und mithilfe der erstellten Azure AD-Benutzer und -Gruppen auf Ihre Geräte angewendet. Dazu gehört möglicherweise das Aktivieren von Antiviren-Apps sowie das Einschränken bestimmter Apps.
- Compliance-Richtlinien sind vorhanden, um eine Firewall oder eine Kennwortlänge auf einem Gerät zu erfordern. Wenn Geräte nicht kompatibel sind, blockiert der bedingte Zugriff den Zugriff auf die Daten Ihrer Organisation.

## <a name="results-and-next-steps"></a>Ergebnisse und nächste Schritte

Ihre Geräte sind in InTune registriert und mit den entsprechenden Richtlinien konfiguriert.

|||
|:-------|:-----|
|![Phase 6: Schutz von Daten](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Wenn Sie die Phasen für die End-to-End-Bereitstellung von Microsoft 365 Enterprise ausführen, ist Ihre nächste Phase der [Informationsschutz](infoprotect-infrastructure.md). |
