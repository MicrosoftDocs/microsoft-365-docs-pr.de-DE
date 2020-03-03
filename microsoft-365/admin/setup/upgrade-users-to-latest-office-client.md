---
title: Aktualisieren der Office 365 für Unternehmen Benutzer auf den neuesten Office-Client
f1.keywords:
- NOCSH
ms.author: janellem
author: janellem
manager: eliree
audience: Admin
ms.topic: troubleshooting
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
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Erfahren Sie, wie Sie Ihre Benutzer auf den neuesten Office-Client aktualisieren.
ms.openlocfilehash: 3d9c92a5362889db69926552848ba4c71d7c4c42
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42360406"
---
# <a name="upgrade-your-office-365-for-business-users-to-the-latest-office-client"></a>Aktualisieren der Office 365 für Unternehmen Benutzer auf den neuesten Office-Client

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 erreicht End-of-Support

Office 2010 wird am 13. Oktober 2020 das Ende der Unterstützung erreichen. Wenn Office 2010 das Ende der Unterstützung erreicht, stellt Microsoft nicht mehr Folgendes bereit:

- Technischer Support für Probleme

- Fehlerbehebungen für entdeckte Probleme

- Sicherheitsfixes für entdeckte Sicherheitslücken

Weitere Informationen finden Sie unter [Office 2010 Ende der Support-Roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) .

 **Ist dies das richtige Thema für Sie?**
  
 Wenn Sie der Administrator sind, der für das Office 365 für Unternehmen Abonnement in Ihrer Organisation verantwortlich ist, sind Sie an der richtigen Stelle. Administratoren sind normalerweise für Aufgaben wie das Verwalten von Benutzern, das Zurücksetzen von Kennwörtern, die Verwaltung von Office-Installationen und das Hinzufügen oder Entfernen von Lizenzen verantwortlich.

 Wenn Sie kein Administrator sind und über ein [Office for Home](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans) -Produkt verfügen, finden Sie weitere Informationen zum Upgrade Ihrer älteren Heim Nutzungs Version von Office unter [How do I Upgrade Office](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx) .

## <a name="getting-ready-to-upgrade"></a>Vorbereiten des Upgrades

Als Administrator können Sie steuern, welche Version von Office-Mitarbeitern in Ihrer Organisation installiert werden kann. Es wird dringend empfohlen, dass Sie Benutzern in Ihrer Organisation beim Ausführen älterer Versionen von Office wie Office 2010, Office 2013 oder Office 2016 ein Upgrade auf die neueste Version zur Verfügung stehen, um die Sicherheits-und Produktivitätsverbesserungen zu nutzen.

## <a name="upgrade-steps"></a>Upgrade-Schritte

Im Folgenden werden Sie schrittweise durch den Prozess der Aktualisierung Ihrer Benutzer auf den neuesten Office-Desktopclient geführt. Es wird empfohlen, diese Schritte vor dem Beginn des Upgradeprozesses durchzulesen.
  
## <a name="step-1---check-system-requirements"></a>Schritt 1 - Prüfen der Systemanforderungen

