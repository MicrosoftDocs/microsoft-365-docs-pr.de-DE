---
title: Erfahren Sie mehr über die Microsoft Compliance-Erweiterung
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Die Microsoft Compliance-Erweiterung erweitert die Überwachung von Dateiaktivitäten und Schutzaktionen auf den Google Chrome-Browser
ms.openlocfilehash: cf7a3cd2e26f2e7d7a116e4a609f98aeea78be19
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843806"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a>Erfahren Sie mehr über die Microsoft Compliance-Erweiterung

[Verhinderung von Datenverlust am Endpunkt (Endpunkt-DLP)](endpoint-dlp-learn-about.md) erweitert die Aktivitätsüberwachung und die Schutzfunktionen von [Microsoft 365-Verhinderung von Datenverlust](dlp-learn-about-dlp.md) auf sensible Elemente auf Windows 10-Geräten. Sobald Geräte in den Microsoft 365 Compliance-Lösungen eingebunden wurden, werden die Informationen zu den Aktionen, die Benutzer mit und an vertraulichen Elementen ausführen, im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt, und Sie können Schutzmaßnahmen für diese Elemente über [DLP-Richtlinien](create-test-tune-dlp-policy.md) erzwingen.

Sobald die Microsoft Compliance-Erweiterung auf einem Windows 10-Gerät installiert ist, werden Organisationen überwachen können, ob ein Benutzer versucht ein vertrauliches Element auf einen Clouddienst mittels Google Chrome hochzuladen, und sie werden Schutzaktionen mittels des DLP erzwingen können.  

## <a name="activities-you-can-monitor-and-take-action-on"></a>Aktivitäten, die Sie überwachen und für die Sie Maßnahmen festlegen können

Mit der Microsoft Compliance-Erweiterung können Sie die folgenden Aktivitätstypen überwachen und verwalten, die von Benutzern mit und an vertraulichen Elementen auf Windows 10-Geräten ausgeführt werden.

Aktivität |Beschreibung  | Unterstützte Richtlinienaktionen|
|---------|---------|---------|
|Datei in die Cloud kopiert  | Erkennt, wenn ein Benutzer versucht, ein vertrauliches Element in eine eingeschränkte Dienstdomäne hochzuladen oder über den Chrome-Browser |überwachen, blockieren|
|Datei gedruckt  |Erkennt, wenn ein Benutzer versucht ein vertrauliches Element zu drucken, das im Chrome-Browser zu einem lokalen Netzwerkdrucker geöffnet ist |überwachen, blockieren mit Außerkraftsetzung, blockieren|
|Datei in die Zwischenablage kopiert |Erkennt, wenn ein Benutzer versucht, Informationen aus einem vertraulichen Element zu kopieren, das in einem Chrome-Browser angezeigt wird, und in eine andere App, einen Prozess, oder ein Element einzufügen. |überwachen, blockieren mit Außerkraftsetzung, blockieren|
|Datei auf Wechselmedium kopiert    | Erkennt, wen ein Benutzer versucht ein vertrauliches Element oder Informationen von einem vertraulichen Element, das im Chrome-Browser geöffnet ist, auf ein Wechselmedium oder USB-Gerät zu kopieren |überwachen, blockieren mit Außerkraftsetzung, blockieren|
|Datei auf die Netzwerkfreigabe kopiert  |Erkennt, wen ein Benutzer versucht ein vertrauliches Element oder Informationen von einem vertraulichen Element, das im Chrome-Browser geöffnet ist, auf eine Netzwerkfreigabe oder ein zugeordnetes Netzwerklaufwerk zu kopieren.|überwachen, blockieren mit Außerkraftsetzung, blockieren |

## <a name="deployment-process"></a>Bereitstellungsprozess
1. [Endpunkt-DLP – Erste Schritte](endpoint-dlp-getting-started.md)
2. [Onboarding-Tools und -Methoden für Windows 10-Computer](dlp-configure-endpoints.md)
3. [Erweiterung auf Ihre Windows 10-Geräte installieren](dlp-chrome-get-started.md)
4. [DLP-Richtlinien erstellen oder bearbeiten](create-test-tune-dlp-policy.md), die „In Cloud hochladen“-Dienste einschränken, oder greifen Sie mittels unzulässiger Browseraktionen zu und wenden Sie sie auf Ihren Microsoft 10-Geräten an

## <a name="next-steps"></a>Nächste Schritte

Lesen Sie [Erste Schritte mit der Microsoft Compliance-Erweiterung](dlp-chrome-get-started.md), um vollständige Bereitstellungsverfahren und -Szenarien zu erhalten.

## <a name="see-also"></a>Mehr dazu

- [Erste Schritte mit der Microsoft Compliance-Erweiterung](dlp-chrome-get-started.md)
- [Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)](endpoint-dlp-learn-about.md)
- [Erste Schritte mit Microsoft Endpunkt-DLP](endpoint-dlp-getting-started.md)
- [Nutzung von Microsoft Endpunkt-DLP ](endpoint-dlp-using.md)
- [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md)
- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)
- [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md)
- [Microsoft Defender für Endpunkt](/windows/security/threat-protection/)
- [Insider-Risikomanagement](insider-risk-management.md)
