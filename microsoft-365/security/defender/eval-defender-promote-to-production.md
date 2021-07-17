---
title: Bewerben Sie Ihre Microsoft 365 Defender Evaluierungsumgebung für die Produktion, Microsoft 365 Defender Evaluierung, testen Sie eine Evaluierung, behalten Sie eine Evaluierung, produktionsbezogene Evaluierung
description: Verwenden Sie diesen Artikel, um Ihre Ausweichen von MDI, MDO, MDE und MCAS in Ihre Liveumgebung in Microsoft 365 Defender oder M365D zu bewerben.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458341"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>Bewerben Ihrer Microsoft 365 Defender Evaluierungsumgebung für die Produktion

**Gilt für:**
- Microsoft 365 Defender

Um Ihre Microsoft 365 Defender Evaluierungsumgebung für die Produktion zu bewerben, erwerben Sie zuerst die erforderliche Lizenz. Führen Sie die Schritte unter [Erstellen der eval-Umgebung](eval-create-eval-environment.md) aus, und erwerben Sie die Office 365 E5-Lizenz (anstatt die kostenlose Testversion starten zu wählen).

Schließen Sie als Nächstes alle zusätzlichen Konfigurationen ab, und erweitern Sie Ihre Pilotgruppen, bis diese die vollständige Produktion erreicht haben. 

## <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity
Defender for Identity erfordert keine zusätzliche Konfiguration. Stellen Sie einfach sicher, dass Sie die erforderlichen Lizenzen erworben und den Sensor auf allen Active Directory-Domänencontrollern und Active Directory-Verbunddiensten (AD FS)-Servern installiert haben. 

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender für Office 365
Nachdem MDO erfolgreich ausgewertet oder pilotiert wurde, kann es in Ihre gesamte Produktionsumgebung übertragen werden.
1. Erwerben und bereitstellen Sie die erforderlichen Lizenzen, und weisen Sie sie Ihren Produktionsbenutzern zu.
2. Führen Sie empfohlene Basisrichtlinienkonfigurationen (standard oder streng) für Ihre Produktions-E-Mail-Domäne oder bestimmte Benutzergruppen erneut aus.
3. Optional können Sie benutzerdefinierte MDO-Richtlinien für Ihre Produktions-E-Mail-Domäne oder Benutzergruppen erstellen und konfigurieren.  Denken Sie jedoch daran, dass alle zugewiesenen Basisrichtlinien immer Vorrang vor benutzerdefinierten Richtlinien haben.
4. Aktualisieren Sie den öffentlichen MX-Eintrag für Ihre Produktions-E-Mail-Domäne so, dass er direkt in EOP aufgelöst wird.
5. Außerbetriebnahme aller SMTP-Gateways von Drittanbietern und Deaktivieren oder Löschen von EXO-Connectors, die diesem Relay zugeordnet sind.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender für Endpunkt
Um die Evaluierungsumgebung von Microsoft Defender für Endpunkt von einem Pilotprojekt zur Produktion zu fördern, integrieren Sie einfach mehr Endpunkte mithilfe der [unterstützten Tools und Methoden](/defender-endpoint/onboard-configure)in den Dienst.

Verwenden Sie die folgenden allgemeinen Richtlinien, um weitere Geräte in Microsoft Defender für Endpunkt zu integrieren. 

1. Stellen Sie sicher, dass das Gerät die [Mindestanforderungen](/defender-endpoint/minimum-requirements)erfüllt.
2. Führen Sie je nach Gerät die Konfigurationsschritte aus, die im Onboarding-Abschnitt des Defender für Endpunkt-Portals angegeben sind.
3. Verwenden Sie das entsprechende Verwaltungstool und die entsprechende Bereitstellungsmethode für Ihre Geräte.
4.  Führen Sie einen Erkennungstest aus, um sicherzustellen, dass die Geräte ordnungsgemäß integriert sind, und melden Sie sich an den Dienst.

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security erfordert keine zusätzliche Konfiguration. Stellen Sie einfach sicher, dass Sie die erforderlichen Lizenzen erworben haben. Wenn Sie die Bereitstellung auf bestimmte Benutzergruppen beschränkt haben, erweitern Sie den Umfang dieser Gruppen, bis Sie die Produktionsskala erreichen. 

