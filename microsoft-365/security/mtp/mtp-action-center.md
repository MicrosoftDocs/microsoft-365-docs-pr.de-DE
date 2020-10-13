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
ms.date: 09/16/2020
ms.openlocfilehash: a89383d99cc3f6c98947d1562daf3467dd48c62d
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429755"
---
# <a name="the-action-center"></a>Das Info-Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Verwenden Sie das Info-Center, um die Ergebnisse aktueller und früherer Untersuchungen auf den Geräten und in den Postfächern Ihrer Organisation anzuzeigen. Je nach Art der Bedrohung und dem daraus resultierenden Urteil werden [Korrekturaktionen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) automatisch oder nach Genehmigung durch das Sicherheits Betriebsteam Ihrer Organisation durchgeführt. Alle Wartungsaktionen – unabhängig davon, ob eine Genehmigung aussteht oder diese bereits genehmigt wurden – werden im Info-Center zusammengefasst. 

![Info-Center](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Eine einzige Oberfläche

Das Info-Center bietet eine einzige Oberfläche für folgende Aufgaben:
- Genehmigen ausstehender Wartungsaktionen
- Anzeigen eines Überwachungsprotokolls von bereits genehmigten Wartungsaktionen und
- Überprüfen abgeschlossener Wartungsaktionen

Ihr Sicherheitsteam kann effektiver und effizienter arbeiten, da das Info-Center eine umfassende Übersicht über Microsoft Threat Protection bei der Arbeit bietet.

## <a name="go-to-the-action-center"></a>Aufrufen des Info-Centers

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

3. Im Wartungscenter werden zwei Registerkarten angezeigt: **Ausstehend** und **Verlauf**.

    - Auf der Registerkarte **Ausstehend** werden Untersuchungen aufgeführt, die von einer Person in Ihrem Sicherheitsteam überprüft und genehmigt werden müssen. Überprüfen Sie alle ausstehenden Elemente, die hier angezeigt werden, und ergreifen Sie entsprechende Maßnahmen.

    - Auf der Registerkarte **Verlauf** werden frühere Untersuchungen und Wartungsaktionen aufgeführt, die automatisch ausgeführt wurden. Sie können Daten für den vergangenen Tag, die letzte Woche, den letzten Monat oder die letzten sechs Monate anzeigen.

4. Wenn nur bestimmte Spalten angezeigt werden sollen, wählen Sie **Spalten anpassen** aus.<br/>![Info-Center in Microsoft Threat Protection](../../media/mtp-action-center.png)

5. Wählen Sie ein Element in der Liste aus, um weitere Details zu einer Untersuchung anzuzeigen. Die Untersuchungsdetailansicht wird geöffnet.<br/>![Untersuchungsdetails](../../media/mtp-air-investdetails.png)

    - Wenn sich die Untersuchung auf e-Mail-Inhalte bezieht (beispielsweise die Entität ist ein Postfach), werden Ermittlungs Details im Security & Compliance Center ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ) geöffnet. 

    - Wenn es bei der Untersuchung um ein Gerät geht, werden die Untersuchungsdetails im Security Center ([https://security.microsoft.com](https://security.microsoft.com)) geöffnet. 

> [!TIP]
> Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen! Weitere Informationen finden Sie unter [How to Report false positives/negatives in Automated Investigation and Response (Air) Funktionen in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

## <a name="available-actions"></a>Verfügbare Aktionen

Wenn Korrekturaktionen ausgeführt werden, werden Sie auf der Registerkarte Verlauf im Wartungscenter aufgeführt. Solche Aktionen umfassen Folgendes:

- Ermittlungs Paket sammeln 
- Gerät isolieren (diese Aktion kann rückgängig gemacht werden) 
- Extern-Computer 
- Freigabecode Ausführung 
- Freigabe aus Quarantäne 
- Anforderungs Beispiel 
- Einschränken der Codeausführung (diese Aktion kann rückgängig gemacht werden) 
- Ausführen des Antivirus-Scans 
- Beenden und isolieren 

## <a name="required-permissions-for-action-center-tasks"></a>Erforderliche Berechtigungen für Info-Center-Aufgaben

Um ausstehende Aktionen im Info-Center zu genehmigen oder abzulehnen, müssen Sie über die Berechtigungen verfügen, die in der folgenden Tabelle aufgeführt sind:

|Wartungsaktion |Erforderliche Rollen und Berechtigungen |
|--|----|
|Microsoft Defender ATP-Wartung (Geräte) |Sicherheitsadministratorrolle in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- oder ---<br/>Rolle Aktive Wartungsaktionen in Microsoft Defender ATP <br/> <br/> Weitere Informationen hierzu finden Sie in den folgenden Ressourcen: <br/>- [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Office 365 ATP-Wartung (Office-Inhalte und E-Mail)  |Sicherheitsadministratorrolle in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- und --- <br/>Dem Security & Compliance Center zugewiesene Rolle "Search and Purge" ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**Wichtig**: Wenn Sie die Sicherheits Administrator Rolle nur im Sicherheits & Compliance Center zugewiesen haben, können Sie nicht auf das Action Center oder die Microsoft Threat Protection-Funktionen zugreifen. Ihnen muss die Sicherheitsadministratorrolle in Azure Active Directory oder im Microsoft 365 Admin Center zugewiesen sein. <br/><br/>Weitere Informationen hierzu finden Sie in den folgenden Ressourcen: <br/>- [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Benutzer, denen in Azure Active Directory die Rolle Globaler Administrator zugewiesen ist, können alle ausstehenden Aktionen im Info-Center genehmigen oder ablehnen. Als bewährte Methode sollte Ihre Organisation jedoch die Anzahl der Personen einschränken, denen die Rolle des globalen Administrators zugewiesen ist. Es wird empfohlen, die oben aufgeführten Rollen Sicherheitsadministrator, Aktive Wartungsaktionen und Suchen und Löschen für Info-Center-Berechtigungen zu verwenden.

## <a name="next-steps"></a>Weitere Schritte 

- [Genehmigen oder Ablehnen ausstehender Aktionen im Anschluss an eine automatisierte Untersuchung](mtp-autoir-actions.md)
- [Anzeigen der Ergebnisse einer automatischen Untersuchung](mtp-autoir-results.md)

