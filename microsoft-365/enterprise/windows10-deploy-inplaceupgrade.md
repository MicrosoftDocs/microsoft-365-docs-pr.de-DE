---
title: Bereitstellen von Windows 10 Enterprise für vorhandene Geräte als direktes Upgrade
description: Enthält Anleitungen zum Konfigurieren und Bereitstellen eines Windows 10 Enterprise-Images mithilfe von Microsoft Endpoint Configuration Manager als direktes Upgrade.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Windows 10 Enterprise, Deployment, Inplace Upgrade, Configuration Manager, Configuration Manager
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 27ed024c47ac671625563d8bf060017cb1757c4c
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112689"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>Schritt 2: Bereitstellen von Windows 10 Enterprise für vorhandene Geräte als direktes Upgrade

*Dieser Abschnitt gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![Phase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Der einfachste Weg zum Upgrade von PCs, auf denen Windows 7 oder Windows 8.1 auf Windows 10 ausgeführt wird, ist ein direktes Upgrade. Sie können eine Konfigurations-Manager-Tasksequenz (Configuration Manager) verwenden, um den Prozess vollständig zu automatisieren. 

Wenn Sie über vorhandene Computer verfügen, auf denen Windows 7 oder Windows 8.1 läuft, wird dieser Pfad empfohlen, wenn Ihre Organisation Windows 10 bereitstellt. Dadurch wird das Windows-Installationsprogramm (Setup. exe) verwendet, um ein direktes Upgrade durchzuführen, mit dem alle Daten, Einstellungen, Anwendungen und Treiber aus der vorhandenen Betriebssystemversion automatisch beibehalten werden. Dies erfordert den geringsten IT-Aufwand, da keine komplexe Bereitstellungsinfrastruktur erforderlich ist.

Führen Sie die folgenden Schritte aus, um ein Windows 10 Enterprise-Image mithilfe von Microsoft Endpoint Configuration Manager als direktes Upgrade zu konfigurieren und bereitzustellen.

## <a name="the-windows-10-deployment-with-configuration-manager-poster"></a>Die Windows 10-Bereitstellung mit dem Configuration Manager-Poster

Das Poster des Configuration Managers ist eine Seite im Querformatmodus (17x11). Klicken Sie auf das Bild unten, um eine PDF in Ihrem Browser anzuzeigen. 

[![Bereitstellen von Windows 10 mit dem Configuration Manager-Poster](./media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://docs.microsoft.com/windows/deployment/media/Windows10DeploymentConfigManager.pdf)

Sie können dieses Poster auch in [PDF-](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf) oder [Visio-](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx) Format herunterladen.

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>Abschnitt 1: Überprüfen der Bereitschaft zum Aktualisieren von Windows

Verwenden Sie zunächst die Upgrade-Bereitschafts Fähigkeit von Windows Analytics, um leistungsstarke Einblicke und Empfehlungen zu den Computern, Anwendungen und Treibern in Ihrer Organisation zu erhalten, ohne zusätzliche Kosten und zusätzliche Infrastrukturanforderungen zu erfüllen. Dieser neue Dienst führt Sie durch Upgrades und Feature-Update-Projekte mithilfe eines Workflows, der auf von Microsoft empfohlenen Methoden basiert. Aktuelle Inventurdaten ermöglichen es Ihnen, Kosten und Risiken in ihren Upgrade-Projekten auszugleichen.

Weitere Informationen, erste Schritte, Verwendung und Problembehandlung für das Upgrade finden Sie unter [Manage Windows Upgrades with Upgrade Readiness](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) .

Führen Sie als nächstes die Anleitung aus, um Configuration Manager (Current Branch) zu verwenden, um Windows 7 oder höheres Betriebssystem auf Windows 10 zu aktualisieren. Wie bei jeder Bereitstellung mit hohem Risiko wird empfohlen, die Benutzerdaten zu sichern, bevor Sie fortfahren. OneDrive Cloud Storage ist für lizenzierte Microsoft 365-Benutzer einsatzfähig und kann verwendet werden, um Ihre Dateien sicher zu speichern. Weitere Informationen finden Sie unter [OneDrive-Schnellstarthandbuch](https://aka.ms/ODfBquickstartguide). Um auf diese Seite zugreifen zu können, müssen Sie sich als mandantenadministrator oder globaler Administrator in einem Office 365-oder Microsoft 365-Mandanten anmelden.

Eine Liste der Configuration Manager-Versionen und der entsprechenden Windows 10-Clientversionen, die unterstützt werden, finden Sie unter [Support für Windows 10 für Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10).

**So überprüfen Sie die Bereitschaft zum Upgrade von Windows**

Überprüfen Sie diese Anforderungen vor dem Starten der Windows 10-Bereitstellung:

- **Windows-Editionen, die für ein Upgrade berechtigt** sind: auf Ihren Geräten müssen Editionen von Windows 7 oder Windows 8.1 ausgeführt werden, die für ein Upgrade auf Windows 10 Enterprise geeignet sind. Eine Liste der unterstützten Editionen finden Sie unter [Windows 10 Upgrade Paths](https://aka.ms/win10upgradepaths). 
- **Unterstützte Geräte** – die meisten Computer, die mit Windows 8.1 kompatibel sind, sind mit Windows 10 kompatibel. Möglicherweise müssen Sie in Windows 10 aktualisierte Treiber installieren, damit Ihre Geräte ordnungsgemäß funktionieren. Weitere Informationen finden Sie unter [Windows 10 Specifications](https://aka.ms/windows10specifications) .
- **Vorbereitung der Bereitstellung** – stellen Sie sicher, dass Sie über Folgendes verfügen, bevor Sie mit der Konfiguration der Bereitstellung beginnen:
    - Windows 10-Installationsmedien: das Installationsmedium muss sich auf einem separaten Laufwerk befinden, wobei die ISO-Daten bereits eingebunden sind. Sie können die ISO von [MSDN-Abonnenten Downloads](https://aka.ms/msdn-subscriber-downloads) oder aus dem [Volume Licensing Service Center](https://aka.ms/mvlsc)abrufen.
    - Sicherungen von Benutzerdaten – wenn Benutzerdaten beim Upgrade migriert werden, empfiehlt es sich, ein Sicherungs Szenario zu konfigurieren. Exportieren Sie beispielsweise alle Benutzerdaten in ein OneDrive-Konto, ein BitLocker zu Go-verschlüsselten USB-Flashlaufwerk oder einen Netzwerkdateiserver. Weitere Informationen finden Sie unter [sichern oder übertragen von Daten in Windows](https://aka.ms/backuptransferdatawindows).
- **Vorbereitung der Umgebung** : Sie verwenden eine vorhandene Configuration Manager-Serverstruktur, um die Betriebssystembereitstellung vorzubereiten. Neben dem Basis Setup sollten die folgenden Konfigurationen in der Configuration Manager-Umgebung vorgenommen werden:
    1. [Erweitern Sie das Active Directory Schema](https://aka.ms/extendadschema) , und [Erstellen Sie einen System Verwaltungs Container](https://aka.ms/createsysmancontainer).
    2. Aktivieren Sie Active Directory Gesamtstruktur Ermittlung und Active Directory System Ermittlung. Weitere Informationen finden Sie unter [configure Discovery Methods for Configuration Manager](https://aka.ms/configurediscoverymethods).
    3. Erstellen von IP-Bereichsgrenzen und begrenzungsgruppen für die Inhalts-und Website Zuweisung. Weitere Informationen finden Sie unter [define Site Barriers and Boundary Groups for Configuration Manager](https://aka.ms/definesiteboundaries).
    4. Fügen Sie die Configuration Manager Reporting Services-Zeiger Rolle hinzu, und konfigurieren Sie Sie. Weitere Informationen finden Sie unter [Configuring Reporting in Configuration Manager](https://aka.ms/configurereporting).
    5. Erstellen Sie eine Dateisystemordner Struktur für Pakete.
    6. Erstellen Sie eine Configuration Manager-Konsolen Ordnerstruktur für Pakete.
    7. Installieren Sie Configuration Manager-Updates (Current Branch) und alle weiteren Voraussetzungen für Windows 10.

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>Part 2: Hinzufügen eines Windows 10-Betriebssystemabbilds mithilfe von Configuration Manager
Jetzt müssen Sie ein Betriebssystem-Upgrade-Paket erstellen, das die vollständigen Windows 10-Installationsmedien enthält. In den folgenden Schritten erstellen Sie mit dem Konfigurations-Manager ein Upgrade-Paket für Windows 10 Enterprise x64.

**So fügen Sie ein Windows 10-Betriebssystemabbild mithilfe von Configuration Manager hinzu**

1. Klicken Sie in der Configuration Manager-Konsole im Arbeitsbereich **Software Bibliothek** mit der rechten Maustaste auf den Knoten **Betriebssystem-Upgrade-Pakete** , und wählen Sie dann **Betriebssystem-Upgrade-Paket hinzufügen**aus.
2. Geben Sie auf der Seite **Datenquelle** den UNC-Pfad zum Windows 10 Enterprise x64-Medium an, und wählen Sie dann **weiter**aus.
3. Geben Sie auf der Seite **Allgemein** das **Windows 10 Enterprise x64-Upgrade**an, und wählen Sie dann **weiter**aus. 
4. Wählen Sie auf der Seite **Zusammenfassung** die Option **weiter**aus, und wählen Sie dann **Schließen**aus. 
5. Klicken Sie mit der rechten Maustaste auf das erstellte **Windows 10 Enterprise x64-Update** Paket, und wählen Sie dann **Inhalte verteilen**aus. 
6. Wählen Sie Ihren Verteilungs Pfad aus.

## <a name="part-3-configure-deployment-settings"></a>Abschnitt 3: Konfigurieren der Bereitstellungseinstellungen
In diesem Schritt konfigurieren Sie eine Aktualisierungstask Sequenz, die die Einstellungen für das Windows 10-Upgrade enthält. Anschließend identifizieren Sie die Geräte, die aktualisiert werden sollen, und stellen dann die Tasksequenz auf diesen Geräten bereit.

### <a name="create-a-task-sequence"></a>Erstellen einer Tasksequenz
Führen Sie die folgenden Schritte aus, um eine Aktualisierungstask Sequenz zu erstellen:
  
1. Erweitern Sie in der Configuration Manager-Konsole im Arbeitsbereich **Software Bibliothek** den Knoten **Betriebssysteme**. 
2. Klicken Sie mit der rechten Maustaste auf den Knoten **Tasksequenzen** , und wählen Sie dann **Tasksequenz erstellen**aus.
3. Wählen Sie auf der Seite **neue Tasksequenz erstellen** die Option **Upgrade eines Betriebssystems aus dem Upgrade-Paket aus**, und wählen Sie dann **weiter**aus.
4. Geben Sie auf der Seite **Task Sequenzinformationen** das **Windows 10 Enterprise x64-Upgrade**an, und wählen Sie dann **weiter**aus.
5. Wählen Sie auf der Seite **Windows-Betriebssystem aktualisieren** die Option **Durchsuchen** aus, und wählen Sie das **Upgrade-Paket für Windows 10 Enterprise x64 Upgrade**aus, wählen Sie **OK**aus, und klicken Sie dann auf **weiter**.
6. Fahren Sie auf den restlichen Seiten des Assistenten fort, und wählen Sie dann **Schließen**aus.

### <a name="create-a-device-collection"></a>Erstellen einer gerätesammlung
Nachdem Sie die Aktualisierungstask Sequenz erstellt haben, müssen Sie eine Sammlung erstellen, die die zu aktualisierbaren Geräte enthält.

> [!NOTE]
> Verwenden Sie die folgenden Einstellungen, um die Bereitstellung auf einem einzelnen Gerät zu testen. Sie können unterschiedliche Mitgliedschaftsregeln verwenden, um Gerätegruppen einzuschließen, wenn Sie dazu fähig sind. Weitere Informationen finden Sie unter [How to Create Collections in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/create-collections).

1. Klicken Sie in der Configuration Manager-Konsole im Arbeitsbereich **Ressourcen und Kompatibilität** mit der rechten Maustaste auf **gerätesammlungen**, und wählen Sie dann **gerätesammlung erstellen**aus. 
2. Geben Sie im Assistenten zum Erstellen von gerätesammlungen auf der Seite **Allgemein** die folgenden Einstellungen ein, und wählen Sie dann **weiter**aus:
    - Name: Windows 10 Enterprise x64 Upgrade
    - Limiting-Auflistung: alle Systeme
3. Wählen Sie auf der Seite **Mitgliedschaftsregeln** die Option Regel > **direkt** Regel **Hinzufügen**aus, um den Assistenten zum Erstellen einer direkten Mitgliedschaftsregel zu starten.
4. Wählen Sie auf der **Willkommens** Seite des Assistenten zum Erstellen einer direkten Mitgliedschaftsregel die Option **weiter**aus.
5. Geben Sie auf der Seite **Ressourcen suchen** die folgenden Einstellungen ein, und ersetzen Sie den Platzhalter **Wert** Text durch den Namen des Geräts, das Sie aktualisieren möchten: 
    - Ressourcenklasse: System Ressource
    - Attribut Name: Name
    - Wert: *PC0003*
6. Wählen Sie auf der Seite **Ressourcen auswählen** Ihr Gerät aus, und wählen Sie **weiter**aus.
7. Schließen Sie den Assistenten zum Erstellen einer direkten Mitgliedschaftsregel und den Assistenten zum Erstellen von gerätesammlungen ab.  
8. Überprüfen Sie die Windows 10 Enterprise x64-Upgrade-Auflistung. Fahren Sie erst fort, wenn die Computer angezeigt werden, die Sie in der Auflistung hinzugefügt haben.

### <a name="create-an-operating-system-deployment"></a>Erstellen einer Betriebssystembereitstellung
Führen Sie die folgenden Schritte aus, um eine Bereitstellung für die Tasksequenz zu erstellen.

1. Klicken Sie in der Configuration Manager-Konsole im Arbeitsbereich **Software Bibliothek** mit der rechten Maustaste auf die Tasksequenz, die Sie in einem vorherigen Schritt erstellt haben, und wählen Sie dann **Bereitstellen**aus.
2. Wählen Sie auf der Seite **Allgemein** die **Windows 10 Enterprise x64-Upgrade** -Auflistung aus, und wählen Sie dann **weiter**aus.
3. Klicken Sie auf der Seite **Inhalt** auf **weiter**.
4. Wählen Sie auf der Seite **Bereitstellungseinstellungen** die folgenden Einstellungen aus, und wählen Sie dann **weiter**aus:

    > [!NOTE]
    > Für diese Testbereitstellung legen Sie den Zweck " **available**" fest, für den ein Benutzereingriff erforderlich ist, um die Bereitstellung zu starten. In einer Produktionsumgebung möchten Sie möglicherweise die Bereitstellung mithilfe des erforderlichen zwecks automatisieren, bei dem zusätzliche Optionen wie die Planung beim Ausführen der Bereitstellung konfiguriert werden. 

    - Aktion: Installieren
    - Zweck: verfügbar

5. Übernehmen Sie auf der Seite **Zeitplanung** die Standardeinstellungen, und wählen Sie dann **weiter**aus.
6. Übernehmen Sie auf der Seite **Benutzeroberfläche** die Standardeinstellungen, und wählen Sie dann **weiter**aus.
7. Übernehmen Sie auf der Seite **Benachrichtigungen** die Standardeinstellungen, und wählen Sie dann **weiter**aus.
8. Wählen Sie auf der Seite **Zusammenfassung** die Option **weiter**aus, und wählen Sie dann **Schließen**aus.

## <a name="part-4-start-the-windows-10-upgrade-task-sequence"></a>Teil 4: Starten der Windows 10-Aktualisierungstask Sequenz
Führen Sie die folgenden Schritte aus, um die Windows 10-Upgrade-Tasksequenz auf dem Gerät zu starten, das Sie aktualisieren.
 
1. Melden Sie sich am Windows-Computer an, und starten Sie das **Software Center**.
2. Wählen Sie die Tasksequenz aus, die Sie in einem vorherigen Schritt erstellt haben, und wählen Sie dann **Installieren**aus.
3. Wenn die Tasksequenz beginnt, initiiert Sie automatisch den in-Place-Upgradeprozess, indem das Windows-Setupprogramm (Setup. exe) mit den erforderlichen Befehlszeilenparametern aufgerufen wird, um ein automatisches Upgrade durchzuführen, das alle Daten, Einstellungen, Apps und Treiber.
4. Nachdem die Tasksequenz erfolgreich abgeschlossen wurde, wird der Computer vollständig auf Windows 10 aktualisiert.

Wenn bei der Verwendung von Windows 10 in einer Unternehmensumgebung Probleme auftreten, konsultieren Sie die [wichtigsten Microsoft-Support-Lösungen für am häufigsten auftretenden Probleme](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Diese Ressourcen umfassen KB-Artikel, Updates und Bibliotheksartikel.

Verwenden Sie während der Einführung von Updates in Ihrer Organisation die Update Compliance-Funktion von Windows Analytics, um eine ganzheitliche Übersicht über die Kompatibilität von Betriebssystemupdates, die Aktualisierung der Bereitstellungs Fortschritte und die Fehlerbehandlung für Windows 10-Geräte bereitzustellen. Dieser neue Dienst verwendet Diagnosedaten einschließlich Installationsfortschritt, Windows Update-Konfiguration und andere Informationen, um solche Einblicke ohne zusätzliche Kosten und ohne zusätzliche Infrastrukturanforderungen bereitzustellen. Unabhängig davon, ob Sie mit Windows Update for Business oder anderen Verwaltungstools verwendet werden, können Sie sicher sein, dass Ihre Geräte ordnungsgemäß aktualisiert werden.

Weitere Informationen, erste Schritte und die Verwendung der Update Kompatibilität finden Sie unter [Monitor Windows Updates and Windows Defender Antivirus with Update Compliance](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) .

Als Zwischenprüfung können Sie sich die [Beendigungskriterien](windows10-exit-criteria.md#crit-windows10-step2) für diesen Schritt anschauen.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![Schritt 3](./media/stepnumbers/Step3.png)| [Bereitstellen von Windows 10 Enterprise für neue Geräte mittels Windows Autopilot](windows10-deploy-autopilot.md) |
