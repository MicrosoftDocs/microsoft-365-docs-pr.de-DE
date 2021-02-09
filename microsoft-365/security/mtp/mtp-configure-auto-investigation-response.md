---
title: Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender
description: Konfigurieren der automatisierten Untersuchung und Reaktion mit Selbstbeantwortung in Microsoft 365 Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.date: 02/08/2021
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 311b5e85055d48fb653c4ca42826f0a92267b00e
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50144993"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender umfasst leistungsstarke automatisierte Untersuchungs- und [Reaktionsfunktionen,](mtp-autoir.md) die Ihrem Sicherheitsteam viel Zeit und Mühe sparen können. Mit [der Selbstrekribung](mtp-autoir.md#how-automated-investigation-and-self-healing-works)imitieren diese Funktionen die Schritte, die ein Sicherheitsanalyst unternehmen würde, um Bedrohungen zu untersuchen und darauf zu reagieren, nur schneller und mit mehr Skalierungsfähigkeit. In diesem Artikel wird beschrieben, wie Sie eine automatisierte Untersuchung und Reaktion in Microsoft 365 Defender konfigurieren.

Führen Sie die folgenden Schritte aus, um automatisierte Untersuchungs- und Reaktionsfunktionen zu konfigurieren:

1. [Überprüfen Sie die Voraussetzungen.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. [Überprüfen oder ändern Sie die Automatisierungsstufe für Gerätegruppen.](#review-or-change-the-automation-level-for-device-groups)
3. [Überprüfen Sie Ihre Sicherheits- und Warnungsrichtlinien in Office 365.](#review-your-security-and-alert-policies-in-office-365)
4. [Stellen Sie sicher, dass Microsoft 365 Defender aktiviert ist.](#make-sure-microsoft-365-defender-is-turned-on)

Nachdem Sie alle eingerichtet haben, können Sie Aktionen [im Aktionscenter anzeigen und verwalten.](mtp-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Voraussetzungen für die automatisierte Untersuchung und Reaktion in Microsoft 365 Defender

|Anforderung |Details |
|:----|:----|
|Abonnementanforderungen |Eines dieser Abonnements: <br/>- Microsoft 365 E5<br/>- Microsoft 365 A5<br/>- Microsoft 365 E5 Security<br/>- Microsoft 365 A5 Security<br/>- Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<p> Siehe [Microsoft 365 Defender-Lizenzierungsanforderungen.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)|
|Netzwerkanforderungen |- [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) aktiviert<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) konfiguriert<br/>- [Integration von Microsoft Defender for Identity](https://docs.microsoft.com/cloud-app-security/mdi-integration) |
|Windows-Computeranforderungen |– Windows 10, Version 1709 oder höher, muss installiert sein (siehe [Windows 10-Versionsinformationen](https://docs.microsoft.com/windows/release-information/)) <br/>– Die folgenden konfigurierten Dienste zum Schutz vor Bedrohungen:<br/>- [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)<br/>- [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Schutz für E-Mail-Inhalte und Office-Dateien |[Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) konfiguriert |
|Berechtigungen | Zum Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen muss Ihnen die Rolle "Globaler Administrator" oder "Sicherheitsadministrator" entweder in Azure Active Directory ( ) oder im [https://portal.azure.com](https://portal.azure.com) Microsoft 365 Admin Center ( ) zugewiesen sein. [https://admin.microsoft.com](https://admin.microsoft.com)<p>Informationen zum Erhalten der erforderlichen Berechtigungen für die Arbeit mit automatisierten Untersuchungs- und Reaktionsfunktionen, z. B. Überprüfen, Genehmigen oder Ablehnen ausstehender Aktionen, finden Sie unter "Erforderliche Berechtigungen für Aufgaben im [Aktionscenter".](mtp-action-center.md#required-permissions-for-action-center-tasks) |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Überprüfen oder Ändern der Automatisierungsstufe für Gerätegruppen

Ob automatisierte Untersuchungen ausgeführt werden und ob Korrekturaktionen automatisch oder nur bei genehmigung für Ihre Geräte ausgeführt werden, hängt von bestimmten Einstellungen ab, z. B. den Gerätegruppenrichtlinien Ihrer Organisation. Überprüfen Sie die Für Ihre Gerätegruppenrichtlinien festgelegte Automatisierungsebene.

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ), und melden Sie sich an.
2. Wechseln Sie zu **"Einstellungsberechtigungen**  >    >  **Gerätegruppen".**
3. Überprüfen Sie ihre Gerätegruppenrichtlinien. Sehen Sie sich insbesondere die Spalte **"Problembehebungsebene"** an. Es wird **empfohlen, "Vollständig - Bedrohungen automatisch zu bedrohen" zu verwenden.**  Möglicherweise müssen Sie Ihre Gerätegruppen erstellen oder bearbeiten, um den grad der Automatisierung zu erhalten, die Sie benötigen. Hilfe zu dieser Aufgabe finden Sie in den folgenden Artikeln:
   - [Wie Bedrohungen behoben werden](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Erstellen und Verwalten von Gerätegruppen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Überprüfen Ihrer Sicherheits- und Warnungsrichtlinien in Office 365

Microsoft bietet integrierte [Warnungsrichtlinien, mit](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) deren Hilfe bestimmte Risiken identifiziert werden können. Zu diesen Risiken gehören der Missbrauch von Exchange-Administratorberechtigungen, Schadsoftwareaktivitäten, potenzielle externe und interne Bedrohungen sowie Risiken der Informationsverwaltung. Einige Warnungen können eine [automatisierte Untersuchung und Reaktion in Office 365 auslösen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Stellen Sie sicher, [dass Ihre Microsoft Defender für Office 365-Features](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) ordnungsgemäß konfiguriert sind.

Obwohl bestimmte Warnungen und Sicherheitsrichtlinien automatisierte Untersuchungen auslösen können, werden für E-Mails und Inhalte keine Automatischen Abhilfemaßnahmen ausgeführt. Stattdessen warten alle Korrekturaktionen für E-Mail- und E-Mail-Inhalte auf die Genehmigung durch Ihr Sicherheitsteam im [Action Center.](mtp-action-center.md)

Sicherheitseinstellungen in Office 365 helfen beim Schutz von E-Mails und Inhalten. Wenn Sie diese Einstellungen anzeigen oder ändern möchten, befolgen Sie die Anweisungen unter ["Schutz vor Bedrohungen".](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

1. Wechseln Sie im Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ) zu **Policies**  >  **Threat Protection**.
2. Stellen Sie sicher, dass alle folgenden Richtlinien konfiguriert sind. Hilfe und Empfehlungen finden Sie unter ["Schutz vor Bedrohungen".](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)
   - [Ansoftware (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Antiphishing in Defender für Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Sichere Anlagen (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Sichere Links (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Antispam (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection)
3. Stellen Sie [sicher, dass Microsoft Defender für Office 365 für SharePoint, OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) und Microsoft Teams aktiviert ist.
4. Stellen Sie sicher, dass die automatische [Bereinigung zur Nullstunde](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) für den E-Mail-Schutz wirksam ist.
5. (Dieser Schritt ist optional.) Überprüfen Sie [Ihre Office 365-Benachrichtigungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) im Microsoft 365 Compliance Center ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). In der Kategorie "Bedrohungsverwaltung" sind mehrere Standardmäßige Warnungsrichtlinien festgelegt. Einige dieser Warnungen können eine automatisierte Untersuchung und Reaktion auslösen. Weitere Informationen finden Sie unter [Standardbenachrichtigungsrichtlinien.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Stellen Sie sicher, dass Microsoft 365 Defender aktiviert ist

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

1. Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ), und melden Sie sich an.
2. Suchen Sie im Navigationsbereich nach Vorfällen, **dem Aktionscenter** und **der Suche,** wie in der vorherigen Abbildung dargestellt. 
   - Wenn **Vorfälle,** **das Action Center** und die **Suche** zu sehen sind, ist Microsoft 365 Defender aktiviert. Lesen Sie das Verfahren, überprüfen oder [ändern Sie die Automatisierungsstufe für Gerätegruppen](#review-or-change-the-automation-level-for-device-groups) (in diesem Artikel).
   - Wenn keine *Vorfälle,* das **Action** **Center** oder **die Suche** zu sehen sind, ist Microsoft 365 Defender möglicherweise nicht aktiviert. Fahren Sie in diesem Fall mit dem [Besuch des Aktionscenters fort.](mtp-action-center.md)
3. Wählen Sie im Navigationsbereich **einstellungen**  >  **Microsoft 365 Defender** aus. Vergewissern Sie sich, dass Microsoft 365 Defender aktiviert ist. 

> [!TIP]
> Benötigen Sie Hilfe? Siehe [Aktivieren von Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).

## <a name="next-steps"></a>Nächste Schritte

- [Abhilfemaßnahmen in Microsoft 365 Defender](mtp-remediation-actions.md)
- [Aufrufen des Aktionszentrums](mtp-action-center.md)
