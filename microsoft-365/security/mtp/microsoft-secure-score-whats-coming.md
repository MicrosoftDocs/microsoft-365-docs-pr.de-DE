---
title: Was kommt in Microsoft Secure Score vor?
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Details berechnet werden und welche Sicherheitsadministratoren erwarten können.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, sicheres Ergebnis, Sicherheitscenter, Verbesserungs Aktionen
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372003"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Was kommt in Microsoft Secure Score vor?

Um Microsoft Secure Score zu einem besseren Vertreter ihrer Sicherheitsposition zu machen und die Benutzerfreundlichkeit zu verbessern, werden wir in naher Zukunft einige Änderungen vornehmen. Ihre Punktzahl und die maximal mögliche Punktzahl ändern sich. Dies impliziert jedoch keine Änderung ihrer Sicherheitsposition.

Informationen zu den neuesten Änderungen finden Sie unter [What es New in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)

## <a name="march-16th-2020"></a>16. März 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Entfernen von Verbesserungs Aktionen, die nicht den Erwartungen für eine zuverlässige Messung entsprechen oder keine sinnvolle Darstellung der Sicherheitsposition bieten

Um sicherzustellen, dass die Microsoft Secure Score sinnvoll ist und dass jede Verbesserungs Aktion messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungs Aktionen.

- Speichern von Benutzerdokumenten in OneDrive für Unternehmen
- Einrichten Office 365 Richtlinien für ATP-sichere Anlagen
- Einrichten Office 365 sicherer Links zum Überprüfen von URLs
- Post Fach Delegierung nicht zulassen
- Zulassen von anonymen Gast Freigabelinks für Websites und Dokumente
- Aktivieren der Cloud-App-Sicherheitskonsole
- Konfigurieren der Ablaufzeit für externe Freigabelinks

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Unterstützen von Sicherheitsstandards für Azure AD Verbesserungs Aktionen

Microsoft Secure Score wird Update Verbesserungs Aktionen zur Unterstützung von [Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), die es einfacher machen, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.

Dies wirkt sich auf die folgenden Verbesserungs Aktionen aus:

- Sicherstellen, dass alle Benutzer mehrstufige Authentifizierung für sicheren Zugriff ausführen können
- MFA für Administratorrollen erforderlich
- Aktivieren der Richtlinie zum Blockieren der Legacy Authentifizierung
