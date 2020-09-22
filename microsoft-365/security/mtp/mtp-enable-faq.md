---
title: Häufig gestellte Fragen beim Aktivieren von Microsoft Threat Protection
description: Hier finden Sie Antworten auf die am häufigsten gestellten Fragen zu Lizenzierung, Berechtigungen, anfänglichen Einstellungen und anderen Produkten und Diensten im Zusammenhang mit der Aktivierung von Microsoft Threat Protection.
keywords: häufig gestellte Fragen, FAQ, gcc, erste Schritte, Aktivieren von MTP, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenz Berechtigung, Seite "Einstellungen"
search.product: eADQiWindows 10XVcnh
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198839"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>Häufig gestellte Fragen beim Aktivieren von Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Hier finden Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von [Microsoft Threat Protection](microsoft-threat-protection.md), einschließlich der erforderlichen Lizenzen und Berechtigungen, der Bereitstellung von Supportdiensten und der anfänglichen Einstellungen.

Anweisungen zum Aktivieren des Diensts finden [Sie unter Aktivieren von Microsoft Threat Protection](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>Ich habe keine Microsoft 365 E5-Lizenz. Kann ich weiterhin Microsoft Threat Protection verwenden?

Kunden mit den folgenden nicht-E5-Lizenzen können Microsoft Threat Protection verwenden:

- Microsoft Defender Advanced Threat Protection
- Azure Advanced Threat Protection
- Microsoft Cloud App Security
- Office 365 Advanced Threat Protection (Plan 2)
 
Eine vollständige Liste unterstützter Lizenzen [finden Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>Muss ich etwas installieren oder bereitstellen, um mit Microsoft Threat Protection zu beginnen?

Nein, Microsoft Threat Protection konsolidiert Daten aus Microsoft 365-Sicherheitsdiensten, die Sie bereits bereitgestellt haben. Sobald Sie die Funktion aktiviert haben, werden Vorfall-, Automatisierungs-und Jagd Erfahrungen im Rahmen der bereitgestellten Produkte ausgeführt. Wenn keines dieser Produkte ordnungsgemäß bereitgestellt wird, zeigt Microsoft Threat Protection keine Daten an und kann keine Aktionen ausführen.

Zur Optimierung Ihrer Microsoft Threat Protection-Erlebnisse wird empfohlen, *alle* unterstützten [Microsoft 365-Sicherheitsprodukte und-Dienste](deploy-supported-services.md)bereitzustellen.

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>Wo verarbeitet und speichert Microsoft Threat Protection meine Daten?
Microsoft Threat Protection wählt automatisch einen optimalen Standort für das Rechenzentrum aus, in dem konsolidierte Daten verarbeitet und gespeichert werden. Wenn Sie Microsoft Defender ATP haben, wird derselbe Speicherort ausgewählt, der von Microsoft Defender ATP verwendet wird.

>[!NOTE]
>Microsoft Defender ATP stellt in den Rechenzentren der Europäischen Union (EU) automatisch Rückstellungen bereit, wenn Sie über das Azure Security Center aktiviert werden. Microsoft Threat Protection wird automatisch im gleichen EU-Rechenzentrum für Kunden bereitgestellt, die Microsoft Defender ATP auf diese Weise bereitgestellt haben. 

Der Speicherort des Rechenzentrums wird vor und nach der Einrichtung des Diensts auf der Seite Einstellungen für Microsoft Threat Protection (**Einstellungen > Microsoft Threat Protection**) angezeigt. Wenn Sie lieber einen anderen rechenzentrumsstandort verwenden möchten, wählen Sie **need help?** im Microsoft 365 Security Center aus, um den Microsoft-Support zu kontaktieren.

## <a name="where-can-i-access-microsoft-threat-protection"></a>Wo kann ich auf Microsoft Threat Protection zugreifen?

Microsoft Threat Protection steht im Microsoft 365 Security Center zur Verfügung. Um zum Sicherheitscenter zu wechseln, navigieren Sie zur URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>Welche Berechtigungen benötige ich für den Zugriff auf Microsoft Threat Protection im Microsoft 365 Security Center?

Konten, denen die folgenden Azure Active Directory (AD)-Rollen zugewiesen sind, können auf Microsoft Threat Protection-Funktionen und -Daten zugreifen:

- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator
- Globaler Leser
- Sicherheitsleseberechtigter

>[!NOTE]
>Rollenbasierte Zugriffssteuerungseinstellungen in Microsoft Defender ATP beeinflussen den Zugriff auf Daten. Weitere Informationen finden Sie unter [Verwalten des Zugriffs auf Microsoft Threat Protection](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>In welcher Zeitzone wird Microsoft Threat Protection standardmäßig verwendet?
Standardmäßig zeigt Microsoft Threat Protection Zeit Informationen in der UTC-Zeitzone an. Sie können diese Einstellung so ändern, dass Sie Ihre lokale Zeitzone verwendet. [Informationen zum Festlegen der Zeitzone](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>Wie kann ich neue Features für Microsoft Threat Protection und Benutzeroberflächen Updates erfahren?

Microsoft stellt regelmäßig Informationen über die verschiedenen Kanäle bereit, einschließlich:

- Das [Nachrichtencenter](../../admin/manage/message-center.md) im Microsoft 365 Admin Center
- Blogposts in der [Microsoft 365 Security & Compliance Tech-Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Holen Sie sich die neuesten öffentlich verfügbaren Benutzeroberflächen, indem Sie die [Vorschaufunktionen](preview.md)aktivieren.

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Ist Microsoft Threat Protection für US Government Community Cloud (GCC) oder GCC High verfügbar?
Zurzeit ist Microsoft Threat Protection dafür nicht verfügbar.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Microsoft Threat Protection](microsoft-threat-protection.md)
- [Aktivieren Sie Microsoft Threat Protection](mtp-enable.md).
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Vorschaufunktionen aktivieren](preview.md)
