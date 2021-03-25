---
title: Konfigurieren erweiterter Features in Microsoft Defender for Endpoint
description: Aktivieren Sie erweiterte Features wie z. B. die Blockdatei in Microsoft Defender for Endpoint.
keywords: Erweiterte Features, Einstellungen, Blockdatei, automatisierte Untersuchung, automatische Lösung, Skype, Microsoft Defender für Identität, Office 365, Azure Information Protection, Intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ed6f6b42570a908a1f4a83d46ef5b2de0c558692
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199741"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>Konfigurieren erweiterter Features in Defender for Endpoint

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

Je nach den von Ihnen verwendeten Microsoft-Sicherheitsprodukten stehen Ihnen möglicherweise einige erweiterte Features zur Verfügung, in die Sie Defender for Endpoint integrieren können.

## <a name="enable-advanced-features"></a>Aktivieren erweiterter Features

1. Wählen Sie im Navigationsbereich Einstellungen **einrichten Erweiterte**  >  **Features aus.**
2. Wählen Sie das erweiterte Feature aus, das Sie konfigurieren möchten, und schalten Sie die Einstellung zwischen **Ein** und **Aus um.**
3. Klicken **Sie auf Einstellungen speichern**.

Verwenden Sie die folgenden erweiterten Features, um besser vor potenziell schädlichen Dateien zu schützen und während der Sicherheitsuntersuchungen bessere Einblicke zu erhalten.

## <a name="automated-investigation"></a>Automatisierte Untersuchung

Aktivieren Sie dieses Feature, um die Automatisierten Untersuchungs- und Korrekturfeatures des Diensts zu nutzen. Weitere Informationen finden Sie unter [Automatisierte Untersuchung](automated-investigations.md).

## <a name="live-response"></a>Liveantwort

Aktivieren Sie dieses Feature, damit Benutzer mit den entsprechenden Berechtigungen eine Liveantwortsitzung auf Geräten starten können.

Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)

## <a name="live-response-for-servers"></a>Liveantwort für Server
Aktivieren Sie dieses Feature, damit Benutzer mit den entsprechenden Berechtigungen eine Liveantwortsitzung auf Servern starten können.

Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)


## <a name="live-response-unsigned-script-execution"></a>Ausführung eines nicht signierten Skripts für Liveantworten

Wenn Sie dieses Feature aktivieren, können Sie nicht signierte Skripts in einer Liveantwortsitzung ausführen.

## <a name="autoresolve-remediated-alerts"></a>Behebung von Warnungen durch Autoresolve

Für Mandanten, die unter oder nach Windows 10, Version 1809, erstellt wurden, ist die automatische Untersuchungs- und Behebungsfunktion standardmäßig so konfiguriert, dass Warnungen aufgelöst werden, bei denen der Ergebnisstatus der automatisierten Analyse "Keine Bedrohungen gefunden" oder "Behoben" ist.  Wenn Warnungen nicht automatisch aufgelöst werden sollen, müssen Sie das Feature manuell deaktivieren.

