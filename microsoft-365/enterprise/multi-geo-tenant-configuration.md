---
title: Microsoft 365 Multi-Geo-Mandantenkonfiguration
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: In diesem Artikel erfahren Sie, wie Sie Satellitenstandorte hinzufügen und Ihren Mandanten für Microsoft 365 Multi-Geo konfigurieren.
ms.openlocfilehash: fb907c02a4714c5a2d8e47245321252e7186a8a7
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040568"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a>Microsoft 365 Multi-Geo-Mandantenkonfiguration

Bevor Sie Ihren Mandanten für Microsoft 365 Multi-Geo konfigurieren, stellen Sie sicher, dass Sie [Plan für Microsoft 365 Multi-Geo](plan-for-multi-geo.md) gelesen haben. Um die Schritte in diesem Artikel auszuführen, benötigen Sie eine Liste der geografischen Standorte, die Sie als Satellitenstandorte aktivieren möchten, und der Testbenutzer, die Sie für diese Standorte bereitstellen möchten.

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a>Hinzufügen der Multi-Geo-Funktionen in Ihrem Microsoft 365-Plan zu Ihrem Mandanten

Wenn Sie Microsoft 365 Multi-Geo verwenden möchten, benötigen Sie den Plan _Multi-Geo-Funktionen in Microsoft 365_. Arbeiten Sie mit Ihrem Kontoteam, um diesen Plan zu Ihrem Mandanten hinzuzufügen. Ihr Kontoteam setzt Sie mit dem entsprechenden Lizenzierungsexperten in Verbindung und konfiguriert Ihren Mandanten für Sie.

Beachten Sie, dass der Plan für _Multi-Geo-Funktionen in Microsoft 365_ ein Serviceplan auf Benutzerebene ist. Sie benötigen eine Lizenz für jeden Benutzer, der an einem Satellitenstandort gehostet werden soll. Sie können mit der Zeit weitere Lizenzen hinzufügen, wenn Sie Benutzer in Ihrem Satellitenstandort hinzufügen.

Nachdem der Plan _Multi-Geo-Funktionen in Microsoft 365_ Ihrem Mandanten bereitgestellt wurde, steht die Registerkarte **Geografische Standorte** im Admin Center von OneDrive sowie SharePoint zur Verfügung.

## <a name="add-satellite-locations-to-your-tenant"></a>Hinzufügen von Satellitenstandorten zu Ihrem Mandanten

Sie müssen für jeden geografischen Standort, an dem Sie Daten speichern möchten, einen Satellitenstandort hinzufügen. In der folgenden Tabelle werden verfügbare geografische Standorte angezeigt:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Screenshot der Seite mit geografischen Orten im SharePoint-Admin Center](../media/sharepoint-multi-geo-admin-center.png)

So fügen Sie einen Satellitenstandort hinzu

1. Öffnen Sie das SharePoint Admin Center.

2. Navigieren Sie zu der Registerkarte **Geografische Standorte**.

3. Klicken Sie auf **Ort hinzufügen**.

4. Wählen Sie den Standort aus, den Sie hinzufügen möchten, und klicken Sie auf **Weiter**.

5. Geben Sie die Domäne ein, die Sie mit dem geografischen Standort verwenden möchten, und klicken Sie dann auf **Hinzufügen**.

6. Klicken Sie auf **Schließen**.

Die Bereitstellung kann je nach Größe des Mandanten bis zu 72 Stunden dauern. Sobald die Bereitstellung für einen Satellitenstandort abgeschlossen ist, erhalten Sie eine E-Mail-Bestätigung. Wenn der neue geografische Standort blau auf der Karte auf der Registerkarte **Geografische Standorte** im OneDrive Admin Center angezeigt wird, können Sie mit dem Festlegen der bevorzugten Datenspeicherorte für die Benutzer für diesen geografischen Standort fortfahren. 

> [!IMPORTANT]
> Ihr neuer Satellitenstandort wird mit Standardeinstellungen eingerichtet. Sie können diesen Satellitenstandort entsprechend den lokalen Complianceanforderungen konfigurieren.

## <a name="setting-users-preferred-data-location"></a>Festlegen des bevorzugten Datenspeicherorts für Benutzer
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

Nachdem Sie die erforderlichen Satellitenstandorte aktiviert haben, können Sie Ihre Benutzerkonten für die Verwendung des bevorzugten Datenspeicherorts aktualisieren. Es wird empfohlen, auch dann einen bevorzugten Datenspeicherort für jeden Benutzer festzulegen, wenn dieser Benutzer am zentralen Datenspeicherort verbleibt.

