---
title: Aufrufen des Info-Centers zum Anzeigen und Genehmigen der Aufgaben für die automatisierte Untersuchung und Wartung
description: Verwenden Sie das Info-Center, um Details zur automatisierten Untersuchung und ausstehenden Genehmigungsaktionen anzuzeigen.
keywords: Info-Center, Bedrohungsschutz, Untersuchung, Warnung, Ausstehend, automatisiert, Erkennung
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.openlocfilehash: aa9f433bc60949aa625d9346421b025121347a2c
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683319"
---
# <a name="the-action-center"></a>Das Info-Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Verwenden Sie das Action Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), um die Ergebnisse von aktuellen und vergangenen Untersuchungen in den Geräten und Postfächern Ihrer Organisation anzuzeigen. Je nach Art der Bedrohung und dem daraus resultierenden Urteil können [Korrekturaktionen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) automatisch oder nach Genehmigung durch das Sicherheits Betriebsteam Ihrer Organisation ausgeführt werden. Alle Wartungsaktionen – unabhängig davon, ob eine Genehmigung aussteht oder diese bereits genehmigt wurden – werden im Info-Center zusammengefasst. 

![Info-Center](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Eine einzige Oberfläche

Das Info-Center bietet eine einzige Oberfläche für folgende Aufgaben:
- Genehmigen ausstehender Wartungsaktionen
- Anzeigen eines Überwachungsprotokolls von bereits genehmigten Wartungsaktionen und
- Überprüfen abgeschlossener Wartungsaktionen

Ihr Sicherheits Betriebsteam kann effektiver und effizienter arbeiten, da das Action Center eine umfassende Ansicht von Microsoft 365 Defender bei der Arbeit bietet.

## <a name="go-to-the-action-center"></a>Aufrufen des Info-Centers

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

3. Im Wartungscenter werden zwei Registerkarten angezeigt: **Ausstehend** und **Verlauf**.

    - Auf der Registerkarte **Ausstehend** werden Untersuchungen aufgeführt, die von einer Person in Ihrem Sicherheitsteam überprüft und genehmigt werden müssen. Überprüfen Sie alle ausstehenden Elemente, die hier angezeigt werden, und ergreifen Sie entsprechende Maßnahmen.

    - Auf der Registerkarte **Verlauf** werden frühere Untersuchungen und Wartungsaktionen aufgeführt, die automatisch ausgeführt wurden. Sie können Daten für den vergangenen Tag, die letzte Woche, den letzten Monat oder die letzten sechs Monate anzeigen.

4. Wenn nur bestimmte Spalten angezeigt werden sollen, wählen Sie **Spalten anpassen** aus.<br/>![Action Center in Microsoft 365 Defender](../../media/mtp-action-center.png)

5. Wählen Sie ein Element in der Liste aus, um weitere Details zu einer Untersuchung anzuzeigen. Die Untersuchungsdetailansicht wird geöffnet.<br/>![Untersuchungsdetails](../../media/mtp-air-investdetails.png)

    - Wenn sich die Untersuchung auf e-Mail-Inhalte bezieht (beispielsweise die Entität ist ein Postfach), werden Ermittlungs Details im Security & Compliance Center ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ) geöffnet. 

    - Wenn es bei der Untersuchung um ein Gerät geht, werden die Untersuchungsdetails im Security Center ([https://security.microsoft.com](https://security.microsoft.com)) geöffnet. 

> [!TIP]
> Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft 365 Defender etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen! Weitere Informationen finden Sie unter [How to Report false positives/negatives in Automated Investigation and Response (Air) Capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).

## <a name="available-actions"></a>Verfügbare Aktionen

Wenn Korrekturaktionen ausgeführt werden, werden Sie auf der Registerkarte **Verlauf** im Wartungscenter aufgeführt. Solche Aktionen umfassen Folgendes:

- Ermittlungs Paket sammeln 
- Gerät isolieren (diese Aktion kann rückgängig gemacht werden) 
- Extern-Computer 
- Freigabecode Ausführung 
- Freigabe aus Quarantäne 
- Anforderungs Beispiel 
- Einschränken der Codeausführung (diese Aktion kann rückgängig gemacht werden) 
- Ausführen des Antivirus-Scans 
- Beenden und isolieren 

> [!NOTE]
> Zusätzlich zu den automatisch ausgeführten Korrekturaktionen kann Ihr Sicherheits Betriebsteam manuelle Aktionen zur Behebung erkannter Bedrohungen durchführen. Weitere Informationen zu automatischen und manuellen Korrekturaktionen finden Sie unter [Korrekturaktionen](mtp-remediation-actions.md).

## <a name="action-source"></a>Aktions Quelle

(**Neu!**) Wie Sie wissen, bringt Microsoft 365 Defender automatisierte Ermittlungs-und Antwortfunktionen in mehreren Diensten zusammen, beispielsweise [Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) und [Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). Das neue und verbesserte Action Center enthält jetzt eine **Aktions Quell** Spalte, in der Sie erfahren, woher jede Korrekturaktion stammt. 

In der folgenden Tabelle werden mögliche Werte der **Aktions Quelle** beschrieben:

| Wert der Aktions Quelle | Beschreibung |
|:-----|:---|
| **Manuelle Geräte Aktion** | Eine manuelle Aktion, die auf einem Gerät ausgeführt wird. Beispiele hierfür sind [Geräte Isolierung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) oder [Dateiquarantäne](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files). |
| **Manuelle e-Mail-Aktion** | Eine manuelle Aktion, die auf e-Mail ausgeführt wird. Ein Beispiel ist das Löschen von e-Mail-Nachrichten oder [das Korrigieren einer e-Mail-Nachricht](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365). |
| **Automatische Geräte Aktion** | Eine automatisierte Aktion, die für eine Entität ausgeführt wird, beispielsweise eine Datei oder ein Prozess. Beispiele für automatisierte Aktionen sind das Senden einer Datei in den Quarantänebereich, das Beenden eines Prozesses und das Entfernen eines Registrierungsschlüssels. (Weitere Informationen finden Sie unter [Korrekturaktionen in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions).) |
| **Automatisierte e-Mail-Aktion** | Eine automatisierte Aktion, die für e-Mail-Inhalte wie eine e-Mail-Nachricht, eine Anlage oder eine URL ausgeführt wird. Beispiele für automatisierte Aktionen sind Soft-Löschen von e-Mail-Nachrichten, Blockieren von URLs und Deaktivieren der externen e-Mail-Weiterleitung. (Weitere Informationen finden Sie unter [Korrekturaktionen in Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions).) |
| **Erweiterte Jagdaktion** | Aktionen, die auf Geräten oder e-Mails mit [Erweiterter Suche](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)durchgeführt werden. |
| **Explorer-Aktion** | Aktionen, die für e-Mail-Inhalte mit [Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)ausgeführt werden. |
| **Manuelle Live-Antwort-Aktion** | Auf einem Gerät ausgeführte Aktionen mit [Live-Antwort](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response). Beispiele hierfür sind das Löschen einer Datei, das Beenden eines Prozesses und das Entfernen eines geplanten Tasks. |
| **Live-Antwortaktion** | Auf einem Gerät mit [Microsoft Defender für Endpunkt-APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)ausgeführte Aktionen. Beispiele für Aktionen sind das Isolieren eines Geräts, das Ausführen eines Antivirus-Scans und das erhalten von Informationen zu einer Datei. |

## <a name="required-permissions-for-action-center-tasks"></a>Erforderliche Berechtigungen für Info-Center-Aufgaben

Um ausstehende Aktionen im Info-Center zu genehmigen oder abzulehnen, müssen Sie über die Berechtigungen verfügen, die in der folgenden Tabelle aufgeführt sind:

|Wartungsaktion |Erforderliche Rollen und Berechtigungen |
|--|----|
|Microsoft Defender für die Endpunkt Sanierung (Geräte) |Sicherheitsadministratorrolle in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- oder ---<br/>In Microsoft Defender für Endpoint zugewiesene Rolle "aktive Behebungsaktionen" <br/> <br/> Weitere Informationen hierzu finden Sie in den folgenden Ressourcen: <br/>- [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung (Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Microsoft Defender für Office 365 Sanierung (Office-Inhalte und e-Mail)  |Sicherheitsadministratorrolle in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- und --- <br/>Dem Security & Compliance Center zugewiesene Rolle "Search and Purge" ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**Wichtig**: Wenn Sie die Sicherheits Administrator Rolle nur im Security & Compliance Center zugewiesen haben, können Sie nicht auf das Action Center oder die Microsoft 365 Defender-Funktionen zugreifen. Ihnen muss die Sicherheitsadministratorrolle in Azure Active Directory oder im Microsoft 365 Admin Center zugewiesen sein. <br/><br/>Weitere Informationen hierzu finden Sie in den folgenden Ressourcen: <br/>- [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Benutzer, denen in Azure Active Directory die Rolle Globaler Administrator zugewiesen ist, können alle ausstehenden Aktionen im Info-Center genehmigen oder ablehnen. Als bewährte Methode sollte Ihre Organisation jedoch die Anzahl der Personen einschränken, denen die Rolle des globalen Administrators zugewiesen ist. Es wird empfohlen, die oben aufgeführten Rollen Sicherheitsadministrator, Aktive Wartungsaktionen und Suchen und Löschen für Info-Center-Berechtigungen zu verwenden.

## <a name="next-steps"></a>Nächste Schritte 

- [Genehmigen oder Ablehnen ausstehender Aktionen im Anschluss an eine automatisierte Untersuchung](mtp-autoir-actions.md)
- [Anzeigen der Ergebnisse einer automatischen Untersuchung](mtp-autoir-results.md)

