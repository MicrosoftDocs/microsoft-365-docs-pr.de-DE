---
title: Aufrufen des Info-Centers zum Anzeigen und Genehmigen der Aufgaben für die automatisierte Untersuchung und Wartung
description: Verwenden sie das Info-Center, um Details zur automatisierten Untersuchung anzuzeigen und ausstehende Aktionen zu genehmigen.
keywords: Info-Center, Bedrohungsschutz, Untersuchung, Warnung, ausstehend, automatisiert, Erkennung
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
ms.openlocfilehash: ee075f34087d28fc9326d408622d05f363bba768
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022585"
---
# <a name="the-action-center"></a>Das Info-Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Das Info-Center bietet eine "einzelne Fenster"-Oberfläche für Vorfall- und Warnungsaufgaben wie:

- Genehmigen ausstehender Korrekturaktionen.
- Anzeigen eines Überwachungsprotokolls von bereits genehmigten Korrekturaktionen.
- Überprüfen abgeschlossener Wartungsaktionen

Da das Info-Center eine umfassende Übersicht über Microsoft 365 Defender bei der Arbeit bietet, kann Ihr Sicherheitsteam effektiver und effizienter arbeiten.

## <a name="the-unified-action-center"></a>Das einheitliche Info-Center

Das einheitliche Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) listet ausstehende und abgeschlossene Abhilfemaßnahmen für Ihre Geräte, E-Mail-& Inhalte für die Zusammenarbeit und Identitäten an einem Ort auf.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Einheitliches Info-Center in Microsoft 365 Defender":::

Beispiel: 

