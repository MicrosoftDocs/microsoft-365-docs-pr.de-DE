---
title: Einrichten erweiterter Sicherheitsrichtlinien für Microsoft 365 Business-Benutzer
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Einrichten von Office 365 Advanced Threat Protection und Schützen vertraulicher Daten.
ms.openlocfilehash: 4728e11a16fdf8a461f5687632df75699923f846
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "33663638"
---
# <a name="set-up-advanced-security-policies"></a>Einrichten erweiterter Sicherheitsrichtlinien

Zusätzlich zu den Richtlinien, die Sie im [Admin Center](security-features.md#microsoft-365-business-admin-center-security-features)einrichten können, können Sie durch Einrichten von [Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653) (ATP) zusätzlichen Schutz gegen Cyber-Bedrohungen hinzufügen. Sie können auch vertrauliche Informationen schützen, indem Sie [Data Loss Prevention](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP), Azure Information Protection (AIP), [Exchange Online-Archivierung](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)einrichten und Ihre Geräte im [InTune-Portal](#go-to-intune-admin-center)verwalten.

Eine Übersicht über die wichtigsten Möglichkeiten, wie Sie Ihr Unternehmen schützen können, finden Sie unter [Top 10 Ways to Secure Microsoft 365 Business Plan](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) , einschließlich der Verwendung von MFA, um eine zweite Form der Anmeldung zu erstellen.

Anweisungen für einfache Anweisungen finden Sie unter [Secure Your Business Training Videos](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787) .

## <a name="increase-email-malware-protection"></a>Mehr Schutz vor Schadsoftware für e-Mails

Schadsoftware ist Software, die ihre Computer oder Ihr Netzwerk beschädigen und möglicherweise Daten von Ihnen stehlen kann, einschließlich persönlicher oder kundenbezogener Informationen. Microsoft 365 Business umfasst eine Grundstufe des Schutzes vor Schadsoftware, aber Sie können diesen Schutz durch Einrichten zusätzlicher Einstellungen erweitern. Anweisungen dazu finden Sie unter Aktivieren des Schulungsvideos zur [Malware Erkennung](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0) .

## <a name="set-up-advanced-threat-protection-features"></a>Einrichten von Advanced Threat Protection-Features

- **Schutz vor** unsicheren Anlagen: ATP identifiziert böswillige Inhalte durch Öffnen von e-Mail-Anlagen in einer virtuellen Umgebung und Durchführen einer Analyse des resultierenden Verhaltens. Der Inhalt wird ausgewertet, um die Absicht zu ermitteln (normal oder bösartig), und ATP blockiert die Bereitstellung unsicherer Anhänge und schützt Sie vor Phishing-Schemata und Ransomware-Infektionen. Informationen zum Aktivieren des Anlagenschutzes finden Sie unter [Einrichten von Office 365 ATP Safe Attachments](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775) -Hilfedokumentation und [Schutz vor böswilligen Dateien](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) kurzes Schulungsvideo.
    
- **Schützen Sie Ihre Umgebung, wenn Benutzer auf böswillige Links klicken:** ATP untersucht auch Links in e-Mails zu dem Zeitpunkt, zu dem ein Benutzer darauf klickt. Wenn ein Link unsicher ist, wird der Benutzer gewarnt, die Website nicht zu besuchen oder zu benachrichtigen, dass die Website blockiert wurde. Dies schützt vor Phishing-Schemata. Um dies zu aktivieren, lesen Sie [Einrichten von Office 365 ATP Safe Links](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies) -Hilfedokumentation und [Schutz vor böswilligen Websites](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) kurzes Schulungsvideo.

- **Schützen Sie Ihre Umgebung vor einem Phishing-Versuch:**  ATP Anti-Phishing wendet eine Reihe von Computer Lernmodellen zusammen mit Identitätswechsel Erkennungsalgorithmen auf eingehende Nachrichten an, um Schutz vor Phishing-Angriffen zu bieten, bei denen jemand versucht, Informationen von Ihnen zu extrahieren, indem er vorgibt, eine bekannte Kontakt. Weitere Informationen finden Sie unter [Einrichten der ATP-](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies) Hilfedokumentation und [Schutz vor Phishing-versuchen](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c) kurzes Schulungsvideo.

## <a name="set-up-dlp-features"></a>Einrichten von DLP-Features

Ein Beispiel zum Einrichten einer Richtlinie zum Schutz vor personenbezogenen Informationen (PII) finden Sie unter [Erstellen einer DLP-Richtlinie aus einer Vorlage](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) . 
  
DLP enthält viele benutzerfreundliche Richtlinienvorlagen für viele verschiedene Gebietsschemas. Beispiel: Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. Sehen Sie sich an, [was die DLP-Richtlinienvorlagen](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) für eine vollständige Liste bieten. Alle diese Vorlagen können ähnlich wie das Beispiel für PII-Vorlagen aktiviert werden. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Einrichten der e-Mail-Aufbewahrung mit der Exchange Online-Archivierung

 Die **Exchange Online-Archivierungs** Lizenz Funktionen bieten Ihnen die Möglichkeit, Compliance-und regulatorische Standards beizubehalten, indem Sie e-Mail-Inhalte für eDiscovery-Zwecke erhalten. Außerdem können Sie Ihr Risiko bei Rechtsstreitigkeiten verringern und eine Möglichkeit zur Wiederherstellung von Daten nach einer Sicherheitsverletzung oder zur Wiederherstellung gelöschter Elemente bieten. Um diese Funktionen zu aktivieren, können Sie die Aufbewahrungszeit für den gesamten Inhalt eines Benutzers beibehalten oder Beibehaltungsrichtlinien für eine größere Anpassung verwenden. 
  
**Rechtsstreit:** Sie können alle Postfachinhalte, einschließlich gelöschter Elemente, beibehalten, indem Sie für ein vollständiges Postfach des Benutzers einen Rechtsstreit halten. 
    
So platzieren Sie ein Postfach im Verwaltungscenter:
    
1. Navigieren Sie im linken Navigationsbereich zu **Users** \> **Active Users**.
    
2. Wählen Sie einen Benutzer aus, dessen Postfach Sie für die Aufbewahrung von Rechtsstreitigkeiten festlegen möchten, und erweitern Sie im Benutzerbereich **e-Mail-Einstellungen** und neben **Weitere Einstellungen** die Option **Exchange-Eigenschaften bearbeiten**.
    
3. Wählen Sie auf der Seite Postfach für den Benutzer im linken Navigationsbereich * * Postfachfunktionen * * aus, und klicken Sie dann auf den Link **aktivieren** , um das **Verfahren**zu übernehmen.
    
4. Im Dialogfeld **Litigation** Hold können Sie die Dauer für die Beweissicherung im Feld **Prozessdauer** für die Beweissicherung angeben, Feld leer lassen, wenn Sie eine unendliche Halteposition platzieren möchten. Sie können auch Notizen hinzufügen und den Briefkasten Besitzer an eine Website weiterleiten, die Sie möglicherweise mehr über \> das Verfahren zum **Speichern**von Rechtsstreitigkeiten erklären müssen.
    
**Aufbewahrung:** Sie können angepasste Aufbewahrungsrichtlinien aktivieren, um beispielsweise eine bestimmte Zeitdauer beizubehalten oder Inhalte dauerhaft am Ende des Aufbewahrungszeitraums zu löschen. Weitere Informationen finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
## <a name="set-up-azure-information-protection-features"></a>Einrichten von Azure Information Protection-Features

Azure Information Protection (AIP) ist eine Cloud-basierte Lösung, die es einer Organisation ermöglicht, Ihre Dokumente und e-Mails durch Anwenden von Bezeichnungen zu klassifizieren und optional zu schützen. Bezeichnungen können von Administratoren automatisch angewendet werden, die Regeln und Bedingungen definieren, manuell von Benutzern oder eine Kombination, in der Benutzer Empfehlungen erhalten.

Die Möglichkeit zum Anwenden der folgenden Einschränkungen beim Senden von e-Mails in Outlook im Web wird automatisch für alle Benutzer aktiviert:
  
- **Nicht weiterleiten**: Empfänger können die Nachricht zwar lesen, aber nicht weiterleiten, drucken oder kopieren
    
- **Encrypt**: die gesamte Nachricht ist verschlüsselt. Empfänger müssen zusätzliche Schritte Unternehmen, um Ihre Identität zu bestätigen, bevor Sie auf verschlüsselte Inhalte zugreifen und die Verschlüsselung nicht entfernen können.
    
- **Vertraulich**: erteilt den Mitarbeitern in Ihrer Organisation vollständige Berechtigungen für die e-Mail-Inhalte und-Anhänge, jedoch nicht für Personen außerhalb Ihrer Organisation. Datenbesitzer können Inhalte jederzeit nachverfolgen und widerrufen.
    
- Streng **vertraulich**: Diese Einschränkung kann auf streng vertrauliche Daten angewendet werden, sodass Mitarbeiter die Daten anzeigen, bearbeiten und beantworten, aber nicht weiterleiten, drucken oder kopieren können. Datenbesitzer können Inhalte jederzeit nachverfolgen und widerrufen.

### <a name="make-sure-azure-information-protection-is-activated"></a>Stellen Sie sicher, dass Azure Information Protection aktiviert ist.

So überprüfen Sie, ob AIP aktiviert ist:

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com/)an.

