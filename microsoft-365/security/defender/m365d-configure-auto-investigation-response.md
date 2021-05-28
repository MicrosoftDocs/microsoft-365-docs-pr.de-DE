---
title: Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender
description: Konfigurieren der automatisierten Untersuchung und Reaktion mit Selbstheilung in Microsoft 365 Defender
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
ms.openlocfilehash: 685c23f4e8daac4f00e0bbd90dcaca9a80703559
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696514"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender umfasst leistungsstarke [automatisierte Untersuchungs- und Reaktionsfunktionen,](m365d-autoir.md) die Ihrem Sicherheitsteam viel Zeit und Aufwand sparen können. Mit [der Selbstheilung](m365d-autoir.md#how-automated-investigation-and-self-healing-works)imitieren diese Funktionen die Schritte, die ein Sicherheitsanalyst unternehmen würde, um Bedrohungen zu untersuchen und darauf zu reagieren, nur schneller und mit mehr Skalierungsfähigkeit.

In diesem Artikel wird beschrieben, wie Sie die automatisierte Untersuchung und Reaktion in Microsoft 365 Defender mit den folgenden Schritten konfigurieren:

1. [Überprüfen Sie die Voraussetzungen](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).
2. [Überprüfen oder Ändern der Automatisierungsebene für Gerätegruppen](#review-or-change-the-automation-level-for-device-groups).
3. [Überprüfen Sie Ihre Sicherheits- und Warnungsrichtlinien in Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Stellen Sie sicher, Microsoft 365 Defender aktiviert ist.](#make-sure-microsoft-365-defender-is-turned-on)

Nachdem Sie alle eingerichtet sind, können Sie Korrekturaktionen im [Aktionscenter anzeigen](m365d-autoir-actions.md)und verwalten.

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Voraussetzungen für die automatisierte Untersuchung und Reaktion in Microsoft 365 Defender

<br>

****

|Anforderung|Details|
|---|---|
|Abonnementanforderungen|Eines der folgenden Abonnements: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E3 mit dem Microsoft 365 E5 Security-Add-On</li><li>Microsoft 365 A3 mit dem Microsoft 365 A5 Security-Add-On</li><li>Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5</li></ul> <p> Weitere [Microsoft 365 von Defender finden Sie unter](./prerequisites.md#licensing-requirements).|
|Netzwerkanforderungen|<ul><li>[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) aktiviert</li><li>[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) konfiguriert</li><li>[Microsoft Defender for Identity-Integration](/cloud-app-security/mdi-integration)</li></ul>|
|Windows-Computeranforderungen|<ul><li>Windows 10, Version 1709 oder höher installiert (Siehe [Windows 10 Versionsinformationen](/windows/release-information/))</li><li>Die folgenden Bedrohungsschutzdienste sind konfiguriert:<ul><li>[Microsoft Defender für Endpunkt](../defender-endpoint/configure-endpoints.md)</li><li>[Microsoft Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|Schutz für E-Mail-Inhalte und Office Dateien|[Microsoft Defender für Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) konfiguriert|
|Berechtigungen|Zum Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen müssen Sie die Rolle globaler Administrator oder Sicherheitsadministrator entweder in Azure Active Directory ( ) oder im Microsoft 365 Admin Center ( ) zugewiesen <https://portal.azure.com> haben. <https://admin.microsoft.com> <p> Informationen zu den berechtigungen, die zum Arbeiten mit automatisierten Untersuchungs- und Reaktionsfunktionen erforderlich sind, z. B. Überprüfen, Genehmigen oder Ablehnen ausstehender Aktionen, finden Sie unter Erforderliche Berechtigungen für Aufgaben im [Aktionscenter](m365d-action-center.md#required-permissions-for-action-center-tasks).|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Überprüfen oder Ändern der Automatisierungsebene für Gerätegruppen

Ob automatisierte Untersuchungen ausgeführt werden und ob Korrekturaktionen automatisch oder nur nach genehmigung für Ihre Geräte ausgeführt werden, hängt von bestimmten Einstellungen ab, z. B. den Gerätegruppenrichtlinien Ihrer Organisation. Überprüfen Sie die konfigurierte Automatisierungsstufe für Ihre Gerätegruppenrichtlinien.

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) und melden Sie sich an.
2. Wechseln Sie **zu Einstellungen**  >  **Berechtigungen**  >  **Gerätegruppen**.
3. Überprüfen Sie ihre Gerätegruppenrichtlinien. Sehen Sie sich insbesondere die Spalte **Behebungsebene** an. Es wird empfohlen, **vollständig zu verwenden – Bedrohungen automatisch zu be behebung.**  Möglicherweise müssen Sie Ihre Gerätegruppen erstellen oder bearbeiten, um den von Ihnen benötigten Automatisierungsgrad zu erreichen. Hilfe zu dieser Aufgabe finden Sie in den folgenden Artikeln:
   - [Wie Bedrohungen behoben werden](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Erstellen und Verwalten von Gerätegruppen](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Überprüfen Sie Ihre Sicherheits- und Warnungsrichtlinien in Office 365

Microsoft bietet integrierte [Warnungsrichtlinien,](../../compliance/alert-policies.md) mit deren Hilfe bestimmte Risiken identifiziert werden können. Diese Risiken umfassen Exchange Missbrauch von Administratorberechtigungen, Schadsoftwareaktivitäten, potenzielle externe und interne Bedrohungen sowie Risiken der Informationsverwaltung. Einige Warnungen können automatisierte [Untersuchungen und Reaktionen in](../office-365-security/office-365-air.md)Office 365. Stellen Sie [sicher, dass Ihr Defender für Office 365](../office-365-security/defender-for-office-365.md) ordnungsgemäß konfiguriert ist.

Obwohl bestimmte Warnungen und Sicherheitsrichtlinien automatisierte Untersuchungen auslösen können, werden für E-Mails und Inhalte keine *Korrekturaktionen automatisch ausgeführt.* Stattdessen warten alle Korrekturaktionen für E-Mail- und E-Mail-Inhalte auf die Genehmigung durch Ihr Sicherheitsteam im [Action Center.](m365d-action-center.md)

Sicherheitseinstellungen in Office 365 schützen E-Mails und Inhalte. Befolgen Sie zum Anzeigen oder Ändern dieser Einstellungen die Anweisungen unter [Schützen vor Bedrohungen.](../office-365-security/protect-against-threats.md)

1. Wechseln Sie Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ) zu Richtlinien & **Regeln** \> **Bedrohungsrichtlinien**.
2. Stellen Sie sicher, dass alle folgenden Richtlinien konfiguriert sind. Hilfe und Empfehlungen finden Sie unter [Protect against threats](/microsoft-365/security/office-365-security/protect-against-threats).
   - [An malware)](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [Antiphishing)](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection)
   - [Sichere Anlagen](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [Sichere Links](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [Antispam](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)
3. Stellen Sie [sicher, dass Microsoft Defender Office 365 für SharePoint, OneDrive und](../office-365-security/protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on) Microsoft Teams aktiviert ist.
4. Stellen Sie sicher, dass die automatische [Bereinigung für den E-Mail-Schutz](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) in der Nullstunde wirksam ist.
5. (Dieser Schritt ist optional.) Überprüfen Sie [Office 365 Benachrichtigungsrichtlinien](../../compliance/alert-policies.md) im Microsoft 365 Compliance Center ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Mehrere Standardbenachrichtigungsrichtlinien befinden sich in der Kategorie Bedrohungsverwaltung. Einige dieser Warnungen können automatisierte Untersuchungen und Reaktionen auslösen. Weitere Informationen finden Sie unter [Standardbenachrichtigungsrichtlinien](../../compliance/alert-policies.md#default-alert-policies).

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Stellen Sie sicher, Microsoft 365 Defender aktiviert ist

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

1. Melden Sie sich beim Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ) an.
2. Suchen Sie im Navigationsbereich nach **Vorfällen, Aktionscenter** und  **Suche**, wie in der vorherigen Abbildung dargestellt.
   - Wenn **Incidents,** **Action Center** und **Hunting** zu sehen sind, Microsoft 365 Defender aktiviert. Weitere Informationen finden Sie im Abschnitt Überprüfen oder [Ändern der Automatisierungsebene](#review-or-change-the-automation-level-for-device-groups) für Gerätegruppen in diesem Artikel.
   - Wenn **Incidents,** Action **Center** oder **Hunting** nicht zu sehen sind, Microsoft 365 Defender möglicherweise nicht aktiviert.  In diesem Fall besuchen [Sie das Aktionscenter](m365d-action-center.md)).
3. Wählen Sie im Navigationsbereich die **Option Einstellungen** Microsoft 365  >  **Defender aus.** Vergewissern Sie Microsoft 365, dass Defender aktiviert ist.

> [!TIP]
> Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter](m365d-enable.md)Aktivieren Microsoft 365 Defender .

## <a name="next-steps"></a>Nächste Schritte

- [Korrekturaktionen in Microsoft 365 Defender](m365d-remediation-actions.md)
- [Aufrufen des Aktionszentrums](m365d-action-center.md)
