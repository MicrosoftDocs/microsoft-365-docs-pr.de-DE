---
title: Vorbereiten Ihrer Microsoft Threat Protection-Testumgebung
description: Vorbereiten der Anmeldung von teilnehmenden, Zeitrahmen, Umgebungs Überlegungen und Adoptions Reihenfolge beim Einrichten Ihrer Microsoft Threat Protection-Testumgebung oder Pilotumgebung
keywords: MTP-Testvorbereitung, MTP-Pilotbereitstellung, Vorbereitung für das Ausführen eines MTP-Pilotprojekts, Ausführen eines Pilot-MTP-Projekts, bereitstellen, vorbereiten, Interessenvertreter, Zeitachse, Umgebung, Endpunkt, Server, Verwaltung, Einführung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a684f49ab8c70a19a17ff43195197677bccbf95b
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816769"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>Vorbereiten Ihrer Testlabor-oder Pilotumgebung für den Microsoft Threat Protection-Test

**Gilt für:**
- Microsoft Threat Protection

Das Erstellen eines Microsoft Threat Protection-Testlabors oder einer Pilotumgebung und deren Bereitstellung ist ein dreistufiger Prozess:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Vorbereiten Ihrer Testlabor-oder Pilotumgebung für den Microsoft Threat Protection-Test" />
      <br/>Phase 1: Vorbereiten </a><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Einrichten Ihres Microsoft Threat Protection-Testlabors oder einer Pilotumgebung" />
      <br/>Phase 2: Setup </a><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="Konfigurieren der einzelnen Microsoft Threat Protection-Pfeiler und an Bord ihrer Endpunkte" />
      <br/>Phase 3: Konfigurieren von & Onboard</a><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

Sie befinden sich derzeit in der Vorbereitungsphase.


Die Vorbereitung ist für eine erfolgreiche Bereitstellung entscheidend. Dieser Abschnitt führt Sie durch die Schritte, die Sie bei der Vorbereitung der Erstellung einer Test Labor-oder Pilotumgebung für Ihre Microsoft Threat Protection-Bereitstellung überprüfen müssen.