[Überprüfen Sie die Systemanforderungen](https://products.office.com/office-system-requirements) für Office, um sicherzustellen, dass Ihre Geräte mit der neuesten Version von Office kompatibel sind. Beispielsweise können neuere Versionen von Office nicht auf Computern mit Windows XP oder Windows Vista installiert werden.
  
> [!TIP]
> Wenn Sie in Ihrer Organisation über Benutzer verfügen, die ältere Versionen von Windows auf ihren PCs oder Laptops ausführen, empfehlen wir ein Upgrade auf Windows 10. Windows 7 hat das Ende der Unterstützung erreicht. Weitere Informationen finden Sie [unter Support für Windows 7 endet im Januar 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) .

Schauen Sie sich die [Systemanforderungen für Windows 10](https://www.microsoft.com/windows/windows-10-specifications) an, um zu sehen, ob Sie Ihr Betriebssystem aktualisieren können.

### <a name="check-application-compatibility"></a>Prüfen der Anwendungskompatibilität

Um ein erfolgreiches Upgrade zu gewährleisten, ist es empfehlenswert, Ihre Office-Anwendungen (einschließlich VBA-Skripts, Makros, Add-Ins von Drittanbietern sowie komplexe Dokumente und Kalkulationstabellen) zu identifizieren und deren Kompatibilität mit der neuesten Office-Version einzuschätzen.
  
Wenn Sie beispielsweise mit der aktuellen Office-Installation Add-Ins von Drittanbietern verwenden, wenden Sie sich an den Hersteller, um sich zu vergewissern, dass diese mit der neuesten Version von Office kompatibel sind.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>Schritt 2 - Überprüfen des vorhandenen Abonnementplans

Einige Office 365-Pläne beinhalten keine vollständigen Desktopversionen von Office. Daher sind die Upgrade-Schritte anders, wenn Ihr Plan kein Office enthält.
  
Sind Sie unsicher, welchen Abonnementplan Sie verwenden? Lesen Sie [Anzeigen des verfügbaren Office 365 Business-Abonnements](../admin-overview/what-subscription-do-i-have.md).
  
Wenn Ihr vorhandener Plan Office enthält, fahren Sie mit [Schritt 3 - Deinstallieren von Office](#step-3---uninstall-office) fort.
  
Wenn Ihr vorhandener Plan Office nicht enthält, wählen Sie eine der folgenden Optionen aus:
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Upgrade-Optionen für Pläne ohne Office

 **Option 1: Wechseln von Office-Abonnements**

Wechseln Sie zu einem Abonnement, das Office enthält. Lesen Sie [Wechseln zu einem anderen Office 365 Business-Plan](../../commerce/subscriptions/switch-to-a-different-plan.md).

**Option 2: erwerben einzelner, einmaliger Käufe von Office oder erwerben von Office über eine Volumenlizenz**

 - Kaufen Sie einen individuellen, einmaligen Kauf von Office. Siehe [Office Home &amp; Business](https://products.office.com/home-and-business) oder [Office Professional](https://products.office.com/professional)

     ODER

 - Kaufen Sie mehrere Kopien von Office über eine Volumenlizenz. Lesen Sie [Vergleich der Suites, die über die Volumenlizenzierung zur Verfügung stehen](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>Schritt 3 - Deinstallieren von Office

Vor der Installation der neuesten Version von Office wird empfohlen, alle älteren Versionen von Office zu deinstallieren. Wenn Sie sich jedoch für das Upgrade von Office entscheiden, beachten Sie die folgenden Fälle, in denen Sie Office nach der Deinstallation nicht erneut installieren können.
  
Wenn Sie Add-Ins von Drittanbietern verwenden, sollten Sie sich an den Hersteller wenden, um zu sehen, ob ein Update mit der neuesten Version von Office funktioniert.

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>Wählen Sie die Office-Version aus, die Sie deinstallieren möchten:

- [Von einem PC](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx)

- [Von einem Mac](https://support.office.com/article/eefa1199-5b58-43af-8a3d-b73dc1a8cae3.aspx)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Bekannte Probleme bei dem Versuch, ältere Office-Versionen nach einer Deinstallation erneut zu installieren

 **Office über eine Volumenlizenz** Wenn Sie keinen Zugriff mehr auf die Quelldateien dieser Volumenlizenzversionen von Office haben, können Sie Sie nicht erneut installieren.

 **Auf dem Computer vorinstallierte Office-Installation** Wenn Sie keinen Datenträger oder Product Key mehr haben (wenn Office mit einem geliefert wurde), können Sie ihn nicht erneut installieren.

 **Nicht unterstützte Office 365 Abonnements** Wenn Ihre Office-Kopie über nicht fort gegebene Abonnements wie Office 365 Small Business Premium oder Office 365 mittelständischen Unternehmen erworben wurde, können Sie keine ältere Version von Office installieren, es sei denn, Sie verfügen über den Product Key, der mit Ihrem Abonnement geliefert wurde.

Wenn Sie die neueste Version von Office neben der älteren Version installieren möchten, können Sie unter [Installieren und Verwenden verschiedener Office-Versionen auf demselben PC](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx) eine Liste der Versionen abrufen, bei denen dies unterstützt wird. Eine Installation, bei der zwei Versionen nebeneinander installiert sind, ist möglicherweise die richtige Wahl, wenn Sie z. B. Add-Ins von Drittanbietern installiert haben, die Sie mit der älteren Office-Version verwenden, und Sie nicht sicher sind, ob sie mit der neuesten Version kompatibel sind.

## <a name="step-4---assign-office-licenses-to-users"></a>Schritt 4 - Zuweisen von Office-Lizenzen zu Benutzern

Wenn Sie dies noch nicht getan haben, weisen Sie allen Benutzern in Ihrer Organisation, die Office installieren müssen, Lizenzen zu, siehe [Zuweisen von Lizenzen zu Benutzern in Office 365 für Unternehmen](../manage/assign-licenses-to-users.md).
  
## <a name="step-5---install-office"></a>Schritt 5 - Installieren von Office

Nachdem Sie überprüft haben, dass die Benutzer, für die Sie ein Upgrade durchführen möchten, über Lizenzen verfügen, müssen Sie Office im letzten Schritt installieren, siehe [herunterladen und installieren oder erneutes Installieren von Office auf Ihrem PC oder Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx).
  
> [!TIP]
> Wenn Sie nicht möchten, dass Ihre Benutzer Office selbst installieren, finden Sie weitere Informationen unter [Verwalten von Software Downloadeinstellungen in Office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365). Sie können das [Office-Bereitstellungs Tool](https://docs.microsoft.com/DeployOffice/overview-of-the-office-2016-deployment-tool) verwenden, um die Office-Software in Ihr lokales Netzwerk herunterzuladen und dann Office mit der Software Bereitstellungsmethode bereitzustellen, die Sie normalerweise verwenden.
