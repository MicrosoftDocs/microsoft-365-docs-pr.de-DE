---
title: Einrichten von Azure Rights Management für die vorherige Version der Office 365-Nachrichtenverschlüsselung
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: Die frühere Version von Office 365 Nachrichtenverschlüsselung hängt von der Microsoft Azure Rights Management (bisher als Windows Azure Active Directory Rights Management bezeichnet) ab.
ms.openlocfilehash: 84922a57c6245cf3214f17ba922417b5e025b796
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081795"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a>Einrichten von Azure Rights Management für die vorherige Version der Office 365-Nachrichtenverschlüsselung

In diesem Thema werden die Schritte beschrieben, die Sie ausführen müssen, um Azure Rights Management (RMS), Teil von Azure Information Protection, zur Verwendung mit der vorherigen Version von Office 365 Message Encryption (OM) zu aktivieren und einzurichten.

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Dieser Artikel bezieht sich nur auf die vorherige Version von OM.
Wenn Sie Ihre Office 365 Organisation noch nicht in die neuen OM-Funktionen verschoben haben, Sie jedoch bereits OM bereitgestellt haben, gelten die Informationen in diesem Artikel für Ihre Organisation. Microsoft empfiehlt, einen Plan für die Umstellung auf die neuen OM-Funktionen zu erstellen, sobald dies für Ihre Organisation sinnvoll ist. Anweisungen finden Sie unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md). Wenn Sie mehr darüber erfahren möchten, wie die neuen Funktionen als erstes funktionieren, lesen Sie [Office 365 Nachrichtenverschlüsselung](ome.md). Der Rest dieses Artikels bezieht sich auf das OM-Verhalten vor der Veröffentlichung der neuen OM-Funktionen.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Voraussetzungen für die Verwendung der vorherigen Version von Office 365 Nachrichtenverschlüsselung
<a name="warmprereqs"> </a>

Office 365 Nachrichtenverschlüsselung (OM), einschließlich IRM, hängt von Azure Rights Management (Azure RMS) ab. Azure RMS ist die Schutztechnologie, die von Azure Information Protection verwendet wird. Um OM verwenden zu können, muss Ihre Office 365 Organisation ein Abonnement für Exchange Online oder Exchange Online Schutz enthalten, das ihrerseits ein Azure Rights Management-Abonnement enthält.
  
- Wenn Sie sich nicht sicher sind, was Ihr Abonnement enthält, finden Sie weitere Informationen unter Exchange Online Dienstbeschreibungen für [Nachrichtenrichtlinien, Wiederherstellung und Kompatibilität](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).

- Wenn Sie kein Azure RMS-Abonnement für Exchange Online oder Exchange Online Schutz haben, müssen Sie ein Abonnement erwerben und zuerst aktivieren.

    Informationen zum Erwerb eines Abonnements für Azure Rights Management finden Sie unter [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). Der folgende Abschnitt enthält Informationen zur Aktivierung von Azure Rights Management.

- Wenn Sie Azure Rights Management, aber nicht für Exchange Online oder Exchange Online Schutz eingerichtet haben, wird in diesem Artikel erläutert, wie Sie Azure Rights Management aktivieren und dann die beste Möglichkeit zum Einrichten von OM für die Verwendung von Azure Rights Management beschrieben.

- Wenn Sie "OM" bereits für die Verwendung von Azure Rights Management für Exchange Online oder Exchange Online Schutz eingerichtet haben, können Sie, je nach Einrichtung, sofort mit der Nutzung von OM und den neuen Funktionen beginnen. In diesem Artikel wird erläutert, wie Sie feststellen können, ob Sie das Aufheben richtig festgelegt haben, was Sie tun müssen, wenn Sie das Setup ändern müssen und was geschieht, wenn Sie das Setup nicht ändern möchten. Um beispielsweise die neuen Funktionen verwenden zu können, müssen Sie Azure RMS mit OM verwenden. Sie können die neuen Funktionen nicht mit einem lokalen Active Directory RMS verwenden.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Aktivieren von Azure Rights Management für die vorherige Version von om in Office 365

