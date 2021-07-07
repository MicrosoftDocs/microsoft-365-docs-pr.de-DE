---
title: Verwenden von Richtlinien zur Verhinderung von Datenverlust für Nicht-Microsoft-Cloud-Apps
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps verwenden.
ms.openlocfilehash: 4bda45a6da6b9626391da37eb9a806b3308c5e7f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322317"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps"></a>Verwenden von Richtlinien zur Verhinderung von Datenverlust für Nicht-Microsoft-Cloud-Apps

Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) für Nicht-Microsoft-Cloud-Apps sind Teil der Microsoft 365 DLP-Suite von Features. Mithilfe dieser Features können Sie vertrauliche Elemente in Microsoft 365 Diensten ermitteln und schützen. Weitere Informationen zu allen Microsoft DLP-Angeboten finden Sie unter ["Verhinderung von Datenverlust".](dlp-learn-about-dlp.md)

Sie können DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps verwenden, um zu überwachen und zu erkennen, wann vertrauliche Elemente über Nicht-Microsoft-Cloud-Apps verwendet und freigegeben werden. Die Verwendung dieser Richtlinien bietet Ihnen die Sichtbarkeit und Kontrolle, die Sie benötigen, um sicherzustellen, dass sie ordnungsgemäß verwendet und geschützt werden, und es hilft, riskantes Verhalten zu verhindern, das sie beeinträchtigen könnte.

## <a name="before-you-begin"></a>Vorabinformationen

### <a name="skusubscriptions-licensing"></a>SKU/Abonnement-Lizenzierung

Bevor Sie mit der Verwendung von DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps beginnen, bestätigen Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und alle Add-Ons. Um auf diese Funktionalität zugreifen und diese verwenden zu können, benötigen Sie eines der folgenden Abonnements oder Add-Ons:

- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 Security

### <a name="permissions"></a>Berechtigungen
Der Benutzer, der die DLP-Richtlinie erstellt, sollte Folgendes sein:
- Globaler Administrator
- Complianceadministrator
- Compliancedatenadministrator

### <a name="prepare-your-cloud-app-security-environment"></a>Vorbereiten der Cloud App Security Umgebung

DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps verwenden Cloud App Security DLP-Funktionen. Um sie zu verwenden, sollten Sie Ihre Cloud App Security Umgebung vorbereiten. Anweisungen finden Sie unter [Festlegen der sofortigen Sichtbarkeit, des Schutzes und der Governanceaktionen für Ihre Apps.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)

### <a name="connect-a-non-microsoft-cloud-app"></a>Verbinden einer Nicht-Microsoft-Cloud-App

Damit die DLP-Richtlinie für eine bestimmte Nicht-Microsoft-Cloud-App verwendet werden kann, muss die App mit Cloud App Security verbunden sein. Diesbezügliche Informationen finden Sie unter:

- [Verbinden Box](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Verbinden Dropbox](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Verbinden G-Suite](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Verbinden Salesforce](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Verbinden Cisco Webex](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

Nachdem Sie Ihre Cloud-Apps mit Cloud App Security verbunden haben, können Sie Microsoft 365 DLP-Richtlinien für sie erstellen.

> [!NOTE]
> Es ist auch möglich, Microsoft Cloud App Security zum Erstellen von DLP-Richtlinien für Microsoft-Cloud-Apps zu verwenden. Es wird jedoch empfohlen, Microsoft 365 zum Erstellen und Verwalten von DLP-Richtlinien für Microsoft-Cloud-Apps zu verwenden.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Erstellen einer DLP-Richtlinie für eine Nicht-Microsoft-Cloud-App

Wenn Sie einen Speicherort für die DLP-Richtlinie auswählen, aktivieren Sie den **Microsoft Cloud App Security** Speicherort.

- Um eine bestimmte App oder Instanz auszuwählen, wählen Sie **"Instanz auswählen"** aus.
- Wenn Sie keine Instanz auswählen, verwendet die Richtlinie alle verbundenen Apps in Ihrem Microsoft Cloud App Security Mandanten.

   ![Speicherorte, an denen die Richtlinie angewendet werden soll](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US und Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

Sie können für jede unterstützte Nicht-Microsoft-Cloud-App verschiedene Aktionen auswählen. Für jede App gibt es verschiedene mögliche Aktionen (abhängig von der Cloud-App-API).

![Regel erstellen](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

Wenn Sie eine Regel in der DLP-Richtlinie erstellen, können Sie eine Aktion für Nicht-Microsoft-Cloud-Apps auswählen. Um Drittanbieter-Apps einzuschränken, wählen Sie **"Drittanbieter-Apps einschränken" aus.**

![Einschränken von Drittanbieter-Apps](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> DLP-Richtlinien, die auf Nicht-Microsoft-Apps angewendet werden, verwenden Microsoft Cloud App Security. Wenn die DLP-Richtlinie für eine Nicht-Microsoft-App erstellt wird, wird dieselbe Richtlinie automatisch in Microsoft Cloud App Security erstellt.

Informationen zum Erstellen und Konfigurieren von DLP-Richtlinien finden Sie unter ["Erstellen von Tests und Optimieren einer DLP-Richtlinie".](./create-test-tune-dlp-policy.md)

## <a name="see-also"></a>Siehe auch

- [Erstellen von Tests und Optimieren einer DLP-Richtlinie](./create-test-tune-dlp-policy.md)
- [Erste Schritte mit der standardmäßigen DLP-Richtlinie](./get-started-with-the-default-dlp-policy.md)
- [Erstellen einer DLP-Richtlinie aus einer Vorlage](./create-a-dlp-policy-from-a-template.md)
