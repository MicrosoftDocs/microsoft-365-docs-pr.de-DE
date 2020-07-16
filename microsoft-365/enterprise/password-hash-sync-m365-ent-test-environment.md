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
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Demonstrieren der Kennworthashsynchronisierung und Anmeldung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 7b1ba549a9ac9d3faec8b717a0f76cca1200352b
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371440"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

*Diese Testumgebungsanleitung kann für Microsoft 365 Enterprise- und Office 365 Enterprise-Testumgebungen verwendet werden.*

Viele Organisationen verwenden Azure AD Connect und die Kennwort-Hash-Synchronisierung, um die Gruppe von Konten in ihrer lokalen Active Directory Domain Services (AD DS)-Gesamtstruktur mit den Konten im Azure AD-Mandanten ihres Microsoft 365-Abonnements zu synchronisieren. In diesem Artikel wird beschrieben, wie Sie Kennwort-Hash-Synchronisierung in der Microsoft 365-Testumgebung hinzufügen können, woraus die folgende Konfiguration resultiert:
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Es gibt zwei Hauptphasen bei der Einrichtung dieser Testumgebung:
  
1. Erstellen der simulierten Microsoft 365-Testumgebung.
2. Installieren und Konfigurieren von Azure AD Connect auf APP1.
    
> [!TIP]
> Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung

