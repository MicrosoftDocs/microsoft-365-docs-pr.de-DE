---
title: Aktivieren von Microsoft 365 Defender im Microsoft 365 Security Center
description: In diesem Artikel erfahren Sie, wie Sie Microsoft 365 Defender aktivieren und ihre Sicherheitsvorfälle und-Antworten integrieren.
keywords: Erste Schritte, Aktivieren von MTP, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenz Berechtigung, Seite "Einstellungen"
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
ms.openlocfilehash: b5bb99ed4b8cee7ea920679e20f69c7a0e002d26
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843636"
---
# <a name="turn-on-microsoft-365-defender"></a>Aktivieren von Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) vereinigt ihren Vorfall Antwortprozess durch die Integration wichtiger Funktionen in Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity. Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.

Microsoft 365 Defender aktiviert automatisch, wenn berechtigte Kunden mit den erforderlichen Berechtigungen Microsoft 365 Security Center besuchen. Lesen Sie diesen Artikel, um die verschiedenen Voraussetzungen und die Vorgehensweise von Microsoft 365 Defender zu verstehen.

## <a name="check-license-eligibility-and-required-permissions"></a>Überprüfen der Lizenz Berechtigung und der erforderlichen Berechtigungen
Eine Lizenz für ein Microsoft 365-Sicherheitsprodukt berechtigt Sie im Allgemeinen zur Verwendung von Microsoft 365 Defender im Microsoft 365 Security Center ohne zusätzliche Lizenzierungskosten. Es wird empfohlen, eine Sicherheitslizenz für Microsoft 365 E5, E5, A5 oder A5 oder eine gültige Kombination von Lizenzen zu erhalten, die Zugriff auf alle unterstützten Dienste bereitstellt.

Ausführliche Lizenzierungsinformationen finden [Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Überprüfen der Rolle
Sie müssen ein **globaler Administrator** oder ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender zu aktivieren. [Anzeigen ihrer Rollen in Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Unterstützte Dienste
Microsoft 365 Defender aggregiert Daten aus den verschiedenen unterstützten Diensten, die Sie bereits bereitgestellt haben. Die Daten werden zentral verarbeitet und gespeichert, um neue Erkenntnisse zu identifizieren und um zentralisierte Antwort Workflows zu ermöglichen. Dies geschieht ohne Beeinträchtigung vorhandener Bereitstellungen, Einstellungen oder Daten, die den integrierten Diensten zugeordnet sind.

Um den besten Schutz zu erhalten und Microsoft 365 Defender zu optimieren, wird empfohlen, alle anwendbaren unterstützten Dienste in Ihrem Netzwerk bereitzustellen. Weitere Informationen finden [Sie unter Deploying supported Services](deploy-supported-services.md).

## <a name="before-starting-the-service"></a>Vor dem Starten des Diensts
Bevor Sie den Dienst aktivieren, zeigt das Microsoft 365 Security Center ( [Security.Microsoft.com](https://security.microsoft.com)) die Seite Microsoft 365 Defender-Einstellungen an, wenn Sie im Navigationsbereich **Vorfälle** , das **Aktionscenter** oder die **Suche** auswählen. Diese Navigationselemente werden nicht angezeigt, wenn Sie nicht berechtigt sind, Microsoft 365 Defender zu verwenden.

![Abbildung der Seite Microsoft 365 Defender-Einstellungen, die angezeigt wird, wenn Microsoft 365 Defender nicht auf ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender-Einstellungen im Microsoft 365 Security Center* aktiviert wurde

## <a name="starting-the-service"></a>Starten des Diensts
Wählen Sie zum Aktivieren von Microsoft 365 Defender einfach **Microsoft 365 Defender aktivieren** aus, und wenden Sie die Änderung an. Sie können auf diese Option auch zugreifen, indem Sie im Navigationsbereich **Einstellungen** ( [Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) auswählen und dann **Microsoft 365 Defender** auswählen.

>[!NOTE]
>Wenn im Navigationsbereich keine **Einstellungen** angezeigt werden oder Sie nicht auf die Seite zugreifen können, überprüfen Sie Ihre Berechtigungen und Lizenzen.

### <a name="data-center-location"></a>Rechenzentrumsstandort
Microsoft 365 Defender speichert und verarbeitet Daten am [gleichen Speicherort, der von Microsoft Defender für Endpoint verwendet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)wird. Wenn Sie nicht über Microsoft Defender für Endpoint verfügen, wird automatisch ein neuer datencenterstandort basierend auf dem Speicherort der aktiven Microsoft 365-Sicherheitsdienste ausgewählt. Der ausgewählte Speicherort des Rechenzentrums wird auf dem Bildschirm angezeigt. 

Wählen Sie **need help aus?** im Microsoft 365 Security Center können Sie sich an den Microsoft-Support wenden, um Microsoft 365 Defender in einem anderen rechenzentrumsstandort zu kontaktieren. 

>[!NOTE]
>Microsoft Defender für Endpoint stellt automatisch Vorkehrungen in den Rechenzentren in der Europäischen Union (EU) bereit, wenn es über Azure Defender * aktiviert wird. Microsoft 365 Defender wird automatisch im gleichen EU-Rechenzentrum für Kunden bereitgestellt, die auf diese Weise einen Defender für Endpoint bereitgestellt haben. 

### <a name="confirm-that-the-service-is-on"></a>Vergewissern Sie sich, dass der Dienst aktiviert ist
Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:

- [Verwalten von Vorfällen](incidents-overview.md)
- Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)
- [Erweiterte Jagd](advanced-hunting-overview.md) Funktionen

![Bild des Microsoft 365 Security Center-Navigationsbereichs mit Microsoft 365 Defender Features ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Security Center mit Incidents Management und anderen Microsoft 365 Defender-Funktionen*

### <a name="getting-microsoft-defender-for-identity-data"></a>Aufrufen von Microsoft Defender für Identitätsdaten
Um Microsoft Defender für Identitätsdaten mit Microsoft 365 Defender freizugeben, stellen Sie sicher, dass Microsoft Cloud App Security und Microsoft Defender for Identity Integration aktiviert ist. Erfahren Sie mehr über [diese Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a>Microsoft 365 Defender deaktivieren
Um die Verwendung von Microsoft 365 Defender zu beenden, wechseln Sie zu **Einstellungen**  >  **Microsoft 365 Defender**  >  **Opt-in/Opt-out** im Microsoft 365 Security Center. Deaktivieren Sie **Microsoft 365 Defender aktivieren** , und wenden Sie die Änderungen an.

Die entsprechenden Features werden aus dem Microsoft 365 Security Center entfernt.

## <a name="get-assistance"></a>Unterstützung erhalten

Wenn Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von Microsoft 365 Defender erhalten möchten, [Lesen Sie die FAQ](mtp-enable-faq.md).

Microsoft-Supportmitarbeiter können Ihnen helfen, den Dienst und die zugehörigen Ressourcen auf Ihrem Mandanten bereitzustellen oder zu entbinden. Um Unterstützung zu erhalten, wählen Sie **need help?** im Microsoft 365 Security Center aus. Wenn Sie sich an den Support wenden, erwähnen Sie Microsoft 365 Defender.

## <a name="related-topics"></a>Verwandte Themen

- [Häufig gestellte Fragen](mtp-enable-faq.md)
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Microsoft 365 Defender (Übersicht)](microsoft-threat-protection.md)
- [Microsoft Defender für Endpoint (Übersicht)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Verteidiger für Office 365 Übersicht](../office-365-security/office-365-atp.md)
- [Übersicht über Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender für die Endpunkt Datenspeicherung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
