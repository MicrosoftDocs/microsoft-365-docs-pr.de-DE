---
title: Aktualisieren Ihrer Office 2010 auf Microsoft 365 – Microsoft 365 Administrator
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Erfahren Sie, wie Sie Microsoft Office für Benutzer in Ihrer Organisation auf den neuesten Office-Client aktualisieren.
ms.topic: article
ms.openlocfilehash: 877659e420079ed607adc13e5bbe44bdc979f5ac
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924695"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>Aktualisieren Ihrer Microsoft 365 für Geschäftsbenutzer auf den neuesten Office-Client

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 erreicht das Ende des Supports

Office 2010 wurde der Support am 13. Oktober 2020 eingestellt. Microsoft stellt Folgendes nicht mehr bereit:

- Technischer Support für Probleme

- Fehlerbehebungen für ermittelte Probleme

- Sicherheitsfixes für erkannte Sicherheitsrisiken

Weitere Informationen finden Sie [unter Office Roadmap zum Ende des Supports 2010.](/deployoffice/endofsupport/office-2010-end-support-roadmap)

 **Ist dies das richtige Thema für Sie?**
  
 Wenn Sie der Administrator sind, der für das Microsoft 365 business-Abonnement in Ihrer Organisation verantwortlich ist, sind Sie am richtigen Ort. Administratoren sind in der Regel für Aufgaben wie das Verwalten von Benutzern, das Zurücksetzen von Kennwörtern, das Verwalten Office Installieren und Das Hinzufügen oder Entfernen von Lizenzen verantwortlich.

 Wenn Sie kein Administrator sind und über ein [Microsoft 365 Family](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) Produkt verfügen, finden Sie unter [How do I upgrade Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) informationen zum Aktualisieren Ihrer älteren Version für die private Nutzung von Office.

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>Vorbereiten des Upgrades auf Microsoft 365

Als Administrator steuern Sie, welche Version von Office Personen in Ihrer Organisation installieren können. Es wird dringend empfohlen, Benutzern in Ihrer Organisation, die ältere Versionen von Office wie Office 2010, Office 2013 oder Office 2016 ausführen, ein Upgrade auf die neueste Version zu ermöglichen, um die Vorteile der Sicherheits- und Produktivitätsverbesserungen zu nutzen.

## <a name="upgrade-steps"></a>Upgradeschritte

Im Folgenden werden Sie schrittweise durch den Prozess der Aktualisierung Ihrer Benutzer auf den neuesten Office-Desktopclient geführt. Es wird empfohlen, diese Schritte vor dem Beginn des Upgradeprozesses durchzulesen.
  
## <a name="step-1---check-system-requirements"></a>Schritt 1 - Prüfen der Systemanforderungen

[Überprüfen Sie die Systemanforderungen](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) für Office, um sicherzustellen, dass Ihre Geräte mit der neuesten Version von Office kompatibel sind. Neuere Versionen von Office können beispielsweise nicht auf Computern mit Windows XP oder Windows Vista installiert werden.
  
> [!TIP]
> Wenn Benutzer in Ihrer Organisation ältere Versionen von Windows auf ihren PCs oder Laptops ausführen, empfehlen wir ein Upgrade auf Windows 10. Windows 7 hat das Ende des Supports erreicht. Weitere Informationen finden Sie [unter "Support für Windows 7 endet im Januar 2020".](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1)

