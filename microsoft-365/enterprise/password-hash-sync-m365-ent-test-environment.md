---
title: Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Demonstrieren der Kennworthashsynchronisierung und Anmeldung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 2d5fbd3ed2a2afb994fc36f5ba3a15a8c55a274e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819388"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

*Diese Testumgebungsanleitung kann für Microsoft 365 Enterprise- und Office 365 Enterprise-Testumgebungen verwendet werden.*

Viele Organisationen verwenden Azure AD Connect und die Kennwort-Hash-Synchronisierung, um die Gruppe von Konten in ihrer lokalen Active Directory Domain Services (AD DS)-Gesamtstruktur mit den Konten im Azure AD-Mandanten ihres Microsoft 365-Abonnements zu synchronisieren. In diesem Artikel wird beschrieben, wie Sie Kennwort-Hash-Synchronisierung in der Microsoft 365-Testumgebung hinzufügen können, woraus die folgende Konfiguration resultiert:
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Es gibt zwei Hauptphasen bei der Einrichtung dieser Testumgebung:
  
1. Erstellen der simulierten Microsoft 365-Testumgebung.
2. Installieren und Konfigurieren von Azure AD Connect auf APP1.
    
> [!TIP]
> Wechseln Sie zu [Microsoft 365 Enterprise Test Lab Ratgeberstapel](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung

Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.
  
![Die simulierte Unternehmensstandardkonfiguration](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus:  
  
- Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5 oder Office 365 E5.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem virtuellen Azure-Netzwerk besteht. DC1 ist ein Domänencontroller für testlab.\<your public domain name> AD DS-Domäne.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Phase 2: Erstellen und Registrieren der TestLab-Domäne

In dieser Phase fügen Sie eine öffentliche DNS-Domäne zu Ihrem Abonnement hinzu.

Arbeiten Sie zunächst mit Ihrem öffentlichen DNS-Registrierungsanbieter zusammen, um basierend auf Ihrem aktuellen Domänennamen einen neuen öffentlichen DNS-Domänennamen zu erstellen und diesen Ihrem Abonnement hinzuzufügen. Es wird empfohlen, dass Sie den Namen **testlab.**\<your public domain> verwenden. Wenn Ihre öffentliche Domänenname beispielsweise **<span>contoso</span>.com** ist, fügen Sie den öffentlichen Domänennamen **<span>testlab</span>.contoso.com** hinzu.
  
Als Nächstes fügen Sie **testlab.**\<your public domain> Domäne zu Ihrer Microsoft 365- oder Office 365-Testversion oder Ihrem bezahlten Abonnement hinzu, indem Sie den Domänenregistrierungsprozess durchlaufen. Dies umfasst das Hinzufügen von zusätzlichen DNS-Einträgen zur Domäne **testlab.**\<your public domain> Domain vorgenommen. Weitere Informationen finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain). 

Nachfolgend sehen Sie die daraus resultierende Konfiguration.
  
![Registrierung des Domänennamens „testlab“](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Diese Konfiguration besteht aus: 

- Microsoft 365 E5 oder Office 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne testlab.\<your public domain name> registriert.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.

Beachten Sie, wie wir testlab.\<your public domain name> heißt jetzt:

- Die Domäne wird von öffentlichen DNS-Datensätzen unterstützt.
- In Ihren Microsoft 365-Abonnements registriert.
- Die Domäne ist die AD DS-Domäne in Ihrem simulierten Intranet.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Phase 3: Installieren von Azure AD Connect auf APP1

In dieser Phase installieren und konfigurieren Sie das Azure AD Connect-Tool auf APP1 und vergewissern sich, dass es funktioniert.
  
Installieren Sie zunächst Azure AD Connect auf APP1 und konfigurieren Sie es.

1. Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ eine Verbindung zu APP1 her.
    
2. Öffnen Sie über den Desktop auf APP1 eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie die folgenden Befehle aus, um die verstärkte Sicherheit in Internet Explorer zu deaktivieren:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Klicken Sie auf der Taskleiste auf **Internet Explorer**, und wechseln Sie zu [https://aka.ms/aadconnect](https://aka.ms/aadconnect).
    
4. Klicken Sie auf der Seite „Microsoft Azure Active Directory Connect“ auf **Herunterladen** und dann auf **Ausführen**.
    
5. Klicken Sie auf der Seite **Willkommen bei Azure AD Connect** auf **Ich stimme zu** und dann auf **Weiter**.
    
6. Klicken Sie auf der Seite **Express-Einstellungen** auf **Express-Einstellungen verwenden**.
    
7. Geben Sie auf der Seite **Mit Azure AD verbinden** unter **Benutzername** den Namen Ihres globalen Administratorkontos und unter **Kennwort** das zugehörige Kennwort ein. Klicken Sie dann auf **Weiter**.
    
8. Geben Sie auf der Seite **Mit AD DS verbinden** den Namen **TESTLAB\\Benutzer1** unter **Benutzername** und das zugehörige Kennwort unter **Kennwort** ein. Klicken Sie dann auf **Weiter**.
    
9. Klicken Sie auf der Seite **Bereit zur Konfiguration** auf **Installieren**.
    
10. Klicken Sie auf der Seite **Konfiguration abgeschlossen** auf **Beenden**.
    
11. Wechseln Sie im Internet Explorer zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. Klicken Sie im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.
    
    Sie sehen das Konto **Benutzer 1**. Dieses Konto gehört zur AD DS-Domäne „TESTLAB“. Dass es angezeigt wird, belegt, dass die Verzeichnissynchronisierung erfolgreich war.
    
13. Klicken Sie auf das **User1**-Konto und dann auf **Lizenzen und Apps**.
    
14. Wählen Sie in **Produktlizenzen** Ihren Standort aus (sofern erforderlich), deaktivieren Sie die **Office 365 E5**-Lizenz, und aktivieren Sie die **Microsoft 365 E5**-Lizenz. 

15. Klicken Sie unten auf der Seite auf **Speichern** und dann auf **Schließen**.
    
Als nächstes testen Sie die Möglichkeit, sich mit <strong>user1@testlab.</strong>\<your domain name> bei Ihrem Abonnement anzumelden Benutzername des User1-Kontos.

1. Melden Sie sich über APP1 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.

2. Wenn Sie zur Eingabe eines Benutzernamens und Kennworts aufgefordert werden, geben Sie <strong>user1@testlab.</strong>\<your domain name> ein und das Kennwort für User1. Sie sollten sich erfolgreich als „Benutzer 1“ anmelden können. 
 
Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator ist. Daher wird das Symbol **Admin** nicht als Option angezeigt. 

Nachfolgend sehen Sie die daraus resultierende Konfiguration.

![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Diese Konfiguration besteht aus:  
  
- Microsoft 365 E5 oder Office 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne TESTLAB.\<your domain name> registriert.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Azure AD Connect wird auf APP1 ausgeführt, um die AD DS-Domäne "TESTLAB" mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements regelmäßig zu synchronisieren.
- Das Konto „Benutzer 1“ in der AD DS-Domäne „TESTLAB“ wurde mit dem Azure AD-Mandanten synchronisiert.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