2. Wählen Sie **alle Dienste** aus, und geben Sie *Azure Information Protection* in das **Suchfeld**ein.

3. Sobald die Ergebnisse angezeigt werden, klicken Sie auf den Start neben **Azure Information Protection** , um Sie zu einem bevorzugten und leicht zu findenden späteren Zeitpunkt zu machen.

4. Wählen Sie **Azure Information Protection** \> **Protection-Aktivierung** aus, und stellen Sie sicher, dass der Status auf Aktiviert festgelegt ist. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Anzeigen der Azure Information Protection-Richtlinie und der Standardbeschriftungen 

So können Sie die vorhandenen Beschriftungen anzeigen und ändern:

1. Wählen Sie auf dem Azure Information Protection- **** \> Dashboard **Bezeichnungen**für Klassifikationen aus. <br/>![Standard Beschriftungen für Azure Information Protection.](media/AIPLabels.png)

2. Sie können eine beliebige Bezeichnung wählen, um Optionen anzuzeigen, Sie können den Anzeigenamen, die Farben usw. ändern.
 
3. Weitere Informationen finden Sie unter [ändern und Erstellen neuer Bezeichnungen](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) , wenn Sie eigene erstellen möchten. 

### <a name="install-the-azure-information-protection-client-manually"></a>Manuelles Installieren des Azure Information Protection-Clients