> [!IMPORTANT]
> Wenn ein Standort, der noch nicht als Satellitenspeicherort oder zentraler Standort konfiguriert wurde, als bevorzugter Datenspeicherort eines Benutzers festgelegt wird, verwendet das System bei der Bereitstellung von OneDrive- und SharePoint-Websites sowie Gruppenpostfächern standardmäßig den zentralen Standort.

> [!TIP]
> Es wird empfohlen, die Prüfungen mit einem Testbenutzer oder einer kleinen Gruppe von Benutzern durchzuführen, bevor die Multi-Geo-Funktionen für Ihre Organisation bereitgestellt werden.

In Azure Active Directory (Azure AD) gibt es zwei Arten von Benutzerobjekten: Nur-Cloud-Benutzer und synchronisierte Benutzer. Bitte befolgen Sie die Anweisungen für die entsprechende Benutzerart.

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a>Synchronisieren der bevorzugten Datenspeicherorte für Benutzer mithilfe von Azure AD Connect 

Wenn Benutzende Ihres Unternehmens von einem firmeninternen Active Directory-System mit Azure AD synchronisiert werden, muss ihre PreferredDataLocation in AD aufgefüllt und mit Azure AD synchronisiert werden.

Folgen Sie dem Prozess in [Azure Active Directory Connect-Synchronisierung: Konfigurieren des bevorzugten Datenstandorts für Microsoft 365-Ressourcen](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation), um die Synchronisierung des bevorzugten Datenstandorts von Ihren lokalen Active Directory Domain Services (AD DS) mit Azure AD zu konfigurieren.

Wir empfehlen, die Einstellung des bevorzugten Datenspeicherorts von Benutzern im Rahmen des Standardworkflows für das Erstellen von Benutzern vorzunehmen.

> [!IMPORTANT]
> Im Falle von Benutzern ohne bereitgestellte OneDrive-Umgebung sollten Sie nach der Synchronisierung des bevorzugten Datenspeicherortes mit Azure AD mindestens 24 Stunden warten, damit die Änderungen in Kraft treten, bevor sich die Benutzer bei OneDrive for Business anmelden. (Durch Festlegen des bevorzugten Datenspeicherorts vor der Anmeldung des Benutzers für die Bereitstellung von OneDrive for Business wird sichergestellt, dass die neue OneDrive-Umgebung an dem richtigen Ort bereitgestellt wird.)

### <a name="setting-preferred-data-location-for-cloud-only-users"></a>Festlegen des bevorzugten Datenspeicherorts für Nur-Cloud-Benutzer 

Wenn die Benutzer Ihres Unternehmens nicht über ein lokales Active Directory-System mit Azure AD synchronisiert werden (d. h. wenn sie in Microsoft 365 oder Azure AD erstellt werden), muss der PDL über das Microsoft Azure Active Directory-Modul für Windows PowerShell festgelegt verwenden.

Die Verfahren in diesem Abschnitt setzen das [Microsoft Azure Active Directory-Modul für Windows PowerShell](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0) voraus. Wenn dieses Modul bereits installiert ist, stellen Sie sicher, dass Sie die neueste Version verwenden.

