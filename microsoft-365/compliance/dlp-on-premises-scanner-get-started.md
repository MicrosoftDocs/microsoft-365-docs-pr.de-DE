---
title: Erste Schritte mit dem lokalen Microsoft 365-DLP-Scanner (Data Loss Prevention, Verhinderung von Datenverlust) (Vorschau)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Einrichten des lokalen Microsoft 365-Scanners zur Verhinderung von Datenverlust
ms.openlocfilehash: 242956a3c6469756481fb823340e715a210562af
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114173"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a>Erste Schritte mit dem lokalen Scanner zur Verhinderung von Datenverlust (Vorschau)

Dieser Artikel führt Sie durch die Voraussetzungen und die Konfiguration für den lokalen Microsoft 365-Scanner zur Verhinderung von Datenverlust.

## <a name="before-you-begin"></a>Vorabinformationen

### <a name="skusubscriptions-licensing"></a>SKU/Abonnement-Lizenzierung

Bevor Sie mit dem lokalen DLP-Scanner beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und etwaige Add-Ons bestätigen. Um an der Vorschau teilnehmen zu können, muss dem Administratorkonto, das die DLP-Regeln erstellt, eine der folgenden Lizenzen zugewiesen werden:

- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 Information Protection & Governance 


Ausführliche Informationen zur Lizenzierung finden Sie unter: [Microsoft 365-Lizenzierungsrichtlinien für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

### <a name="permissions"></a>Berechtigungen


Daten vom lokalen DLP-Scanner können im [Aktivitäts-Explorer](data-classification-activity-explorer.md) angezeigt werden. Es gibt vier Rollen, die Berechtigungen für den Aktivitäten-Explorer gewähren; das Konto, das Sie für den Zugriff auf die Daten verwenden, muss eine der folgenden Rollen aufweisen:

- Globaler Administrator
- Compliance-Administrator
- Sicherheitsadministrator
- Compliancedatenadministrator

### <a name="dlp-on-premises-scanner-prerequisites"></a>Voraussetzungen für den lokalen DLP-Scanner

- Der Azure Information Protection (AIP)-Scanner implementiert DLP-Richtlinienabgleich und -Richtliniendurchsetzung. Der Scanner wird als Teil des AIP-Clients installiert, sodass Ihre Installation alle Voraussetzungen für AIP, den AIP-Client und den AIP Unified Labeling-Scanner (Scanner für einheitliche Bezeichnungen) erfüllen muss.
- Bereitstellen des AIP-Clients und Scanners Weitere Informationen finden Sie unter: [Installieren des einheitlichen AIP-Bezeichnungsclients](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) und [], unter [Konfigurieren und Installieren des Azure Information Protection Unified Labeling-Scanners](/azure/information-protection/deploy-aip-scanner-configure-install).
- Es muss mindestens ein Etikett und eine Richtlinie im Mandanten veröffentlicht sein, auch wenn alle Ihre Erkennungsregeln nur auf vertraulichen Informationstypen basieren.

## <a name="deploy-the-dlp-on-premises-scanner"></a>Bereitstellen des lokalen DLP-Scanners

1. Folgen Sie den Anweisungen unter [Installieren des AIP Unified Labeling-Clients](/azure/information-protection/rms-client/install-unifiedlabelingclient-app). 
2. Folgen Sie den Anweisungen unter [Konfigurieren und Installieren des Azure Unified Labeling-Scanners](/azure/information-protection/deploy-aip-scanner-configure-install), um die Scannerinstallation abzuschließen.
    1. Die Konfiguration von Netzwerkerkennungsaufträgen ist ein optionaler Schritt. Sie können es überspringen und bestimmte Repositorys definieren, die in Ihrem Inhaltsscanauftrag gescannt werden sollen.
    2. Sie müssen einen Inhaltsscanauftrag erstellen und die Repositorys angeben, in denen Dateien gehostet werden, die vom DLP-Modul ausgewertet werden müssen.
    3. Aktivieren Sie DLP-Regeln im erstellten Inhaltsscanauftrag und setzen Sie die Option **Erzwingen** auf **Aus**, es sei denn, Sie möchten direkt mit der DLP-Durchsetzungsphase fortfahren.
3. Bestätigen Sie, das Ihr Inhaltsscanauftrag dem richtigen Cluster zugewiesen ist. Wenn Sie noch keinen Inhaltsscanauftrag erstellt haben, erstellen Sie einen neuen Auftrag und weisen Sie ihn dem Cluster zu, der die Scannerknoten enthält, auf denen die Public Preview-Version ausgeführt wird.

4. Stellen Sie eine Verbindung her zur [Azure Information Protection-Erweiterung im Azure-Portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) und fügen Sie Ihre Repositorys dem Inhaltsscanauftrag hinzu, der den Scan ausführt.

5. Führen Sie einen der folgenden Schritte aus, um den Scan auszuführen:
    1. Festlegen des Scannerzeitplans
    1. Verwenden der manuellen Option **Jetzt scannen** im Portal
    1. oder führen Sie das **Start-AIPScan** PowerShell Cmdlet aus

   > [!IMPORTANT]
   > Denken Sie daran, dass der Scanner standardmäßig einen Delta-Scan des Repositorys ausführt und die Dateien, die bereits im vorherigen Scan-Zyklus gescannt wurden, übersprungen werden, es sei denn, die Datei wurde geändert oder Sie haben einen vollständigen erneuten Scan eingeleitet. Ein vollständiger Rescan kann mithilfe der Option **Alle Dateien erneut scannen** in der Benutzeroberfläche oder durch Ausführen von **Start-AIPScan-Reset** eingeleitet werden.

6.  Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies) im Microsoft 365 Compliance Center.

