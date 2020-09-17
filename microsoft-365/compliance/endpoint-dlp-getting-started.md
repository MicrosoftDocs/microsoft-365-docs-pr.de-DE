---
title: Erste Schritte mit Microsoft 365 Endpunkt-DLP (Vorschau)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Richten Sie Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust) ein, um Dateiaktivitäten zu überwachen und schützende Maßnahmen für diese Dateien auf Endpunkten anzuwenden.
ms.openlocfilehash: 43ab2a30570f153f16819ede2eeed1f0e091da74
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949845"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a>Endpunkt-DLP (Vorschau) – Erste Schritte

Microsoft Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust) ist Bestandteil der Microsoft 365 DLP-Feature-Suite, mit der Sie vertrauliche Elemente in Microsoft 365-Diensten ermitteln und schützen können. Weitere Informationen zu den Microsoft-DLP-Angeboten finden Sie unter [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md). Weitere Informationen zu Endpunkt-DLP finden Sie unter [Informationen zu Endpunkt-DLP (Vorschau)](endpoint-dlp-learn-about.md)

Microsoft Endpunkt-DLP ermöglicht es Ihnen, Windows 10-Geräte zu überwachen und zu erkennen, wenn vertrauliche Elemente verwendet und freigegeben werden. Auf diese Weise erhalten Sie die nötige Übersicht und Kontrolle, um sicherzustellen, dass sie ordnungsgemäß verwendet und geschützt werden, und um ihre Gefährdung durch riskantes Verhalten zu verhindern.

## <a name="before-you-begin"></a>Vorabinformationen

### <a name="skusubscriptions-licensing"></a>SKU/Abonnement-Lizenzierung

Bevor Sie mit Endpunkt-DLP beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und etwaige Add-Ons überprüfen. Für den Zugriff auf und die Verwendung von Endpunkt-DLP-Funktionen müssen Sie über eines der folgenden Abonnements oder Add-Ons verfügen.

- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Microsoft 365 E5 Compliance
- Microsoft 365 A5 Compliance
- Microsoft 365 E5 Information Protection und Governance
- Microsoft 365 A5 Information Protection und Governance

### <a name="permissions"></a>Berechtigungen

Zum Aktivieren der Geräteverwaltung muss das von Ihnen verwendete Konto eine der folgenden Rollen aufweisen:

- Globaler Administrator
- Sicherheitsadministrator
- Compliance-Administrator

Wenn Sie ein benutzerdefiniertes Konto verwenden möchten, um die Einstellungen für die Geräteverwaltung anzuzeigen, muss es eine der folgenden Rollen aufweisen:

- Globaler Administrator
- Compliance-Administrator
- Compliancedaten-Administrator
- Globale Leseberechtigung

Wenn Sie ein benutzerdefiniertes Konto für den Zugriff auf die Seite für das Onboarding/Offboarding verwenden möchten, muss es eine der folgenden Rollen aufweisen:

- Globaler Administrator
- Compliance-Administrator

Wenn Sie ein benutzerdefiniertes Konto zum Aktivieren/Deaktivieren der Geräteüberwachung verwenden möchten, muss es eine der folgenden Rollen aufweisen:

- Globaler Administrator
- Compliance-Administrator

Endpunkt-DLP-Daten können im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt werden. Es gibt vier Rollen, die Berechtigungen für den Aktivitäten-Explorer gewähren; das Konto, das Sie für den Zugriff auf die Daten verwenden, muss eine der folgenden Rollen aufweisen:

- Globaler Administrator
- Compliance-Administrator
- Sicherheitsadministrator
- Compliancedaten-Administrator

### <a name="prepare-your-endpoints"></a>Vorbereiten der Endpunkte

Vergewissern Sie sich, dass die Windows 10-Geräte, auf die Sie Endpunkt-DLP anwenden möchten, die nachstehenden Anforderungen erfüllen.

