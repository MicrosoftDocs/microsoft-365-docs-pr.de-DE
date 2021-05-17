---
title: Aufrufen des Info-Centers zum Anzeigen und Genehmigen der Aufgaben für die automatisierte Untersuchung und Wartung
description: Verwenden Sie das Info-Center, um Details zur automatisierten Untersuchung und ausstehenden Genehmigungsaktionen anzuzeigen.
keywords: Info-Center, Bedrohungsschutz, Untersuchung, Warnung, Ausstehend, automatisiert, Erkennung
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7bea9a1632e7a9ed9d394c2c411123d0601a9397
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274580"
---
# <a name="the-action-center"></a>Das Info-Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Das Aktionscenter bietet eine "einzelne Fensterausschnitt"-Erfahrung für Vorfall- und Warnungsaufgaben, z. B.:

- Genehmigen ausstehender Korrekturaktionen.
- Anzeigen eines Überwachungsprotokolls bereits genehmigter Korrekturaktionen.
- Überprüfen abgeschlossener Wartungsaktionen

Da das Action Center eine umfassende Ansicht von Microsoft 365 defender at work bietet, kann Ihr Sicherheitsteam effektiver und effizienter arbeiten.

## <a name="the-unified-action-center"></a>Das einheitliche Aktionscenter

Das einheitliche Aktionscenter ( ) listet ausstehende und abgeschlossene Korrekturaktionen für Ihre Geräte, E-Mails & Inhalte der Zusammenarbeit und Identitäten an einem [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) Ort auf.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Unified Action Center in Microsoft 365 Defender":::

Beispiel: 

