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
ms.technology: m365d
ms.openlocfilehash: 45e02e4ce7d5d813cc8215a1f27ed9c415707cb1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930426"
---
# <a name="the-action-center"></a>Das Info-Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Verwenden Sie das Action Center ( ), um die Ergebnisse aktueller und früherer Untersuchungen auf den Geräten und Postfächern Ihrer [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) Organisation zu sehen. Je nach Art der Bedrohung und [](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) der resultierenden Wertung können Korrekturaktionen automatisch oder nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt werden. Alle Wartungsaktionen – unabhängig davon, ob eine Genehmigung aussteht oder diese bereits genehmigt wurden – werden im Info-Center zusammengefasst. 

![Info-Center](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Eine einzige Oberfläche

Das Info-Center bietet eine einzige Oberfläche für folgende Aufgaben:
- Genehmigen ausstehender Wartungsaktionen
- Anzeigen eines Überwachungsprotokolls von bereits genehmigten Wartungsaktionen und
- Überprüfen abgeschlossener Wartungsaktionen

Ihr Sicherheitsteam kann effektiver und effizienter arbeiten, da das Action Center einen umfassenden Überblick über Microsoft 365 Defender bei der Arbeit bietet.

## <a name="go-to-the-action-center"></a>Aufrufen des Info-Centers

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

3. Im Aktionscenter werden zwei Registerkarten angezeigt: **"Ausstehend"** und **"Verlauf".**

    - Auf der Registerkarte **Ausstehend** werden Untersuchungen aufgeführt, die von einer Person in Ihrem Sicherheitsteam überprüft und genehmigt werden müssen. Überprüfen Sie alle ausstehenden Elemente, die hier angezeigt werden, und ergreifen Sie entsprechende Maßnahmen.

    - Auf der Registerkarte **Verlauf** werden frühere Untersuchungen und Wartungsaktionen aufgeführt, die automatisch ausgeführt wurden. Sie können Daten für den vergangenen Tag, die letzte Woche, den letzten Monat oder die letzten sechs Monate anzeigen.

4. Wenn nur bestimmte Spalten angezeigt werden sollen, wählen Sie **Spalten anpassen** aus.<br/>![Action Center in Microsoft 365 Defender](../../media/mtp-action-center.png)

5. Wählen Sie ein Element in der Liste aus, um weitere Details zu einer Untersuchung anzuzeigen. Die Untersuchungsdetailansicht wird geöffnet.<br/>![Untersuchungsdetails](../../media/mtp-air-investdetails.png)

    - Wenn sich die Untersuchung auf E-Mail-Inhalte bezieht (z. B. die Entität ist ein Postfach), werden die Untersuchungsdetails im Security & Compliance Center ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ) geöffnet. 

    - Wenn es bei der Untersuchung um ein Gerät geht, werden die Untersuchungsdetails im Security Center ([https://security.microsoft.com](https://security.microsoft.com)) geöffnet. 

> [!TIP]
> Wenn Sie der Meinung sind, dass etwas von automatisierten Untersuchungs- und Antwortfeatures in Microsoft 365 Defender übersehen oder falsch erkannt wurde, teilen Sie uns dies mit! Erfahren [Sie, wie Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen (AIR) in Microsoft 365 Defender melden.](mtp-autoir-report-false-positives-negatives.md)

## <a name="available-actions"></a>Verfügbare Aktionen

Wenn Korrekturmaßnahmen ergriffen werden, werden sie auf der Registerkarte **"Verlauf"** im Aktionscenter aufgeführt. Dazu gehören folgende Aktionen:

- Erfassen des Untersuchungspakets 
- Gerät isolieren (diese Aktion kann rückgängig gemacht werden) 
- Offboardcomputer 
- Codeausführung veröffentlichen 
- Isolieren 
- Anforderungsbeispiel 
- Einschränken der Codeausführung (diese Aktion kann rückgängig gemacht werden) 
- Ausführen eines Antivirenscans 
- Beenden und Isolieren 

> [!NOTE]
> Zusätzlich zu Denkmaßnahmen, die automatisch ausgeführt werden, kann Ihr Sicherheitsteam manuelle Maßnahmen ergreifen, um erkannte Bedrohungen zu adressieren. Weitere Informationen zu automatischen und manuellen Wartungsaktionen finden Sie unter ["Problembehebungsaktionen".](mtp-remediation-actions.md)

## <a name="action-source"></a>Aktionsquelle

(**NEU!**) Wie Sie wissen, vereint Microsoft 365 Defender automatisierte Untersuchungs- und Reaktionsfunktionen in mehreren Diensten, z. B. [Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) und Microsoft Defender für Office [365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) Das neue und verbesserte Aktionscenter enthält jetzt eine Quellspalte "Aktion", die Ihnen mitteilt, woher die einzelnen Korrekturmaßnahmen stammen.  

In der folgenden Tabelle werden mögliche **Aktionsquellenwerte** beschrieben:

| Aktionsquellenwert | Beschreibung |
|:-----|:---|
| **Manuelle Geräteaktion** | Eine manuelle Aktion auf einem Gerät. Beispiele hierfür [sind Geräteisolation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) oder [Dateiquarantäne.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files) |
| **Manuelle E-Mail-Aktion** | Eine manuelle Aktion für E-Mails. Ein Beispiel enthält das soft-deleting von E-Mail-Nachrichten oder [die Behebung einer E-Mail-Nachricht.](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365) |
| **Automatisierte Geräteaktion** | Eine automatisierte Aktion für eine Entität, z. B. eine Datei oder einen Prozess. Beispiele für automatisierte Aktionen sind das Senden einer Datei in Quarantäne, das Beenden eines Prozesses und das Entfernen eines Registrierungsschlüssels. (Siehe [Korrekturaktionen in Microsoft Defender for Endpoint.)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions) |
| **Automatisierte E-Mail-Aktion** | Eine automatisierte Aktion für E-Mail-Inhalte, z. B. eine E-Mail-Nachricht, anlage oder URL. Beispiele für automatisierte Aktionen sind das soft-deleting von E-Mail-Nachrichten, das Blockieren von URLs und das Deaktivieren der externen E-Mail-Weiterleitung. (Siehe [Korrekturaktionen in Microsoft Defender für Office 365.)](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions) |
| **Erweiterte Suche** | Aktionen auf Geräten oder E-Mails mit [erweiterter Suche.](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview) |
| **Explorer-Aktion** | Aktionen für E-Mail-Inhalte mit [Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer). |
| **Manuelle Liveantwortaktion** | Aktionen, die auf einem Gerät mit [Liveantwort ergriffen werden.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) Beispiele hierfür sind das Löschen einer Datei, das Beenden eines Prozesses und das Entfernen einer geplanten Aufgabe. |
| **Liveantwortaktion** | Aktionen, die auf einem Gerät mit [Microsoft Defender für Endpunkt-APIs .](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis) Beispiele für Aktionen sind das Isolieren eines Geräts, das Ausführen eines Antivirenscans und das Abrufen von Informationen zu einer Datei. |

## <a name="required-permissions-for-action-center-tasks"></a>Erforderliche Berechtigungen für Info-Center-Aufgaben

Um ausstehende Aktionen im Info-Center zu genehmigen oder abzulehnen, müssen Sie über die Berechtigungen verfügen, die in der folgenden Tabelle aufgeführt sind:

|Wartungsaktion |Erforderliche Rollen und Berechtigungen |
|--|----|
|Problembehebung für Microsoft Defender für Endpunkte (Geräte) |Sicherheitsadministratorrolle in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- oder ---<br/>Rolle "Aktive Wartungsaktionen", die in Microsoft Defender for Endpoint zugewiesen ist <br/> <br/> Weitere Informationen hierzu finden Sie in den folgenden Ressourcen: <br/>- [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung (Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Wartung von Microsoft Defender für Office 365 (Office-Inhalte und E-Mail)  |Sicherheitsadministratorrolle in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- und --- <br/>Search and Purge role assigned the Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**WICHTIG:** Wenn Ihnen die Rolle "Sicherheitsadministrator" nur im Security & Compliance Center zugewiesen ist, können Sie nicht auf das Action Center oder die Microsoft 365 Defender-Funktionen zugreifen. Ihnen muss die Sicherheitsadministratorrolle in Azure Active Directory oder im Microsoft 365 Admin Center zugewiesen sein. <br/><br/>Weitere Informationen hierzu finden Sie in den folgenden Ressourcen: <br/>- [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Benutzer, denen in Azure Active Directory die Rolle Globaler Administrator zugewiesen ist, können alle ausstehenden Aktionen im Info-Center genehmigen oder ablehnen. Als bewährte Methode sollte Ihre Organisation jedoch die Anzahl der Personen einschränken, denen die Rolle des globalen Administrators zugewiesen ist. Es wird empfohlen, die oben aufgeführten Rollen Sicherheitsadministrator, Aktive Wartungsaktionen und Suchen und Löschen für Info-Center-Berechtigungen zu verwenden.

## <a name="next-steps"></a>Nächste Schritte 

- [Genehmigen oder Ablehnen ausstehender Aktionen nach einer automatischen Untersuchung](mtp-autoir-actions.md)
- [Anzeigen der Ergebnisse einer automatischen Untersuchung](mtp-autoir-results.md)