Sie müssen die Azure-Rechteverwaltung aktivieren, damit die Benutzer in Ihrer Organisation den von Ihnen gesendeten Nachrichten Informationen Schutz und Nachrichten und Dateien öffnen können, die durch den Azure Rights Management-Dienst geschützt wurden. Anweisungen finden Sie unter [Aktivieren von Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Wenn Sie die Aktivierung abgeschlossen haben, kehren Sie hier zurück, und fahren Sie mit den Aufgaben in diesem Artikel fort.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Einrichten der vorherigen Version von OM für die Verwendung von Azure RMS durch Importieren von vertrauenswürdigen Veröffentlichungsdomänen (vor)

Ein TPD ist eine XML-Datei, die Informationen zu den Einstellungen für die Rechteverwaltung Ihrer Organisation enthält. Das TPD enthält beispielsweise Informationen zum Server-Lizenzgeberzertifikat (SLC), das zum Signieren und Verschlüsseln von Zertifikaten und Lizenzen, zu den für die Lizenzierung und zur Veröffentlichung verwendeten URLs usw. verwendet wird. Sie importieren die TPD mithilfe von Windows PowerShell in Ihre Office 365 Organisation.
  
> [!IMPORTANT]
> Zuvor konnten Sie vor aus dem Active Directory Rights Management Service (AD RMS) in Ihre Office 365 Organisation importieren. Dadurch wird jedoch verhindert, dass Sie die neuen OM-Funktionen verwenden und wird nicht empfohlen. Wenn Ihre Office 365 Organisation derzeit auf diese Weise konfiguriert ist, empfiehlt Microsoft, einen Plan für die Migration von Ihrem lokalen Active Directory RMS zu Cloud-basierten Azure Information Protection zu erstellen. Weitere Informationen finden Sie unter [Migrieren von AD RMS zu Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). Die neuen OM-Funktionen können erst verwendet werden, wenn Sie die Migration zu Azure Information Protection abgeschlossen haben.
  
 **So importieren Sie vor aus Azure RMS**
  
1. Stellen [Sie mithilfe von Remote-PowerShell eine Verbindung zu Exchange Online her](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Wählen Sie die URL für die Schlüssel Freigabe aus, die dem geografischen Standort Ihrer Office 365 Organisation entspricht:

|**Standort**|**URL für den Schlüssel Freigabespeicherort**|
|:-----|:-----|
|Nordamerika  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Europäische Union  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Asien  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Südamerika  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 für Behörden (Community-Cloud der US-Regierung)  <br/> Dieser RMS-Schlüssel Freigabespeicherort ist für Kunden reserviert, die Office 365 für die Verwaltung von SKUs erworben haben.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. Konfigurieren Sie den Speicherort für die Schlüssel Freigabe, indem Sie das Cmdlet " [IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) " wie folgt ausführen: 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    Beispielsweise zum Konfigurieren des Speicherorts für die Schlüssel Freigabe, wenn sich Ihre Organisation in Nordamerika befindet:
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. Führen Sie das [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) -Cmdlet mit dem-RMSOnline-Schalter aus, um die TPD von Azure Rights Management zu importieren: 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    Dabei ist *TPDName* der Name, den Sie für die TPD verwenden möchten. Beispiel: "Contoso North American TPD". 
    
5. Um sicherzustellen, dass Sie Ihre Office 365 Organisation erfolgreich für die Verwendung des Azure Rights Management-Diensts konfiguriert haben, führen Sie das Cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) mit dem-RMSOnline-Schalter wie folgt aus: 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    Dieses Cmdlet prüft unter anderem die Konnektivität mit dem Azure Rights Management-Dienst, lädt das TPD herunter und überprüft seine Gültigkeit.
    
6. Führen Sie das Cmdlet " [IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) " wie folgt aus, um die Verfügbarkeit von Azure Rights Management-Vorlagen in Outlook im Internet und Outlook zu deaktivieren: 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. Führen Sie das Cmdlet " [IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) " wie folgt aus, um Azure Rights Management für Ihre cloudbasierten e-Mail-Organisation zu aktivieren und für die Verwendung von Azure Rights Management für Office 365 Nachrichtenverschlüsselung zu konfigurieren: 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. Verwenden Sie das Test-IRMConfiguration-Cmdlet, um die Azure Rights Management-Funktionalität zu testen, um sicherzustellen, dass Sie die TPD und die aktivierte Azure-Rechteverwaltung erfolgreich importiert haben. Details finden Sie in "Beispiel 1" unter [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Ich habe die frühere Version von OM mit Active Directory Rights Management nicht mit Azure Information Protection eingerichtet, was kann ich tun?
<a name="importTPDs"> </a>

Sie können weiterhin die e-Mail-Flussregeln für Nachrichtenverschlüsselung in Office 365 mit Active Directory Rights Management verwenden, aber Sie können die neuen OM-Funktionen nicht konfigurieren oder verwenden. Stattdessen müssen Sie zu Azure Information Protection migrieren. Informationen zur Migration und was dies für Ihre Organisation bedeutet, finden Sie unter [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).
  
## <a name="next-steps"></a>Nächste Schritte
<a name="importTPDs"> </a>

Wenn Sie das Azure Rights Management-Setup abgeschlossen haben, wenn Sie die neuen OM-Funktionen aktivieren möchten, finden Sie weitere Informationen unter [Einrichten von neuen Office 365 Nachrichten Verschlüsselungsfunktionen, die auf Azure Information Protection basieren.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)
  
Nachdem Sie Ihre Organisation für die Verwendung der neuen OM-Funktionen eingerichtet haben, sind Sie bereit, e- [Mail-Flussregeln zu definieren, um e-Mail-Nachrichten mit neuen OM-Funktionen zu schützen](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="related-topics"></a>Verwandte Themen
<a name="importTPDs"> </a>

[Verschlüsselung in Office 365](encryption.md)
  
[Technische Details zur Verschlüsselung in Office 365](technical-reference-details-about-encryption.md)
  
[Was ist Azure Rights Management?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