- Wenn Sie zuvor das Office 365 Security & Compliance Center ( ) verwendet [https://protection.office.com](https://protection.office.com) haben, testen Sie das einheitliche Info-Center im Microsoft 365 Defender-Portal ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Wenn Sie das Info-Center im Microsoft Defender Security Center ( ) verwendet [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) haben, versuchen Sie es mit dem einheitlichen Info-Center im Microsoft 365 Defender-Portal ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Wenn Sie bereits das Microsoft 365 Defender-Portal ( ) verwendet haben, [https://security.microsoft.com](https://security.microsoft.com) sehen Sie mehrere Verbesserungen im Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).

Das einheitliche Info-Center vereint Korrekturaktionen in Defender für Endpunkt und Defender für Office 365. Es definiert eine gemeinsame Sprache für alle Korrekturmaßnahmen und bietet eine einheitliche Untersuchungserfahrung. Ihr Sicherheitsteam verfügt über einen "einzigen Bereich" zum Anzeigen und Verwalten von Abhilfemaßnahmen.  

Sie können das einheitliche Info-Center verwenden, wenn Sie über die entsprechenden Berechtigungen und eines oder mehrere der folgenden Abonnements verfügen:

- [Defender für Endpunkt](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> Weitere Informationen finden Sie unter ["Anforderungen".](./prerequisites.md)

## <a name="using-the-action-center"></a>Verwenden des Info-Centers

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 
2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

Wenn Sie das Info-Center besuchen, werden zwei Registerkarten angezeigt: **ausstehende Aktionen** und **Verlauf.** In der folgenden Tabelle wird zusammengefasst, was auf den einzelnen Registerkarten angezeigt wird:

|Registerkarte  |Beschreibung  |
|---------|---------|
|**Ausstehend**     | Zeigt eine Liste der Aktionen an, die Aufmerksamkeit erfordern. Sie können Aktionen einzeln genehmigen oder ablehnen oder mehrere Aktionen auswählen, wenn sie den gleichen Aktionstyp haben (z. B. Quarantänedatei). <p>**TIPP:** Stellen Sie sicher, dass ausstehende Aktionen so schnell wie möglich überprüft und genehmigt (oder abgelehnt) werden, damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden können.       |
|**Verlauf**     | Dient als Überwachungsprotokoll für ausgeführte Aktionen, z. B.: <br/>– Korrekturmaßnahmen, die als Ergebnis automatisierter Untersuchungen durchgeführt wurden <br/>– Maßnahmen zur Behebung verdächtiger oder bösartiger E-Mail-Nachrichten, Dateien oder URLs<br/>– Abhilfemaßnahmen, die von Ihrem Sicherheitsteam genehmigt wurden <br/>– Befehle, die ausgeführt wurden, und Korrekturaktionen, die während der Live Response-Sitzungen angewendet wurden<br/>– Abhilfemaßnahmen, die von Ihrem Antivirenschutz durchgeführt wurden <p>Bietet eine Möglichkeit, bestimmte Aktionen rückgängig zu machen (siehe [Abgeschlossene Aktionen rückgängig machen).](m365d-autoir-actions.md#undo-completed-actions)        |

Sie können Daten im Info-Center anpassen, sortieren, filtern und exportieren.

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="Im Info-Center können Sie Ihre Aktionsliste sortieren, filtern und anpassen.":::

- Wählen Sie eine Spaltenüberschrift aus, um Elemente in aufsteigender oder absteigender Reihenfolge zu sortieren.
- Verwenden Sie den Zeitraumfilter, um Daten für den letzten Tag, die letzte Woche, 30 Tage oder 6 Monate anzuzeigen.
- Wählen Sie die Spalten aus, die Sie anzeigen möchten.
- Geben Sie an, wie viele Elemente auf jeder Datenseite enthalten sein sollen.
- Verwenden Sie Filter, um nur die Elemente anzuzeigen, die Sie sehen möchten.
- Wählen Sie **"Exportieren"** aus, um Ergebnisse in eine .csv Datei zu exportieren.

## <a name="actions-tracked-in-the-action-center"></a>Im Info-Center nachverfolgte Aktionen

Alle Aktionen, unabhängig davon, ob die Genehmigung aussteht oder bereits ausgeführt wurde, werden im Info-Center nachverfolgt. Zu den verfügbaren Aktionen gehören:

- Untersuchungspaket sammeln 
- Gerät isolieren (diese Aktion kann rückgängig machen) 
- Offboarding des Computers 
- Freigeben der Codeausführung 
- Aus Quarantäne freigeben 
- Anforderungsbeispiel 
- Einschränken der Codeausführung (diese Aktion kann rückgängig machen) 
- Antivirusscan ausführen 
- Beenden und Isolieren 

Zusätzlich zu Korrekturmaßnahmen, die automatisch als Ergebnis [automatisierter Untersuchungen](m365d-autoir.md)durchgeführt werden, verfolgt das Info-Center auch Aktionen, die Ihr Sicherheitsteam ausgeführt hat, um erkannte Bedrohungen zu adressieren, und Aktionen, die als Ergebnis von Bedrohungsschutzfeatures in Microsoft 365 Defender ausgeführt wurden. Weitere Informationen zu automatischen und manuellen Wartungsaktionen finden Sie unter ["Wartungsaktionen".](m365d-remediation-actions.md)

## <a name="viewing-action-source-details"></a>Anzeigen von Details zur Aktionsquelle

(**NEU!**) Das verbesserte Info-Center enthält jetzt eine **Quellspalte für Aktionen,** die Ihnen mitteilt, woher jede Aktion stammt. In der folgenden Tabelle werden mögliche **Aktionsquellwerte** beschrieben:

| Aktionsquellwert | Beschreibung |
|:-----|:---|
| **Manuelle Geräteaktion** | Eine manuelle Aktion, die auf einem Gerät ausgeführt wird. Beispiele sind [Geräteisolation](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) oder [Dateiquarantäne.](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files) |
| **Manuelle E-Mail-Aktion** | Eine manuelle Aktion für E-Mails. Ein Beispiel umfasst das vorläufige Löschen von E-Mail-Nachrichten oder [das Korrigieren einer E-Mail-Nachricht.](../office-365-security/remediate-malicious-email-delivered-office-365.md) |
| **Automatisierte Geräteaktion** | Eine automatisierte Aktion für eine Entität, z. B. eine Datei oder einen Prozess. Beispiele für automatisierte Aktionen sind das Senden einer Datei in die Quarantäne, das Beenden eines Prozesses und das Entfernen eines Registrierungsschlüssels. (Siehe ["Wartungsaktionen" in Microsoft Defender für Endpunkt.)](../defender-endpoint/manage-auto-investigation.md#remediation-actions) |
| **Automatisierte E-Mail-Aktion** | Eine automatisierte Aktion für E-Mail-Inhalte, z. B. eine E-Mail-Nachricht, eine Anlage oder eine URL. Beispiele für automatisierte Aktionen sind das vorläufige Löschen von E-Mail-Nachrichten, das Blockieren von URLs und das Deaktivieren der externen E-Mail-Weiterleitung. (Informationen zum Office 365 finden [Sie unter "Wartungsaktionen in Microsoft](../office-365-security/air-remediation-actions.md)Defender".) |
| **Erweiterte Suchaktion** | Aktionen, die auf Geräten oder E-Mails mit [erweiterter Suche](./advanced-hunting-overview.md)ausgeführt werden. |
| **Explorer-Aktion** | Aktionen, die für E-Mail-Inhalte mit [Explorer](../office-365-security/threat-explorer.md)ausgeführt werden. |
| **Manuelle Live-Antwortaktion** | Aktionen, die auf einem Gerät mit [Liveantwort](../defender-endpoint/live-response.md)ausgeführt werden. Beispiele hierfür sind das Löschen einer Datei, das Beenden eines Prozesses und das Entfernen einer geplanten Aufgabe. |
| **Live-Antwortaktion** | Aktionen, die auf einem Gerät mit [Microsoft Defender für Endpunkt-APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)ausgeführt werden. Beispiele für Aktionen sind das Isolieren eines Geräts, das Ausführen eines Antivirenscans und das Abrufen von Informationen zu einer Datei. |

## <a name="required-permissions-for-action-center-tasks"></a>Erforderliche Berechtigungen für Info-Center-Aufgaben

Zum Ausführen von Aufgaben, z. B. das Genehmigen oder Ablehnen ausstehender Aktionen im Info-Center, müssen Ihnen berechtigungen zugewiesen sein, wie in der folgenden Tabelle aufgeführt:

|Wartungsaktion |Erforderliche Rollen und Berechtigungen |
|--|----|
|Microsoft Defender für Endpunkt-Wartung (Geräte) |**Sicherheitsadministratorrolle,** die entweder in Azure Active Directory (Azure AD) ( [https://portal.azure.com](https://portal.azure.com) ) oder der Microsoft 365 Admin Center ( ) zugewiesen ist [https://admin.microsoft.com](https://admin.microsoft.com)<br/>--- oder ---<br/>**Rolle "Aktive Abhilfemaßnahmen"** in Microsoft Defender für Endpunkt zugewiesen <br/> <br/> Weitere Informationen hierzu finden Sie in den folgenden Ressourcen: <br/>- [Administratorrollenberechtigungen in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung (Microsoft Defender für Endpunkt)](../defender-endpoint/user-roles.md)  |
|Korrektur von Microsoft Defender für Office 365 (Office Inhalt und E-Mail)  |**Sicherheitsadministratorrolle,** die entweder in Azure AD ( [https://portal.azure.com](https://portal.azure.com) ) oder der Microsoft 365 Admin Center ( ) zugewiesen ist [https://admin.microsoft.com](https://admin.microsoft.com)<br/>--- und --- <br/>Im Security & Compliance Center zugewiesene **Rolle "Suchen und Löschen"** ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**WICHTIG:** Wenn Ihnen die **Rolle "Sicherheitsadministrator"** nur im Office 365 Security & Compliance Center ( ) zugewiesen [https://protection.office.com](https://protection.office.com) ist, können Sie nicht auf das Info-Center oder Microsoft 365 Defender-Funktionen zugreifen. Ihnen muss die **Rolle "Sicherheitsadministrator"** in Azure AD oder dem Microsoft 365 Admin Center zugewiesen sein. <br/><br/>Weitere Informationen hierzu finden Sie in den folgenden Ressourcen: <br/>- [Administratorrollenberechtigungen in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Berechtigungen im Security & Compliance Center](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> Benutzer, denen die Rolle **"Globaler Administrator"** in Azure AD zugewiesen ist, können alle ausstehenden Aktionen im Info-Center genehmigen oder ablehnen. Als bewährte Methode sollte Ihre Organisation jedoch die Anzahl der Personen einschränken, denen die Rolle **"Globaler Administrator"** zugewiesen ist. Wir empfehlen die Verwendung der Rollen **"Sicherheitsadministrator",** **"Aktive Abhilfemaßnahmen"** und **"Suchen und Löschen",** die in der vorherigen Tabelle für Info-Center-Berechtigungen aufgeführt sind.

## <a name="next-step"></a>Nächster Schritt 

- [Anzeigen und Genehmigen von Korrekturaktionen](m365d-autoir-actions.md)