Sehen Sie sich die [systemanforderungen Windows 10](https://www.microsoft.com/windows/windows-10-specifications) an, um festzustellen, ob Sie deren Betriebssysteme aktualisieren können.

### <a name="check-application-compatibility"></a>Prüfen der Anwendungskompatibilität

Um ein erfolgreiches Upgrade zu gewährleisten, ist es empfehlenswert, Ihre Office-Anwendungen (einschließlich VBA-Skripts, Makros, Add-Ins von Drittanbietern sowie komplexe Dokumente und Kalkulationstabellen) zu identifizieren und deren Kompatibilität mit der neuesten Office-Version einzuschätzen.
  
Wenn Sie beispielsweise mit der aktuellen Office-Installation Add-Ins von Drittanbietern verwenden, wenden Sie sich an den Hersteller, um sich zu vergewissern, dass diese mit der neuesten Version von Office kompatibel sind.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>Schritt 2 - Überprüfen des vorhandenen Abonnementplans

Einige Microsoft 365 Pläne enthalten nicht die vollständigen Desktopversionen von Office, und die Schritte zum Upgrade unterscheiden sich, wenn Ihr Plan keine Office enthält.
  
Sind Sie unsicher, welchen Abonnementplan Sie verwenden? Erfahren [Sie, welche Microsoft 365 business-Abonnement ich habe?](../admin-overview/what-subscription-do-i-have.md)
  
Wenn Ihr vorhandener Plan Office enthält, fahren Sie mit [Schritt 3 - Deinstallieren von Office](#step-3---uninstall-office) fort.
  
Wenn Ihr vorhandener Plan Office nicht enthält, wählen Sie eine der folgenden Optionen aus:
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Upgrade-Optionen für Pläne ohne Office

 **Option 1: Wechseln Office Abonnements**

Wechseln Sie zu einem Abonnement, das Office enthält. Weitere Informationen finden Sie unter [Wechseln zu einem anderen Microsoft 365 business-Plan.](../../commerce/subscriptions/switch-to-a-different-plan.md)

**Option 2: Kaufen einzelner, einmaliger Käufe von Office oder Kaufen von Office über eine Volumenlizenz**

 - Kaufen Sie einen einzelnen, einmaligen Kauf von Office. Siehe [Office Home &amp; Business](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b) oder [Office Professional](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)

     ODER

 - Kaufen Sie mehrere Kopien von Office über eine Volumenlizenz. Lesen Sie [Vergleich der Suites, die über die Volumenlizenzierung zur Verfügung stehen](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>Schritt 3 - Deinstallieren von Office

Vor der Installation der neuesten Version von Office wird empfohlen, alle älteren Versionen von Office zu deinstallieren. Wenn Sie sich jedoch für das Upgrade von Office entscheiden, beachten Sie die folgenden Fälle, in denen Sie Office nach der Deinstallation nicht neu installieren können.
  
Wenn Sie über Add-Ins von Drittanbietern verfügen, wenden Sie sich an den Hersteller, um festzustellen, ob ein Update vorhanden ist, das mit der neuesten Version von Office funktioniert.

> [!TIP]
> Wenn beim Deinstallieren von Office Probleme auftreten, können Sie mit dem Microsoft Support- und Wiederherstellungs-Assistent-Tool Office entfernen: [Microsoft Support- und Wiederherstellungs-Assistent herunterladen und ausführen.](https://go.microsoft.com/fwlink/?LinkID=2155008)

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>Wählen Sie die Office-Version aus, die Sie deinstallieren möchten:

- [Von einem PC](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Von einem Mac](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Bekannte Probleme bei dem Versuch, ältere Office-Versionen nach einer Deinstallation erneut zu installieren

 **Office über eine Volumenlizenz** Wenn Sie keinen Zugriff mehr auf die Quelldateien dieser Volumenlizenzversionen von Office haben, können Sie sie nicht erneut installieren.

 **Office auf Ihrem Computer vorinstalliert** Wenn Sie keinen Datenträger oder Product Key mehr haben (wenn Office mit einem datenträger oder Product Key enthalten ist), können Sie ihn nicht erneut installieren.

 **Nicht unterstützte Abonnements** Wenn Ihre Kopie von Office über nicht mehr gekündigte Abonnements wie Office 365 Small Business Premium oder Office 365 Mid-size Business abgerufen wurde, können Sie keine ältere Version von Office installieren, es sei denn, Sie verfügen über den Product Key, der in Ihrem Abonnement enthalten ist.

Wenn Sie die neueste Version von Office neben der älteren Version installieren möchten, können Sie unter [Installieren und Verwenden verschiedener Office-Versionen auf demselben PC](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf) eine Liste der Versionen abrufen, bei denen dies unterstützt wird. Eine Installation, bei der zwei Versionen nebeneinander installiert sind, ist möglicherweise die richtige Wahl, wenn Sie z. B. Add-Ins von Drittanbietern installiert haben, die Sie mit der älteren Office-Version verwenden, und Sie nicht sicher sind, ob sie mit der neuesten Version kompatibel sind.

## <a name="step-4---assign-office-licenses-to-users"></a>Schritt 4 - Zuweisen von Office-Lizenzen zu Benutzern

Wenn Sie dies noch nicht getan haben, weisen Sie Allen Benutzern in Ihrer Organisation Lizenzen zu, die Office installieren müssen. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern in Microsoft 365 for Business.](../manage/assign-licenses-to-users.md)
  
## <a name="step-5---install-office"></a>Schritt 5 - Installieren von Office

Nachdem Sie überprüft haben, dass alle Benutzer, die Sie aktualisieren möchten, Über Lizenzen verfügen, besteht der letzte Schritt darin, sie Office installieren zu lassen. Weitere Informationen finden Sie [unter Herunterladen und Installieren oder Erneutes Installieren Office auf Ihrem PC oder Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)
  
> [!TIP]
> Wenn Sie nicht möchten, dass Ihre Benutzer Office selbst installieren, lesen Sie die [Informationen unter Verwalten von Softwaredownloadeinstellungen in Office 365](/DeployOffice/manage-software-download-settings-office-365). Sie können das [Office-Bereitstellungstool](/DeployOffice/overview-office-deployment-tool) verwenden, um die Office-Software in Ihr lokales Netzwerk herunterzuladen und dann Office mithilfe der in der Regel verwendeten Softwarebereitstellungsmethode bereitzustellen.