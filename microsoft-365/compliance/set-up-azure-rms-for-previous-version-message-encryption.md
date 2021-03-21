---
title: Einrichten der Azure Rights Management für die vorherige Version der Nachrichtenverschlüsselung
f1.keywords:
- NOCSH
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
description: Die vorherige Version der Office 365-Nachrichtenverschlüsselung hängt von der Verwaltung von Microsoft Azure-Rechten (früher als Windows Azure Active Directory Rights Management bekannt).
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919491"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Einrichten der Azure Rights Management für die vorherige Version der Nachrichtenverschlüsselung

In diesem Thema werden die Schritte beschrieben, die Sie ausführen müssen, um Azure Rights Management (RMS), teil von Azure Information Protection, für die Verwendung mit der vorherigen Version von Office 365 Message Encryption (OME) zu aktivieren und zu einrichten.

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Dieser Artikel gilt nur für die vorherige Version von OME

Wenn Sie Ihre Organisation noch nicht in die neuen OME-Funktionen verschoben haben, aber bereits OME bereitgestellt haben, gelten die Informationen in diesem Artikel für Ihre Organisation. Microsoft empfiehlt, einen Plan für den Wechsel zu den neuen OME-Funktionen zu erstellen, sobald dies für Ihre Organisation sinnvoll ist. Anweisungen finden Sie unter [Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md). Weitere Informationen zur Funktionsweise der neuen Funktionen finden Sie unter [Office 365 Message Encryption](ome.md). Der Rest dieses Artikels bezieht sich auf das OME-Verhalten vor der Veröffentlichung der neuen OME-Funktionen.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Voraussetzungen für die Verwendung der vorherigen Version der Office 365-Nachrichtenverschlüsselung
<a name="warmprereqs"> </a>

Office 365 Message Encryption (OME), einschließlich IRM, hängt von Azure Rights Management (Azure RMS) ab. Azure RMS ist die von Azure Information Protection verwendete Schutztechnologie. Für die Verwendung von OME muss Ihre Organisation ein Exchange Online- oder Exchange Online Protection-Abonnement enthalten, das wiederum ein Azure Rights Management-Abonnement enthält.
  
