---
title: Konfigurieren von IRM für die Verwendung eines lokalen AD RMS-Servers
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie die Verwaltung von Informationsrechten (Information Rights Management, IRM) in Exchange Online für die Verwendung eines AD RMS-Servers (Active Directory Rights Management Service) konfigurieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a520a3e55ae1137a0a4cc417dc68097d0793d978
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908565"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>Konfigurieren von IRM für die Verwendung eines lokalen AD RMS-Servers
  
Für die Verwendung mit lokalen Bereitstellungen verwendet irM (Information Rights Management) in Exchange Online Active Directory-Rechteverwaltungsdienste (AD RMS), eine Information Protection-Technologie in Windows Server 2008 und höher. IRM-Schutz wird auf E-Mails angewendet, indem eine AD RMS-Berechtigungsrichtlinienvorlage auf eine E-Mail angewendet wird. Rechte werden der Nachricht selbst zugeordnet, sodass der Schutz sowohl online und offline als auch innerhalb und außerhalb der Firewall der Organisation stattfindet.
  
Mit diesem Thema wird die Konfiguration von IRM für die Verwendung eines AD RMS-Servers erläutert. Informationen zur Verwendung der neuen Funktionen für die Office 365-Nachrichtenverschlüsselung mit Azure Active Directory und Azure Rights Management finden Sie unter Häufig gestellte Fragen zur [Office 365-Nachrichtenverschlüsselung.](./ome-faq.md)
  
Weitere Informationen zu IRM in Exchange Online finden Sie unter [Verwaltung von Informationsrechten in Exchange Online](information-rights-management-in-exchange-online.md).
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 30 Minuten

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Information Rights Management" im Thema [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions). 

- Ein AD RMS-Server mit Windows Server 2008 oder höher. Informationen zum Bereitstellen von AD RMS finden Sie im Thema zum [Installieren eines AD RMS-Clusters](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).

