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
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487458"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*

Viele Organisationen verwenden Azure AD Connect und die Kennwort-Hash-Synchronisierung, um die Gruppe von Konten in ihrer lokalen Active Directory Domain Services (AD DS)-Gesamtstruktur mit den Konten im Azure AD-Mandanten ihres Microsoft 365-Abonnements zu synchronisieren. 

In diesem Artikel wird beschrieben, wie Sie der Microsoft 365-Testumgebung eine Kennworthash Synchronisierung hinzufügen können, die zu dieser Konfiguration führt:
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Das Einrichten dieser Testumgebung umfasst drei Phasen:
- [Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [Phase 2: Erstellen und Registrieren der TestLab-Domäne](#phase-2-create-and-register-the-testlab-domain)
- [Phase 3: Installieren von Azure AD Connect auf APP1](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung

Befolgen Sie die Anweisungen unter [simulierte Enterprise-Basiskonfiguration für Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Die resultierende Konfiguration sieht wie folgt aus:
  
![Die simulierte Unternehmensstandardkonfiguration](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.
- Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem virtuellen Azure-Netzwerk besteht. DC1 ist ein Domänencontroller für die testlab. <*ihren öffentlichen Domänennamen*> AD DS Domäne.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Phase 2: Erstellen und Registrieren der TestLab-Domäne

Fügen Sie in dieser Phase eine öffentliche DNS-Domäne hinzu, und fügen Sie Sie dann Ihrem Abonnement hinzu.

Arbeiten Sie zunächst mit Ihrem öffentlichen DNS-Registrierungsanbieter zusammen, um einen neuen öffentlichen DNS-Domänennamen zu erstellen, der auf dem aktuellen Domänennamen basiert, und fügen Sie ihn dann Ihrem Abonnement hinzu. Es wird empfohlen, den Namen **testlab. <*ihrer öffentlichen Domäne* > **zu verwenden. Wenn Ihr öffentlicher Domänenname beispielsweise " ** <span>contoso</span>. com"** lautet, fügen Sie den öffentlichen Domänennamen hinzu: ** <span>testlab</span>. contoso.com**.
  
Fügen Sie als nächstes das **testlab. <*Ihrer Public Domain* > ** -Domäne zu Ihrem Microsoft 365-Test-oder kostenpflichtigen Abonnement hinzu, indem Sie den Domänen Registrierungsprozessdurch gehen. Dies umfasst das Hinzufügen zusätzlicher DNS-Einträge zum **testlab. <*Ihrer Public Domain* > ** -Domäne. Weitere Informationen finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](../admin/setup/add-domain.md).

Die resultierende Konfiguration sieht wie folgt aus:
  
![Registrierung des Domänennamens „testlab“](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Diese Konfiguration besteht aus: 

- Ein Microsoft 365 E5-Test-oder kostenpflichtiges Abonnement mit der DNS-Domäne testlab. <*ihren öffentlichen Domänennamen*> registriert.
- Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.

Beachten Sie, wie testlab. <*ihren öffentlichen Domänennamen*> jetzt lautet:

- Die Domäne wird von öffentlichen DNS-Datensätzen unterstützt.
- In Ihren Microsoft 365-Abonnements registriert.
- Die Domäne ist die AD DS-Domäne in Ihrem simulierten Intranet.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Phase 3: Installieren von Azure AD Connect auf APP1

Installieren und konfigurieren Sie in dieser Phase das Azure AD Connect-Tool auf App1, und stellen Sie dann sicher, dass es funktioniert.
  
Installieren und konfigurieren Sie zunächst Azure AD Connect auf App1.

1. Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ eine Verbindung zu APP1 her.
    
2. Öffnen Sie über den Desktop auf APP1 eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie die folgenden Befehle aus, um die verstärkte Sicherheit in Internet Explorer zu deaktivieren:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Wählen Sie in der Taskleiste **Internet Explorer** aus, und wechseln Sie zu [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
4. Wählen Sie auf der Seite Microsoft Azure Active Directory Verbindung die Option **herunterladen**aus, und wählen Sie dann **Ausführen**aus.
    
5. Klicken Sie auf der Seite **Willkommen bei Azure AD Connect** auf **Ich stimme**zu, und wählen Sie dann **weiter**aus.
    
6. Wählen Sie auf der Seite **Express-Einstellungen** die Option **Express-Einstellungen verwenden**aus.
    
7. Geben Sie auf der Seite mit **Azure AD verbinden** den Namen Ihres globalen Administratorkontos in **username ein,** geben Sie sein Kennwort in **Kennwort**ein, und klicken Sie dann auf **weiter**.
    
8. Geben Sie auf der Seite mit **AD DS verbinden** in **username** **TESTLAB \\ User1** ein, geben Sie das Kennwort in **Kennwort**ein, und klicken Sie dann auf **weiter**.
    
9. Wählen Sie auf der Seite " **vorbereiten zur Konfiguration** " die Option " **Installieren**" aus.
    
10. Wählen Sie auf der Seite **Konfiguration abgeschlossen** die Option **Beenden**aus.
    
11. Wechseln Sie im Internet Explorer zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. Wählen Sie im linken Navigationsbereich die Option **Benutzer > aktive Benutzer**aus.
    
    Sie sehen das Konto **Benutzer 1**. Dieses Konto gehört zur AD DS-Domäne „TESTLAB“. Dass es angezeigt wird, belegt, dass die Verzeichnissynchronisierung erfolgreich war.
    
13. Wählen Sie das Konto **User1** aus, und wählen Sie dann **Lizenzen und apps**aus.
    
14. Wählen Sie unter **Produktlizenzen**Ihren Standort (falls erforderlich) aus, deaktivieren Sie die **Office 365 E5** -Lizenz, und aktivieren Sie dann die **Microsoft 365 E5** -Lizenz. 

15. Klicken Sie unten auf der Seite auf **Speichern** , und wählen Sie dann **Schließen**aus.
    
Als nächstes testen Sie die Möglichkeit, sich bei Ihrem Abonnement mit dem **User1@testlab anzumelden. <*Ihren Domänennamen* > ** Benutzernamen des user1-Kontos:

1. Melden Sie sich über APP1 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.

2. Wenn Sie zur Eingabe eines Benutzernamens und Kennworts aufgefordert werden, geben Sie **User1@testlab. <*Ihren Domänennamen* > ** und das user1-Kennwort ein. Sie sollten sich erfolgreich als „Benutzer 1“ anmelden können.
 
Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator ist. Daher wird das Symbol **Admin** nicht als Option angezeigt. 

Die resultierende Konfiguration sieht wie folgt aus:

![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Diese Konfiguration besteht aus:  
  
- Microsoft 365 E5 oder Office 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne TESTLAB. <*Ihren Domänennamen*> registriert.
- Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Azure AD Connect wird auf App1 ausgeführt, um die TESTLAB AD DS Domäne regelmäßig mit dem Azure AD Mandanten Ihres Microsoft 365-Abonnements zu synchronisieren.
- Das Konto „Benutzer 1“ in der AD DS-Domäne „TESTLAB“ wurde mit dem Azure AD-Mandanten synchronisiert.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
