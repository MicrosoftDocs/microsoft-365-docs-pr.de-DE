---
title: Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender
description: Konfigurieren der automatischen Untersuchung und Reaktion mit Selbstkorrektur in Microsoft 365 Defender
search.appverid: MET150
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: e25fab99718c791c64b583283237815736c450ae
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793184"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender bietet leistungsstarke [automatisierte Untersuchungs- und Reaktionsfunktionen,](m365d-autoir.md) mit denen Ihr Sicherheitsteam viel Zeit und Mühe sparen kann. Bei [der Selbstkorrektur](m365d-autoir.md#how-automated-investigation-and-self-healing-works)imitieren diese Funktionen die Schritte, die ein Sicherheitsanalyst ausführen würde, um Bedrohungen zu untersuchen und darauf zu reagieren, nur schneller und mit mehr Skalierungsfähigkeit.

In diesem Artikel wird beschrieben, wie Sie die automatisierte Untersuchung und Reaktion in Microsoft 365 Defender mit den folgenden Schritten konfigurieren:

1. [Überprüfen Sie die Voraussetzungen.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. [Überprüfen oder ändern Sie die Automatisierungsstufe für Gerätegruppen.](#review-or-change-the-automation-level-for-device-groups)
3. [Überprüfen Sie Ihre Sicherheits- und Warnungsrichtlinien in Office 365.](#review-your-security-and-alert-policies-in-office-365)
4. [Stellen Sie sicher, dass Microsoft 365 Defender aktiviert ist.](#make-sure-microsoft-365-defender-is-turned-on)

Nachdem Sie dann alle eingerichtet sind, können Sie [Korrekturaktionen im Info-Center anzeigen und verwalten.](m365d-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Voraussetzungen für die automatisierte Untersuchung und Reaktion in Microsoft 365 Defender

<br>

****

|Anforderung|Details|
|---|---|
|Abonnementanforderungen|Eines dieser Abonnements: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E3 mit dem Microsoft 365 E5 Security-Add-On</li><li>Microsoft 365 A3 mit dem Microsoft 365 A5 Security-Add-On</li><li>Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5</li></ul> <p> Siehe [Microsoft 365 Defender-Lizenzierungsanforderungen.](./prerequisites.md#licensing-requirements)|
|Netzwerkanforderungen|<ul><li>[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) aktiviert</li><li>[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) konfiguriert</li><li>[Microsoft Defender for Identity-Integration](/cloud-app-security/mdi-integration)</li></ul>|
|Windows-Computeranforderungen|<ul><li>Windows 10, Version 1709 oder höher installiert (siehe [Windows 10 Versionsinformationen)](/windows/release-information/)</li><li>Die folgenden Bedrohungsschutzdienste konfiguriert:<ul><li>[Microsoft Defender für Endpunkt](../defender-endpoint/configure-endpoints.md)</li><li>[Microsoft Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|Schutz für E-Mail-Inhalte und Office-Dateien|[Microsoft Defender für Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) konfiguriert|
|Berechtigungen|Um automatisierte Untersuchungs- und Reaktionsfunktionen zu konfigurieren, müssen Sie die Rolle "Globaler Administrator" oder "Sicherheitsadministrator" entweder in Azure Active Directory ( ) oder im Microsoft 365 Admin Center ( ) zugewiesen <https://portal.azure.com> <https://admin.microsoft.com> haben. <p> Informationen zum Abrufen der erforderlichen Berechtigungen zum Arbeiten mit automatisierten Untersuchungs- und Reaktionsfunktionen, z. B. Überprüfen, Genehmigen oder Ablehnen ausstehender Aktionen, finden Sie unter ["Erforderliche Berechtigungen für Info-Center-Aufgaben".](m365d-action-center.md#required-permissions-for-action-center-tasks)|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Überprüfen oder Ändern der Automatisierungsstufe für Gerätegruppen

Ob automatisierte Untersuchungen ausgeführt werden und ob Korrekturmaßnahmen automatisch oder nur nach der Genehmigung Für Ihre Geräte ausgeführt werden, hängt von bestimmten Einstellungen ab, z. B. den Gerätegruppenrichtlinien Ihrer Organisation. Überprüfen Sie die konfigurierte Automatisierungsstufe für Ihre Gerätegruppenrichtlinien.

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) und melden Sie sich an.
2. Wechseln Sie zu **Einstellungen**  >  **Berechtigungsgerätegruppen.**  >  
3. Überprüfen Sie die Gerätegruppenrichtlinien. Sehen Sie sich insbesondere die Spalte **"Korrekturebene" an.** Es wird empfohlen, **"Vollständig" zu verwenden, um Bedrohungen automatisch zu beheben.**  Möglicherweise müssen Sie Ihre Gerätegruppen erstellen oder bearbeiten, um den gewünschten Automatisierungsgrad zu erhalten. Hilfe zu dieser Aufgabe finden Sie in den folgenden Artikeln:
   - [Wie Bedrohungen behoben werden](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Erstellen und Verwalten von Gerätegruppen](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Überprüfen Sie Ihre Sicherheits- und Warnungsrichtlinien in Office 365

Microsoft bietet integrierte [Warnungsrichtlinien,](../../compliance/alert-policies.md) mit denen bestimmte Risiken erkannt werden können. Zu diesen Risiken gehören Exchange Missbrauch von Administratorberechtigungen, Schadsoftwareaktivitäten, potenzielle externe und interne Bedrohungen sowie Informationsgovernance-Risiken. Einige Warnungen können [eine automatisierte Untersuchung und Reaktion in Office 365](../office-365-security/office-365-air.md)auslösen. Stellen Sie sicher, dass Ihre [Defender für Office 365](../office-365-security/defender-for-office-365.md) Features ordnungsgemäß konfiguriert sind.

Obwohl bestimmte Warnungen und Sicherheitsrichtlinien automatisierte Untersuchungen auslösen können, *werden für E-Mails und Inhalte keine automatischen Abhilfemaßnahmen ausgeführt.* Stattdessen warten alle Korrekturaktionen für E-Mail- und E-Mail-Inhalte auf die Genehmigung durch Ihr Sicherheitsteam im [Info-Center.](m365d-action-center.md)

Sicherheitseinstellungen in Office 365 zum Schutz von E-Mails und Inhalten beitragen. Um diese Einstellungen anzuzeigen oder zu ändern, befolgen Sie die Anweisungen unter ["Schutz vor Bedrohungen".](../office-365-security/protect-against-threats.md)

1. Wechseln Sie im Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ) zu Richtlinien & Richtlinien für **Bedrohungsregeln.** \> 
2. Stellen Sie sicher, dass alle folgenden Richtlinien konfiguriert sind. Hilfe und Empfehlungen finden Sie unter ["Schutz vor Bedrohungen".](/microsoft-365/security/office-365-security/protect-against-threats)
   - [Antischadsoftware](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [Antiphishing](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
   - [Sichere Anlagen](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [Sichere Links](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [Antispam](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)
3. Stellen Sie sicher, dass [Microsoft Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams](../office-365-security/protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on) aktiviert ist.
4. Stellen Sie sicher, dass die [automatische Bereinigung von null Stunden für den E-Mail-Schutz](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) wirksam ist.
5. (Dieser Schritt ist optional.) Überprüfen Sie Ihre [Office 365 Warnungsrichtlinien](../../compliance/alert-policies.md) im Microsoft 365 Compliance Center ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Mehrere Standardwarnungsrichtlinien sind in der Kategorie "Bedrohungsverwaltung" enthalten. Einige dieser Warnungen können eine automatisierte Untersuchung und Reaktion auslösen. Weitere Informationen finden Sie unter [Standardwarnungsrichtlinien.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Stellen Sie sicher, dass Microsoft 365 Defender aktiviert ist.

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP eingeschaltet":::

1. Melden Sie sich beim Microsoft 365 Security Center an ( [https://security.microsoft.com](https://security.microsoft.com) ).
2. Suchen Sie im Navigationsbereich nach **Vorfällen,** **Info-Center** und **Suche,** wie in der vorherigen Abbildung dargestellt.
   - Wenn **Vorfälle,** **Das Info-Center** und **die Suche** angezeigt werden, ist Microsoft 365 Defender aktiviert. Weitere Informationen finden Sie im Abschnitt ["Überprüfen oder Ändern der Automatisierungsstufe für Gerätegruppen"](#review-or-change-the-automation-level-for-device-groups) in diesem Artikel.
   - Wenn **Vorfälle,** **Info-Center** oder **Suche** *nicht* angezeigt werden, ist Microsoft 365 Defender möglicherweise nicht aktiviert. Besuchen Sie in diesem Fall [das Info-Center).](m365d-action-center.md)
3. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Microsoft 365 Defender** aus. Vergewissern Sie sich, dass Microsoft 365 Defender aktiviert ist.

> [!TIP]
> Benötigen Sie Hilfe? Weitere Informationen finden Sie unter [Aktivieren Microsoft 365 Defender](m365d-enable.md).

## <a name="next-steps"></a>Nächste Schritte

- [Korrekturaktionen in Microsoft 365 Defender](m365d-remediation-actions.md)
- [Aufrufen des Aktionszentrums](m365d-action-center.md)
