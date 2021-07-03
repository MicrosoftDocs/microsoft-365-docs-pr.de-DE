---
title: Häufig gestellte Fragen beim Aktivieren von Microsoft 365 Defender
description: Erhalten Sie Antworten auf die am häufigsten gestellten Fragen zu Lizenzierung, Berechtigungen, anfänglichen Einstellungen und anderen Produkten und Diensten im Zusammenhang mit der Aktivierung von Microsoft 365 Defender
keywords: häufig gestellte Fragen, häufig gestellte Fragen, GCC, erste Schritte, Microsoft 365 Defender aktivieren, Microsoft 365 Defender, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenzberechtigung, Einstellungsseite
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
ms.openlocfilehash: 1ba049e9fe608ba8bd559180c5a30060b10ee9e0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53285985"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Häufig gestellte Fragen beim Aktivieren von Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Lesen Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren [von Microsoft 365 Defender,](microsoft-365-defender.md)einschließlich der erforderlichen Lizenzen und Berechtigungen, der Bereitstellung von Supportdiensten und der anfänglichen Einstellungen.

Anweisungen zum Aktivieren des Diensts [finden Sie unter Aktivieren Microsoft 365 Defender](m365d-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Ich habe keine Microsoft 365 E5 Lizenz. Kann ich weiterhin Microsoft 365 Defender verwenden?

Kunden mit den folgenden Nicht-E5-Lizenzen können Microsoft 365 Defender verwenden:

- Microsoft Defender für Endpunkt
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Microsoft Defender für Office 365 (Plan 2)

Eine vollständige Liste der unterstützten Lizenzen [finden Sie unter den Lizenzierungsanforderungen.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Muss ich etwas installieren oder bereitstellen, um mit der Verwendung von Microsoft 365 Defender zu beginnen?

Nein, Microsoft 365 Defender konsolidiert Daten aus Microsoft 365 Sicherheitsdiensten, die Sie bereits bereitgestellt haben. Sobald Sie es aktiviert haben, werden Vorfall-, Automatisierungs- und Sucherfahrungen im Rahmen der bereitgestellten Produkte funktionieren. Wenn keines dieser Produkte ordnungsgemäß bereitgestellt wird, zeigt Microsoft 365 Defender keine Daten an und kann keine Maßnahmen ergreifen.

Um Ihre Microsoft 365 Defender Zu optimieren, empfehlen wir, *alle* unterstützten [Microsoft 365 Sicherheitsprodukte und -dienste](deploy-supported-services.md)bereitzustellen.

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Wo werden meine Daten von Microsoft 365 Defender verarbeitet und gespeichert?

Microsoft 365 Defender wählt automatisch einen optimalen Standort für das Rechenzentrum aus, in dem konsolidierte Daten verarbeitet und gespeichert werden. Wenn Sie Microsoft Defender für Endpunkt haben, wählt es den gleichen Speicherort aus, der von Defender für Endpunkt verwendet wird.

>[!NOTE]
>Microsoft Defender für Endpunkt stellt automatisch in Rechenzentren der Europäischen Union (EU) bereit, wenn es über Azure Defender aktiviert ist. Microsoft 365 Defender werden automatisch im selben EU-Rechenzentrum für Kunden bereitgestellt, die Microsoft Defender für Endpunkt auf diese Weise bereitgestellt haben.

Der Rechenzentrumsstandort wird vor und nach der Bereitstellung des Diensts auf der Einstellungsseite für Microsoft 365 Defender (**Einstellungen > Microsoft 365 Defender**) angezeigt. Wenn Sie lieber einen anderen Rechenzentrumsstandort verwenden möchten, wählen Sie **"Benötigen Sie Hilfe?"** im Microsoft 365 Security Center aus, um sich an den Microsoft-Support zu wenden.

## <a name="where-can-i-access-microsoft-365-defender"></a>Wo kann ich auf Microsoft 365 Defender zugreifen?

Microsoft 365 Defender ist im Microsoft 365 Security Center verfügbar. Um zum Sicherheitscenter zu wechseln, navigieren Sie zur <https://security.microsoft.com> URL.

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Welche Berechtigungen benöte ich für den Zugriff auf Microsoft 365 Defender im Microsoft 365 Security Center?

Konten, die den folgenden Azure Active Directory (Azure AD)-Rollen zugewiesen sind, können auf Microsoft 365 Defender Funktionen und Daten zugreifen:

- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator
- Globaler Leser
- Sicherheitsleseberechtigter

> [!NOTE]
> Rollenbasierte Zugriffssteuerungseinstellungen in Microsoft Defender für Endpunkt beeinflussen den Zugriff auf Daten. Weitere Informationen finden Sie unter [Verwalten des Zugriffs auf Microsoft 365 Defender.](m365d-permissions.md)

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Welche Zeitzone Microsoft 365 Defender standardmäßig?

Standardmäßig zeigt Microsoft 365 Defender Zeitinformationen in der UTC-Zeitzone an. Sie können diese Einstellung so ändern, dass Ihre lokale Zeitzone verwendet wird. [Informationen zum Festlegen der Zeitzone](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Wie kann ich mehr über neue Microsoft 365 Defender Feature- und UI-Updates erfahren?

Microsoft stellt regelmäßig Informationen über die verschiedenen Kanäle bereit, einschließlich:

- Das [Nachrichtencenter](../../admin/manage/message-center.md) in Microsoft 365 Admin Center
- Blogposts in der [Microsoft 365 Security & Compliance Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Rufen Sie die neuesten öffentlich verfügbaren Benutzeroberflächen ab, indem Sie [die Vorschaufeatures](preview.md)aktivieren.

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Ist Microsoft 365 Defender für US-Government Community Cloud (GCC) oder GCC High verfügbar?

Zurzeit ist Microsoft Threat Protection dafür nicht verfügbar.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Microsoft 365 Defender](microsoft-365-defender.md)
- [Aktivieren Sie Microsoft 365 Defender](m365d-enable.md).
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Vorschaufeatures aktivieren](preview.md)
