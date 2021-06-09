---
title: Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind
description: Konfigurieren Sie Geräte ordnungsgemäß, um die resilienz gegenüber Bedrohungen insgesamt zu erhöhen und Ihre Fähigkeit, Angriffe zu erkennen und darauf zu reagieren, zu verbessern.
keywords: Onboarding, Intune-Verwaltung, Microsoft Defender für Endpunkt, Microsoft Defender, Windows Defender, Verringerung der Angriffsfläche, ASR, Sicherheitsgrundwerte
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dccc623bfa6c3f5e8fe4d88ccfafd66d3e53482a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840898"
---
# <a name="ensure-your-devices-are-configured-properly"></a>Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Mit ordnungsgemäß konfigurierten Geräten können Sie die resilienz insgesamt gegen Bedrohungen erhöhen und Ihre Fähigkeit verbessern, Angriffe zu erkennen und darauf zu reagieren. Mithilfe der Sicherheitskonfigurationsverwaltung können Sie sicherstellen, dass Ihre Geräte:

- Onboarding in Microsoft Defender für Endpunkt
- Erfüllen oder Überschreiten der Sicherheitsbaselinekonfiguration von Defender für Endpunkt
- Strategische Angriffsflächen-Gegenmaßnahmen

Klicken Sie im Navigationsmenü auf **"Konfigurationsverwaltung",** um die Seite "Gerätekonfigurationsverwaltung" zu öffnen.

![Seite "Verwaltung der Sicherheitskonfiguration"](images/secconmgmt_main.png)<br>
*Seite "Gerätekonfigurationsverwaltung"*

Sie können den Konfigurationsstatus auf Organisationsebene nachverfolgen und schnell Maßnahmen ergreifen, um auf eine schlechte Onboarding-Abdeckung, Compliance-Probleme und schlecht optimierte Angriffsflächenminderungen über direkte, tiefe Links zu Geräteverwaltungsseiten in Microsoft Intune und Microsoft 365 Security Center zu reagieren.

Dadurch profitieren Sie von Folgendem:
- Umfassende Sichtbarkeit der Ereignisse auf Ihren Geräten
- Robuste Bedrohungserkennung und leistungsstarke Gerätelerntechnologien für die Verarbeitung von Rohereignissen und die Identifizierung der Aktivität von Sicherheitsverletzungen und Bedrohungsindikatoren
- Ein vollständiger Stapel von Sicherheitsfeatures, die so konfiguriert sind, dass die Installation schädlicher Implente, das Missbrauch von Systemdateien und -prozessen, die Datenexfiltration und andere Bedrohungsaktivitäten effizient beendet werden.
- Optimierte Angriffsflächenminderungen, die die strategische Abwehr von Bedrohungsaktivitäten maximieren und gleichzeitig die Auswirkungen auf die Produktivität minimieren

## <a name="enroll-devices-to-intune-management"></a>Registrieren von Geräten bei der Intune-Verwaltung

Die Gerätekonfigurationsverwaltung arbeitet eng mit der Intune-Geräteverwaltung zusammen, um den Bestand der Geräte in Ihrer Organisation und die grundlegende Sicherheitskonfiguration einzurichten. Sie können Konfigurationsprobleme auf von Intune verwalteten Windows 10-Geräten nachverfolgen und verwalten.

Bevor Sie sicherstellen können, dass Ihre Geräte ordnungsgemäß konfiguriert sind, registrieren Sie sie bei der Intune-Verwaltung. Die Intune-Registrierung ist robust und verfügt über mehrere Registrierungsoptionen für Windows 10 Geräte. Weitere Informationen zu Intune-Registrierungsoptionen finden Sie unter "Einrichten der [Registrierung für Windows Geräte".](/intune/windows-enroll)

>[!NOTE]
>Um Windows Geräte bei Intune zu registrieren, müssen Administratoren bereits Lizenzen zugewiesen worden sein. [Informationen zum Zuweisen von Lizenzen für die Geräteregistrierung.](/intune/licenses-assign)

>[!TIP] 
>Um die Geräteverwaltung über Intune zu optimieren, [verbinden Sie Intune mit Defender für Endpunkt.](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)

## <a name="obtain-required-permissions"></a>Abrufen der erforderlichen Berechtigungen
Standardmäßig können nur Benutzer, denen die Rolle "Globaler Administrator" oder "Intune-Dienstadministrator" in Azure AD zugewiesen wurde, die gerätekonfigurationsprofile verwalten und zuweisen, die für das Onboarding von Geräten und die Bereitstellung der Sicherheitsgrundwerte erforderlich sind.

Wenn Ihnen andere Rollen zugewiesen wurden, stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen:

- Vollständige Berechtigungen für Gerätekonfigurationen
- Vollständige Berechtigungen für Sicherheitsgrundwerte
- Leseberechtigungen für Gerätekompatibilitätsrichtlinien
- Leseberechtigungen für die Organisation

![Erforderliche Berechtigungen für Intune](images/secconmgmt_intune_permissions.png)<br>
*Gerätekonfigurationsberechtigungen in Intune*

>[!TIP] 
>Weitere Informationen zum Zuweisen von Berechtigungen für Intune [finden Sie unter Erstellen benutzerdefinierter Rollen.](/intune/create-custom-role#to-create-a-custom-role)

## <a name="in-this-section"></a>Inhalt dieses Abschnitts
Thema | Beschreibung
:---|:---
[Geräte in Defender für Endpunkt integrieren](configure-machines-onboarding.md)| Nachverfolgen des Onboardingstatus von von Intune verwalteten Geräten und Onboarding weiterer Geräte über Intune. 
[Erhöhen der Compliance für die Defender für Endpunkt-Sicherheitsgrundwerte](configure-machines-security-baseline.md) | Nachverfolgen der Geplanten Compliance und Nichtkonformität. Stellen Sie die Sicherheitsgrundwerte auf mehr von Intune verwalteten Geräten bereit.
[Optimieren der Bereitstellung und Erkennung von ASR-Regeln](configure-machines-asr.md) | Überprüfen Sie die Regelbereitstellung und optimieren Sie die Erkennungen mithilfe von Auswirkungsanalysetools im Microsoft 365 Security Center.

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
