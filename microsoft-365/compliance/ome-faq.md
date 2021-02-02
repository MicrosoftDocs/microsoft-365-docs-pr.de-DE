---
title: Häufig gestellte Fragen zur Nachrichtenverschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: Haben Sie eine Frage zur Funktionsweise der neuen Nachrichtenschutzfunktionen? Suchen Sie hier nach einer Antwort.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a88d853905ed8462972c9f423254a49424974bb7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066838"
---
# <a name="message-encryption-faq"></a>Häufig gestellte Fragen zur Nachrichtenverschlüsselung

Haben Sie eine Frage zur Funktionsweise der neuen Nachrichtenschutzfunktionen? Suchen Sie hier nach einer Antwort. Sehen Sie sich auch häufig gestellte Fragen zum Datenschutz [in Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) an, um Antworten auf Fragen zum Datenschutzdienst Azure Rights Management in Azure Information Protection zu erhalten.

## <a name="what-is-office-365-message-encryption-ome"></a>Was ist Die Office 365-Nachrichtenverschlüsselung (OME)?

OME kombiniert E-Mail-Verschlüsselungs- und Rechteverwaltungsfunktionen. Rechteverwaltungsfunktionen werden von Azure Information Protection unterstützt.

## <a name="who-can-use-ome"></a>Wer kann OME verwenden?

Sie können die neuen Funktionen für OME unter den folgenden Bedingungen verwenden:
  
- Wenn Sie OME oder IRM noch nie für Exchange Online in Office 365 eingerichtet haben.

- Wenn Sie OME und IRM eingerichtet haben, können Sie diese Schritte ausführen, wenn Sie den Azure Rights Management Service von Azure Information Protection verwenden.

- Wenn Sie Exchange Online mit active Directory Rights Management Service (AD RMS) verwenden, können Sie diese neuen Funktionen nicht sofort aktivieren. Stattdessen müssen Sie [AD RMS zuerst zu Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) migrieren. Wenn Sie die Migration abgeschlossen haben, können Sie OME erfolgreich einrichten.

  Wenn Sie weiterhin lokale AD RMS mit Exchange Online verwenden möchten, anstatt zu Azure Information Protection zu migrieren, können Sie diese neuen Funktionen nicht verwenden.

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>Welche Abonnements muss ich verwenden, um die neuen OME-Funktionen zu verwenden?

Um die neuen Funktionen von OME verwenden zu können, benötigen Sie einen der folgenden Pläne:
  
- Die Office 365-Nachrichtenverschlüsselung wird als Teil von Office 365 Enterprise E3 und E5, Microsoft Enterprise E3 und E5, Microsoft 365 Business Premium, Office 365 A1, A3 und A5 sowie Office 365 Government G3 und G5 angeboten. Kunden benötigen keine zusätzlichen Lizenzen, um die neuen Schutzfunktionen zu erhalten, die von Azure Information Protection unterstützt werden.

- Sie können Azure Information Protection Plan 1 auch den folgenden Plänen hinzufügen, um die neuen Funktionen für die Office 365-Nachrichtenverschlüsselung zu erhalten: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard oder Office 365 Enterprise E1.

- Jeder Benutzer, der von der Office 365-Nachrichtenverschlüsselung profitieren kann, muss lizenziert sein, damit er von diesem Feature abgedeckt wird.

