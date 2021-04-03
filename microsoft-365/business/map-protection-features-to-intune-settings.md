---
title: Wie werden Schutzfunktionen in Microsoft 365 Business Premium den Intune-Einstellungen zugewiesen?
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
ms.date: 8/13/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Erfahren Sie, wie Schutzfunktionen in Microsoft 365 Business Premium intune-Einstellungen zuordnungen. Mit dem Abonnement erhalten Sie eine Lizenz zum Ändern von Intune-Einstellungen.
ms.openlocfilehash: 9a6dcf014e009389e49860fa96486c264c22f501
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580112"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>Wie werden Schutzfunktionen in Microsoft 365 Business Premium den Intune-Einstellungen zugewiesen?

## <a name="android-and-ios-application-protection-settings"></a>Schutzeinstellungen für Android- und iOS-Anwendungen

In der folgenden Tabelle ist die Zuordnung von Android- und iOS-Einstellungen der Anwendungsschutzrichtlinie zu Intune-Einstellungen detailliert ausgeführt.
  
Um die Intune-Einstellung zu finden, melden Sie sich mit Ihren Microsoft 365 Business Premium-Administratoranmeldeinformationen an, und wechseln Sie zu **Admin Center** und dann **zu Intune**.
  
 > [!IMPORTANT]
 > 
 > Mit einem Microsoft 365 Business Premium-Abonnement erhalten Sie eine Lizenz zum Ändern aller Intune-Einstellungen. Erste [Schritte finden Sie unter Einführung in Intune.](/intune/introduction-intune)
  
Wählen Sie den richtliniennamen, den Sie z. B. Anwendungsrichtlinie für Android verwenden &mdash; &mdash; möchten, und wählen Sie dann **Richtlinieneinstellungen aus.**
  
Unter **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**
  
|**Anwendungsrichtlinieneinstellung in Android oder iOS**|**Intune-Einstellung(en)**|
|:-----|:-----|
|Arbeitsdateien von einem inaktiven Gerät löschen nach  <br/> |Offline-Intervall (in Tagen), bevor App-Daten zurückgesetzt werden  <br/> |
|Benutzer zum Speichern von Arbeitsdateien auf OneDrive for Business zwingen  <br/> Beachten Sie, dass nur OneDrive for Business zulässig ist  <br/> |Speicherdienste zum Speichern von Unternehmensdaten auswählen  <br/> |
|||
   
Unter **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten**
  
|**Anwendungsrichtlinieneinstellung in Android oder iOS**|**Intune-Einstellung(en)**|
|:-----|:-----|
|Arbeitsdateien von einem inaktiven Gerät löschen nach  <br/> |Offline-Intervall (in Tagen), bevor App-Daten zurückgesetzt werden  <br/> |
|Benutzer zum Speichern von Arbeitsdateien auf OneDrive for Business zwingen  <br/> Beachten Sie, dass nur OneDrive for Business zulässig ist  <br/> |Speicherdienste zum Speichern von Unternehmensdaten auswählen  <br/> |
|Arbeitsdateien verschlüsseln  <br/> |App-Daten verschlüsseln  <br/> |
|Unter **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten** <br/> ||
|Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern  <br/> | PIN für Zugriff anfordern  <br/>  Dadurch werden zugleich diese Einstellungen festgelegt:  <br/> **Einfache PIN zulassen** auf **Ja** <br/> **PIN-Länge** auf 4  <br/> **Fingerabdruck anstelle von PIN zulassen** auf **Ja** <br/> **App PIN deaktivieren, wenn Geräte-PIN verwaltet wird** auf **Nein** <br/> |
|Pin zurücksetzen, wenn die Anmeldung so oft fehlschlägt (dies ist deaktiviert, wenn keine PIN erforderlich ist)  <br/> |Anzahl der Versuche vor dem Zurücksetzen der PIN  <br/> |
|Benutzer müssen sich erneut anmelden, nachdem sich Office-Apps im Leerlauf befinden (dies ist deaktiviert, wenn keine PIN erforderlich ist)  <br/> | Zugriffsanforderungen nach (Minuten) erneut überprüfen  <br/>  Dadurch werden zugleich diese Einstellungen festgelegt:  <br/> **Timeout** wird auf Minuten festgelegt  <br/>  Die Anzahl Minuten entspricht der Einstellung in Microsoft 365 Business.  <br/> **Offline-Toleranzperiode** ist standardmäßig auf 720 Minuten festgelegt  <br/> |
|Zugriff auf Arbeitsdateien auf Geräten mit entfernten Nutzungsbeschränkungen verweigern  <br/> |Ausführen verwalteter Apps auf Geräten mit Jailbreak oder Rootzugriff blockieren  <br/> |
|Benutzern das Kopieren von Inhalten aus Office-Apps in persönliche Apps erlauben  <br/> | Ausschneiden, Kopieren und Einfügen mit anderen Apps einschränken  <br/>  Wenn die Microsoft 365 Business Premium-Option auf **Ein** festgelegt ist, werden diese drei Optionen auch auf **Alle Apps** in Intune festgelegt:  <br/> **Zulassen, dass die App Daten an andere Apps überträgt** <br/> **Zulassen, dass die App Daten von anderen Apps empfängt** <br/> **Ausschneiden, Kopieren und Einfügen mit anderen Apps einschränken** <br/>  Wenn die Option Microsoft 365 Business auf **Ein** festgelegt ist, werden alle Intune-Optionen wie folgt festgelegt:  <br/> **Zulassen, dass die App Daten an andere Apps überträgt** wird auf **Richtlinienverwaltete Apps** festgelegt <br/> **Zulassen, dass die App Daten von anderen Apps empfängt** wird auf **Alle Apps** festgelegt <br/> **Ausschneiden, Kopieren und Einfügen mit anderen Apps einschränken** wird auf **Richtlinienverwaltete Apps mit Einfügen** festgelegt <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Einstellungen zum Anwendungsschutz in Windows 10