1.  [Stellen Sie eine Verbindung her, und melden Sie sich mit den Anmeldeinformationen eines globaler Administrators für Ihren Mandanten an](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2.  Verwenden Sie das [Set-MsolUser](https://docs.microsoft.com/powershell/msonline/v1/set-msoluser)-Cmdlet zum Festlegen des bevorzugten Datenspeicherorts für jeden Benutzer. Zum Beispiel:

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    Sie können mithilfe des Get-MsolUser-Cmdlets prüfen, ob der bevorzugte Datenspeicherort korrekt festgelegt wurde. Zum Beispiel:

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Screenshot des PowerShell-Fensters mit Set-MsolUser](../media/multi-geo-tenant-configuration-image3.png)

Wir empfehlen, die Einstellung des bevorzugten Datenspeicherorts von Benutzern im Rahmen des Standardworkflows für das Erstellen von Benutzern vorzunehmen.

> [!IMPORTANT]
> Im Falle von neuen Benutzern ohne bereitgestellte OneDrive-Umgebung sollten Sie nach der Einstellung des bevorzugten Datenspeicherortes mindestens 24 Stunden warten, damit die Änderungen in Kraft treten, bevor sich die Benutzer bei OneDrive for Business anmelden. (Durch Festlegen des bevorzugten Datenspeicherorts vor der Anmeldung des Benutzers für die Bereitstellung von OneDrive for Business wird sichergestellt, dass die neue OneDrive-Umgebung an dem richtigen Ort bereitgestellt wird.)

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a>Bereitstellung von OneDrive und Auswirkungen auf den bevorzugten Datenspeicherort

Wenn für einen Benutzer bereits eine OneDrive-Website im Mandanten erstellt wurde, wird beim Festlegen des bevorzugten Speicherorts die vorhandene OneDrive-Bereitstellung nicht automatisch verschoben. Informationen zum Verschieben des OneDrive eines Benutzers finden Sie unter [OneDrive for Business Geo Move](move-onedrive-between-geo-locations.md).

> [!NOTE]
> Exchange Online verlagert das Postfach des Benutzers automatisch, wenn sich die PLD ändert und "MailboxRegion" nicht mehr mit dem Code für den geografischen Standort der Postfachdatenbank entspricht. Weitere Informationen finden Sie unter [Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung.](https://docs.microsoft.com/microsoft-365/enterprise/administering-exchange-online-multi-geo)

Wenn ein Benutzer nicht über eine OneDrive-Website innerhalb des Mandanten verfügt, wird OneDrive in Übereinstimmung mit den jeweiligen PDL-Einstellungen bereitgestellt, sofern der PDL des Benutzers einem der Satellitenstandorte des Unternehmens entspricht.

## <a name="configuring-multi-geo-search"></a>Konfigurieren der Multi-Geo-Suche

Der Multi-Geo-Mandant verfügt über aggregierte Suchfunktionen, mit denen eine Suchabfrage Ergebnisse von allen Orten innerhalb des Mandanten zurückgibt.

Standardmäßig geben Suchen von diesen Einstiegspunkten aggregierte Ergebnisse zurück, auch wenn sich jeder Suchindex an dem jeweiligen relevanten geografischen Standort befindet:

- OneDrive for Business

- Delve

- SharePoint-Homepage

- Suchcenter

Darüber hinaus können Multi-Geo-Suchfunktionen für Ihre benutzerdefinierte Suchanwendung konfiguriert werden, die die SharePoint-Suche-API verwendet.

Anweisungen, einschließlich Einschränkungen und Unterschiede, finden Sie unter [Konfigurieren der Suche für Multi-Geo in OneDrive for Business](configure-search-for-multi-geo.md).

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a>Überprüfen der Microsoft 365 Multi-Geo-Konfiguration

Im Folgenden finden Sie einige grundlegende Anwendungsfälle, in denen eine Überprüfung vor dem Rollout von Microsoft 365 Multi-Geo im Unternehmen möglicherweise sinnvoll ist. Nach Abschluss dieser Tests und zusätzlicher Anwendungsfälle, die für Ihr Unternehmen relevant sind, können Sie der ursprünglichen Pilotgruppe bei Bedarf weitere Benutzer hinzufügen.

**OneDrive for Business**

Wählen Sie OneDrive im Microsoft 365-Startprogramm aus und bestätigen Sie, dass Sie automatisch an den entsprechenden geografischen Standort des Benutzers (gemäß dessen PDL) weitergeleitet werden. OneDrive for Business sollte jetzt an diesem Standort bereitgestellt werden. Versuchen Sie nach der Bereitstellung, einige Dokumente hoch- und herunterzuladen.

**Mobile OneDrive-App**

Melden Sie sich bei Ihrer mobilen OneDrive-App mit den Anmeldeinformationen Ihres Testkontos an. Stellen Sie sicher, dass Ihre OneDrive for Business-Dateien angezeigt werden und mit denjenigen auf Ihrem Mobilgerät interagieren können.

**OneDrive-Synchronisierungsclient**

Vergewissern Sie sich, dass der OneDrive-Synchronisierungsclient den geografischen Standort für OneDrive for Business nach Anmeldung automatisch erkennt. Wenn Sie den Synchronisierungsclient herunterladen müssen, klicken Sie in der OneDrive-Bibliothek auf **Synchronisieren**.

**Office-Anwendungen**

Vergewissern Sie sich, dass Sie auf OneDrive for Business zugreifen können, indem Sie sich von einer Office-Anwendung wie Word aus anmelden. Öffnen Sie die Office-Anwendung, und wählen Sie „OneDrive – <TenantName>„. Office erkennt Ihren OneDrive-Ort und zeigt die Dateien, die Sie öffnen können.

**Freigabe**

Testen Sie die Freigabe von OneDrive-Dateien. Vergewissern Sie sich, dass die Personenauswahl alle SharePoint-Onlinebenutzer unabhängig vom geografischen Standort anzeigt.