- Informationen zum Installieren und Konfigurieren von Windows PowerShell sowie zum Herstellen einer Verbindung mit dem Dienst finden Sie unter [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Thema gelten können, finden Sie unter [Tastenkombinationen für](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)das Exchange Admin Center in Exchange Online .

> [!TIP]
> Liegt ein Problem vor? Bitten Sie in den Exchange-Foren um Hilfe. Besuchen Sie die Foren unter [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) oder [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="how-do-you-do-this"></a>Wie gehen Sie dazu vor?
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>Schritt 1: Verwenden der AD RMS-Konsole für den Export einer vertrauenswürdigen Veröffentlichungsdomäne von einem AD RMS-Server

Der erste Schritt ist das Exportieren einer vertrauenswürdigen Veröffentlichungsdomäne (TPD) vom lokalen AD RMS-Server in eine XML-Datei. Die vertrauenswürdige Veröffentlichungsdomäne (TPD) beinhaltet die folgenden, für die Verwendung von RMS-Funktionen erforderlichen Einstellungen:
  
- Das lizenzgebende Serverzertifikat (SLC) zum Signieren und Verschlüsseln von Zertifikaten und Lizenzen.

- Die für Lizenzierung und Veröffentlichung verwendeten URLs.

- Die AD RMS-Rechterichtlinienvorlagen, die mit dem spezifischen lizenzgebenden Serverzertifikat (SLC) für diese TPD erstellt wurden.

Wenn Sie die TPD importieren, wird sie in Exchange Online gespeichert und geschützt.
  
1. Öffnen Sie die AD RMS-Konsole, und erweitern Sie dann den AD RMS-Cluster.

2. Erweitern Sie in der Konsolenstruktur den Knoten **Vertrauensrichtlinien**, und klicken Sie dann auf **Vertrauenswürdige Veröffentlichungsdomänen**.

3. Wählen Sie das Zertifikat für die zu exportierende Domäne im Ergebnisbereich aus.

4. Klicken Sie im Bereich **Aktionen** auf **Vertrauenswürdige Veröffentlichungsdomäne exportieren**.

5. Klicken Sie im Feld **Veröffentlichungsdomänendatei** auf **Speichern unter**, um die Datei an einem bestimmten Speicherort auf dem lokalen Computer zu speichern. Geben Sie einen Dateinamen und die  `.xml`-Dateinamenerweiterung an, und klicken Sie dann auf **Speichern**.

6. Geben Sie in den Feldern **Kennwort** und **Kennwort bestätigen** ein sicheres Kennwort ein, das zum Verschlüsseln der Datei der vertrauenswürdigen Veröffentlichungsdomäne verwendet wird. Dieses Kennwort muss beim Importieren der TPD in die Cloud-basierte E-Mail-Organisation angegeben werden. 

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>Schritt 2: Verwenden der Exchange-Verwaltungsshell zum Importieren der TPD in Exchange Online

Nachdem die TPD in eine XML-Datei exportiert wurde, müssen Sie sie in Exchange Online importieren. Beim Importieren einer TPD werden auch die Vorlagen Ihrer Organisation aus AD RMS importiert. Die erste importierte TPD wird zur Standard-TPD für die Cloud-basierte Organisation. Wenn Sie eine weitere TPD importieren, können Sie diese mithilfe der Option **Default** als die für Benutzer verfügbare Standard-TPD festlegen. 
  
Führen Sie zum Importieren der TPD in Windows PowerShell den folgenden Befehl aus:
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

Die Werte für die Parameter  _ExtranetLicensingUrl_ und  _IntranetLicensingUrl_ können Sie in der Konsole der Active Directory-Rechteverwaltungsdienste abrufen. Wählen Sie den AD RMS-Cluster in der Konsolenstruktur aus. Die URLs für die Lizenzierung werden im Ergebnisbereich angezeigt. Diese URLs werden von E-Mail-Clients verwendet, wenn Inhalt entschlüsselt werden muss und wenn Exchange Online die zu verwendende TPD ermitteln muss.
  
Beim Ausführen dieses Befehls werden Sie zur Eingabe eines Kennworts aufgefordert. Geben Sie das Kennwort ein, das Sie beim Exportieren der TPD vom AD RMS-Server angegeben haben.
  
Beispiel: Durch den folgenden Befehl wird die TPD mit dem Namen "Exported TPD" anhand der vom AD RMS-Server exportierten XML-Datei importiert und auf dem Desktop des Administratorkontos gespeichert. Mit dem Name-Parameter wird ein Name für die TPD angegeben.
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).
  
#### <a name="how-do-you-know-this-step-worked"></a>Woher wissen Sie, dass dieser Schritt erfolgreich war?

Führen Sie zur Überprüfung eines erfolgreichen Imports der TPD das Cmdlet **Get-RMSTrustedPublishingDomain** zum Abruf von TPDs in Ihrer Exchange Online-Organisation auf. Für Einzelheiten finden Sie Beispiele unter [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>Schritt 3: Verwenden der Exchange-Verwaltungsshell zur Verteilung einer AD RMS-Rechterichtlinienvorlage

Nach dem Import der TPD müssen Sie sicherstellen, dass eine AD RMS-Rechterichtlinienvorlage verteilt wird. Eine verteilte Vorlage ist für Outlook im Web (früher als Outlook Web App bezeichnet) sichtbar, die die Vorlagen dann auf eine E-Mail-Nachricht anwenden können.
  
Führen Sie den folgenden Befehl aus, um eine Liste aller Vorlagen in der Standard-TPD anzuzeigen:
  
```powershell
Get-RMSTemplate -Type All | fl
```

Wenn der Wert des Parameters  _Type_ `Archived` lautet, ist die Vorlage nicht für Benutzer sichtbar. In Outlook im Web sind nur verteilte Vorlagen in der Standard-TPD verfügbar.
  
Führen Sie zum Verteilen einer Vorlage den folgenden Befehl aus:
  
```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

Beispiel: Durch den folgenden Befehl wird die Vorlage "Company Confidential" importiert:
  
```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) und [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).
  
**Vorlage "Nicht weiterleiten"**
  
Wenn Sie die Standard-TPD aus der lokalen Organisation in Exchange Online importieren, wird eine RMS-Rechterichtlinienvorlage mit der Bezeichnung **Do Not Forward** importiert. Diese Vorlage wird standardmäßig verteilt, wenn Sie die Standard-TPD importieren. Die Vorlage **Do Not Forward** kann nicht mit dem Cmdlet **Set-RMSTemplate** geändert werden. 
  
Wenn die Vorlage **Do Not Forward** auf eine Nachricht angewendet wird, kann die Nachricht nur von Empfängern der Nachricht gelesen werden. Darüber hinaus können Empfänger folgende Aktionen ausführen:
  
- Weiterleiten der Nachricht an eine andere Person

- Kopieren von Inhalt aus der Nachricht

- Drucken der Nachricht

> [!IMPORTANT]
> Durch die Vorlage **Do Not Forward** kann nicht verhindert werden, dass Informationen in einer Nachricht mit Drittanbieter-Bildschirmaufnahmeprogrammen oder Kameras kopiert oder von Benutzern manuell übertragen werden. 
  
Sie können zusätzliche AD RMS-Rechterichtlinienvorlagen auf dem AD RMS-Server in der lokalen Organisation erstellen, um Ihre Anforderungen hinsichtlich des IRM-Schutzes zu erfüllen. Wenn Sie zusätzliche AD RMS-Vorlagen erstellen, müssen Sie die TPD erneut vom lokalen AD RMS-Server exportieren und die TPD in der Cloud-basierten E-Mail-Organisation aktualisieren.
  
#### <a name="how-do-you-know-this-step-worked"></a>Woher wissen Sie, dass dieser Schritt erfolgreich war?

Führen Sie zur Überprüfung einer erfolgreichen Verteilung einer AD RMS-Rechterichtlinienvorlage das Cmdlet **Get-RMSTemplate** zur Prüfung der Eigenschaften der Vorlage aus. Für Einzelheiten finden Sie Beispiele unter [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>Schritt 4: Verwenden der Exchange-Verwaltungsshell zur Aktivierung von IRM

Führen Sie nach dem Import der TPD und der Verteilung der AD RMS-Rechterichtlinienvorlage den folgenden Befehl zur Aktivierung von IRM für Ihre Cloud-basierte E-Mail-Organisation aus.
  
```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).
  
#### <a name="how-do-you-know-this-step-worked"></a>Woher wissen Sie, dass dieser Schritt erfolgreich war?

Zur Überprüfung einer erfolgreichen Aktivierung von IRM führen Sie das Cmdlet [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) zur Prüfung der IRM-Konfiguration in der Exchange Online-Organisation aus.
  
## <a name="how-do-you-know-this-task-worked"></a>Woher wissen Sie, dass diese Aufgabe erfolgreich war?
<a name="sectionSection2"> </a>

Führen Sie zur Überprüfung eines erfolgreichen Imports der TPD und einer erfolgreichen Aktivierung von IRM folgende Schritte aus:
  
- Verwenden Sie das Cmdlet **Test-IRMConfiguration**, um die Funktionalität von IRM zu überprüfen. Details finden Sie in "Beispiel 1" unter [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).

- Verfassen Einer neuen Nachricht in Outlook im Web und  IRM-protect, indem Sie die Option Berechtigungen festlegen im erweiterten Menü auswählen ( ![ Symbol für weitere Optionen ](../media/ITPro-EAC-MoreOptionsIcon.gif) ).