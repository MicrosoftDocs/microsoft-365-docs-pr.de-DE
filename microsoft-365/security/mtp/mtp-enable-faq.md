---
title: Häufig gestellte Fragen beim Aktivieren von Microsoft 365 Defender
description: Hier finden Sie Antworten auf die am häufigsten gestellten Fragen zu Lizenzierung, Berechtigungen, anfänglichen Einstellungen und anderen Produkten und Diensten im Zusammenhang mit der Aktivierung von Microsoft 365 Defender.
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
ms.openlocfilehash: bfb58cb043f2bc641245814c41e389ddcdbfdefa
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842416"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Häufig gestellte Fragen beim Aktivieren von Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Hier finden Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von [Microsoft 365 Defender](microsoft-threat-protection.md), einschließlich der erforderlichen Lizenzen und Berechtigungen, der Bereitstellung von Supportdiensten und der anfänglichen Einstellungen.

Anweisungen zum Aktivieren des Diensts finden [Sie unter Aktivieren von Microsoft 365 Defender](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Ich habe keine Microsoft 365 E5-Lizenz. Kann ich weiterhin Microsoft 365 Defender verwenden?

Kunden mit den folgenden nicht-E5-Lizenzen können Microsoft 365 Defender verwenden:

- Microsoft Defender für Endpunkt
- Microsoft Defender für Identity
- Microsoft Cloud App-Sicherheit
- Verteidiger für Office 365 (Plan 2)
 
Eine vollständige Liste unterstützter Lizenzen [finden Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Muss ich etwas installieren oder bereitstellen, um mit Microsoft 365 Defender zu beginnen?

Nein, Microsoft 365 Defender konsolidiert Daten von Microsoft 365-Sicherheitsdiensten, die Sie bereits bereitgestellt haben. Sobald Sie die Funktion aktiviert haben, werden Vorfall-, Automatisierungs-und Jagd Erfahrungen im Rahmen der bereitgestellten Produkte ausgeführt. Wenn keines dieser Produkte ordnungsgemäß bereitgestellt wird, zeigt Microsoft 365 Defender keine Daten an und kann keine Aktionen ausführen.

Zur Optimierung Ihrer Microsoft 365 Defender-Erlebnisse wird empfohlen, *alle* unterstützten [Microsoft 365-Sicherheitsprodukte und-Dienste](deploy-supported-services.md)bereitzustellen.

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Wo verarbeitet und speichert Microsoft 365 Defender meine Daten?
Microsoft 365 Defender wählt automatisch einen optimalen Standort für das Rechenzentrum aus, in dem konsolidierte Daten verarbeitet und gespeichert werden. Wenn Sie über Microsoft Defender für Endpoint verfügen, wird derselbe Speicherort ausgewählt, der von Defender für Endpoint verwendet wird.

>[!NOTE]
>Microsoft Defender für Endpoint stellt automatisch Vorkehrungen in den Rechenzentren in der Europäischen Union (EU) bereit, wenn es über Azure Defender * aktiviert wird. Microsoft 365 Defender wird automatisch im gleichen EU-Rechenzentrum für Kunden bereitgestellt, die Microsoft Defender für Endpoint auf diese Weise bereitgestellt haben. 

Der Speicherort des Rechenzentrums wird vor und nach der Einrichtung des Diensts auf der Seite Einstellungen für Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ) angezeigt. Wenn Sie lieber einen anderen rechenzentrumsstandort verwenden möchten, wählen Sie **need help?** im Microsoft 365 Security Center aus, um den Microsoft-Support zu kontaktieren.

## <a name="where-can-i-access-microsoft-365-defender"></a>Wo kann ich auf Microsoft 365 Defender zugreifen?

Microsoft 365 Defender steht im Microsoft 365 Security Center zur Verfügung. Um zum Sicherheitscenter zu wechseln, navigieren Sie zur URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Welche Berechtigungen benötige ich für den Zugriff auf Microsoft 365 Defender im Microsoft 365 Security Center?

Konten, denen die folgenden Azure Active Directory (AD)-Rollen zugewiesen sind, können auf Microsoft 365 Defender-Funktionen und-Daten zugreifen:

- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator
- Globaler Leser
- Sicherheitsleseberechtigter

>[!NOTE]
>Rollenbasierte Zugriffssteuerungseinstellungen in Microsoft Defender für Endpoint beeinflussen den Zugriff auf Daten. Weitere Informationen finden Sie unter [Managing Access to Microsoft 365 Defender](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>In welcher Zeitzone wird Microsoft 365 Defender standardmäßig verwendet?
Standardmäßig zeigt Microsoft 365 Defender Zeit Informationen in der UTC-Zeitzone an. Sie können diese Einstellung so ändern, dass Sie Ihre lokale Zeitzone verwendet. [Informationen zum Festlegen der Zeitzone](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Wie kann ich neue Features von Microsoft 365 Defender und Benutzeroberflächen Updates erfahren?

Microsoft stellt regelmäßig Informationen über die verschiedenen Kanäle bereit, einschließlich:

- Das [Nachrichtencenter](../../admin/manage/message-center.md) im Microsoft 365 Admin Center
- Blogposts in der [Microsoft 365 Security & Compliance Tech-Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Holen Sie sich die neuesten öffentlich verfügbaren Benutzeroberflächen, indem Sie die [Vorschaufunktionen](preview.md)aktivieren.

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Ist Microsoft 365 Defender für US Government Community Cloud (gcc) oder gcc High verfügbar?
Zurzeit ist Microsoft Threat Protection dafür nicht verfügbar.

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft 365 Defender (Übersicht)](microsoft-threat-protection.md)
- [Aktivieren Sie Microsoft 365 Defender](mtp-enable.md).
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Vorschaufeatures aktivieren](preview.md)