In der folgenden Tabelle ist die Zuordnung von Windows 10-Einstellungen der Anwendungsschutzrichtlinie zu Intune-Einstellungen detailliert ausgeführt.
  
Um die Intune-Einstellung zu finden, melden Sie sich mit Ihren Microsoft 365 Business Premium-Administratoranmeldeinformationen an, und wechseln Sie zum [Azure-Portal](https://portal.azure.com). Wählen **Sie Weitere Dienste** aus, und geben Sie Intune in den Filter **ein.** Wählen **Sie Intune App Protection** App Policy \> **aus.**
  
 > [!IMPORTANT]
 >
 >Mit einem Microsoft 365 Business Premium-Abonnement können Sie nur die Intune-Einstellungen ändern, die den in Microsoft 365 Business Premium verfügbaren Einstellungen zugewiesen sind. 
  
Um die verfügbaren Einstellungen zu erkunden, wählen Sie den gewünschten Richtliniennamen aus, und wählen Sie dann im linken Navigationsbereich **allgemeine, Zuweisungen,** zugelassene **Apps,** Apps ausschalten, Erforderliche Einstellungen oder **Erweiterte** Einstellungen aus. 
  
|**Anwendungsrichtlinieneinstellung in Windows 10**|**Intune-Einstellung(en)**|
|:-----|:-----|
|Arbeitsdateien verschlüsseln  <br/> |**Erweiterte Einstellungen** \> **Datenschutz**: **Beim Aufheben der Registrierung Verschlüsselungsschlüssel widerrufen** und **Zugriff auf geschützte Daten widerrufen, wenn das Gerät bei MDM registriert wird** sind beide auf **Ein** festgelegt.  <br/> |
|Verhindern, dass Benutzer Unternehmensdaten in persönliche Dateien kopieren.  <br/> |**Erforderliche Einstellungen** \> **Windows Information Protection-Modus**. **On** in Microsoft 365 Business Premium ordnet zu: **Außerkraftsetzungen** ausblenden , **Aus** in Microsoft 365 Business Premium ordnet zu: **Aus**.  <br/> |
|Zugriffssteuerung auf Office-Dokumente  <br/> | Wenn dies in Microsoft 365 Business Premium auf **Ein** festgelegt ist,  <br/> **Erweiterte Einstellungen** \> **Zugriff**, **Verwenden Sie Windows Hello for Business als Methode zum Anmelden bei Windows** auf **Ein** festgelegt, wobei die folgenden zusätzlichen Einstellungen gelten:  <br/> **Legen Sie die für die PIN erforderliche Mindestanzahl an Zeichen fest** ist auf **4** festgelegt.  <br/> **Konfigurieren Sie die Verwendung von Großbuchstaben in der Windows Hello for Business-PIN** ist auf **Verwendung von Großbuchstaben für die PIN nicht zulassen** festgelegt.  <br/> **Konfigurieren Sie die Verwendung von Kleinbuchstaben in der Windows Hello for Business-PIN** ist auf **Verwendung von Kleinbuchstaben für die PIN nicht zulassen** festgelegt.  <br/> **Konfigurieren Sie die Verwendung von Sonderzeichen in der Windows Hello for Business-PIN** ist auf **Verwendung von Sonderzeichen für die PIN nicht zulassen** festgelegt.  <br/> **Geben Sie den Zeitraum (in Tagen)** an, für den eine PIN verwendet werden kann, bevor das System erfordert, dass der Benutzer die Änderung auf **0 festgelegt hat.**  <br/> **Geben Sie die Anzahl der letzten PINs an, die einem Benutzerkonto zugeordnet und nicht wiederverwendet werden können** ist auf **0** festgelegt.  <br/> **Zulässige Anzahl von Authentifizierungsfehlern, bevor das Gerät zurückgesetzt wird** ist auf den gleichen Wert wie in Microsoft 365 Business festgelegt (standardmäßig 5).  <br/> **Die maximal zulässige Zeit (in Minuten) nach dem Wechsel des Gerät in den Leerlauf, bis das Gerät durch die PIN oder ein Kennwort gesperrt wird** ist auf den gleichen Wert wie in Microsoft 365 Business festgelegt.  <br/> |
|Wiederherstellung geschützter Daten aktivieren  <br/> |**Erweiterte Einstellungen** \> **Datenschutz**: **Zeigen Sie das Datenschutzsymbol des Unternehmens an** und **Verwenden Sie Azure RMS für WIP** sind auf **Ein** festgelegt.  <br/> |
|Weitere Cloudspeicherorte des Unternehmens schützen  <br/> |**Erweiterte Einstellungen** \> **Geschützte Domänen** und **Cloudressourcen** zeigen Domänen und SharePoint-Websites an.  <br/> |
|Von diesen Apps verwendete Dateien werden geschützt  <br/> |Die Liste der geschützten Apps ist in **Zugelassene Apps** aufgeführt.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Geräterichtlinieneinstellungen in Windows 10

In der folgenden Tabelle ist die Zuordnung von Windows 10-Einstellungen der Gerätekonfiguration zu Intune-Einstellungen detailliert ausgeführt.
  
Um die Intune-Einstellung zu finden, melden Sie sich mit Ihren Microsoft 365 Business Premium-Administratoranmeldeinformationen an, und wechseln Sie zum [Azure-Portal,](https://portal.azure.com)wählen Sie dann **Weitere** Dienste aus, und geben Sie Intune in den **Filter** ein, wählen Sie  \> **Intune-Gerätekonfigurationsprofile** \> aus. Then select **Device policy for Windows 10** \> **Properties** \> **Settings**.
  
|**Einstellung der Windows 10-Geräterichtlinie**|**Intune-Einstellung(en)**|
|:-----|:-----|
|PCs vor Viren und anderen Bedrohungen mithilfe von Windows Defender Antivirus schützen  <br/> |Echtzeitüberwachung zulassen = EIN  <br/> Cloudschutz zulassen = EIN  <br/> Beim Senden von Beispielen beim Benutzer nachfragen = Sichere Beispiele automatisch senden (standardmäßig automatische Übermittlung von nicht personenbezogenen Daten)  <br/> |
|PCs vor webbasierten Bedrohungen in Microsoft Edge schützen  <br/> |**SmartScreen** in den **Edge Browser-Einstellungen** ist auf **Erforderlich** festgelegt.  <br/> |
|Bildschirm deaktivieren, wenn ein Gerät im Leerlauf ist für (Minuten)  <br/> |Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung  <br/> |
|Benutzern den Download von Apps aus dem Microsoft Store erlauben  <br/> |Benutzerdefinierte URI-Richtlinie  <br/> |
|Benutzern den Zugriff auf Cortana erlauben  <br/> |**Allgemein** \> **Cortana** wird in Intune **blockiert,** wenn es **in** Microsoft 365 Business Premium deaktiviert ist.  <br/> |
|Benutzern erlauben, Windows-Tipps und Werbung von Microsoft zu empfangen  <br/> |**Windows-Spotlight**, alle blockiert, wenn dies **in** Microsoft 365 Business Premium deaktiviert ist.  <br/> |
|Windows 10-Geräte automatisch auf dem neuesten Stand halten  <br/> | Diese Einstellung ist in **Microsoft Intune** Service updates - \> **Windows 10 Update Rings** enthalten, wählen Sie **Updaterichtlinie für Windows 10-Geräte** und dann  \> **Eigenschafteneinstellungen aus.**  <br/>  Wenn die Microsoft 365 Business Premium-Einstellung auf **Ein** festgelegt ist, werden alle folgenden Einstellungen festgelegt:  <br/> **Der Dienstzweig** ist auf **CB** (CBB) festgelegt, wenn dies in Microsoft 365 Business Premium deaktiviert ist.  <br/> **Microsoft-Produktupdates** ist auf **Zulassen** festgelegt.  <br/> **Windows-Treiber** ist auf **Zulassen** festgelegt.  <br/> **Automatisches Updateverhalten** ist auf **Zur Wartungszeit automatisch installieren** mit diesen Werten festgelegt:  <br/> **Beginn der Nutzungszeit** ist auf **6 Uhr** festgelegt.  <br/> **Ende der Nutzungszeit** ist auf **22 Uhr** festgelegt.  <br/> **Rückstellungszeitraum für Qualitätsupdates (Tage)** ist auf **0** festgelegt.  <br/> **Rückstellungszeitraum für Funktionsupdates (Tage)** ist auf **0** festgelegt.  <br/> **Downloadmodus für Bereitstellungsoptimierung** ist auf **HTTP kombiniert mit Peering hinter derselben NAT** festgelegt.  <br/> |
|||