- Wenn Sie nicht sicher sind, was Ihr Abonnement enthält, lesen Sie die Exchange Online-Dienstbeschreibungen für [Nachrichtenrichtlinie, Wiederherstellung und Compliance](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

- Wenn Sie über Azure Rights Management verfügen, aber nicht für Exchange Online oder Exchange Online Protection eingerichtet sind, wird in diesem Artikel erläutert, wie Sie Azure Rights Management aktivieren, und anschließend wird die beste Methode zum Einrichten von OME für die Zusammenarbeit mit Azure Rights Management beschrieben.

- Wenn Sie OME bereits für die Zusammenarbeit mit Azure Rights Management für Exchange Online oder Exchange Online Protection eingerichtet haben, können Sie je nach Einrichtung sofort mit der Verwendung von OME und den neuen Funktionen beginnen. In diesem Artikel wird erläutert, wie Sie bestimmen, ob Sie OME ordnungsgemäß eingerichtet haben, was sie tun müssen, wenn Sie Ihr Setup ändern müssen und was geschieht, wenn Sie sich dafür entscheiden, das Setup nicht zu ändern. Um beispielsweise die neuen Funktionen nutzen zu können, müssen Sie Azure RMS mit OME verwenden. Sie können die neuen Funktionen nicht mit einem lokalen Active Directory RMS verwenden.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Aktivieren der Azure Rights Management für die vorherige Version von OME in Office 365

Sie müssen Azure Rights Management aktivieren, damit die Benutzer in Ihrer Organisation Informationsschutz auf Nachrichten anwenden können, die sie senden, und Nachrichten und Dateien öffnen können, die durch den Azure Rights Management-Dienst geschützt wurden. Anweisungen finden Sie unter [Aktivieren von Azure Rights Management](/azure/information-protection/activate-service). Nachdem Sie die Aktivierung abgeschlossen haben, kehren Sie hier zurück, und fahren Sie mit den Aufgaben in diesem Artikel fort.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Einrichten der vorherigen Version von OME für die Verwendung von Azure RMS durch Importieren von vertrauenswürdigen Veröffentlichungsdomänen (Trusted Publishing Domains, TPDs)

Eine TPD ist eine XML-Datei, die Informationen zu den Einstellungen für die Rechteverwaltung Ihrer Organisation enthält. Die TPD enthält beispielsweise Informationen zum Serverlizenzgeberzertifikat (Server Lizenzgeberzertifikat), das zum Signieren und Verschlüsseln von Zertifikaten und Lizenzen verwendet wird, die URLs, die für lizenzierung und Veröffentlichung verwendet werden, und so weiter. Sie importieren die TPD mithilfe von Windows PowerShell.
  
> [!IMPORTANT]
> Zuvor konnten Sie TPDs aus dem Active Directory Rights Management Service (AD RMS) in Ihre Organisation importieren. Dadurch wird jedoch verhindert, dass Sie die neuen OME-Funktionen verwenden und wird nicht empfohlen. Wenn Ihre Organisation derzeit auf diese Weise konfiguriert ist, empfiehlt Microsoft, einen Plan für die Migration von Ihrem lokalen Active Directory RMS zu cloudbasierten Azure Information Protection zu erstellen. Weitere Informationen finden Sie unter [Migrieren von AD RMS zu Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). Sie können die neuen OME-Funktionen erst verwenden, wenn Sie die Migration zu Azure Information Protection abgeschlossen haben.
  
 **So importieren Sie TPDs aus Azure RMS**
  
1. [Herstellen einer Verbindung mit Exchange Online mithilfe von Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Wählen Sie die Schlüsselfreigabe-URL aus, die dem geografischen Standort Ihrer Organisation entspricht:

|**Ort**|**URL des Schlüsselfreigabespeicherorts**|
|:-----|:-----|
|Nordamerika  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Europäische Union  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Asien  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Südamerika  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 für Behörden (Community-Cloud der US-Regierung)  <br/> Dieser RMS-Schlüsselfreigabespeicherort ist für Kunden reserviert, die Office 365 für Regierungs-SKUs erworben haben.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. Konfigurieren Sie den Speicherort für die Schlüsselfreigabe, indem Sie das [Cmdlet Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) wie folgt ausführen: 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   So konfigurieren Sie beispielsweise den Speicherort für die Schlüsselfreigabe, wenn sich Ihre Organisation in Nordamerika befindet:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. Führen Sie [das Cmdlet Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) mit der Option -RMSOnline aus, um die TPD aus der Azure Rights Management zu importieren: 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Dabei  *ist TPDName*  der Name, den Sie für die TPD verwenden möchten. Beispiel: "Contoso North American TPD". 

5. Führen Sie das [Cmdlet Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) mit der Option -RMSOnline wie folgt aus, um sicherzustellen, dass Ihre Organisation erfolgreich für die Verwendung des Azure Rights Management-Diensts konfiguriert wurde:

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Unter anderem überprüft dieses Cmdlet die Konnektivität mit dem Azure Rights Management-Dienst, lädt die TPD herunter und überprüft deren Gültigkeit.

6. Führen Sie [das Cmdlet Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) wie folgt aus, um die Bereitstellung von Azure Rights Management-Vorlagen in Outlook im Web und Outlook zu deaktivieren: 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Führen Sie das [Cmdlet Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) wie folgt aus, um Azure Rights Management für Ihre cloudbasierte E-Mail-Organisation zu aktivieren und es für die Verwendung von Azure Rights Management für Die Office 365-Nachrichtenverschlüsselung zu konfigurieren:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Um sicherzustellen, dass Sie die TPD erfolgreich importiert und Azure Rights Management aktiviert haben, verwenden Sie das cmdlet Test-IRMConfiguration, um die Azure Rights Management-Funktionalität zu testen. Details finden Sie in "Beispiel 1" unter [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Ich habe die vorherige Version von OME mit Active Directory Rights Management und nicht Mit Azure Information Protection eingerichtet. Was kann ich tun?
<a name="importTPDs"> </a>

Sie können ihre vorhandenen Nachrichtenflussregeln für die Office 365-Nachrichtenverschlüsselung weiterhin mit active Directory Rights Management verwenden, sie können die neuen OME-Funktionen jedoch nicht konfigurieren oder verwenden. Stattdessen müssen Sie zu Azure Information Protection migrieren. Informationen zur Migration und was dies für Ihre Organisation bedeutet, finden Sie unter Migrieren von [AD RMS zu Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).
  
## <a name="next-steps"></a>Nächste Schritte
<a name="importTPDs"> </a>

Wenn Sie die neuen OME-Funktionen aktivieren möchten, nachdem Sie das Azure Rights Management-Setup abgeschlossen haben, finden Sie weitere Informationen unter Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen, die auf [Azure Information Protection aufgebaut sind.](./set-up-new-message-encryption-capabilities.md)
  
Nachdem Sie Ihre Organisation für die Verwendung der neuen OME-Funktionen eingerichtet haben, können Sie Nachrichtenflussregeln definieren, um E-Mail-Nachrichten mit neuen [OME-Funktionen zu schützen.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>Verwandte Themen
<a name="importTPDs"> </a>

[Verschlüsselung in Office 365](encryption.md)
  
[Technische Details zur Verschlüsselung in Office 365](technical-reference-details-about-encryption.md)
  
[Was ist Azure Rights Management?](/information-protection/understand-explore/what-is-azure-rms)