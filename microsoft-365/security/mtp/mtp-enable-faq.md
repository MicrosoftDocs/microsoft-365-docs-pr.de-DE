---
title: Häufig gestellte Fragen beim Aktivieren von Microsoft 365 Defender
description: Erhalten Sie Antworten auf die am häufigsten gestellten Fragen zu Lizenzierung, Berechtigungen, Anfänglichen Einstellungen und anderen Produkten und Diensten im Zusammenhang mit der Aktivierung von Microsoft 365 Defender.
keywords: Häufig gestellte Fragen, HÄUFIG gestellte Fragen, GCC, erste Schritte, MTP aktivieren, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenzberechtigung, Einstellungsseite
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930186"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Häufig gestellte Fragen beim Aktivieren von Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Lesen Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von [Microsoft 365 Defender,](microsoft-threat-protection.md)einschließlich der erforderlichen Lizenzen und Berechtigungen, der Bereitstellung von Supportdiensten und anfänglichen Einstellungen.

Anweisungen zum Aktivieren des Diensts finden Sie unter ["Aktivieren von Microsoft 365 Defender".](mtp-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Ich habe keine Microsoft 365 E5-Lizenz. Kann ich Weiterhin Microsoft 365 Defender verwenden?

Kunden mit den folgenden Nicht-E5-Lizenzen können Microsoft 365 Defender verwenden:

- Microsoft Defender für Endpunkt
- Microsoft Defender for Identity
- Microsoft Cloud App-Sicherheit
- Defender für Office 365 (Plan 2)
 
Eine vollständige Liste der unterstützten Lizenzen finden Sie [in den Lizenzierungsanforderungen.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Muss ich etwas installieren oder bereitstellen, um mit der Verwendung von Microsoft 365 Defender zu beginnen?

Nein, Microsoft 365 Defender konsolidiert Daten aus Microsoft 365-Sicherheitsdiensten, die Sie bereits bereitgestellt haben. Sobald Sie sie aktivieren, funktionieren die Vorfall-, Automatisierungs- und Sucheerfahrungen im Rahmen der bereitgestellten Produkte. Wenn keines dieser Produkte ordnungsgemäß bereitgestellt ist, zeigt Microsoft 365 Defender keine Daten an und kann keine Maßnahmen ergreifen.

Um Ihre Microsoft 365 Defender-Erfahrungen  zu optimieren, empfehlen wir die Bereitstellung aller unterstützten [Microsoft 365-Sicherheitsprodukte und -Dienste.](deploy-supported-services.md)

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Wo werden meine Daten von Microsoft 365 Defender verarbeiten und gespeichert?
Microsoft 365 Defender wählt automatisch einen optimalen Speicherort für das Rechenzentrum aus, in dem konsolidierte Daten verarbeitet und gespeichert werden. Wenn Sie über Microsoft Defender für Endpoint verfügen, wählt es den gleichen Speicherort aus, der auch von Defender für Endpoint verwendet wird.

>[!NOTE]
>Microsoft Defender for Endpoint wird automatisch in Rechenzentren der Europäischen Union (EU) bereitgestellt, wenn sie über Azure Defender aktiviert sind. Microsoft 365 Defender wird automatisch im selben EU-Rechenzentrum für Kunden bereitgestellt, die Microsoft Defender for Endpoint auf diese Weise bereitgestellt haben. 

Der Standort des Rechenzentrums wird vor und nach der Bereitstellung des Diensts auf der Einstellungsseite für Microsoft 365 Defender ( Einstellungen >**Microsoft 365 Defender) angezeigt.** Wenn Sie lieber einen anderen Rechenzentrumsstandort verwenden möchten, wählen Sie **Hilfe?** im Microsoft 365 Security Center aus, um den Support von Microsoft zu kontaktieren.

## <a name="where-can-i-access-microsoft-365-defender"></a>Wo kann ich auf Microsoft 365 Defender zugreifen?

Microsoft 365 Defender ist im Microsoft 365 Security Center verfügbar. Um zum Security Center zu wechseln, navigieren Sie zur [https://security.microsoft.com](https://security.microsoft.com) URL.

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Welche Berechtigungen muss ich für den Zugriff auf Microsoft 365 Defender im Microsoft 365 Security Center benötigen?

Konten, denen die folgenden Azure Active Directory (AD)-Rollen zugewiesen sind, können auf Microsoft 365 -Defender-Funktionen und -Daten zugreifen:

- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator
- Globaler Leser
- Sicherheitsleseberechtigter

>[!NOTE]
>Rollenbasierte Zugriffssteuerungseinstellungen in Microsoft Defender for Endpoint beeinflussen den Zugriff auf Daten. Weitere Informationen finden Sie unter Verwalten [des Zugriffs auf Microsoft 365 Defender](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>In welcher Zeitzone wird Microsoft 365 Defender standardmäßig verwendet?
Standardmäßig zeigt Microsoft 365 Defender Zeitinformationen in der Zeitzone UTC an. Sie können diese Einstellung so ändern, dass Ihre lokale Zeitzone verwendet wird. [Informationen zum Festlegen der Zeitzone](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Wie kann ich mehr über neue Features und Benutzeroberflächenupdates für Microsoft 365 Defender erfahren?

Microsoft stellt regelmäßig Informationen über die verschiedenen Kanäle zur Verfügung, darunter:

- Das [Nachrichtencenter](../../admin/manage/message-center.md) im Microsoft 365 Admin Center
- Blogbeiträge in der [Microsoft 365 Security & Compliance Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Erhalten Sie die neuesten öffentlich verfügbaren Funktionen, indem Sie [Vorschaufeatures aktivieren.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Ist Microsoft 365 Defender für US Government Community Cloud (GCC) oder GCC High verfügbar?
Zurzeit ist Microsoft Threat Protection dafür nicht verfügbar.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Microsoft 365 Defender](microsoft-threat-protection.md)
- [Aktivieren Sie Microsoft 365 Defender.](mtp-enable.md)
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Vorschaufeatures aktivieren](preview.md)
