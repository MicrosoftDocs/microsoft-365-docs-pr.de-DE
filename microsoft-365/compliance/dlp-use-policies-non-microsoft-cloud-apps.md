---
title: Verwenden von Richtlinien zur Verhinderung von Datenverlust für nicht-Microsoft-Cloud-Apps (Vorschau)
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
description: Hier erfahren Sie, wie Sie DLP-Richtlinien für nicht-Microsoft-Cloud-Apps verwenden.
ms.openlocfilehash: dd5a7a4bc0725d0785daec6b7635047cd91f20a2
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422734"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Verwenden von Richtlinien zur Verhinderung von Datenverlust für nicht-Microsoft-Cloud-Apps (Vorschau)

DLP-Richtlinien (Data Loss Prevention) für nicht-Microsoft-Cloud-apps sind Teil der Microsoft 365 DLP-Suite mit Features; Mithilfe dieser Funktionen können Sie vertrauliche Elemente in Microsoft 365-Diensten ermitteln und schützen. Weitere Informationen zu allen Microsoft DLP-Angeboten finden Sie unter [Übersicht über Verhinderung von Datenverlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).

Sie können DLP-Richtlinien für nicht-Microsoft-Cloud-Apps verwenden, um zu überwachen und zu erkennen, wann vertrauliche Elemente verwendet und über nicht-Microsoft-Cloud-apps freigegeben werden. Durch die Verwendung dieser Richtlinien erhalten Sie die Sichtbarkeit und Kontrolle, die Sie benötigen, um sicherzustellen, dass Sie ordnungsgemäß verwendet und geschützt werden, und Sie können riskantes Verhalten verhindern, das Sie gefährden kann.

## <a name="before-you-begin"></a>Vorabinformationen

### <a name="skusubscriptions-licensing"></a>SKU/Abonnement-Lizenzierung

Bevor Sie mit der Verwendung von DLP-Richtlinien für nicht-Microsoft-Cloud-apps beginnen, müssen Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und alle Add-ons bestätigen. Für den Zugriff auf und die Verwendung dieser Funktion benötigen Sie eines der folgenden Abonnements oder Add-ons:

- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 Security

### <a name="prepare-your-cloud-app-security-environment"></a>Vorbereiten der Cloud-App-Sicherheitsumgebung

DLP-Richtlinien für nicht-Microsoft-Cloud-Apps verwenden Cloud App Security DLP-Funktionen. Um Sie zu verwenden, sollten Sie Ihre Cloud-App-Sicherheitsumgebung vorbereiten. Anweisungen finden Sie unter [Festlegen von isntant-Sichtbarkeits-, Schutz-und Steuerungsaktionen für Ihre apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).

### <a name="connect-a-non-microsoft-cloud-app"></a>Verbinden einer nicht-Microsoft-Cloud-App

Damit die DLP-Richtlinie für eine bestimmte nicht-Microsoft-Cloud-App verwendet werden kann, muss die APP mit der Cloud-App-Sicherheit verbunden sein. Diesbezügliche Informationen finden Sie unter:

- [Feld "verbinden"](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Dropbox verbinden](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Connect G-Suite](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Verbinden von Salesforce](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Verbinden von Cisco WebEx](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

Nachdem Sie Ihre Cloud-apps mit der Cloud-App-Sicherheit verbunden haben, können Sie Microsoft 365 DLP-Richtlinien für diese erstellen.

>[!NOTE]
>Es ist auch möglich, mithilfe von Microsoft Cloud App Security DLP-Richtlinien für Microsoft Cloud-apps zu erstellen. Es wird jedoch empfohlen, Microsoft 365 zum Erstellen und Verwalten von DLP-Richtlinien in Microsoft Cloud-apps zu verwenden.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Erstellen einer DLP-Richtlinie für eine nicht von Microsoft erstellte Cloud-App

Wenn Sie einen Speicherort für die DLP-Richtlinie auswählen, aktivieren Sie den **Microsoft Cloud-App-Sicherheits** Speicherort.

- Zum Auswählen einer bestimmten app oder Instanz wählen Sie **Instanz auswählen**aus.
- Wenn Sie keine Instanz auswählen, verwendet die Richtlinie alle verbundenen apps in Ihrem Microsoft Cloud-App-Sicherheits Mandanten.

   ![Standorte zum Anwenden der Richtlinie](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US und Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

Sie können verschiedene Aktionen für jede unterstützte nicht-Microsoft-Cloud-App auswählen. Für jede APP gibt es verschiedene mögliche Aktionen (abhängig von der Cloud-App-API).

![Regel erstellen](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

Wenn Sie eine Regel in der DLP-Richtlinie erstellen, können Sie eine Aktion für nicht-Microsoft-Cloud-apps auswählen. Um Drittanbieter-apps einzuschränken, wählen Sie **Apps für Drittanbieter einschränken**aus.

![Einschränken von Drittanbieter-apps](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

Informationen zum Erstellen und Konfigurieren von DLP-Richtlinien finden Sie unter [Create Test and Tune a DLP Policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).

## <a name="see-also"></a>Siehe auch

- [Erstellen von Tests und Optimieren einer DLP-Richtlinie](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [Erste Schritte mit der standardmäßigen DLP-Richtlinie](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [Erstellen einer DLP-Richtlinie aus einer Vorlage](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