- Die vollständige Liste finden Sie in den [Exchange Online-Dienstbeschreibungen](https://technet.microsoft.com/library/exchange-online-service-description.aspx) für die Office 365-Nachrichtenverschlüsselung.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>Kann ich Exchange Online mit Ihrem eigenen Schlüssel (BYOK) in Azure Information Protection verwenden?

Ja. Microsoft empfiehlt, dass Sie die Schritte zum Einrichten von BYOK ausführen, bevor Sie OME einrichten.
  
Weitere Informationen zu BYOK finden Sie unter [Planung und Implementierung Ihres Azure Information Protection-Mandantenschlüssels.](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Ändern OME und BYOK mit Azure Information Protection den Ansatz von Microsoft bei Datenanforderungen von Drittanbietern wie Vorladungen?

Nein. OME und die Option zum Bereitstellen und Steuern Ihrer eigenen Verschlüsselungsschlüssel, die als BYOK bezeichnet werden, von Azure Information Protection wurden nicht für die Reaktion auf Vorladungen von Strafverfolgungsbehörden entwickelt. OME wurde mit BYOK für Azure Information Protection für Compliance-orientierte Kunden entwickelt. Microsoft nimmt Anfragen von Drittanbietern für Kundendaten sehr ernst. Als Clouddienstanbieter setzen wir uns immer für den Datenschutz von Kundendaten ein. Für den Fall, dass wir eine Vorladung erhalten, versuchen wir immer, den Dritten an den Kunden umzuleiten, um die Informationen zu erhalten. (Lesen Sie den Blog von Brad Smith: [Schützen von Kundendaten vor Behörden-Schnüffing).](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) Wir veröffentlichen regelmäßig detaillierte Informationen zu der Anforderung, die wir erhalten. Weitere Informationen zu Datenanforderungen von Drittanbietern finden Sie unter [Reagieren](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) auf Anfragen von Behörden und Strafverfolgungsbehörden für den Zugriff auf Kundendaten im Microsoft Trust Center. Siehe auch "Offenlegung von Kundendaten" in den [Onlinedienstbedingungen (OST).](https://www.microsoft.com/Licensing/product-licensing/products.aspx)
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>Wie ist dieses Feature mit älteren Features der Office 365-Nachrichtenverschlüsselung (OME) und der Verwaltung von Informationsrechten (Information Rights Management, IRM) verbunden?

Die neuen Funktionen für die Office 365-Nachrichtenverschlüsselung sind eine Weiterentwicklung der vorhandenen IRM- und Legacy-OME-Lösungen. In der folgenden Tabelle finden Sie weitere Details.
  
**Vergleich von älteren OME-, IRM- und neuen OME-Funktionen**

| Funktion | Frühere Versionen von OME | IRM | Neue OME-Funktionen |
|:-----|:-----|:-----|:-----|
|**Senden einer verschlüsselten E-Mail**|Nur über Exchange-Nachrichtenflussregeln|Von Outlook für Windows, Outlook für Mac oder Outlook im Web initiierter Endbenutzer; oder über Exchange-Nachrichtenflussregeln|Von Outlook für Windows, Outlook für Mac oder Outlook im Web initiierter Endbenutzer; oder über Nachrichtenflussregeln|
|**Rechteverwaltung**|-|Option "Nicht weiterleiten" und benutzerdefinierte Vorlagen|Option "Nicht weiterleiten", "Nur verschlüsseln", Standardvorlagen und benutzerdefinierte Vorlagen|
|**Unterstützter Empfängertyp**|Nur externe Empfänger|Nur interne Empfänger|Interne und externe Empfänger|
|**Benutzererfahrung für Empfänger**|Externe Empfänger haben eine HTML-Nachricht erhalten, die sie in einem Browser oder einer heruntergeladenen mobilen App heruntergeladen und geöffnet haben.|Interne Empfänger haben nur verschlüsselte E-Mails in Outlook für Windows, Outlook für Mac und Outlook im Web empfangen.|Interne und externe Empfänger erhalten E-Mails in Outlook für Windows, Outlook für Mac, Outlook im Web, Outlook für Android und Outlook für iOS oder über ein Webportal, unabhängig davon, ob sie sich in derselben Organisation oder in einer beliebigen Organisation befinden. Das OME-Portal erfordert keinen separaten Download.|
|**Bring Your Own Key Support**|Nicht verfügbar|Nicht verfügbar| BYOK unterstützt|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>Wie ermögliche ich die neuen OME-Funktionen für meine Organisation?

Weitere [Informationen finden Sie unter Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen.](set-up-new-message-encryption-capabilities.md)
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>Ist die vorherige Version von OME veraltet?

Sie können weiterhin die vorherige Version von OME verwenden, sie ist zu diesem Zeitpunkt nicht veraltet. Wir ermutigen Organisationen jedoch dringend, die neue und verbesserte OME-Lösung zu verwenden. Kunden, die OME noch nicht bereitgestellt haben, können keine neue Bereitstellung der vorherigen Version von OME einrichten.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>Meine Organisation verwendet Active Directory Rights Management. Kann ich diese Funktion verwenden?

Nein. Wenn Sie Exchange Online mit active Directory Rights Management Service (AD RMS) verwenden, können Sie diese neuen Funktionen nicht sofort aktivieren. Stattdessen müssen Sie [AD RMS zuerst zu Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) migrieren.
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>Meine Organisation verfügt über eine Exchange-Hybridbereitstellung. Kann ich dieses Feature verwenden?

Lokale Benutzer können verschlüsselte E-Mails mithilfe von Exchange Online-Nachrichtenflussregeln senden. Dazu müssen Sie E-Mails über Exchange Online routen. Weitere Informationen finden Sie in Teil 2: Konfigurieren von E-Mails für den Fluss von [Ihrem E-Mail-Server zu Microsoft 365.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>Welchen E-Mail-Client muss ich zum Erstellen einer verschlüsselten OME-Nachricht verwenden? Welche Anwendungen werden für das Senden geschützter Nachrichten unterstützt?

Sie können geschützte Nachrichten aus Outlook 2016, Outlook 2013 für Windows und Mac und aus Outlook im Web erstellen. Weitere Informationen zum Senden verschlüsselter Nachrichten finden Sie unter Senden, Anzeigen und Antworten auf verschlüsselte [Nachrichten in Outlook für PC.](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us)
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>Welche E-Mail-Clients werden unterstützt, um geschützte E-Mails zu lesen und darauf zu antworten?

Microsoft 365-Benutzer können Outlook für Windows und Mac (2013 und 2016), Outlook im Web und Outlook Mobile (Android und iOS) lesen und beantworten. Sie können auch den nativen iOS-E-Mail-Client verwenden, wenn dies in Ihrer Organisation erlaubt ist. Wenn Sie kein Microsoft 365-Benutzer sind, können Sie verschlüsselte Nachrichten im Web über Ihren Webbrowser lesen und beantworten.

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>Welche E-Mail-Clients unterstützen nur verschlüsselte E-Mails?

Microsoft 365-Benutzer können Outlook für PC, Version 2019, und Microsoft 365 verwenden, um E-Mails zu erstellen, die durch die Richtlinie zum Verschlüsseln geschützt sind.  Das bedeutet, dass Nachrichten, auf die die neue Richtlinie zum Verschlüsseln angewendet wurde, direkt in Outlook im Web, in Outlook für iOS und Android und jetzt in Outlook für PC, Version 2019 und Microsoft 365, gelesen werden können.

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>Gibt es eine Größenbeschränkung für Nachrichten, die Sie mit OME senden können?

Ja. Die maximale Nachrichtengröße, die Sie mit OME senden können, einschließlich Anlagen, beträgt 25 MB. Weitere Informationen finden Sie unter [Nachrichtenbeschränkungen.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1)

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>Welche Dateitypen werden als Anlagen in geschützten E-Mails unterstützt? Erben Anlagen die Schutzrichtlinien, die geschützten E-Mails zugeordnet sind?

Sie können einen beliebigen Dateityp an eine geschützte E-Mail anfügen. Mit einer Ausnahme werden Schutzrichtlinien nur auf die Dateiformate angewendet, die in den Dateitypen erwähnt werden, die vom [Azure Information Protection Client unterstützt werden.](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types) OME unterstützt nicht die 97-2003-Versionen der folgenden Office-Programme: Word (DOC), Excel (XLS) und PowerPoint (.ppt).

Wenn ein Dateiformat unterstützt wird, z. B. eine Word-, Excel- oder PowerPoint-Datei, wird die Datei immer geschützt, auch nachdem die Anlage vom Empfänger heruntergeladen wurde. Nehmen wir beispielsweise an, dass eine Anlage durch "Nicht weiterleiten" geschützt ist. Der ursprüngliche Empfänger lädt die Datei herunter, erstellt eine Nachricht an einen neuen Empfänger und fügt die Datei an. Wenn der neue Empfänger die Datei empfängt, kann der Empfänger die geschützte Datei nicht öffnen.
  
## <a name="are-pdf-file-attachments-supported"></a>Werden PDF-Dateianlagen unterstützt?

Die kurze Antwort lautet "Ja". Mit der PDF-Verschlüsselung können Sie vertrauliche PDF-Dokumente durch sichere Kommunikation oder sichere Zusammenarbeit schützen. Wenn Sie E-Mails senden, verschlüsselt der Office 365-Dienst PDF-Dateianlagen, nicht den Outlook-Client.

Für Outlook im Web, Outlook für iOS und Outlook für Android können Sie gesendete PDFs ohne zusätzliche Schritte verschlüsseln. Diese Clients unterstützen systemeigene PDF-Verschlüsselung.

Die Verschlüsselung von PDF-Dateianlagen wird von Outlook Desktop systemintern nicht unterstützt. Stattdessen müssen Sie Exchange-Nachrichtenflussregeln oder DLP einrichten, um zuerst Verschlüsselung auf PDF-Anlagen anzuwenden. Wenn Sie E-Mails von Outlook Desktop mit einer PDF-Anlage senden, sendet der Client die Nachricht mit der Anlage zuerst an den Dienst. Wenn der Dienst die Datei empfängt, wendet der Dienst den OME-Schutz der Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) oder der Nachrichtenflussregel in Exchange Online an. Als Nächstes sendet Exchange Online die Nachricht mit der geschützten PDF-Dateianlage.

Führen Sie den folgenden Befehl in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)aus, um die Verschlüsselung für PDF-Anlagen zu aktivieren:

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

Mit der PDF-Verschlüsselung können Sie vertrauliche PDF-Dokumente durch sichere Kommunikation oder sichere Zusammenarbeit schützen. Für alle Outlook-Clients erben Nachrichten und ungeschützte PDF-Anlagen den OME-Schutz der Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) oder der Nachrichtenflussregel in Exchange Online. Wenn ein Outlook im Web-Benutzer ein ungeschütztes PDF-Dokument anfügen und nachrichtenschutziert, erbt die Nachricht den Schutz der Nachricht. Benutzer können die verschlüsselten Anlagen nur in Anwendungen öffnen, die geschützte PDFs unterstützen (z. B. das OME-Portal und den Azure Information Protection Viewer).

> [!IMPORTANT]
> Der Outlook-Desktopclient unterstützt keine PDF-Verschlüsselung.

## <a name="are-onedrive-for-business-attachments-supported"></a>Werden OneDrive for #A0 unterstützt?

Not yet. OneDrive for #A0 werden nicht unterstützt, und Endbenutzer können E-Mails, die eine OneDrive for #A1 enthalten, nicht verschlüsseln.
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>Welche E-Mail-Clients unterstützen die Vorschau verschlüsselter Anlagen in geschützten E-Mails?

Wenn Anlagen durch geschützte E-Mails geschützt sind, bieten die Outlook-Clients die Möglichkeit, eine Vorschau des Dokuments direkt anzuzeigen. Outlook unterstützt die Vorschau von Office-Dokumenten (docx, xlsx, pptx, doc, xls, ppt). Outlook im Web unterstützt die Vorschau von Office-Dokumenten (DOCX, XLSX, PPTX) und PDF.  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>Welche E-Mail-Clients unterstützen die Sperrung geschützter E-Mails?

Outlook im Web unterstützt die Sperrung geschützter E-Mails.  Weitere [Informationen finden Sie unter Widerrufen einer verschlüsselten](https://docs.microsoft.com/microsoft-365/compliance/revoke-ome-encrypted-mail?view=o365-worldwide#how-to-revoke-an-encrypted-message-that-you-sent) Nachricht, die Sie gesendet haben.


## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>Kann ich Nachrichten durch Das Einrichten von Richtlinien automatisch verschlüsseln?

Ja. Verwenden Sie Nachrichtenflussregeln in Exchange Online, um eine Nachricht basierend auf bestimmten Bedingungen automatisch zu verschlüsseln. Sie können beispielsweise Richtlinien erstellen, die auf der Empfänger-ID, der Empfängerdomäne oder dem Inhalt des Nachrichtentexts oder Betreffs basieren. Weitere [Informationen finden Sie unter Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten in Office 365.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>Kann ich die Verschlüsselung für eingehende und ausgehende E-Mails automatisch entfernen?

Administratoren können eine Nachrichtenflussregel einrichten, um die Verschlüsselung für ausgehende E-Mails zu entfernen. Sie können keine Regel einrichten, um die Verschlüsselung für eingehende E-Mails zu entfernen.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>Kann ich Nachrichten automatisch verschlüsseln, indem ich Richtlinien in der Verhinderung von Datenverlust (Data Loss Prevention, DLP) über das Security &amp; Compliance Center einstelle?

Ja. Sie können Nachrichtenflussregeln in Exchange Online oder mithilfe von DLP im Security &amp; Compliance Center einrichten.
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>Kann ich verschlüsselte Nachrichten mit meinem Unternehmensbranding anpassen?

Ja. Informationen zum Anpassen von E-Mail-Nachrichten und zum OME-Portal finden Sie unter "Hinzufügen der Marke Ihrer Organisation zu Ihren verschlüsselten Nachrichten". Weitere Informationen finden Sie unter "Hinzufügen [der Marke Ihrer Organisation zu Ihren verschlüsselten Nachrichten".](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>Gibt es Berichtsfunktionen oder Einblicke für verschlüsselte E-Mails?

Es gibt einen Verschlüsselungsbericht im Security and Compliance Center. Siehe ["Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center".](../security/office-365-security/view-email-security-reports.md)
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>Kann ich die Nachrichtenverschlüsselung mit Compliancefeatures wie eDiscovery verwenden?

Ja. Alle verschlüsselten E-Mail-Nachrichten können von microsoft 365-Compliancefeatures ermittelt werden.

## <a name="can-i-remove-encryption-from-email"></a>Kann ich die Verschlüsselung aus E-Mails entfernen?

Administratoren können eine Nachrichtenflussregel einrichten, um die Verschlüsselung aus ausgehenden E-Mails zu entfernen. Die Verschlüsselung mithilfe einer Nachrichtenflussregel kann nicht aus eingehenden Nachrichten entfernt werden.

## <a name="is-delegated-access-supported"></a>Wird delegierter Zugriff unterstützt?

Diese Funktion kann gegenwärtig nicht verwendet werden.

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>Kann ich als freigegebenes Postfach senden und E-Mails verschlüsseln?

Wenn jemand eine E-Mail-Nachricht sendet, die einer Verschlüsselungs-Nachrichtenflussregel entspricht, wird die Nachricht verschlüsselt, bevor sie gesendet wird.

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>Kann ich verschlüsselte Nachrichten öffnen, die an ein freigegebenes Postfach gesendet werden?

Ja. Verschlüsselte Nachrichten werden für ein freigegebenes Postfach unterstützt.

- Benutzer können geschützte E-Mails in einem freigegebenen Postfach öffnen, in dem das freigegebene Postfach eine geschützte E-Mail als Teil einer Verteilergruppe empfangen hat.

- Benutzer können Anlagen anzeigen, die Schutz von E-Mails erben, wenn sie Outlook für Windows, Outlook für Mac und Outlook im Web verwenden.

In der folgenden Tabelle sind die unterstützten Clients für freigegebene Postfächer aufgeführt.

| Plattform | Lesen von E-Mails | Anzeigen von E-Mail-Anlagen |
|----------|-----------|------------------------|
| Outlook im Web | Ja | Ja                |
| Outlook für Windows| Ja | Ja                |
| Outlook für Mac    | Ja | Ja                |
| Outlook für Android| Ja | Nein                 |
| Outlook für iOS    | Ja | Nein                 |
|

Es gibt derzeit zwei bekannte Einschränkungen:

- Sie können Keine Anlagen zu E-Mails öffnen, die Sie auf mobilen Geräten mit Outlook Mobile erhalten.

- Die Zuweisung über eine E-Mail-aktivierte Sicherheitsgruppe wird nicht unterstützt. Wir unterstützen nur den Zugriff durch direkte Benutzerzuweisung auf das freigegebene Postfach, und die automatische Zuordnung ist für Exchange Online aktiviert. Die automatischeMapping ist für Exchange Online standardmäßig aktiviert.

**So weisen Sie dem freigegebenen Postfach einen Benutzer zu**

1. [Stellen Sie mithilfe von Remote PowerShell eine Verbindung mit Exchange Online herzustellen.](https://technet.microsoft.com/library/jj984289?v=exchg.150%29.aspx)

2. Führen Sie Add-MailboxPermission cmdlet mit dem Parameter "Automapping" aus. In diesem Beispiel wird Ayla Vollzugriff auf ein Supportpostfach erteilt.

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```
   
 ## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>Kann ich verschlüsselte Nachrichten öffnen, die an das Postfach eines anderen Benutzers mit Fullaccess gesendet werden?

Benutzer können verschlüsselte Nachrichten öffnen, solange sie direkten Zugriff erhalten und die automatischeMapping aktiviert ist. Der Zugriff ist nicht zulässig, wenn der Zugriff über eine E-Mail-aktivierte Sicherheitsgruppe gewährt wird.

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>Was kann ich tun, wenn ich den einmal übergebenen Code nicht erhalte, nachdem ich ihn angefordert habe?

Überprüfen Sie zunächst den Junk- oder Spamordner in Ihrem E-Mail-Client. DKIM- und DMARC-Einstellungen für Ihre Organisation können dazu führen, dass diese E-Mails als Spam gefiltert werden.

Überprüfen Sie als Nächstes die Quarantäne im Security & Compliance Center. Häufig werden Nachrichten, die einen einmal übergebenen Code enthalten, insbesondere die ersten Nachrichten, die Ihre Organisation empfängt, in Quarantäne gestellt.
