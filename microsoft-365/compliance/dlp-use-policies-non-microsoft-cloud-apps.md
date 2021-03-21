---
title: Verwenden von Richtlinien zur Verhinderung von Datenverlust für Nicht-Microsoft-Cloud-Apps (Vorschau)
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
description: Erfahren Sie, wie Sie dlp-Richtlinien für Nicht-Microsoft-Cloud-Apps verwenden.
ms.openlocfilehash: 6787add3ef8b2d6ded22bd05c0ff9658c4b7fbfc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922081"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Verwenden von Richtlinien zur Verhinderung von Datenverlust für Nicht-Microsoft-Cloud-Apps (Vorschau)

#A0 (Data Loss Prevention, Verhinderung von Datenverlust) für Nicht-Microsoft-Cloud-Apps sind Teil der Microsoft 365 DLP-Suite mit Features. Mithilfe dieser Features können Sie vertrauliche Elemente in microsoft 365-Diensten ermitteln und schützen. Weitere Informationen zu allen Microsoft DLP-Angeboten finden Sie unter [Overview of data loss prevention](./data-loss-prevention-policies.md?view=o365-worldwide).

Sie können DLP-Richtlinien verwenden, um Nicht-Microsoft-Cloud-Apps zu überwachen und zu erkennen, wenn vertrauliche Elemente über Nicht-Microsoft-Cloud-Apps verwendet und freigegeben werden. Die Verwendung dieser Richtlinien bietet Ihnen die Sichtbarkeit und Kontrolle, die Sie sicherstellen müssen, dass sie ordnungsgemäß verwendet und geschützt sind, und verhindert riskantes Verhalten, das sie gefährden könnte.

## <a name="before-you-begin"></a>Vorabinformationen

### <a name="skusubscriptions-licensing"></a>SKU/Abonnement-Lizenzierung

Bevor Sie mit der Verwendung von DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps beginnen, bestätigen Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und alle Add-Ons. Um auf diese Funktionalität zu zugreifen und diese zu verwenden, benötigen Sie eines der folgenden Abonnements oder Add-Ons:

- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 Security

### <a name="prepare-your-cloud-app-security-environment"></a>Vorbereiten Ihrer Cloud App Security-Umgebung

DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps verwenden Cloud App Security DLP-Funktionen. Um es zu verwenden, sollten Sie Ihre Cloud App Security-Umgebung vorbereiten. Anweisungen finden Sie unter [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).

### <a name="connect-a-non-microsoft-cloud-app"></a>Verbinden einer Nicht-Microsoft-Cloud-App

Um die DLP-Richtlinie für eine bestimmte Cloud-App zu verwenden, die keine Microsoft-App ist, muss die App mit Cloud App Security verbunden sein. Diesbezügliche Informationen finden Sie unter:

- [Connect Box](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Verbinden von Dropbox](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Connect G-Suite](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Verbinden von Salesforce](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Verbinden von Cisco Webex](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

Nachdem Sie Ihre Cloud-Apps mit Cloud App Security verbinden, können Sie für sie Microsoft 365-DLP-Richtlinien erstellen.

>[!NOTE]
>Es ist auch möglich, Microsoft Cloud App Security zum Erstellen von DLP-Richtlinien für Microsoft-Cloud-Apps zu verwenden. Es wird jedoch empfohlen, Microsoft 365 zum Erstellen und Verwalten von DLP-Richtlinien für Microsoft-Cloud-Apps zu verwenden.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Erstellen einer DLP-Richtlinie für eine Nicht-Microsoft-Cloud-App

Wenn Sie einen Speicherort für die DLP-Richtlinie auswählen, aktivieren Sie den **Microsoft Cloud App Security-Speicherort.**

- Wählen Sie Instanz auswählen aus, um eine bestimmte App oder Instanz **auszuwählen.**
- Wenn Sie keine Instanz auswählen, verwendet die Richtlinie alle verbundenen Apps in Ihrem Microsoft Cloud App Security-Mandanten.

   ![Speicherorte, an die die Richtlinie angewendet werden soll](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US und Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

Sie können verschiedene Aktionen für jede unterstützte Nicht-Microsoft-Cloud-App auswählen. Für jede App gibt es verschiedene mögliche Aktionen (abhängig von der Cloud-App-API).

![Regel erstellen](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

Wenn Sie eine Regel in der DLP-Richtlinie erstellen, können Sie eine Aktion für Nicht-Microsoft-Cloud-Apps auswählen. Um Apps von Drittanbietern einzuschränken, wählen Sie Apps von **Drittanbietern einschränken aus.**

![Einschränken von Drittanbieter-Apps](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

Informationen zum Erstellen und Konfigurieren von DLP-Richtlinien finden Sie unter [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).

## <a name="see-also"></a>Siehe auch

- [Erstellen von Tests und Optimieren einer DLP-Richtlinie](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [Erste Schritte mit der standardmäßigen DLP-Richtlinie](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [Erstellen einer DLP-Richtlinie aus einer Vorlage](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)