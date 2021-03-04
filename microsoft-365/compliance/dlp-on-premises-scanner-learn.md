---
title: Informationen zum lokalen Microsoft 365-DLP-Scanner (Data Loss Prevention, Verhinderung von Datenverlust) (Vorschau)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: Der lokale Scanner zur Verhinderung von Datenverlust in Microsoft 365 erweitert die Überwachung von Dateiaktivitäten und Schutzmaßnahmen für diese Dateien auf lokale Dateifreigaben sowie SharePoint-Ordner und Dokumentbibliotheken. Dateien werden mit dem Azure Information Protection (AIP) -Scanner gescannt und geschützt
ms.openlocfilehash: 996de5ea640a16ef2a250830d7167aa316b54a21
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50417359"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Erfahren Sie mehr über den lokalen Microsoft 365-Scanner zur Verhinderung von Datenverlust (Vorschau)

Der lokale Scanner zur Verhinderung von Datenverlust von Microsoft ist Teil der Microsoft 365 DLP-Suite (Data Loss Prevention), mit der Sie vertrauliche Elemente in allen Microsoft 365-Diensten erkennen und schützen können. Weitere Informationen zu den Microsoft-DLP-Angeboten finden Sie unter [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md).

Der **lokale DLP-Scanner** durchsucht lokale ruhende Daten in Dateifreigaben und SharePoint-Dokumentbibliotheken und -Ordnern nach vertraulichen Elementen, die bei einer undichten Stelle ein Risiko für Ihr Unternehmen darstellen oder das Risiko eines Verstoßes gegen Compliance-Richtlinien darstellen. Dies gibt Ihnen die Sichtbarkeit und Kontrolle, die Sie benötigen, um sicherzustellen, dass sensible Elemente ordnungsgemäß verwendet und geschützt werden, und um riskantes Verhalten zu vermeiden, das sie gefährden könnte. Der lokale DLP-Scanner erkennt vertrauliche Informationen mithilfe [integrierter](sensitive-information-type-entity-definitions.md) oder [benutzerdefinierter vertraulicher Informations](create-a-custom-sensitive-information-type.md)typen, [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) oder Dateieigenschaften. Die Informationen darüber, was Benutzer mit vertraulichen Elementen tun, werden im [Aktivitäts-Explorer](data-classification-activity-explorer.md) sichtbar gemacht, und Sie können Schutzaktionen für diese Elemente über [DLP-Richtlinien](create-test-tune-dlp-policy.md) erzwingen.

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a>Der lokale DLP-Scanner basiert auf dem Azure Information Protection-Scanner

Der lokale DLP-Scanner basiert auf einer vollständigen Implementierung des Azure Information Protection (AIP) -Scanners, um vertrauliche Elemente zu überwachen, zu kennzeichnen und zu schützen. Wenn Sie mit dem AIP-Scanner nicht vertraut sind, empfehlen wir Ihnen dringend, sich mit ihm vertraut zu machen. Weitere Informationen finden Sie in diesen Artikeln:

- [Was ist Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Was ist der Azure Information Protection-Scanner für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)
- [Anforderungen für die Installation und Bereitstellung des einheitlichen Azure Information Protection-Scanner für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-prereqs)
- [Lernprogramm: Installieren des Azure Information Protection-Scanner für einheitliche Bezeichnungen (AIP)](https://docs.microsoft.com/azure/information-protection/tutorial-install-scanner)
- [Konfigurieren und Installieren des Azure Information Protection-Scanners für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)
- [ Azure Information Protection-Client für einheitliche Bezeichnungen – Versionsverlauf und Supportrichtlinie](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a>Lokale DLP-Scanneraktionen

Der lokale DLP-Scanner erkennt Dateien mit einer der folgenden vier Methoden:

- Vertrauliche Informationstypen
- Vertraulichkeitsbezeichnungen
- Dateierweiterung
- Benutzerdefinierte Dokumenteigenschaften nur für Office-Dateien 

Wenn eine erkannte Datei ein potenzielles Risiko darstellt, wenn sie durchgesickert ist oder gegen die Compliance-Richtlinien verstößt, kann der lokale DLP-Scanner eine dieser vier Aktionen ausführen.

|Aktion |Beschreibung  |
|---------|---------|
|**Verhindern Sie, dass diese Personen auf Dateien zugreifen, die im lokalen Scanner gespeichert sind – Jeder** | Wenn diese Aktion erzwungen wird, blockiert sie den Zugriff auf alle Konten mit Ausnahme des Inhaltseigentümers, des letzten Kontos, das das Element geändert hat, und des Administrators. Dazu werden alle Konten aus den NTFS/SharePoint-Berechtigungen auf Dateiebene entfernt, mit Ausnahme des Dateieigentümers, des Repository-Eigentümers (festgelegt in der Einstellung [Repository-Eigentümer festlegen](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) im Inhaltsscanauftrag), des letzten Modifikators (kann nur in SharePoint identifiziert werden) und des Administrators. Dem Scannerkonto werden auch FC-Rechte für die Datei gewährt.|
|**Blockieren Sie den Zugriff dieser Personen auf Dateien, die im lokalen Scanner gespeichert sind. Blockieren Sie den organisationsweiten (öffentlichen) Zugriff**    |Wenn diese Aktion erzwungen wird, werden die SIDs **_Jeder_*_, _*_NT-AUTORITÄT \ authentifizierte Benutzer_*_, und _*_Domänenbenutzer_** aus der ACL (File Access Control List) entfernt. Nur Benutzer und Gruppen, denen explizit Rechte für die Datei oder den übergeordneten Ordner gewährt wurden, können auf die Datei zugreifen.|
|**Berechtigungen für die Datei festlegen**|Wenn diese Aktion erzwungen wird, erzwingt sie, dass die Datei die Berechtigungen ihres übergeordneten Ordners erbt. Standardmäßig wird diese Aktion nur erzwungen, wenn die Berechtigungen für den übergeordneten Ordner restriktiver sind als die Berechtigungen, die bereits in der Datei enthalten sind. Wenn beispielsweise die ACL in der Datei so eingestellt ist, dass nur **_bestimmte Benutzer_*_ zugelassen sind und der übergeordnete Ordner so konfiguriert ist, dass die Gruppe*_Domänenbenutzer_*_ zulässig ist, werden die Berechtigungen des übergeordneten Ordners nicht von der Datei geerbt. Sie können dieses Verhalten überschreiben, indem Sie die Option _* Erben, auch wenn übergeordnete Berechtigungen weniger restriktiv sind** auswählen.|
|**Entfernen der Datei von einem falschen Speicherort**|Wenn diese Aktion erzwungen wird, ersetzt sie die Originaldatei durch eine Stub-Datei mit der Erweiterung .txt und legt eine Kopie der Originaldatei in einem Quarantäneordner ab. 

## <a name="whats-different-in-the-on-premises-scanner"></a>Was ist anders im lokalen Scanner?

Es gibt einige zusätzliche Konzepte, die Sie kennen müssen, bevor Sie sich mit dem lokalen Scanner befassen.

### <a name="aip-repositories-and-content-scan-jobs"></a>AIP-Repositorys und Inhaltsscanaufträge

Sie müssen einen AIP-Inhaltsscanauftrag erstellen und die Repositorys identifizieren, in denen sich die Dateien befinden, die von dem DLP-Modul ausgewertet werden sollen. Stellen Sie sicher, dass Sie DLP-Regeln im erstellten AIP-Inhaltsscanauftrag aktivieren.

### <a name="policy-tips"></a>Richtlinientipps

[Richtlinientipps](use-notifications-and-policy-tips.md) sind für lokale Scanner nicht verfügbar.


### <a name="viewing-dlp-on-premises-scanner-events"></a>Anzeigen von lokalen DLP-Scannerereignissen

Sie können die lokalen DLP-Scannerdaten im M365 Compliance Center-[Aktivitäts-Explorer](data-classification-activity-explorer.md) anzeigen. 

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie sich mit dem lokalen DLP-Scanner vertraut gemacht haben, sind Ihre nächsten Schritte:

1. [Erste Schritte mit dem lokalen DLP-Scanner](dlp-on-premises-scanner-get-started.md)
2. [Verwenden Sie den lokalen DLP-Scanner](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit dem lokalen Microsoft-Scanner zur Verhinderung von Datenverlust](dlp-on-premises-scanner-get-started.md)
- [Verwenden Sie den lokalen Scanner zur Verhinderung von Datenverlust von Microsoft](dlp-on-premises-scanner-use.md)
- [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md)
- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)
- [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md)