## <a name="prerequisites"></a>Voraussetzungen
Erfahren Sie mehr über die Lizenzierungs-, Hardware-und Softwareanforderungen und andere Konfigurationseinstellungen für die Einrichtung und Verwendung von Microsoft Threat Protection. Lesen Sie die Mindestanforderungen für [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?view=o365-worldwide), [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Interessengruppen und Abmelden
Im folgenden Abschnitt werden alle Beteiligten identifiziert, die an dem Projekt beteiligt sind und die sich möglicherweise für die Evaluierung oder das Ausführen eines Pilotprojekts anmelden, überprüfen oder auf dem laufenden halten müssen.

>[!NOTE]
>Nicht alle Organisationen haben möglicherweise die Fälligkeit der Sicherheitsorganisation für solche Rollen. Wenden Sie sich in diesem Fall an Ihr Führungsteam unter Review and Approval Verantwortlichkeiten.

Hinzufügen von Beteiligten zur folgenden Tabelle entsprechend Ihrer Organisation

-   Also = Sign-off für dieses Projekt

-   R = dieses Projekt überprüfen und eingabebereit stellen

-   I = über dieses Projekt informiert

| Name                 | Rolle                                                                                                                                                                                                          | Aktion |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Namen und e-Mail eingeben | **Chief Information Security Officer (CISO)** *ein Executive Representative, der innerhalb der Organisation als Sponsor für die neue Technologiebereitstellung fungiert.*                                                  | Also     |
| Namen und e-Mail eingeben | **Leiter des Cyber Defense Operations Center (Cdoc)** *ein Vertreter des Cdoc-Teams, das dafür verantwortlich ist, zu definieren, wie diese Änderung mit den Prozessen im Kunden-Sicherheits Betriebsteam abgeglichen wird.*       | Also     |
| Namen und e-Mail eingeben | **Security Architect** *ein Vertreter des Sicherheitsteams, das für die Definition dieser Änderung an der Kern Sicherheitsarchitektur in der Organisation verantwortlich ist.*                         | R      |
| Namen und e-Mail eingeben | **Arbeitsplatz Architekt** *ein Vertreter des IT-Teams, der dafür verantwortlich ist, zu definieren, wie diese Änderung an der zentralen Arbeitsplatz Architektur in der Organisation ausgerichtet ist.*                             | R      |
| Namen und e-Mail eingeben | **Security Analyst** *ein Vertreter des Cdoc-Teams, der eine Eingabe in Bezug auf die Erkennungsfunktionen, die Benutzeroberfläche und die allgemeine Nützlichkeit dieser Änderung aus Sicht der Sicherheitsvorgänge bereitstellen kann.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Vorbereiten des Azure-Active Directory
Überspringen Sie diesen Schritt, wenn Sie die Synchronisierung zwischen Active Directory und Azure Active Directory lokal aktiviert haben. Lesen Sie die Dokumentation zu bewährten Methoden aus Azure Active Directory. Die folgenden Schritte sind für die Evaluierung oder Ausführung eines Pilotprojekts für Microsoft Threat Protection optimiert.

1. Wechseln Sie zum [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) -Portal > **Azure AD Connect**. 
![Bild von Azure Active Directory Portalseite](../../media/mtp-eval-1.png) <br> 

2. Klicken Sie auf **herunterladen** aus **Microsoft Azure Active Directory Connect** , und übertragen Sie Sie auf Ihren Domänen Controller.
![Bild der Azure Active Directoru Connect-Download Seite](../../media/mtp-eval-2.png) <br>

3. Führen Sie auf dem Domänencontroller den Azure Active Directory Connect-Assistenten aus. Lesen Sie die Lizenzbedingungen und die Datenschutzerklärung, und aktivieren Sie das Kontrollkästchen, wenn Sie zustimmen. Klicken Sie auf **Weiter**.
![Bild Azure AD Willkommensseite für Connect](../../media/mtp-eval-3.png) <br>

4. Navigieren Sie zu **Express Einstellungen**.
![Seite "Bild der Express-Einstellungen"](../../media/mtp-eval-4.png) <br>

5. Geben Sie Ihre globalen Administratoranmeldeinformationen ein. Klicken Sie auf **Weiter**.
![Image von Connect to Azure AD Page, auf der Sie Ihre globalen Administratoranmeldeinformationen eingeben sollten](../../media/mtp-eval-5.png) <br>

6. Geben Sie Ihre Active Directory-Domänendienste Anmeldeinformationen für den Unternehmensadministrator ein. Klicken Sie auf **Weiter**.
![Bild von Connect to AD DS Seite, auf der Sie Ihre Anmeldeinformationen eingeben sollten](../../media/mtp-eval-6.png) <br>

7. Klicken Sie auf **Installieren** , um die Konfiguration zu bestätigen.
![Seite "Bild der Konfigurations Bestätigung"](../../media/mtp-eval-7.png) <br>

8. Herzlichen Glückwunsch, Sie haben Azure Active Directory Connect erfolgreich konfiguriert.
![Bild einer erfolgreich konfigurierten Azure Active Directory Connect-Seite](../../media/mtp-eval-8.png) <br>

Sie können nun [Benutzer und Gruppen zu Active Directory hinzufügen](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) und [eine Sam-R-Richtlinie konfigurieren](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).  


## <a name="configuration-order"></a>Konfigurations Reihenfolge
Die folgende Tabelle gibt die Reihenfolge an, die Microsoft für die Konfiguration der Microsoft Threat Protection-Komponenten für Ihre Test Labor-oder Pilot Umgebungs Bereitstellung empfiehlt.

| Komponente                               | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rangfolge der Konfigurations Reihenfolge |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Office 365 Advanced Threat Protection| Office 365 ATP schützt Ihre Organisation vor böswilligen Bedrohungen durch e-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. <br> [Weitere Informationen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)                                                                                                                                                                                                                                             | 1                    |
|Azure Advanced Threat Protection|Azure ATP verwendet Active Directory Signale, um erweiterte Bedrohungen, kompromittierte Identitäten und böswillige Insider Aktionen, die an Ihre Organisation gerichtet sind, zu identifizieren, zu erkennen und zu untersuchen. <br> [Weitere Informationen](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2  |
|Microsoft Cloud App-Sicherheit| Microsoft Cloud App Security ist ein Cloud Access Security Broker (CASB), der in mehreren Clouds arbeitet. Es bietet umfangreiche Sichtbarkeit, Kontrolle über Daten Reisen und ausgefeilte Analysen, um Bedrohungen für alle Cloud-Dienste zu identifizieren und zu bekämpfen. <br> [Weitere Informationen](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                    |
|Microsoft Defender Advanced Threat Protection | Die Microsoft Defender ATP-Funktionen für die Endpunkterkennung und Beantwortung bieten erweiterte Angriffserkennungen, die nahezu in Echtzeit umgesetzt werden können. Sicherheitsanalysten können Benachrichtigungen effektiv priorisieren, Einblick in den gesamten Umfang einer Verletzung erhalten und Aktionen ergreifen, um Bedrohungen zu beheben. <br> [Weitere Informationen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Nächster Schritt
![Phase 2: Setup](../../media/setup.png) <br>[Phase 2: Setup](setup-mtpeval.md)<br> Einrichten Ihres Microsoft Threat Protection-Testlabors oder einer Pilotumgebung