Befolgen Sie die Anweisungen in der [simulierten Unternehmensstandardkonfiguration für Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Damit wird die Konfiguration unten implementiert.
  
![Die simulierte Unternehmensstandardkonfiguration](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus:  
  
- Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5 oder Office 365 E5.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem virtuellen Azure-Netzwerk besteht. DC1 ist ein Domänencontroller für die AD DS-Domäne testlab.\<Name Ihrer öffentlichen Domäne>. Phase 2: Erstellen und Registrieren der TestLab-Domäne

## <a name="phase-2-create-and-register-the-testlab-domain"></a>In dieser Phase fügen Sie eine öffentliche DNS-Domäne zu Ihrem Abonnement hinzu.

First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription.

Als erstes arbeiten Sie mit Ihrem öffentlichen DNS-Registrierungsanbieter, um einen neuen öffentlichen DNS-Domänennamen basierend auf Ihrem aktuellen Domänennamen zu erstellen, und fügen diesen Ihrem Abonnement hinzu. Es wird empfohlen, dass Sie den Namen "**testlab.**\<Ihre öffentliche Domäne>" verwenden. Wenn der Name Ihrer öffentliche Domänen beispielsweise "**<span>contoso</span>.com**" ist, fügen Sie den öffentlichen Domänennamen "**<span>testlab</span>.contoso.com**" hinzu.
  
Dies umfasst das Hinzufügen von zusätzlichen DNS-Einträgen zur Domäne **testlab.** \<Ihre öffentliche Domäne>. Weitere Informationen finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain). Nachfolgend sehen Sie die daraus resultierende Konfiguration. Registrierung des Domänennamens „testlab“ Diese Konfiguration besteht aus:  

Testversionen oder kostenpflichtige Abonnements von Microsoft 365 E5 oder Office 365 E5 mit der registrieren DNS-Domäne testlab.\<Name Ihrer öffentlichen Domäne>.
  
![Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Für „testlab.\<Name Ihrer öffentlichen Domäne>“ gilt jetzt Folgendes:

- Die Domäne wird von öffentlichen DNS-Datensätzen unterstützt. In Ihren Microsoft 365-Abonnements registriert.
- Die Domäne ist die AD DS-Domäne in Ihrem simulierten Intranet.

Wenn Sie aufgefordert werden, einen Benutzernamen und ein Kennwort anzugeben: Geben Sie „<strong>user1@testlab.</strong>\<Name Ihrer öffentlichen Domäne>“ und das Kennwort für „Benutzer1“ an. Sie sollten sich erfolgreich als „Benutzer1“ anmelden können.

- Installieren Sie zunächst Azure AD Connect auf APP1 und konfigurieren Sie es.
- Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ eine Verbindung zu APP1 her.
- Öffnen Sie über den Desktop auf APP1 eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie die folgenden Befehle aus, um die verstärkte Sicherheit in Internet Explorer zu deaktivieren:
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Klicken Sie auf der Taskleiste auf **Internet Explorer**, und wechseln Sie zu [https://aka.ms/aadconnect](https://aka.ms/aadconnect).

Klicken Sie auf der Seite „Microsoft Azure Active Directory Connect“ auf **Herunterladen** und dann auf **Ausführen**.
  
Klicken Sie auf der Seite **Willkommen bei Azure AD Connect** auf **Ich stimme zu** und dann auf **Weiter**.

1. Klicken Sie auf der Seite **Express-Einstellungen** auf **Express-Einstellungen verwenden**.
    
2. Geben Sie auf der Seite **Mit Azure AD verbinden** unter **Benutzername** den Namen Ihres globalen Administratorkontos und unter **Kennwort** das zugehörige Kennwort ein. Klicken Sie dann auf **Weiter**.
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Geben Sie auf der Seite **Mit AD DS verbinden** den Namen **TESTLAB\\Benutzer1** unter **Benutzername** und das zugehörige Kennwort unter **Kennwort** ein. Klicken Sie dann auf **Weiter**.
    
4. Klicken Sie auf der Seite **Bereit zur Konfiguration** auf **Installieren**.
    
5. Klicken Sie auf der Seite **Konfiguration abgeschlossen** auf **Beenden**.
    
6. Wechseln Sie im Internet Explorer zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
7. Klicken Sie im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.
    
8. Sie sehen das Konto **Benutzer 1**.
    
9. Dieses Konto gehört zur AD DS-Domäne „TESTLAB“. Dass es angezeigt wird, belegt, dass die Verzeichnissynchronisierung erfolgreich war.
    
10. Klicken Sie auf das **User1**-Konto und dann auf **Lizenzen und Apps**.
    
11. Wählen Sie in **Produktlizenzen** Ihren Standort aus (sofern erforderlich), deaktivieren Sie die **Office 365 E5**-Lizenz, und aktivieren Sie die **Microsoft 365 E5**-Lizenz.
    
12. Klicken Sie unten auf der Seite auf **Speichern** und dann auf **Schließen**.
    
    Als Nächstes testen Sie, ob Sie sich mit dem Benutzernamen "<strong>user1@testlab.</strong>\<Name Ihrer öffentlichen Domäne>" des Kontos "User1" bei Ihrem Abonnement anmelden können. Melden Sie sich über APP1 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.
    
13. When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password.
    
14. You should successfully sign in as User1. 

15. Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator ist.
    
Daher wird das Symbol **Admin** nicht als Option angezeigt. Nachfolgend sehen Sie die daraus resultierende Konfiguration.

1. Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung

2. Diese Konfiguration besteht aus:  Testversionen oder kostenpflichtigen Abonnements von Microsoft 365 E5 oder Office 365 E5 mit der registrieren DNS-Domäne „TESTLAB.\<Ihr Domänenname>. Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. 
 
Azure AD Connect wird auf APP1 ausgeführt, um die AD DS-Domäne "TESTLAB" mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements regelmäßig zu synchronisieren. Das Konto „Benutzer 1“ in der AD DS-Domäne „TESTLAB“ wurde mit dem Azure AD-Mandanten synchronisiert. 

Nächster Schritt

![Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Siehe auch 
  
- [Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) [Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)
- [Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.
- The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.

## <a name="next-step"></a>Next step

Explore additional <bpt id="p1">[</bpt>identity<ept id="p1">](m365-enterprise-test-lab-guides.md#identity)</ept> features and capabilities in your test environment.

## <a name="see-also"></a>See also

<bpt id="p1">[</bpt>Microsoft 365 Enterprise Test Lab Guides<ept id="p1">](m365-enterprise-test-lab-guides.md)</ept>

<bpt id="p1">[</bpt>Deploy Microsoft 365 Enterprise<ept id="p1">](deploy-microsoft-365-enterprise.md)</ept>

<bpt id="p1">[</bpt>Microsoft 365 Enterprise documentation<ept id="p1">](https://docs.microsoft.com/microsoft-365-enterprise/)</ept>


