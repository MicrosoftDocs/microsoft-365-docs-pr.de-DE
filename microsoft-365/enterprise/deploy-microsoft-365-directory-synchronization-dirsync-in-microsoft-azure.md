---
title: Bereitstellen der Microsoft 365-Verzeichnissynchronisierung in Microsoft Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: In diesem Artikel erfahren Sie, wie Sie Azure AD Connect auf einem virtuellen Computer in Azure bereitstellen, um Konten zwischen dem lokalen Verzeichnis und dem Azure AD Mandanten zu synchronisieren.
ms.openlocfilehash: 8db78d20ee4c2186918a0b3b433f8f0ae056816e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690647"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a>Bereitstellen der Microsoft 365-Verzeichnissynchronisierung in Microsoft Azure

Azure Active Directory (Azure AD) Connect (früher als Verzeichnissynchronisierungstool, Verzeichnissynchronisierungstool oder das DirSync.exe Tool bezeichnet) ist eine Anwendung, die Sie auf einem Server mit Domänenbeitritt installieren, um Ihre lokalen Active Directory-Domänendienste (AD DS) Benutzer mit dem Azure AD Mandanten Ihres Microsoft 365-Abonnements zu synchronisieren. Microsoft 365 verwendet Azure AD für seinen Verzeichnisdienst. Ihr Microsoft 365-Abonnement enthält einen Azure AD Mandanten. Dieser Mandant kann auch für die Verwaltung der Identitäten Ihrer Organisation mit anderen Cloud-Arbeitsauslastungen verwendet werden, einschließlich anderer SaaS-Anwendungen und apps in Azure.

Sie können Azure AD Connect auf einem lokalen Server installieren, doch wir empfehlen aus den folgenden Gründen die Installation auf einem virtuellen Computer in Azure:
  
- Sie können cloudbasierte Server schneller bereitstellen und konfigurieren und so die Dienste Ihren Benutzern schneller zur Verfügung stellen.
- Azure bietet eine bessere Verfügbarkeit von Websites mit weniger Aufwand.
- Sie können die Anzahl der lokalen Server in Ihrer Organisation verringern.

Diese Lösung erfordert Konnektivität zwischen dem lokalen Netzwerk und Ihrem virtuellen Azure-Netzwerk. Weitere Informationen finden Sie unter [Verbinden eines lokalen Netzwerks mit einem virtuellen Microsoft Azure-Netzwerk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md). 
  
> [!NOTE]
> In diesem Artikel wird die Synchronisierung einer einzelnen Domäne in einer einzelnen Gesamtstruktur beschrieben. Azure AD Connect synchronisiert alle AD DS Domänen in der Active Directory Gesamtstruktur mit Microsoft 365. Wenn Sie mehrere Active Directory Gesamtstrukturen für die Synchronisierung mit Microsoft 365 haben, finden Sie weitere Informationen unter [Multi-Forest Directory Sync with Single Sign-on Scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091). 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a>Übersicht über die Bereitstellung der Microsoft 365-Verzeichnissynchronisierung in Azure

Das folgende Diagramm zeigt Azure AD Connect auf einem virtuellen Computer in Azure (dem Verzeichnissynchronisierungsserver), mit dem eine lokale AD DS Gesamtstruktur mit einem Microsoft 365-Abonnement synchronisiert wird.
  
![Azure AD Connect-Tool auf einem virtuellen Computer in Azure synchronisieren lokaler Konten mit dem Azure AD Mandanten eines Microsoft 365-Abonnements mit Datenfluss](../media/CP-DirSyncOverview.png)
  
In diesem Diagramm gibt es zwei Netzwerke, die über eine Standort-zu-Standort-VPN- oder ExpressRoute-Verbindung verbunden sind. Es gibt ein lokales Netzwerk, in dem AD DS-Domänencontroller enthalten sind, und ein virtuelles Azure-Netzwerk mit einem Verzeichnissynchronisierungsserver, einem virtuellen Computer mit ausgeführtem [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). Es gibt zwei Hauptdatenströme, die vom Verzeichnissynchronisierungsserver stammen:
  
-  Azure AD Connect fragt einen Domänencontroller im lokalen Netzwerk auf Änderungen an Benutzerkonten und Kennwörtern ab.
-  Azure AD Connect sendet die Änderungen an Konten und Kennwörtern an die Azure AD Instanz Ihres Microsoft 365-Abonnements. Da sich der Verzeichnissynchronisierungsserver in einem erweiterten Teil Ihres lokalen Netzwerks befindet, werden diese Änderungen über den Proxy Server des lokalen Netzwerks gesendet.
    
