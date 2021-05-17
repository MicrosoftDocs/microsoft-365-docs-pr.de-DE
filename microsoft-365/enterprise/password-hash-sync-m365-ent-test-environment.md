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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Demonstrieren der Kennworthashsynchronisierung und Anmeldung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921504"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 als auch für Office 365 Enterprise verwendet werden.*

Viele Organisationen verwenden Azure AD Connect und die Kennwort-Hash-Synchronisierung, um die Gruppe von Konten in ihrer lokalen Active Directory Domain Services (AD DS)-Gesamtstruktur mit den Konten im Azure AD-Mandanten ihres Microsoft 365-Abonnements zu synchronisieren. 

In diesem Artikel wird beschrieben, wie Sie der testumgebung Microsoft 365 Kennworthashsynchronisierung hinzufügen können, was zu dieser Konfiguration führt:
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Das Einrichten dieser Testumgebung umfasst drei Phasen:
- [Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [Phase 2: Erstellen und Registrieren der TestLab-Domäne](#phase-2-create-and-register-the-testlab-domain)
- [Phase 3: Installieren von Azure AD Connect auf APP1](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung

Befolgen Sie die Anweisungen in [simulierter Unternehmensbasiskonfiguration für Microsoft 365.](simulated-ent-base-configuration-microsoft-365-enterprise.md) Die resultierende Konfiguration sieht wie die folgenden aus:
  
![Die simulierte Unternehmensstandardkonfiguration](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.
- Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem virtuellen Azure-Netzwerk besteht. DC1 ist ein Domänencontroller für das testlab.<*öffentlichen* Domänennamen> AD DS-Domäne.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Phase 2: Erstellen und Registrieren der TestLab-Domäne

Fügen Sie in dieser Phase eine öffentliche DNS-Domäne hinzu, und fügen Sie sie dann Ihrem Abonnement hinzu.

Arbeiten Sie zunächst mit Ihrem öffentlichen DNS-Registrierungsanbieter zusammen, um einen neuen öffentlichen DNS-Domänennamen zu erstellen, der auf Ihrem aktuellen Domänennamen basiert, und fügen Sie ihn dann Ihrem Abonnement hinzu. Es wird empfohlen, den Namen **testlab.<*Ihrer öffentlichen Domäne zu verwenden.* >** Wenn Ihr öffentlicher Domänenname beispielsweise **<span>contoso</span>.com** ist, fügen Sie den öffentlichen Domänennamen hinzu: **<span>testlab</span>.contoso.com**.
  
Fügen Sie als Nächstes **das  > testlab.<** Ihrer öffentlichen Domäne zu Ihrem test- oder kostenpflichtigen Microsoft 365 hinzu, indem Sie den Domänenregistrierungsprozess durchfahren. Dies besteht aus dem Hinzufügen zusätzlicher DNS-Einträge zum **testlab.<*Ihrer öffentlichen Domäne.* >** Weitere Informationen finden Sie unter [Add a domain to Microsoft 365](../admin/setup/add-domain.md).

Die resultierende Konfiguration sieht wie die folgenden aus:
  
![Registrierung des Domänennamens „testlab“](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Diese Konfiguration besteht aus: 

- Ein Microsoft 365 E5 oder kostenpflichtiges Abonnement mit der DNS-Domäne testlab.<Ihrem öffentlichen Domänennamen> registriert. 
- Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.

Beachten Sie, wie testlab.<*Ihrem öffentlichen* Domänennamen> ist:

- Die Domäne wird von öffentlichen DNS-Datensätzen unterstützt.
- In Ihren Microsoft 365-Abonnements registriert.
- Die Domäne ist die AD DS-Domäne in Ihrem simulierten Intranet.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Phase 3: Installieren von Azure AD Connect auf APP1

Installieren und konfigurieren Sie in dieser Phase das Azure AD Verbinden App1, und überprüfen Sie dann, ob es funktioniert.
  
Installieren und konfigurieren Sie zunächst Azure AD Verbinden app1.

1. Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ eine Verbindung zu APP1 her.
    
2. Öffnen Sie über den Desktop auf APP1 eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie die folgenden Befehle aus, um die verstärkte Sicherheit in Internet Explorer zu deaktivieren:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Wählen Sie auf der Taskleiste **Internet Explorer aus,** und wechseln Sie zu [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
4. Wählen Sie Microsoft Azure Active Directory Verbinden Seite **Herunterladen** aus, und wählen Sie dann **Ausführen aus.**
    
5. Wählen Sie **auf der Seite** Willkommen bei Azure AD Verbinden Ich stimme zu , und wählen Sie dann Weiter **aus.** 
    
6. Wählen Sie **auf Einstellungen** Seite Expresseinstellungen **verwenden aus.**
    
7. Geben Sie **auf Verbinden Azure AD** den Namen Ihres globalen Administratorkontos in Benutzername **ein,** geben Sie das Kennwort in **Kennwort** ein, und wählen Sie dann **Weiter aus.**
    
8. Geben Sie **auf Verbinden Zu AD DS** den Namen **TESTLAB \\ User1** in **Benutzername ein,** geben Sie das Kennwort in **Kennwort** ein, und wählen Sie dann **Weiter aus.**
    
9. Wählen Sie **auf der Seite** Bereit zum Konfigurieren die Option Installieren **aus.**
    
10. Wählen Sie **auf der Seite Konfiguration abgeschlossen** die Option Beenden **aus.**
    
11. Wechseln Sie im Internet Explorer zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. Wählen Sie im linken Navigationsbereich Benutzer **> Aktive Benutzer aus.**
    
    Sie sehen das Konto **Benutzer 1**. Dieses Konto gehört zur AD DS-Domäne „TESTLAB“. Dass es angezeigt wird, belegt, dass die Verzeichnissynchronisierung erfolgreich war.
    
13. Wählen Sie **das Benutzerkonto 1** aus, und wählen Sie dann **Lizenzen und Apps aus.**
    
14. Wählen **Sie unter** Produktlizenzen Ihren Standort aus (falls erforderlich), deaktivieren Sie die Office 365 **E5-Lizenz,** und aktivieren Sie dann die **Microsoft 365 E5** Lizenz. 

15. Wählen **Sie unten** auf der Seite Speichern aus, und wählen Sie dann Schließen **aus.**
    
Testen Sie als Nächstes die Möglichkeit, sich bei Ihrem Abonnement mit dem **user1@testlab.< >** Ihrem Domänennamenbenutzernamen des Benutzerkontos "User1" zu anmelden:

1. Melden Sie sich über APP1 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.

2. Wenn Sie zur Eingabe eines Benutzernamens und Kennworts aufgefordert werden, geben **User1@testlab.< >** Domänennamen und das Kennwort User1 an. Sie sollten sich erfolgreich als „Benutzer 1“ anmelden können.
 
Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator ist. Daher wird das Symbol **Admin** nicht als Option angezeigt. 

Die resultierende Konfiguration sieht wie die folgenden aus:

![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Diese Konfiguration besteht aus:  
  
- Microsoft 365 E5 oder Office 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne TESTLAB.<*Ihren* Domänennamen> registriert.
- Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Azure AD Verbinden wird auf APP1 ausgeführt, um die DOMÄNE TESTLAB AD DS regelmäßig mit dem Azure AD-Mandanten Ihres Microsoft 365 synchronisieren.
- Das Konto „Benutzer 1“ in der AD DS-Domäne „TESTLAB“ wurde mit dem Azure AD-Mandanten synchronisiert.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)