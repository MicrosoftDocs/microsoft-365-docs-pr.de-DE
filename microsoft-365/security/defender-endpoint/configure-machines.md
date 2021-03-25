---
title: Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind
description: Konfigurieren Sie Geräte ordnungsgemäß, um die Ausfallsicherheit gegen Bedrohungen insgesamt zu erhöhen und Ihre Fähigkeit zum Erkennen und Reagieren auf Angriffe zu verbessern.
keywords: Onboard, Intune-Verwaltung, MDATP, WDATP, Microsoft Defender, Windows Defender, erweiterter Bedrohungsschutz, Reduzierung der Angriffsfläche, ASR, Sicherheitsgrundlinie
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
ms.openlocfilehash: e7b00ceafc2761f42c316f434a27acf7c551e7cf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163363"
---
# <a name="ensure-your-devices-are-configured-properly"></a>Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Mit ordnungsgemäß konfigurierten Geräten können Sie die Ausfallsicherheit gegen Bedrohungen insgesamt erhöhen und Ihre Fähigkeit zum Erkennen und Reagieren auf Angriffe verbessern. Die Verwaltung der Sicherheitskonfiguration trägt dazu bei, dass Ihre Geräte:

- Onboarding bei Microsoft Defender for Endpoint
- Erfüllen oder Überschreiten der Basiskonfiguration der Defender for Endpoint-Sicherheitsbasis
- Strategische Gegenmaßnahmen zur Angriffsfläche

Klicken **Sie im Navigationsmenü** auf Konfigurationsverwaltung, um die Seite Gerätekonfigurationsverwaltung zu öffnen.

![Sicherheitskonfigurationsverwaltungsseite](images/secconmgmt_main.png)<br>
*Seite "Gerätekonfigurationsverwaltung"*

Sie können den Konfigurationsstatus auf Organisatorischer Ebene nachverfolgen und schnell Maßnahmen ergreifen, um auf eine schlechte Onboardingabdeckung, Kompatibilitätsprobleme und schlecht optimierte Gegenmaßnahmen zur Angriffsfläche durch direkte, tiefe Links zu Geräteverwaltungsseiten in Microsoft Intune und Microsoft 365 Security Center zu reagieren.

Dabei profitieren Sie von:
- Umfassende Sichtbarkeit der Ereignisse auf Ihren Geräten
- Robuste Bedrohungsintelligenz und leistungsstarke Gerätelerntechnologien für die Verarbeitung von Unformatereignissen und das Identifizieren der Verletzungsaktivität und Bedrohungsindikatoren
- Ein vollständiger Stapel von Sicherheitsfeatures, die so konfiguriert sind, dass die Installation von schädlichen Implanten, die Entführung von Systemdateien und -verfahren, die Daten-Exfiltration und andere Bedrohungsaktivitäten effizient beendet werden.
- Optimierte Gegenmaßnahmen gegen Angriffsflächen, Maximierung der strategischen Verteidigung gegen Bedrohungsaktivitäten bei gleichzeitiger Minimierung der Produktivitätsauswirkungen

## <a name="enroll-devices-to-intune-management"></a>Registrieren von Geräten für die Intune-Verwaltung

Die Gerätekonfigurationsverwaltung arbeitet eng mit der Intune-Geräteverwaltung zusammen, um das Inventar der Geräte in Ihrer Organisation und die grundlegende Sicherheitskonfiguration zu erstellen. Sie können Konfigurationsprobleme auf von Intune verwalteten Windows 10-Geräten nachverfolgen und verwalten.

Bevor Sie sicherstellen können, dass Ihre Geräte ordnungsgemäß konfiguriert sind, registrieren Sie sie bei der Intune-Verwaltung. Die Intune-Registrierung ist robust und verfügt über mehrere Registrierungsoptionen für Windows 10-Geräte. Weitere Informationen zu Intune-Registrierungsoptionen finden Sie unter Einrichten [der Registrierung für Windows-Geräte.](https://docs.microsoft.com/intune/windows-enroll)

>[!NOTE]
>Zum Registrieren von Windows-Geräten bei Intune müssen Administratoren bereits Lizenzen zugewiesen worden sein. [Informationen zum Zuweisen von Lizenzen für die Geräteregistrierung](https://docs.microsoft.com/intune/licenses-assign).

>[!TIP] 
>Um die Geräteverwaltung über Intune zu optimieren, [verbinden Sie Intune mit Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).

## <a name="obtain-required-permissions"></a>Abrufen der erforderlichen Berechtigungen
Standardmäßig können nur Benutzer, denen die Rolle "Globaler Administrator" oder "Intune Service Administrator" in Azure AD zugewiesen wurde, die gerätekonfigurationsprofile verwalten und zuweisen, die für das Onboarding von Geräten und die Bereitstellung der Sicherheitsbasis erforderlich sind.

Wenn Ihnen andere Rollen zugewiesen wurden, stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen:

- Vollständige Berechtigungen für Gerätekonfigurationen
- Vollständige Berechtigungen für Sicherheitsgrundwerte
- Lesen von Berechtigungen für Gerätekonformitätsrichtlinien
- Lesen von Berechtigungen für die Organisation

![Erforderliche Berechtigungen für Intune](images/secconmgmt_intune_permissions.png)<br>
*Gerätekonfigurationsberechtigungen für Intune*

>[!TIP] 
>Weitere Informationen zum Zuweisen von Berechtigungen für Intune finden Sie [unter Erstellen benutzerdefinierter Rollen](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role).

## <a name="in-this-section"></a>Inhalt dieses Abschnitts
Thema | Beschreibung
:---|:---
[In Defender for Endpoint integrierte Geräte](configure-machines-onboarding.md)| Verfolgen Sie den Onboardingstatus von von Intune verwalteten Geräten, und integrieren Sie weitere Geräte über Intune. 
[Erhöhen der Einhaltung der Sicherheitsgrundlinie für Defender for Endpoint](configure-machines-security-baseline.md) | Verfolgen Sie die Geplante Compliance und Nichtcompliance. Stellen Sie die Sicherheitsgrundlinie auf mehr von Intune verwalteten Geräten zur Verfügung.
[Optimieren der Bereitstellung und Erkennung von ASR-Regeln](configure-machines-asr.md) | Überprüfen sie die Erkennung von Regelbereitstellungen und Optimierungen mithilfe von Impact Analysis Tools im Microsoft 365 Security Center.

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