> [!NOTE]
> In dieser Lösung wird die Synchronisierung einer einzelnen Active Directory Domäne in einer einzelnen Active Directory Gesamtstruktur beschrieben. Azure AD Connect synchronisiert alle Active Directory Domänen in der Active Directory Gesamtstruktur mit Microsoft 365. Wenn Sie mehrere Active Directory Gesamtstrukturen für die Synchronisierung mit Microsoft 365 haben, finden Sie weitere Informationen unter [Multi-Forest Directory Sync with Single Sign-on Scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091). 
  
Es gibt bei der Bereitstellung dieser Lösung zwei wichtige Schritte:
  
1. Erstellen eines virtuellen Azure-Netzwerks und Einrichten einer Standort-zu-Standort-VPN-Verbindung mit dem lokalen Netzwerk. Weitere Informationen finden Sie unter [Verbinden eines lokalen Netzwerks mit einem virtuellen Microsoft Azure-Netzwerk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).
    
2. Installieren Sie [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) auf einem virtuellen Computer mit Domänenbeitritt in Azure, und synchronisieren Sie dann die lokale AD DS mit Microsoft 365. Dies umfasst:
    
    Erstellen eines Virtueller Azure-Computer zum Ausführen von Azure AD Connect.
    
    Installieren und Konfigurieren von [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).
    
    Für das Konfigurieren Azure AD Connect sind die Anmeldeinformationen (Benutzername und Kennwort) eines Azure AD Administratorkontos und eines AD DS Unternehmensadministrator Kontos erforderlich. Azure AD Connect wird sofort und kontinuierlich ausgeführt, um die lokale AD DS Gesamtstruktur mit Microsoft 365 zu synchronisieren.
    
Bevor Sie diese Lösung in der Produktionsumgebung bereitstellen, können Sie die Anweisungen in [der simulierten Unternehmensbasis Konfiguration](simulated-ent-base-configuration-microsoft-365-enterprise.md) verwenden, um diese Konfiguration als Machbarkeitsstudie, für Vorführungen oder für Experimente festzulegen.
  
> [!IMPORTANT]
> Wenn die Konfiguration von Azure AD Connect abgeschlossen ist, werden die Anmeldeinformationen für das AD DS-Unternehmensadministratorkonto nicht gespeichert. 
  
> [!NOTE]
> In dieser Lösung wird das Synchronisieren einer einzelnen AD DS Gesamtstruktur mit Microsoft 365 beschrieben. Die in diesem Artikel beschriebene Topologie stellt nur eine Möglichkeit dar, diese Lösung zu implementieren. Die Topologie Ihrer Organisation kann je nach Ihren eindeutigen Netzwerkanforderungen und Sicherheitsüberlegungen unterschiedlich sein. 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a>Planen des Hostens eines Verzeichnissynchronisierungsservers für Microsoft 365 in Azure
<a name="PlanningVirtual"> </a>

### <a name="prerequisites"></a>Voraussetzungen

Lesen Sie die folgenden Voraussetzungen für diese Lösung, ehe Sie mit diesem Vorgang beginnen:
  
- Überprüfen Sie die dazugehörigen Planungsinhalte in [Planen des virtuellen Azure-Netzwerks](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).
    
- Stellen Sie sicher, dass alle [Voraussetzungen](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) für die Konfiguration des virtuellen Azure-Netzwerks erfüllt sind.
    