1. Auf den Geräten muss Windows 10 Build 1809 oder höher ausgeführt werden.
2. Alle Geräte müssen in [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), oder in Azure AD Hybrid eingebunden sein.
3. Installieren Sie den Microsoft Edge-Browser auf dem Endpunktgerät, um Richtlinienaktionen für die Aktivität „Hochladen in die Cloud“ durchzusetzen. Weitere Informationen finden Sie unter [Herunterladen des auf Chromium basierenden neuen Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

## <a name="onboarding-devices-into-device-management"></a>Onboarding von Geräten für die Geräteverwaltung

 Sie müssen die Geräteüberwachung aktivieren und die Endpunkte einbinden, bevor vertrauliche Elemente auf einem Gerät überwacht und geschützt werden können. Beide Aktionen werden im Microsoft 365 Compliance-Portal durchgeführt.

Wenn Sie das Onboarding von noch nicht eingebundenen Geräten vornehmen möchten, laden Sie das entsprechende Skript herunter, und installieren Sie es auf diesen Geräten. Wenden Sie das [Verfahren zum Onboarding von Geräten](endpoint-dlp-getting-started.md#onboarding-devices) an.

Wenn bereits Geräte in [Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/) eingebunden sind, werden sie in der Liste der verwalteten Geräte angezeigt. Folgen Sie dem [Verfahren bei in MDATP eingebundenen Geräten](endpoint-dlp-getting-started.md#with-devices-onboarded-into-mdatp).

### <a name="onboarding-devices"></a>Onboarding von Geräten

In diesem Bereitstellungsszenario werden Sie das Onboarding von noch nicht eingebundenen Geräten vornehmen, und Sie werden dafür sorgen, dass vertrauliche Elemente auf Windows 10-Geräten im Hinblick auf versehentliche Freigabe überwacht und geschützt sind.

1. Öffnen Sie das [Microsoft Compliance Center](https://compliance.microsoft.com).
2. Öffnen Sie die Seite "Einstellungen", und wählen Sie **Geräte-Onboarding** aus. 

   ![Aktivieren der Geräteverwaltung](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > In der Regel dauert es zwar nur ungefähr eine Minute, bis das Geräte-Onboarding aktiviert ist, warten Sie aber mindestens 30 Minuten, bevor Sie sich an den Microsoft-Support wenden.

3. Wählen Sie **Geräteverwaltung** aus, um die Liste der **Geräte** zu öffnen. Die Liste ist leer, solange keine Geräte eingebunden sind.
4. Wählen Sie **Onboarding** aus, um mit dem Onboarding-Prozess zu beginnen.
5. Wählen Sie die Art der Bereitstellung auf diesen zusätzlichen Geräten aus der Liste der **Bereitstellungsmethoden** und anschließend **Paket herunterladen** aus.

   ![Bereitstellungsmethode](../media/endpoint-dlp-getting-started-3-deployment-method.png)
6. Führen Sie die unter [Onboarding-Tools und -Methoden für Windows 10-Computer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) beschriebenen entsprechenden Verfahren aus. Über diesen Link gelangen Sie zu einer Zielseite, auf der MDATP-Prozeduren beschrieben werden, die dem in Schritt 5 ausgewählten Bereitstellungspaket entsprechen:
    - Onboarding von Windows 10-Computern mithilfe von Gruppenrichtlinien
    - Onboarding von Windows-Computern mithilfe von Microsoft Endpoint Configuration Manager
    - Onboarding von Windows 10-Computern mit Tools für die Verwaltung von Mobilgeräten
    - Onboarding von Windows 10-Computern mithilfe eines lokalen Skripts
    - Onboarding von nicht-persistenten Computern einer VD-Infrastruktur (Virtual Desktop)

Nach Abschluss des Endpunkt-Onboardings sollten diese in der Liste der Geräte aufgeführt sein, und das Übertragen von Aktivitätsüberwachungsprotokollen an den Aktivitäten-Explorer sollte beginnen.

> [!NOTE]
> Diese Funktion erfordert eine Lizenz. Ohne die erforderliche Lizenz werden keine Daten angezeigt und es ist kein Zugriff auf sie möglich.

### <a name="with-devices-onboarded-into-mdatp"></a>Bei in MDATP eingebundenen Geräten

In diesem Szenario ist MDATP bereits installiert, und Endpunkte senden Protokolle. Alle diese Endpunkte werden in der Liste der verwalteten Geräte angezeigt. Über das [Geräte-Onboarding](endpoint-dlp-getting-started.md#onboarding-devices) können Sie weiterhin neue Geräte in Endpunkt-DLP einbinden, um die Abdeckung zu erweitern.

1. Öffnen Sie das [Microsoft Compliance Center](https://compliance.microsoft.com).
2. Öffnen Sie die Seite "Einstellungen", und wählen Sie **Geräteüberwachung aktivieren** aus.
3. Wählen Sie **Geräteverwaltung** aus, um die Liste der **Geräte** zu öffnen. Es sollte die Liste der Geräte angezeigt werden, die bereits Berichte für MDATP erstellen. ![Geräteverwaltung](../media/endpoint-dlp-getting-started-2-device-management.png)
4. Wenn Sie zusätzliche Geräte einbinden möchten, wählen Sie **Onboarding** aus.
5. Wählen Sie die Art der Bereitstellung auf diesen zusätzlichen Geräten aus der Liste der **Bereitstellungsmethoden** und anschließend **Paket herunterladen** aus.
6. Führen Sie die unter [Onboarding-Tools und -Methoden für Windows 10-Computer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) beschriebenen entsprechenden Verfahren aus. Über diesen Link gelangen Sie zu einer Zielseite, auf der MDATP-Prozeduren beschrieben werden, die dem in Schritt 5 ausgewählten Bereitstellungspaket entsprechen:
    - Onboarding von Windows 10-Computern mithilfe von Gruppenrichtlinien
    - Onboarding von Windows-Computern mithilfe von Microsoft Endpoint Configuration Manager
    - Onboarding von Windows 10-Computern mit Tools für die Verwaltung von Mobilgeräten
    - Onboarding von Windows 10-Computern mithilfe eines lokalen Skripts
    - Onboarding von nicht-persistenten Computern einer VD-Infrastruktur (Virtual Desktop)

Nach Abschluss des Endpunkt-Onboardings sollten diese in der Tabelle der **Geräte** aufgeführt sein, und das Übertragen von Überwachungsprotokollen an den **Aktivitäten-Explorer** sollte beginnen.

> [!NOTE]
>Diese Funktion erfordert eine Lizenz. Ohne die erforderliche Lizenz werden keine Daten angezeigt und es ist kein Zugriff auf sie möglich.

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>Anzeigen von Endpunkt-DLP-Daten im Aktivitäten-Explorer

1. Öffnen Sie im Microsoft 365 Compliance Center die Seite [Datenklassifizierung](https://compliance.microsoft.com/dataclassification?viewid=overview) für Ihre Domäne, und wählen Sie den Aktivitäten-Explorer aus.
2. Unter [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md) erfahren Sie Näheres dazu, wie Sie auf alle Daten zu Ihren Endpunktgeräten zugreifen und diese filtern können.

![Aktivitäten-Explorer-Filter für Endpunktgeräte](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a>Nächste Schritte
Jetzt, da Geräte eingebunden sind und entsprechende Aktivitätsdaten im Aktivitäten-Explorer angezeigt werden, können Sie mit dem nächsten Schritt fortfahren, bei dem Sie DLP-Richtlinien zum Schutz Ihrer vertraulichen Elemente erstellen werden.

- [Nutzung von Endpunkt-DLP (Vorschau)](endpoint-dlp-using.md)

## <a name="see-also"></a>Siehe auch

- [Informationen zu Endpunkt-DLP (Vorschau)](endpoint-dlp-learn-about.md)
- [Nutzung von Endpunkt-DLP (Vorschau)](endpoint-dlp-using.md)
- [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md)
- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)
- [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md)
- [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)
- [Onboarding-Tools und -Methoden für Windows 10-Computer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure Active Directory (AAD) Einbindung](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [Herunterladen des auf Chromium basierenden neuen Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
