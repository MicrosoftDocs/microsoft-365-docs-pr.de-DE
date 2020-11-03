---
title: Erweiterte Jagd Abdeckung mit den richtigen Einstellungen erweitern
description: Überprüfen Sie die Überwachungseinstellungen auf Windows-Geräten und anderen Einstellungen, um sicherzustellen, dass Sie die umfassendsten Daten in Advanced Hunting abrufen können.
keywords: Erweiterte Jagd, Vorfall, Pivot, Entität, Überwachungseinstellungen, Benutzerkontenverwaltung, Sicherheitsgruppenverwaltung, Bedrohungs Suche, Cyber Threat Hunting, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 82faff2599cd61fa1a4deb3129e1e6780d3f529c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842476"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Erweiterte Jagd Abdeckung mit den richtigen Einstellungen erweitern

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die [Erweiterte Suche](advanced-hunting-overview.md) beruht auf Daten, die aus verschiedenen Quellen stammen, einschließlich Ihrer Geräte, Ihrer Office 365 Arbeitsbereiche, Azure AD und Microsoft Defender for Identity. Um die umfassendsten Daten zu erhalten, stellen Sie sicher, dass Sie über die richtigen Einstellungen in den entsprechenden Datenquellen verfügen.

## <a name="advanced-security-auditing-on-windows-devices"></a>Erweiterte Sicherheitsüberwachung auf Windows-Geräten
Aktivieren Sie diese erweiterten Überwachungseinstellungen, um sicherzustellen, dass Sie Daten zu Aktivitäten auf Ihren Geräten abrufen, einschließlich der lokalen Kontoverwaltung, der Verwaltung lokaler Sicherheitsgruppen und der Erstellung von Diensten.

| Daten | Beschreibung | Schema Tabelle | Konfigurieren von |
| --- | --- | --- | --- |
| Kontoverwaltung | Als verschiedene Werte erfasste Ereignisse, die das `ActionType` erstellen, löschen und andere kontobezogene Aktivitäten des lokalen Kontos anzeigen | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Bereitstelleneiner erweiterten Sicherheitsüberwachungsrichtlinie: über [Wachen der Benutzerkontenverwaltung](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Informationen zu erweiterten Sicherheitsüberwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Sicherheitsgruppenverwaltung | Als verschiedene Werte erfasste Ereignisse, die die `ActionType` Erstellung lokaler Sicherheitsgruppen und andere Aktivitäten der lokalen Gruppenverwaltung anzeigen | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Bereitstelleneiner erweiterten Sicherheitsüberwachungsrichtlinie: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Informationen zu erweiterten Sicherheitsüberwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Dienstinstallation | Mit dem Wert erfasste Ereignisse `ActionType` `ServiceInstalled` , die angeben, dass ein Dienst erstellt wurde | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Bereitstelleneiner erweiterten Sicherheitsüberwachungsrichtlinie: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Informationen zu erweiterten Sicherheitsüberwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft Defender für Identity-Sensor auf dem Domänencontroller
Wenn Sie Active Directory lokal betreiben, müssen Sie den Microsoft Defender for Identity-Sensor auf dem Domänencontroller installieren, um Daten für Microsoft Defender for Identity zu erhalten. Bei der Installation und ordnungsgemäßen Konfiguration werden diese Daten auch in die erweiterte Suche über Microsoft Defender for Identity übermittelt und bieten ein ganzheitlicheres Bild von Identitätsinformationen und Ereignissen in Ihrem Netzwerk. Mit diesen Daten wird auch die Fähigkeit von Microsoft Defender for Identity verbessert, relevante Warnungen zu generieren, die auch von Advanced Hunting abgedeckt werden. 

| Daten | Beschreibung | Schema Tabelle | Konfigurieren von |
| --- | --- | --- | --- |
| Domänencontroller | Daten aus lokalen Active Directory, die an Microsoft Defender für identitätsbezogene Informationen wie Kontodetails, Anmeldeaktivitäten und Active Directory Abfragen gesendet werden. | Mehrere Tabellen, einschließlich [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)und [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Installieren von Microsoft Defender für Identity Sensor](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Aktivieren relevanter Windows-Ereignisse](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