- Wenn Sie zuvor das Office 365 Security & Compliance Center ( ) verwendet haben, testen Sie das einheitliche [https://protection.office.com](https://protection.office.com) Action Center im Microsoft 365 Security Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Wenn Sie das Aktionscenter im Microsoft Defender Security Center ( ) verwendet haben, versuchen Sie es mit dem [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) einheitlichen Aktionscenter im Microsoft 365 Security Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Wenn Sie bereits das Microsoft 365 Security Center ( ) verwendet haben, werden verschiedene Verbesserungen [https://security.microsoft.com](https://security.microsoft.com) im Action Center ( ) [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) angezeigt.

Im einheitlichen Aktionscenter werden Korrekturaktionen in Defender for Endpoint und Defender for Office 365. Es definiert eine gemeinsame Sprache für alle Korrekturaktionen und bietet eine einheitliche Untersuchungserfahrung. Ihr Sicherheitsbetriebsteam verfügt über eine "einzelne Glasfenster"-Erfahrung zum Anzeigen und Verwalten von Korrekturaktionen.  

Sie können das einheitliche Aktionscenter verwenden, wenn Sie über entsprechende Berechtigungen und mindestens eines der folgenden Abonnements verfügen:

- [Defender für Endpunkt](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> Weitere Informationen finden Sie unter [Requirements](./prerequisites.md).

## <a name="using-the-action-center"></a>Verwenden des Aktionscenters

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 
2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

Wenn Sie das Aktionscenter besuchen, werden zwei Registerkarten angezeigt: **Ausstehende Aktionen** und **Verlauf**. In der folgenden Tabelle wird zusammengefasst, was auf den einzelnen Registerkarten angezeigt wird:

|Registerkarte  |Beschreibung  |
|---------|---------|
|**Ausstehend**     | Zeigt eine Liste der Aktionen an, die Aufmerksamkeit erfordern. Sie können Aktionen gleichzeitig genehmigen oder ablehnen oder mehrere Aktionen auswählen, wenn sie denselben Aktionstyp haben (z. B. Quarantänedatei). <p>**TIPP:** Achten Sie darauf, ausstehende Aktionen so schnell wie möglich zu überprüfen und zu genehmigen (oder abzulehnen), damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden können.       |
|**Verlauf**     | Dient als Überwachungsprotokoll für Aktionen, die ergriffen wurden, z. B.: <br/>– Abhilfemaßnahmen, die als Ergebnis automatisierter Untersuchungen ergriffen wurden <br/>– Korrekturaktionen, die für verdächtige oder schädliche E-Mail-Nachrichten, Dateien oder URLs ergriffen wurden<br/>– Korrekturaktionen, die vom Sicherheitsbetriebsteam genehmigt wurden <br/>– Befehle, die ausgeführt wurden, und Behebungsaktionen, die während Liveantwortsitzungen angewendet wurden<br/>– Abhilfemaßnahmen, die von Ihrem Antivirenschutz ausgeführt wurden <p>Bietet eine Möglichkeit, bestimmte Aktionen rückgängig zu machen (siehe [Rückgängig gemachte Aktionen](m365d-autoir-actions.md#undo-completed-actions)).        |

Sie können Daten im Aktionscenter anpassen, sortieren, filtern und exportieren.

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="Mit dem Aktionscenter können Sie Ihre Aktionsliste sortieren, filtern und anpassen.":::

- Wählen Sie eine Spaltenüberschrift aus, um Elemente in aufsteigender oder absteigender Reihenfolge zu sortieren.
- Verwenden Sie den Zeitraumfilter, um Daten für den letzten Tag, die letzte Woche, 30 Tage oder 6 Monate anzeigen zu können.
- Wählen Sie die Spalten aus, die Sie anzeigen möchten.
- Geben Sie an, wie viele Elemente auf jeder Datenseite enthalten sein müssen.
- Verwenden Sie Filter, um nur die Elemente zu sehen, die Sie anzeigen möchten.
- Wählen **Sie Exportieren** aus, um Ergebnisse in eine .csv exportieren.

## <a name="actions-tracked-in-the-action-center"></a>Im Aktionscenter nachverfolgte Aktionen

Alle Aktionen, unabhängig davon, ob sie noch ausstehen oder bereits ergriffen wurden, werden im Aktionscenter nachverfolgt. Folgende Aktionen sind verfügbar:

- Untersuchungspaket sammeln 
- Gerät isolieren (diese Aktion kann rückgängig gemacht werden) 
- Offboarding des Computers 
- Ausführung von Releasecode 
- Veröffentlichung aus der Quarantäne 
- Anforderungsbeispiel 
- Einschränken der Codeausführung (diese Aktion kann rückgängig gemacht werden) 
- Antivirusscan ausführen 
- Beenden und Isolieren 

Neben Denkmaßnahmen, die automatisch als Ergebnis automatisierter Untersuchungen ausgeführt [werden,](m365d-autoir.md)verfolgt das Action Center auch Aktionen, die Ihr Sicherheitsteam zur Behebung erkannter Bedrohungen ergriffen hat, sowie Aktionen, die als Ergebnis von Bedrohungsschutzfeatures in Microsoft 365 Defender ausgeführt wurden. Weitere Informationen zu automatischen und manuellen Korrekturaktionen finden Sie unter [Remediation actions](m365d-remediation-actions.md).

## <a name="viewing-action-source-details"></a>Anzeigen von Details zur Aktionsquelle

(**NEU!**) Das verbesserte Aktionscenter enthält jetzt eine **Aktionsquellenspalte,** in der Sie erfahren, woher die einzelnen Aktionen stammen. In der folgenden Tabelle werden mögliche **Aktionsquellenwerte** beschrieben:

| Aktionsquellenwert | Beschreibung |
|:-----|:---|
| **Manuelle Geräteaktion** | Eine manuelle Aktion auf einem Gerät. Beispiele hierfür [sind Geräteisolation](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) oder [Dateiquarantäne.](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files) |
| **Manuelle E-Mail-Aktion** | Eine manuelle Aktion für E-Mails. Ein Beispiel umfasst das Soft-Deleting von E-Mail-Nachrichten oder [das Löschen einer E-Mail-Nachricht.](../office-365-security/remediate-malicious-email-delivered-office-365.md) |
| **Automatische Geräteaktion** | Eine automatisierte Aktion für eine Entität, z. B. eine Datei oder einen Prozess. Beispiele für automatisierte Aktionen sind das Senden einer Datei in quarantäne, das Beenden eines Prozesses und das Entfernen eines Registrierungsschlüssels. (Siehe [Korrekturaktionen in Microsoft Defender for Endpoint](../defender-endpoint/manage-auto-investigation.md#remediation-actions).) |
| **Automatisierte E-Mail-Aktion** | Eine automatisierte Aktion für E-Mail-Inhalte, z. B. eine E-Mail-Nachricht, anlage oder URL. Beispiele für automatisierte Aktionen sind das soft-deleting von E-Mail-Nachrichten, das Blockieren von URLs und das Deaktivieren der externen E-Mail-Weiterleitung. (Weitere [Informationen finden Sie unter Korrekturaktionen in Microsoft Defender Office 365](../office-365-security/air-remediation-actions.md).) |
| **Erweiterte Suche** | Aktionen auf Geräten oder E-Mails mit [erweiterter Suche](./advanced-hunting-overview.md). |
| **Explorer-Aktion** | Aktionen für E-Mail-Inhalte mit [Explorer](../office-365-security/threat-explorer.md). |
| **Manuelle Liveantwortaktion** | Aktionen, die auf einem Gerät mit [Liveantwort ergriffen werden.](../defender-endpoint/live-response.md) Beispiele hierfür sind das Löschen einer Datei, das Beenden eines Prozesses und das Entfernen einer geplanten Aufgabe. |
| **Liveantwortaktion** | Aktionen auf einem Gerät mit [Microsoft Defender für Endpunkt-APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis). Beispiele für Aktionen sind das Isolieren eines Geräts, das Ausführen eines Antivirenscans und das Abrufen von Informationen zu einer Datei. |

## <a name="required-permissions-for-action-center-tasks"></a>Erforderliche Berechtigungen für Info-Center-Aufgaben

Zum Ausführen von Aufgaben, z. B. genehmigen oder ablehnen ausstehende Aktionen im Aktionscenter, müssen Ihnen berechtigungen zugewiesen werden, wie in der folgenden Tabelle aufgeführt:

|Wartungsaktion |Erforderliche Rollen und Berechtigungen |
|--|----|
|Microsoft Defender for Endpoint Remediation (Devices) |**Sicherheitsadministratorrolle,** die entweder in Azure Active Directory (Azure AD) ( ) oder im [https://portal.azure.com](https://portal.azure.com) Microsoft 365 Admin Center ( ) zugewiesen ist [https://admin.microsoft.com](https://admin.microsoft.com)<br/>--- oder ---<br/>In Microsoft Defender for Endpoint **zugewiesene** Rolle für aktive Korrekturaktionen <br/> <br/> Weitere Informationen hierzu finden Sie in den folgenden Ressourcen: <br/>- [Administratorrolleberechtigungen in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung (Microsoft Defender for Endpoint)](../defender-endpoint/user-roles.md)  |
|Microsoft Defender for Office 365 remediation (Office content and email)  |**Sicherheitsadministratorrolle,** die entweder in Azure AD ( ) oder [https://portal.azure.com](https://portal.azure.com) im Microsoft 365 Admin Center ( ) zugewiesen ist [https://admin.microsoft.com](https://admin.microsoft.com)<br/>--- und --- <br/>**Such- und Bereinigungsrolle** im Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**WICHTIG**: Wenn  Die Rolle "Sicherheitsadministrator" nur im Office 365 Security & Compliance Center ( ) zugewiesen ist, können Sie nicht auf das Action Center oder die [https://protection.office.com](https://protection.office.com) Microsoft 365 Defender-Funktionen zugreifen. Die Rolle **"Sicherheitsadministrator"** muss in Azure AD oder im Microsoft 365 zugewiesen sein. <br/><br/>Weitere Informationen hierzu finden Sie in den folgenden Ressourcen: <br/>- [Administratorrolleberechtigungen in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Berechtigungen im Security & Compliance Center](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> Benutzer, denen die **Rolle "Globaler Administrator"** in Azure AD zugewiesen ist, können alle ausstehenden Aktionen im Aktionscenter genehmigen oder ablehnen. Als bewährte Methode sollte Ihre Organisation jedoch die Anzahl der Personen begrenzen, denen die Rolle **"Globaler Administrator"** zugewiesen ist. Es wird empfohlen, die in der vorherigen Tabelle aufgeführten Rollen **"Sicherheitsadministrator",**"Aktive Korrekturmaßnahmen" und "Suchen und Löschen" für Berechtigungen im Aktionscenter zu verwenden.  

## <a name="next-step"></a>Nächster Schritt 

- [Anzeigen und Verwalten von Korrekturaktionen](m365d-autoir-actions.md)