So installieren Sie den AIP-Client manuell:

1. Laden Sie **AzInfoProtection. exe** aus dem [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018)herunter.
 
2. Sie können überprüfen, ob die Installation erfolgreich war, indem Sie ein Word-Dokument anzeigen und sicherstellen, dass die Option **Protect** auf der Registerkarte **Start** verfügbar ist. <br/>![Registerkarte Schutz in einem Word-Dokument.](media/Word_Protect.png)

Weitere Informationen finden Sie unter [Installieren des Clients](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).

## <a name="go-to-intune-admin-center"></a>Wechseln Sie zu InTune Admin Center

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com/)an.

2. Wählen Sie **alle Dienste** aus, und geben Sie in *InTune* in das **Suchfeld**ein.

3. Sobald die Ergebnisse angezeigt werden, klicken Sie auf den Start neben **Microsoft InTune** , um Sie zu einem bevorzugten und leicht zu findenden späteren Zeitpunkt zu machen.

Zusätzlich zum Admin Center können Sie InTune verwenden, um die Geräte Ihrer Organisation zu registrieren und zu verwalten. Weitere Informationen finden Sie unter [Capabilities by Enrollment Method for Windows Devices](https://docs.microsoft.com/intune/enrollment-method-capabs) and [Enrollment Options for Devices Managed by InTune](https://docs.microsoft.com/intune/enrollment-options).

## <a name="microsoft-secure-score"></a>Microsoft-Sicherheitsbewertung