7. Wählen Sie **Richtlinie erstellen** und erstellen Sie eine Test-DLP-Richtlinie. Weitere Informationen finden Sie unter [Erstellen einer DLP-Richtlinie aus einer Vorlage](create-a-dlp-policy-from-a-template.md) wenn Sie Hilfe beim Erstellen einer Richtlinie benötigen. Stellen Sie sicher, dass Sie es im Test ausführen, bis Sie mit diesem Feature vertraut sind. Verwenden Sie diese Parameter für Ihre Richtlinie:
    1. Scope die lokale DLP-Scannerregel bei Bedarf auf bestimmte Speicherorte. Wenn Sie **Speicherorte** auf **Alle** festlegen, unterliegen alle vom Scanner gescannten Dateien der DLP-Regelübereinstimmung und -durchsetzung.
    1. Bei der Angabe der Standorte können Sie entweder eine Ausschluss- oder eine Einschlussliste verwenden. Während der öffentlichen Vorschau können Sie nicht beide festlegen. Sie können entweder festlegen, dass die Regel nur für Pfade relevant ist, die mit einem der in der Einschlussliste aufgeführten Muster übereinstimmen, oder für alle Dateien mit Ausnahme der Dateien, die mit dem in der Einschlussliste aufgeführten Muster übereinstimmen. Es werden keine lokalen Pfade unterstützt. Hier sind einige Beispiele für gültige Pfade:
      - \\\server\share
      - \\\server\share\folder1\subfolderabc
      - \*\\folder1
      - \*secret\*.docx
      - \*secret\*.\*
      - https:// sp2010.local/sites/HR
      - https://\*/HR 
    3. Hier sind einige Beispiele für nicht akzeptable Werte:
      - \*
      - \*\\a
      - Aaa
      - c:\
      - C:\test

> [!IMPORTANT]
> Die Ausschlussliste hat Vorrang vor der Einschlussliste.

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a>Anzeigen von lokalen DLP-Scannerwarnungen im DLP-Verwaltungsdashboard unter Benachrichtigungen

1. Öffnen Sie die [Seite zur Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies) im Microsoft 365 Compliance Center und wählen Sie **Warnungen** aus.

2. Wenden Sie in [Konfigurieren und Anzeigen von Warnungen für DLP-Richtlinien](dlp-configure-view-alerts-policies.md) beschriebenen Verfahrensweisen an, um Warnungen für Ihre Endpunkt-DLP-Richtlinien anzuzeigen.

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a>Anzeigen des lokalen DLP-Scanners im Aktivitäten-Explorer und im Überwachungsprotokoll

> [!NOTE]
> Für den lokalen Scanner muss die Überwachung aktiviert sein. In Microsoft 365 ist die Überwachung standardmäßig aktiviert.

1. Öffnen Sie die Seite [Datenklassifizierung](https://compliance.microsoft.com/dataclassification?viewid=overview) für Ihre Domäne im Microsoft 365 Compliance Center und wählen Sie Aktivitäten-Explorer aus.

2. Beziehen Sie sich auf die Anweisungen unter [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md), um auf alle Daten für Ihre lokalen Scannerstandorte zuzugreifen und diese zu filtern.

3. Öffnen Sie das [Überwachungsprotokoll im Compliance Center](https://security.microsoft.com/auditlogsearch). Während der öffentlichen Vorschau sind die DLP-Regelübereinstimmungen in der Benutzeroberfläche des Überwachungsprotokolls verfügbar oder können über [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps)PowerShell aufgerufen werden. 


## <a name="next-steps"></a>Nächste Schritte
Nachdem Sie eine Testrichtlinie für lokale DLP-Standorte bereitgestellt haben und die Aktivitätsdaten im Aktivitäten-Explorer anzeigen können, können Sie mit dem nächsten Schritt fortfahren. Sie können nun DLP-Richtlinien erstellen, die Ihre vertraulichen Elemente schützen.

- [Verwendung von lokalem DLP (Vorschau)](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Siehe auch

- [Erfahren Sie mehr über den lokalen DLP-Scanner (Vorschau)](dlp-on-premises-scanner-learn.md)
- [Verwenden Sie den lokalen DLP-Scanner (Vorschau)](dlp-on-premises-scanner-use.md)
- [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md)
- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)
- [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md)
- [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)