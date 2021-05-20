---
title: Häufig gestellte Fragen beim Aktivieren Microsoft 365 Defender
description: Erhalten Sie Antworten auf die am häufigsten gestellten Fragen zur Lizenzierung, berechtigungen, anfänglichen Einstellungen und anderen Produkten und Diensten im Zusammenhang mit der Aktivierung Microsoft 365 Defender
keywords: Häufig gestellte Fragen, HÄUFIG gestellte Fragen, GCC, erste Schritte, Aktivieren von Microsoft 365 Defender, Microsoft 365 Defender, M365, Sicherheit, Datenspeicherort, erforderlichen Berechtigungen, Lizenzberechtigung, Einstellungsseite
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572765"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Häufig gestellte Fragen beim Aktivieren Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Lesen Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von [Microsoft 365 Defender,](microsoft-365-defender.md)einschließlich erforderlicher Lizenzen und Berechtigungen, bereitstellen von Supportdiensten und anfänglichen Einstellungen.

Anweisungen zum Aktivieren des Diensts finden Sie unter [Aktivieren Microsoft 365 Defender](m365d-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Ich habe keine Microsoft 365 E5 Lizenz. Kann ich defender weiterhin Microsoft 365 verwenden?

Kunden mit den folgenden Nicht-E5-Lizenzen können defender Microsoft 365 verwenden:

- Microsoft Defender für Endpunkt
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Microsoft Defender für Office 365 (Plan 2)
 
Eine vollständige Liste der unterstützten Lizenzen finden Sie [in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Muss ich etwas installieren oder bereitstellen, um mit der Verwendung von Microsoft 365 starten?

Nein, Microsoft 365 Defender daten aus Microsoft 365, die Sie bereits bereitgestellt haben. Sobald Sie dies aktivieren, werden Die Erfahrungen mit Vorfällen, Automatisierung und Suche im Rahmen der bereitgestellten Produkte verwendet. Wenn keines dieser Produkte ordnungsgemäß bereitgestellt wird, zeigt Microsoft 365 Defender keine Daten an und kann keine Aktionen ergreifen.

Zur Optimierung ihrer Microsoft 365 von Defender empfehlen  wir die Bereitstellung aller [unterstützten](deploy-supported-services.md)Microsoft 365 und Dienste .

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Wo werden Microsoft 365 Von Defender verarbeiten und meine Daten gespeichert?
Microsoft 365 Defender wählt automatisch einen optimalen Speicherort für das Rechenzentrum aus, in dem konsolidierte Daten verarbeitet und gespeichert werden. Wenn Sie über Microsoft Defender for Endpoint verfügen, wird derselbe Speicherort ausgewählt, der von Defender for Endpoint verwendet wird.

>[!NOTE]
>Microsoft Defender for Endpoint stellt automatisch In Rechenzentren in der Europäischen Union (EU) bereit, wenn sie über Azure Defender aktiviert sind. Microsoft 365 Defender stellt automatisch im gleichen EU-Rechenzentrum Kunden zur Verfügung, die Microsoft Defender for Endpoint auf diese Weise bereitgestellt haben. 

Der Speicherort des Rechenzentrums wird vor und nach der Bereitstellung des Diensts auf der Einstellungsseite für Microsoft 365 Defender ( Einstellungen > Microsoft 365 Defender )**angezeigt.** Wenn Sie lieber einen anderen Rechenzentrumsspeicherort verwenden möchten, wählen Sie Hilfe **benötigen?** im Microsoft 365 Security Center aus, um den Microsoft-Support zu kontaktieren.

## <a name="where-can-i-access-microsoft-365-defender"></a>Wo kann ich auf Microsoft 365 zugreifen?

Microsoft 365 Defender ist in Microsoft 365 Security Center verfügbar. Um zum Sicherheitscenter zu wechseln, navigieren Sie zur URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Welche Berechtigungen benötigt ich für den Zugriff auf Microsoft 365 Defender in Microsoft 365 Security Center?

Konten, denen die folgenden Azure Active Directory (Azure AD) zugewiesen sind, können auf Microsoft 365 Funktionen und Daten von Defender zugreifen:

- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator
- Globaler Leser
- Sicherheitsleseberechtigter

>[!NOTE]
>Rollenbasierte Zugriffssteuerungseinstellungen in Microsoft Defender for Endpoint beeinflussen den Zugriff auf Daten. Weitere Informationen finden Sie unter [Verwalten des Zugriffs auf Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>In welcher Zeitzone Microsoft 365 Defender standardmäßig?
Standardmäßig zeigt Microsoft 365 Defender Zeitinformationen in der UTC-Zeitzone an. Sie können diese Einstellung so ändern, dass Ihre lokale Zeitzone verwendet wird. [Informationen zum Festlegen der Zeitzone](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Wie erfahre ich mehr über neue Microsoft 365 und Benutzeroberflächenupdates für Defender?

Microsoft stellt regelmäßig Informationen über die verschiedenen Kanäle zur Verfügung, darunter:

- Das [Nachrichtencenter](../../admin/manage/message-center.md) im Microsoft 365 Admin Center
- Blogposts in der [Microsoft 365 Security & Compliance Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Erhalten Sie die neuesten öffentlich verfügbaren Erfahrungen, indem Sie [Vorschaufeatures aktivieren.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Ist Microsoft 365 Defender für GOVERNMENT COMMUNITY CLOUD (GCC) oder GCC Verfügbar?
Zurzeit ist Microsoft Threat Protection dafür nicht verfügbar.

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft 365 Übersicht über Defender](microsoft-365-defender.md)
- [Aktivieren sie Microsoft 365 Defender](m365d-enable.md).
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Vorschaufeatures aktivieren](preview.md)