- Verfügen über ein Microsoft 365-Abonnement, das das Feature Active Directory Integration enthält. Informationen zu Microsoft 365-Abonnements finden Sie auf der [Microsoft 365-Abonnementseite](https://products.office.com/compare-all-microsoft-office-products?tab=2).
    
- Bereitstellen eines virtuellen Azure-Computers, der Azure AD Connect ausgeführt wird, um Ihre lokale AD DS Gesamtstruktur mit Microsoft 365 zu synchronisieren.
    
    Sie benötigen die Anmeldeinformationen (Namen und Kennwörter) für das AD DS-Unternehmensadministratorkonto und ein Azure AD-Administratorkonto.
    
### <a name="solution-architecture-design-assumptions"></a>Entwurfsannahmen für die Lösungsarchitektur

In der folgenden Liste werden die für diese Lösung getroffenen Design-Entscheidungen beschrieben.
  
- Diese Lösung verwendet ein einzelnes virtuelles Azure-Netzwerk mit einer einzelnen Standort-zu-Standort-VPN-Verbindung. Das virtuelle Azure-Netzwerk hostet ein einzelnes Subnetz, das einen Server, den Verzeichnissynchronisierungsserver mit ausgeführtem Azure AD Connect, enthält. 
    
- Im lokalen Netzwerk sind ein Domänencontroller und DNS-Server vorhanden.
    
- Azure AD Connect wird für die Kennworthashsynchronisierung anstatt für das einmalige Anmelden verwendet. Sie müssen keine Infrastruktur für Active Directory-Verbunddienste (AD FS) bereitstellen. Weitere Informationen zu Optionen für einmaliges Anmelden und Kennworthashsynchronisierung finden Sie unter [Wählen der richtigen Authentifizierungsmethode für Ihre Azure Active Directory-Hybrididentitätslösung](https://aka.ms/auth-options).
    
Es folgen einige weitere Entwurfsoptionen, die Sie berücksichtigen sollten, wenn Sie diese Lösung in Ihrer Umgebung bereitstellen:
  
- Wenn es in einem vorhandenen virtuellen Azure-Netzwerk DNS-Server gibt, bestimmen Sie, ob der Verzeichnissynchronisierungsserver diese für die Namensauflösung anstelle der DNS-Server im lokalen Netzwerk verwenden soll.
    
- Wenn es Domänencontroller in einem vorhandenen virtuellen Azure-Netzwerk gibt, bestimmen Sie, ob die Konfiguration von Active Directory-Standorten und-Diensten ggf. eine bessere Option für Sie ist. Der Verzeichnissynchronisierungsserver kann die Domänencontroller im virtuellen Azure-Netzwerk anstatt die Domänencontroller im lokalen Netzwerk abfragen, um nach Änderungen an Benutzerkonten und Kennwörtern zu suchen.
    
## <a name="deployment-roadmap"></a>Fahrplan für die Bereitstellung

Das Bereitstellen von Azure AD Connect auf einem virtuellen Computer in Azure umfasst drei Phasen:
  
- Phase 1: Erstellen und Konfigurieren des virtuellen Azure-Netzwerks
    
- Phase 2: Erstellen und Konfigurieren des virtuellen Azure-Computers
    
- Phase 3: Installieren und Konfigurieren von Azure AD Connect
    
Nach der Bereitstellung müssen Sie auch Standorte und Lizenzen für die neuen Benutzerkonten in Microsoft 365 zuweisen.


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a>Phase 1: Erstellen und Konfigurieren des virtuellen Azure-Netzwerks

Zum Erstellen und Konfigurieren des virtuellen Azure-Netzwerks durchlaufen Sie [Phase 1: Vorbereitung Ihres lokalen Netzwerks](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) und [Phase 2: Erstellen des standortübergreifenden virtuellen Azure-Netzwerks](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) im Fahrplan für die Bereitstellung von [Verbinden eines lokalen Netzwerks mit einem virtuellen Microsoft Azure-Netzwerk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).
  
Nachfolgend sehen Sie die daraus resultierende Konfiguration.
  
![Phase 1 des Verzeichnissynchronisierungsservers für Microsoft 365, gehostet in Azure](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
Diese Abbildung zeigt ein lokales Netzwerk, das über eine Standort-zu-Standort-VPN- oder ExpressRoute-Verbindung mit einem virtuellen Azure-Netzwerk verbunden ist.
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a>Phase 2: Erstellen und Konfigurieren des virtuellen Azure-Computers

Erstellen Sie den virtuellen Computer in Azure anhand der Anweisungen unter [Erstellen Ihres ersten virtuellen Windows-Computers im Azure-Portal](https://go.microsoft.com/fwlink/p/?LinkId=393098). Verwenden Sie die folgenden Einstellungen:
  
- Wählen Sie im Bereich **Grundlagen** das gleiche Abonnement, den gleichen Ort und die gleiche Ressourcengruppe als virtuelles Netzwerk aus. Bewahren Sie den Benutzernamen und das Kennwort an einem sicheren Ort auf. Sie benötigen diese Informationen später für die Verbindung mit dem virtuellen Computer.
    
- Wählen Sie im Bereich zum Auswählen einer **Größe** die Größe **A2 Standard** aus.
    
- Wählen Sie im Bereich **Einstellungen** im Abschnitt **Speicher** den Speichertyp **Standard** aus. Wählen Sie im Abschnitt **Netzwerk** den Namen des virtuellen Netzwerks und das Subnetz zum Hosten des Verzeichnissynchronisierungsservers (nicht das Gateway-Subnetz). Alle anderen Einstellungen bleiben bei ihren Standardwerten.
    
Stellen Sie sicher, dass der Verzeichnissynchronisierungsserver DNS ordnungsgemäß verwendet. Überprüfen Sie dazu Ihr internes DNS, und vergewissern Sie sich, dass für den virtuellen Computer ein Adresseintrag (A-Datensatz) mit seiner IP-Adresse hinzugefügt wurde. 
  
Befolgen Sie die Anweisungen unter [Herstellen einer Verbindung mit dem virtuellen Computer und Anmelden](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon), um über eine Remotedesktopverbindung eine Verbindung mit dem Verzeichnissynchronisierungsserver herzustellen. Fügen Sie den virtuellen Computer nach dem Anmelden der lokalen AD DS-Domäne hinzu.
  
Damit Azure AD Connect auf Internetressourcen zugreifen kann, müssen Sie den Verzeichnissynchronisierungsserver für die Verwendung des lokalen Netzwerkproxyservers konfigurieren. Wenden Sie sich für mögliche zusätzlichen Konfigurationsschritte an Ihren Netzwerkadministrator.
  
Nachfolgend sehen Sie die daraus resultierende Konfiguration.
  
![Phase 2 des Verzeichnissynchronisierungsservers für Microsoft 365, gehostet in Azure](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
Diese Abbildung zeigt den virtuellen Computer des Verzeichnissynchronisierungsservers im lokalen virtuellen Azure-Netzwerk.
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a>Phase 3: Installieren und Konfigurieren von Azure AD Connect

Gehen Sie wie folgt vor:
  
1. Stellen Sie mithilfe einer Remotedesktopverbindung mit einem AD DS-Domänenkonto, das über lokale Administratorberechtigungen verfügt, eine Verbindung mit dem Verzeichnissynchronisierungsserver her. Siehe [Herstellen einer Verbindung mit dem virtuellen Computer und Anmelden](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).
    
2. Öffnen Sie auf dem Verzeichnissynchronisierungsserver den Artikel [Einrichten der Verzeichnissynchronisierung für Microsoft 365](set-up-directory-synchronization.md) , und befolgen Sie die Anweisungen für die Verzeichnissynchronisierung mit Kennworthash Synchronisierung.
    
> [!CAUTION]
> Setup erstellt das Konto **AAD_xxxxxxxxxxxx** in der Organisationseinheit (OU) Lokale Benutzer. Verschieben oder entfernen Sie dieses Konto nicht, da dann die Synchronisierung misslingt.
  
Nachfolgend sehen Sie die daraus resultierende Konfiguration.
  
![Phase 3 des Verzeichnissynchronisierungsservers für Microsoft 365, gehostet in Azure](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
Diese Abbildung zeigt den Verzeichnissynchronisierungsserver mit Azure AD Connect im lokalen virtuellen Azure-Netzwerk.
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a>Zuweisen von Speicherorten und Lizenzen zu Benutzern in Microsoft 365

Azure AD Connect Konten zu Ihrem Microsoft 365-Abonnement vom lokalen AD DS hinzufügt, müssen die Konten jedoch mit einem Standort und Lizenzen konfiguriert sein, damit sich Benutzer bei Microsoft 365 anmelden und die Dienste verwenden können. Führen Sie die folgenden Schritte aus, um den Speicherort hinzuzufügen und Lizenzen für die entsprechenden Benutzerkonten zu aktivieren:
  
1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com)an, und klicken Sie dann auf **Admin**.
    
2. Klicken Sie im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.
    
3. Aktivieren Sie in der Liste der Benutzerkonten das Kontrollkästchen neben dem zu aktivierenden Benutzer.
    
4. Klicken Sie auf der Seite für den Benutzer auf **Bearbeiten** für **Produktlizenzen**.
    
5. Wählen Sie auf der Seite **Produktlizenzen** unter **Speicherort** einen Speicherort für den Benutzer aus, und aktivieren Sie dann die entsprechenden Lizenzen für den Benutzer.
    
6. Wenn Sie fertig sind, klicken Sie auf **Speichern**, und klicken Sie dann zweimal auf **Schließen**.
    
7. Kehren Sie zu Schritt 3 zurück, um weitere Benutzer zu bearbeiten.
    
## <a name="see-also"></a>Siehe auch

[Microsoft 365 Lösungs- und Architektur-Center](../solutions/solution-architecture-center.md)
  
[Verbinden eines lokalen Netzwerks mit einem virtuellen Microsoft Azure-Netzwerk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[Herunterladen von Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594)
  
[Einrichten der Verzeichnissynchronisierung für Microsoft 365](set-up-directory-synchronization.md)
  