> [!TIP]
> Für Mandanten, die vor dieser Version erstellt wurden, müssen Sie dieses Feature manuell auf der Seite Erweiterte [Features aktivieren.](https://securitycenter.windows.com/preferences2/integration)

> [!NOTE]
>
> - Das Ergebnis der automatischen Lösungsaktion kann sich auf die Berechnung des Geräterisikoniveaus, die auf den aktiven Warnungen basiert, die auf einem Gerät gefunden wurden, beeinflussen.
> - Wenn ein Sicherheitsbetriebsanalyst den Status einer Warnung manuell auf "In Bearbeitung" oder "Aufgelöst" legt, überschreibt die Funktion für die automatische Lösung sie nicht.

## <a name="allow-or-block-file"></a>Zulassen oder Blockieren von Dateien

Das Blockieren ist nur verfügbar, wenn Ihre Organisation die folgenden Anforderungen erfüllt:

- Verwendet Microsoft Defender Antivirus als aktive Antischasoftwarelösung und,
- Das cloudbasierte Schutzfeature ist aktiviert

Mit diesem Feature können Sie potenziell schädliche Dateien in Ihrem Netzwerk blockieren. Durch das Blockieren einer Datei wird verhindert, dass sie auf Geräten in Ihrer Organisation gelesen, geschrieben oder ausgeführt wird.

So aktivieren **Sie Dateien zulassen oder** blockieren:

1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Erweiterte Features**  >  **Zulassen oder Blockieren von Datei aus.**

1. Umschalten der Einstellung zwischen **Ein** und **Aus**.

    ![Abbildung erweiterter Einstellungen für die Blockdateifunktion](images/atp-preferences-setup.png)

1. Wählen **Sie einstellungen speichern** unten auf der Seite aus.

Nachdem Sie dieses Feature aktivieren, können [Sie](respond-file-alerts.md#allow-or-block-file) Dateien über die Registerkarte Indikator **hinzufügen** auf der Profilseite einer Datei blockieren.

## <a name="custom-network-indicators"></a>Benutzerdefinierte Netzwerkindikatoren

Wenn Sie dieses Feature aktivieren, können Sie Indikatoren für IP-Adressen, Domänen oder URLs erstellen, die basierend auf Ihrer benutzerdefinierten Indikatorliste bestimmen, ob sie zugelassen oder blockiert werden.

Um dieses Feature verwenden zu können, müssen auf Geräten Windows 10, Version 1709 oder höher, ausgeführt werden. Sie sollten auch über Netzwerkschutz im Blockmodus und Version 4.18.1906.3 oder höher der Antischalwareplattform verfügen, siehe [KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).

Weitere Informationen finden Sie unter [Manage indicators](manage-indicators.md).

> [!NOTE]
> Der Netzwerkschutz nutzt Reputationsdienste, die Anforderungen an Orten verarbeiten, die sich möglicherweise außerhalb des für Ihre Defender for Endpoint-Daten ausgewählten Speicherorts befinden.

## <a name="show-user-details"></a>Anzeigen von Benutzerdetails

Aktivieren Sie dieses Feature, damit Benutzerdetails in Azure Active Directory gespeichert sind. Details umfassen das Bild, den Namen, den Titel und die Abteilungsinformationen eines Benutzers bei der Untersuchung von Benutzerkontenentitäten. Informationen zum Benutzerkonto finden Sie in den folgenden Ansichten:

- Dashboard für Sicherheitsvorgänge
- Warnungswarteschlange
- Seite "Gerätedetails"

Weitere Informationen finden Sie unter [Untersuchen eines Benutzerkontos](investigate-user.md).

## <a name="skype-for-business-integration"></a>Skype for Business-Integration

Wenn Sie die Skype for Business-Integration aktivieren, können Sie mit Benutzern über Skype for Business, E-Mail oder Telefon kommunizieren. Dies kann nützlich sein, wenn Sie mit dem Benutzer kommunizieren und Risiken mindern müssen.

> [!NOTE]
> Wenn ein Gerät vom Netzwerk isoliert wird, gibt es ein Popup, in dem Sie die Outlook- und Skype-Kommunikation aktivieren können, wodurch die Kommunikation mit dem Benutzer ermöglicht wird, während er vom Netzwerk getrennt ist. Diese Einstellung gilt für die Skype- und Outlook-Kommunikation, wenn sich Geräte im Isolationsmodus befinden.

## <a name="azure-advanced-threat-protection-integration"></a>Azure Advanced Threat Protection-Integration

Die Integration in Azure Advanced Threat Protection ermöglicht es Ihnen, direkt in ein anderes Microsoft Identity-Sicherheitsprodukt zu pivotieren. Azure Advanced Threat Protection erweitert eine Untersuchung um zusätzliche Einblicke zu einem mutmaßlich gefährdeten Konto und zugehörigen Ressourcen. Durch aktivieren dieses Feature bereichern Sie die gerätebasierte Untersuchungsfunktion, indem Sie aus identifikationsbezogener Sicht über das Netzwerk pivotieren.

> [!NOTE]
> Sie benötigen die entsprechende Lizenz, um dieses Feature zu aktivieren.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 Threat Intelligence-Verbindung

Dieses Feature ist nur verfügbar, wenn Sie über ein aktives Office 365 E5 oder das Threat Intelligence-Add-On verfügen. Weitere Informationen finden Sie auf der Office 365 Enterprise E5-Produktseite.

Wenn Sie dieses Feature aktivieren, können Sie Daten aus Office 365 Advanced Threat Protection in Das Microsoft Defender Security Center integrieren, um eine umfassende Sicherheitsuntersuchung für Office 365-Postfächer und Windows-Geräte durchführen zu können.

> [!NOTE]
> Sie benötigen die entsprechende Lizenz, um dieses Feature zu aktivieren.

Um kontextbezogene Geräteintegration in Office 365 Threat Intelligence zu erhalten, müssen Sie die Defender for Endpoint-Einstellungen im Security & Compliance-Dashboard aktivieren. Weitere Informationen finden Sie unter [Threat investigation and response](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).

## <a name="microsoft-threat-experts"></a>Microsoft-Bedrohungsexperten

Von den beiden Microsoft Threat Expert-Komponenten ist eine gezielte Angriffsbenachrichtigung allgemein verfügbar. Die Experten-bei-Bedarf-Funktion befindet sich noch in der Vorschau. Sie können die Experten-bei-Bedarf-Funktion nur verwenden, wenn Sie eine Vorschau beantragt haben und Ihre Anwendung genehmigt wurde. Sie können gezielte Angriffsbenachrichtigungen von Microsoft Threat Experts über das Benachrichtigungsdashboard ihres Defender for Endpoint-Portals und per E-Mail empfangen, wenn Sie es konfigurieren.

> [!NOTE]
> Die Microsoft Threat Experts-Funktion in Defender for Endpoint ist mit einer E5-Lizenz für [Enterprise Mobility + Security verfügbar.](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

Wenn Sie diese Einstellung aktivieren, werden Defender for Endpoint-Signale an Microsoft Cloud App Security weitergeleitet, um einen tieferen Einblick in die Verwendung von Cloudanwendung zu erhalten. Weitergeleitete Daten werden am gleichen Speicherort wie Ihre Cloud App Security-Daten gespeichert und verarbeitet.

> [!NOTE]
> Dieses Feature ist mit einer E5-Lizenz für [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) auf Geräten mit Windows 10, Version 1709 (Os Build 16299.1085 mit [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, verfügbar. Version 1803 (Betriebssystem build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, Version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) oder höher Windows 10-Versionen.

## <a name="azure-information-protection"></a>Azure Information Protection

Wenn Sie diese Einstellung aktivieren, können Signale an Azure Information Protection weitergeleitet werden. Sie bietet Datenbesitzern und Administratoren Einblick in geschützte Daten auf integrierten Geräten und Geräterisikobewertungen.

## <a name="microsoft-secure-score"></a>Microsoft-Sicherheitsbewertung

Weiterleitung von Microsoft Defender for Endpoint-Signalen an Microsoft Secure Score im Microsoft 365 Security Center. Wenn Sie dieses Feature aktivieren, erhält Microsoft Secure Score Einblick in die Sicherheitslage des Geräts. Weitergeleitete Daten werden am gleichen Speicherort wie Ihre Microsoft Secure Score-Daten gespeichert und verarbeitet.

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Aktivieren der Microsoft Defender for Endpoint-Integration über das Microsoft Defender for Identity-Portal

Um kontextbezogene Geräteintegration in Microsoft Defender for Identity zu erhalten, müssen Sie das Feature auch im Microsoft Defender for Identity-Portal aktivieren.

1. Melden Sie sich beim [Microsoft Defender for Identity-Portal mit](https://portal.atp.azure.com/) einer globalen Administrator- oder Sicherheitsadministratorrolle an.

2. Klicken **Sie auf Instanz erstellen**.

3. Umschalten Sie die Integrationseinstellung auf **Ein,** und klicken Sie auf **Speichern.**

Nachdem Sie die Integrationsschritte in beiden Portalen abgeschlossen haben, können Sie relevante Warnungen auf der Seite Gerätedetails oder Benutzerdetails anzeigen.

## <a name="microsoft-intune-connection"></a>Microsoft Intune-Verbindung

Defender for Endpoint kann in [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) integriert werden, um den [risikobasierten bedingten](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)Zugriff auf Geräte zu ermöglichen. Wenn Sie [dieses Feature aktivieren,](configure-conditional-access.md)können Sie Defender for Endpoint-Geräteinformationen für Intune freigeben und so die Richtliniendurchsetzung verbessern.

> [!IMPORTANT]
> Sie müssen die Integration in Intune und Defender for Endpoint aktivieren, um dieses Feature verwenden zu können. Weitere Informationen zu bestimmten Schritten finden Sie unter [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).

Dieses Feature ist nur verfügbar, wenn Sie über Folgendes verfügen:

- Ein lizenzierter Mandant für Enterprise Mobility + Security E3 und Windows E5 (oder Microsoft 365 Enterprise E5)
- Eine aktive Microsoft Intune-Umgebung, bei der Intune-verwaltete Windows [10-Geräte Azure AD beigetreten sind.](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/)

### <a name="conditional-access-policy"></a>Richtlinie für bedingten Zugriff

Wenn Sie die Intune-Integration aktivieren, erstellt Intune automatisch eine klassische Richtlinie für bedingten Zugriff (Conditional Access, CA). Diese klassische Zertifizierungsstellenrichtlinie ist eine Voraussetzung für das Einrichten von Statusberichten in Intune. Es sollte nicht gelöscht werden.

> [!NOTE]
> Die von Intune erstellte klassische Zertifizierungsstellenrichtlinie unterscheidet sich von modernen [Richtlinien](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)für bedingten Zugriff, die zum Konfigurieren von Endpunkten verwendet werden.

## <a name="preview-features"></a>Vorschaufeatures

Erfahren Sie mehr über neue Features in der Defender for Endpoint-Vorschauversion, und testen Sie als erstes die kommenden Features, indem Sie die Vorschaufunktion aktivieren.

Sie haben Zugriff auf anstehende Features, zu denen Sie Feedback geben können, um die Allgemeine Erfahrung zu verbessern, bevor Features allgemein verfügbar sind.

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Freigeben von Endpunktwarnungen mit Microsoft Compliance Center

Weitergeleitet Endpunktsicherheitswarnungen und deren Triagestatus an das Microsoft Compliance Center, sodass Sie Insider-Risikomanagementrichtlinien mit Warnungen verbessern und interne Risiken vor schaden verursachen können. Weitergeleitete Daten werden am gleichen Speicherort wie Ihre Office 365-Daten verarbeitet und gespeichert.

Nach dem Konfigurieren der [Sicherheitsrichtlinienverletzungsindikatoren](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-settings.md#indicators) in den Einstellungen für das Insiderrisikomanagement werden Defender for Endpoint-Warnungen für das Insiderrisikomanagement für anwendbare Benutzer freigegeben.

## <a name="related-topics"></a>Verwandte Themen

- [Aktualisieren von Einstellungen für die Datenaufbewahrung](data-retention-settings.md)
- [Konfigurieren von Benachrichtigungen](configure-email-notifications.md)
