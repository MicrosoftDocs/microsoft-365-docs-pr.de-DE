---
title: Konfigurieren von automatisierten Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection
description: Konfigurieren der automatischen Untersuchung und Reaktion mit der Selbstheilung in Microsoft Threat Protection
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 10/07/2020
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection: M365-security-compliance.
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: f904512f9fd07e2065f3d27a5bd5adc56a3565d5
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384790"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Konfigurieren von automatisierten Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft Threat Protection umfasst leistungsstarke [automatisierte Ermittlungs-und Antwortfunktionen](mtp-autoir.md) , mit denen Ihr Sicherheits Betriebsteam viel Zeit und Mühe sparen kann. Mit der Selbstheilung simulieren diese Funktionen die Schritte, die ein Sicherheitsanalytiker ausführen würde, um Bedrohungen zu untersuchen und zu reagieren, und zwar nur schneller und mit mehr Skalierungsmöglichkeiten. In diesem Artikel wird beschrieben, wie Sie die automatische Untersuchung und Antwort in Microsoft Threat Protection konfigurieren.

Führen Sie die folgenden Schritte aus, um automatisierte Ermittlungs-und Antwortfunktionen zu konfigurieren:

1. [Überprüfen Sie die Voraussetzungen](#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection).
2. [Überprüfen oder ändern Sie die Automatisierungsstufe für Gerätegruppen](#review-or-change-the-automation-level-for-device-groups).
3. [Überprüfen Sie Ihre Sicherheits-und Warnungsrichtlinien in Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Stellen Sie sicher, dass Microsoft Threat Protection aktiviert ist](#make-sure-microsoft-threat-protection-is-turned-on).

Nachdem Sie alle eingerichtet haben, [Überprüfen Sie ausstehende und abgeschlossene Aktionen im Wartungscenter](#review-pending-and-completed-actions-in-the-action-center). 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Voraussetzungen für die automatische Untersuchung und Reaktion in Microsoft Threat Protection

|Anforderung |Details |
|--|--|
|Abonnementanforderungen |Eines der Abonnements: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 a5 <br/>-Microsoft 365 E5-Sicherheit<br/>-Microsoft 365 a5-Sicherheit<br/>-Office 365 E5 Plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>Weitere Informationen finden Sie unter [Microsoft Threat Protection License Requirements](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Netzwerkanforderungen |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) muss aktiviert sein<br/>- [Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) konfiguriert<br/>- [Microsoft Cloud-App-Sicherheit in Azure ATP integriert](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows-Computeranforderungen |-Windows 10, Version 1709 oder höher (siehe [Windows 10 – Versionsinformationen](https://docs.microsoft.com/windows/release-information/)) mit den folgenden konfigurierten Threat Protection-Diensten:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Microsoft Defender-Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Schutz für e-Mail-Inhalte und Office-Dateien |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) konfiguriert |
|Berechtigungen |-Um automatisierte Ermittlungs-und Antwortfunktionen zu konfigurieren, muss die Rolle globaler Administrator oder Sicherheitsadministrator entweder in Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) oder im Microsoft 365 Admin Center () zugewiesen sein [https://admin.microsoft.com](https://admin.microsoft.com) .<br/><br/>-Informationen zu den Berechtigungen, die für die Arbeit mit automatisierten Ermittlungs-und Antwortfunktionen erforderlich sind, beispielsweise das überprüfen, genehmigen oder ablehnen von ausstehenden Aktionen, finden Sie unter [Required Permissions for Action Center Tasks](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Überprüfen oder Ändern der Automatisierungsebene für Gerätegruppen

Ob automatische Untersuchungen ausgeführt werden und ob Korrekturaktionen automatisch oder nur bei Genehmigung für Ihre Geräte vorgenommen werden, hängt von bestimmten Einstellungen ab, beispielsweise von den Gerätegruppen Richtlinien Ihrer Organisation. Überprüfen Sie die für Ihre Gerätegruppen Richtlinien festgelegte Automatisierungsstufe.

1. Wechseln Sie zum Sicherheits Center von Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ), und melden Sie sich an.

2. Wechseln Sie zu **Einstellungen**  >  **Berechtigungen**  >  **Gerätegruppen**. 

3. Überprüfen Sie Ihre Gerätegruppen Richtlinien. Sehen Sie sich insbesondere die Spalte **Korrektur Ebene** an. Es wird empfohlen, **vollständig behebende Bedrohungen automatisch**zu verwenden.  Möglicherweise müssen Sie Ihre Gerätegruppen erstellen oder bearbeiten, um die gewünschte Automatisierungsstufe zu erhalten. Wenn Sie Hilfe zu dieser Aufgabe erhalten möchten, lesen Sie die folgenden Artikel:

   - [So werden Bedrohungen behoben](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   
   - [Erstellen und Verwalten von Gerätegruppen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Überprüfen der Sicherheits-und Warnungsrichtlinien in Office 365

Microsoft stellt integrierte [Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) bereit, mit denen bestimmte Risiken identifiziert werden können. Zu diesen Risiken gehören Exchange-Administratorberechtigungen, Malwareaktivitäten, potenzielle externe und interne Bedrohungen sowie Risiken bei der Informationssteuerung. Einige Warnungen können [automatisierte Untersuchungen und Antworten in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)auslösen. Stellen Sie sicher, dass Ihre [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) -Features ordnungsgemäß konfiguriert sind.

Obwohl bestimmte Warnungen und Sicherheitsrichtlinien automatische Untersuchungen auslösen können, werden keine Korrekturaktionen für e-Mails und Inhalte automatisch durchgeführt. Stattdessen warten alle Korrekturaktionen für e-Mail-und e-Mail-Inhalte auf die Genehmigung durch Ihr Sicherheits Betriebsteam im [Action Center](mtp-action-center.md).

Sicherheitseinstellungen in Office 365 helfen, e-Mails und Inhalte zu schützen. Um diese Einstellungen anzuzeigen oder zu ändern, befolgen Sie die Anweisungen unter [Protect Against Threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

1. Wechseln Sie im Microsoft 365 Security Center ( [https://security.microsoft.com/](https://security.microsoft.com/) ) zu **Richtlinien**  >  **Threat Protection**.

2. Stellen Sie sicher, dass alle der folgenden Richtlinien konfiguriert sind. Informationen zum Abrufen von Hilfe und Empfehlungen finden Sie unter [Protect Against Threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

   - [Anti-Malware (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [ATP-Anti-Phishing (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Sichere ATP-Anhänge (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [ATP-sichere Links (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Anti-Spam (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. Stellen Sie sicher, dass [Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) aktiviert ist.

5. Stellen Sie sicher, dass die [Automatische Säuberungsaktion für den e-Mail-Schutz Null Stunden](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) gültig ist. 

8. (Dies ist optional.) Überprüfen Sie Ihre [Office 365 Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) im Microsoft 365 Compliance Center ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Mehrere standardmäßige Warnungsrichtlinien befinden sich in der Kategorie "Threat Management". Einige dieser Warnungen können automatisierte Untersuchungen und Antworten auslösen. Weitere Informationen finden Sie unter [default Alert Policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies).
 
## <a name="make-sure-microsoft-threat-protection-is-turned-on"></a>Stellen Sie sicher, dass Microsoft Threat Protection aktiviert ist.

1. Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ), und melden Sie sich an.

2. Suchen Sie im Navigationsbereich nach **Incidents**, **Action Center**und **Hunting**, wie in der folgenden Abbildung dargestellt:

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP auf":::

   - Wenn Sie **Incidents**, **Action Center**und **Hunting**sehen, ist Microsoft Threat Protection aktiviert. Fahren Sie mit dem nächsten Verfahren fort, [überprüfen oder ändern Sie die Automatisierungsstufe für Gerätegruppen](#review-or-change-the-automation-level-for-device-groups).

   - Wenn Sie *keine* **Vorfälle**, kein **Wartungscenter**oder keine **Suche**sehen, ist Microsoft Threat Protection möglicherweise nicht aktiviert. Fahren Sie in diesem Fall mit dem nächsten Schritt fort.

3. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Microsoft Threat Protection**aus. Vergewissern Sie sich, dass Microsoft Threat Protection aktiviert ist. 

   Benötigen Sie Hilfe? Weitere Informationen finden Sie unter [Aktivieren von Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>Überprüfen der ausstehenden und abgeschlossenen Aktionen im Wartungscenter

Nachdem Sie die automatische Untersuchung und Antwort in Microsoft Threat Protection konfiguriert haben, müssen Sie im nächsten Schritt das Aktionscenter besuchen ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ). Dort können Sie ausstehende Aktionen überprüfen und genehmigen und anzeigen, welche Korrekturaktionen automatisch vorgenommen wurden. 

[Besuchen Sie das Action Center](mtp-action-center.md).
