---
title: Problembehandlung und Supportinformationen
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: In diesem Thema werden die Schritte zur Problembehandlung für Endbenutzer und Administratoren beschrieben, und Sie erhalten Informationen zum Kontaktieren des technischen Supports.
ms.openlocfilehash: 2a8019ed58bfb88183d20a8292bd5a30d9b43f13
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082596"
---
# <a name="troubleshooting-and-support-information"></a>Problembehandlung und Supportinformationen

In diesem Thema werden die Schritte zur Problembehandlung für Endbenutzer und Administratoren beschrieben, und Sie erhalten Informationen zum Kontaktieren des technischen Supports.
  
## <a name="troubleshooting-for-users"></a>Problembehandlung für Benutzer

Gelegentlich treten Probleme mit Microsoft Office Outlook auf, nachdem Sie das Add-In "Junk-E-Mail-Berichtsprogramm" hinzugefügt haben. Im Folgenden sind Probleme aufgeführt, die möglicherweise auftreten, sowie Tipps zum Behandeln dieser Probleme. 
  
- Das Programm reagiert nicht, wenn Sie auf **Junk-E-Mail melden** klicken
    
- Outlook reagiert nicht mehr, wenn Sie eine E-Mail auswählen
    
- Gemeldete Junk-E-Mails können nicht übermittelt werden, und es wird eine Unzustellbarkeitsnachricht angezeigt
    
### <a name="troubleshooting-tip"></a>Tipps zur Problembehandlung

1. Schließen Sie Microsoft Office Outlook, und starten Sie die Anwendung neu.
    
2. Überprüfen Sie, ob Sie eine Testnachricht erstellen und senden können. Zu diesem Zweck können Sie eine Testnachricht an ein anderes E-Mail-Konto senden, für das Sie verantwortlich sind, und anschließend überprüfen, ob die E-Mail empfangen wurde.
    
Wenn das Problem weiterhin auftritt, wenden Sie sich an Ihren IT-Administrator.
  
> [!TIP]
> Sie können Spamnachrichten auch direkt an Microsoft senden (verwenden Sie zu diesem Zweck die E-Mail-Adresse [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com)). Falsch positive Ergebnisse können Sie an folgende E-Mail-Adresse senden: [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com).Weitere Informationen finden Sie unter [Übermitteln von Spam-, Nicht-Spamnachrichten und Nachrichten, die als betrügerische Phishing-Angriffe angesehen werden, an Microsoft zur Analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
## <a name="troubleshooting-for-administrators"></a>Problembehandlung für Administratoren

Als Administrator können Sie auf Probleme mit Benutzern stoßen, die das Add-In "Junk-E-Mail-Berichtsprogramm" für Microsoft Office Outlook verwenden. Es folgen einige Tipps zur Lösung von Problemen, die möglicherweise auftreten. 
  
 **Problem:** Benutzer werden in einer Fehlermeldung wiederholt aufgefordert, ihren Systemadministrator zu kontaktieren. 
  
### <a name="troubleshooting-tip"></a>Tipps zur Problembehandlung

1. Legen Sie den folgenden Registrierungsschlüsselwert auf "Verbose" fest:
    
  - **32-Bit-Version von Outlook auf einem 32-Bit-Betriebssystem:**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **32-Bit-Version von Outlook auf einem 64-Bit-Betriebssystem:**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **64-Bit-Version von Outlook (immer auf einem 64-Bit-Betriebssystem installiert):**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
2. Starten Sie Microsoft Office Outlook neu, und bitten Sie die Benutzer, sich zu melden, wenn die Fehlermeldung erneut angezeigt wird.
    
3. Erfassen Sie die Protokollinformationen am folgenden Speicherort: 
    
    %LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt
    
4. Kontaktieren Sie den technischen Support für Exchange Online Protection, und übergeben Sie den Mitarbeitern diese Protokollinformationen. 
    
 **Problem:** Benutzer haben festgelegt, dass sie keine Bestätigung erhalten möchten, wenn sie eine Nachricht als Junk-E-Mail melden, möchten nun jedoch eine solche Bestätigung erhalten. 
  
### <a name="troubleshooting-tip"></a>Tipps zur Problembehandlung

1. Legen Sie den folgenden Registrierungsschlüsselwert auf "True" fest: HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk
    
2. Starten Sie Microsoft Office Outlook neu.
    
## <a name="support-information"></a>Supportinformationen

Wenn Sie Hilfe bei der Installation, Konfiguration oder Deinstallation des Add-Ins benötigen, wenden Sie sich über den Link Neue Dienstanforderung auf der Seite Support im Microsoft 365 Admin Center an den technischen Support. Weitere Optionen, einschließlich der Übermittlung einer Dienstanforderung über die Telefon-und Self-Support-Optionen, finden Sie unter [Hilfe und Support für EoP](help-and-support-for-eop.md).
  
## <a name="for-more-information"></a>Weitere Informationen

[Aktivieren des Berichtsnachrichts-Add-Ins](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)
  
[Melden von Junk-E-Mails an Microsoft](report-junk-email-messages-to-microsoft.md)
  

