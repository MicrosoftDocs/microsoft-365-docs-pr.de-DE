---
title: Häufig gestellte Fragen beim Aktivieren von Microsoft 365 Defender
description: Erhalten Sie Antworten auf die am häufigsten gestellten Fragen zu Lizenzierung, Berechtigungen, Anfänglichen Einstellungen und anderen Produkten und Diensten im Zusammenhang mit der Aktivierung von Microsoft 365 Defender.
keywords: häufig gestellte Fragen, HÄUFIG GESTELLTE Fragen, GCC, erste Schritte, Aktivieren von MTP, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenzberechtigung, Einstellungsseite
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
ms.openlocfilehash: 7482bf614e7cb3ffad6596f3c5d8bc554d46d912
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068648"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Häufig gestellte Fragen beim Aktivieren von Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Lesen Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von [Microsoft 365 Defender,](microsoft-365-defender.md)einschließlich erforderlicher Lizenzen und Berechtigungen, bereitstellen von Supportdiensten und anfänglichen Einstellungen.

Anweisungen zum Aktivieren des Diensts finden Sie [unter Aktivieren von Microsoft 365 Defender](m365d-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Ich habe keine Microsoft 365 E5-Lizenz. Kann ich Microsoft 365 Defender weiterhin verwenden?

Kunden mit den folgenden Nicht-E5-Lizenzen können Microsoft 365 Defender verwenden:

- Microsoft Defender für Endpunkt
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Microsoft Defender für Office 365 (Plan 2)
 
Eine vollständige Liste der unterstützten Lizenzen finden Sie [in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Muss ich etwas installieren oder bereitstellen, um mit Microsoft 365 Defender zu beginnen?

Nein, Microsoft 365 Defender konsolidiert Daten von Microsoft 365-Sicherheitsdiensten, die Sie bereits bereitgestellt haben. Sobald Sie dies aktivieren, werden Die Erfahrungen mit Vorfällen, Automatisierung und Suche im Rahmen der bereitgestellten Produkte verwendet. Wenn keines dieser Produkte ordnungsgemäß bereitgestellt wird, zeigt Microsoft 365 Defender keine Daten an und kann keine Aktionen ergreifen.

Um Ihre Microsoft 365 Defender-Erfahrungen  zu optimieren, empfehlen wir die Bereitstellung aller unterstützten [Microsoft 365-Sicherheitsprodukte und -dienste.](deploy-supported-services.md)

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Wo werden meine Daten von Microsoft 365 Defender verarbeiten und gespeichert?
Microsoft 365 Defender wählt automatisch einen optimalen Speicherort für das Rechenzentrum aus, in dem konsolidierte Daten verarbeitet und gespeichert werden. Wenn Sie über Microsoft Defender for Endpoint verfügen, wird derselbe Speicherort ausgewählt, der von Defender for Endpoint verwendet wird.

>[!NOTE]
>Microsoft Defender for Endpoint stellt automatisch In Rechenzentren in der Europäischen Union (EU) bereit, wenn sie über Azure Defender aktiviert sind. Microsoft 365 Defender stellt automatisch im gleichen EU-Rechenzentrum Kunden zur Verfügung, die Microsoft Defender for Endpoint auf diese Weise bereitgestellt haben. 

Der Speicherort des Rechenzentrums wird vor und nach der Bereitstellung des Diensts auf der Einstellungsseite für Microsoft 365 Defender (**Einstellungen > Microsoft 365 Defender**) angezeigt. Wenn Sie lieber einen anderen Rechenzentrumsstandort verwenden möchten, wählen Sie **Hilfe benötigen?** im Microsoft 365 Security Center aus, um den Microsoft-Support zu kontaktieren.

## <a name="where-can-i-access-microsoft-365-defender"></a>Wo kann ich auf Microsoft 365 Defender zugreifen?

Microsoft 365 Defender ist im Microsoft 365 Security Center verfügbar. Um zum Sicherheitscenter zu wechseln, navigieren Sie zur URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Welche Berechtigungen muss ich für den Zugriff auf Microsoft 365 Defender im Microsoft 365 Security Center benötigen?

Konten, denen die folgenden Azure Active Directory (AD)-Rollen zugewiesen sind, können auf Microsoft 365 Defender-Funktionen und -Daten zugreifen:

- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator
- Globaler Leser
- Sicherheitsleseberechtigter

>[!NOTE]
>Rollenbasierte Zugriffssteuerungseinstellungen in Microsoft Defender for Endpoint beeinflussen den Zugriff auf Daten. Weitere Informationen finden Sie unter [Verwalten des Zugriffs auf Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>In welcher Zeitzone wird Microsoft 365 Defender standardmäßig verwendet?
Standardmäßig zeigt Microsoft 365 Defender Zeitinformationen in der UTC-Zeitzone an. Sie können diese Einstellung so ändern, dass Ihre lokale Zeitzone verwendet wird. [Informationen zum Festlegen der Zeitzone](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Wie kann ich mehr über neue Microsoft 365 Defender-Feature- und Benutzeroberflächenupdates erfahren?

Microsoft stellt regelmäßig Informationen über die verschiedenen Kanäle zur Verfügung, darunter:

- Das [Nachrichtencenter](../../admin/manage/message-center.md) im Microsoft 365 Admin Center
- Blogposts in der [Microsoft 365 Security & Compliance Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Erhalten Sie die neuesten öffentlich verfügbaren Erfahrungen, indem Sie [Vorschaufeatures aktivieren.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Ist Microsoft 365 Defender für die US Government Community Cloud (GCC) oder GCC High verfügbar?
Zurzeit ist Microsoft Threat Protection dafür nicht verfügbar.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Microsoft 365 Defender](microsoft-365-defender.md)
- [Aktivieren Sie Microsoft 365 Defender](m365d-enable.md).
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Vorschaufeatures aktivieren](preview.md)
