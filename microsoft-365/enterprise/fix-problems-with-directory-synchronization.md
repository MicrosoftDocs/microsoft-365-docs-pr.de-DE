---
title: Beheben von Problemen bei der Verzeichnissynchronisierung für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MBS150
ms.assetid: 79c43023-5a47-45ae-8068-d8a26eee6bc2
description: Beschreibt häufige Ursachen von Problemen mit der Verzeichnissynchronisierung in Office 365 und bietet ein paar Methoden, wie man diese Probleme beheben kann.
ms.openlocfilehash: 80b4a88e91230a8736f209ecd65c58b2882c25d6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690821"
---
# <a name="fixing-problems-with-directory-synchronization-for-microsoft-365"></a>Beheben von Problemen bei der Verzeichnissynchronisierung für Microsoft 365

Mithilfe der Verzeichnissynchronisierung können Sie weiterhin Benutzer und Gruppen lokal verwalten und Änderungen, Ergänzungen und Löschungen in der Cloud synchronisieren. Das Setup ist jedoch etwas kompliziert, und es kann mitunter schwierig sein, die Problemursachen zu finden. Wir verfügen über Ressourcen, mit denen Sie mögliche Probleme aufspüren und beheben können.
  
## <a name="how-do-i-know-if-something-is-wrong"></a>Wie kann ich feststellen, ob ein Fehler vorliegt?

Als ersten Hinweis auf eine fehlerhafte Funktionsweise zeigt die Kachel "DirSync-Status" im Microsoft 365 Admin Center an, dass ein Problem vorliegt.
  
Außerdem sendet Microsoft 365 Ihnen eine E-Mail (an die alternative und an Ihre Administrator-E-Mail-Adresse), aus der hervorgeht, dass bei Ihrem Mandanten Verzeichnissynchronisierungsfehler aufgetreten sind. Ausführlichere Informationen hierzu finden Sie unter [Ermitteln von Fehlern bei der Verzeichnissynchronisierung in Microsoft 365](identify-directory-synchronization-errors.md).
  
## <a name="how-do-i-get-azure-active-directory-connect-tool"></a>Wie erhalte ich das Azure Active Directory Connect-Tool?

Navigieren Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com) zu **Benutzer** \> **Aktive Benutzer**. Klicken Sie auf das Menü **Mehr** (drei Punkte), und wählen Sie **Verzeichnissynchronisierung** aus. 
  
Folgen Sie den [Anweisungen im Assistenten](set-up-directory-synchronization.md), um Azure AD Connect herunterzuladen. 
  
Wenn Sie weiterhin die Azure Active Directory (Azure AD)-Synchronisierung (DirSync) verwenden, finden Sie unter [Beheben von Fehlern bei der Installation und beim Konfigurations-Assistenten für das Azure Active Directory-Synchronisierungstool in Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=396717) Informationen zu den Systemanforderungen für die Installation von DirSync, den dazu erforderlichen Berechtigungen sowie zur Problembehandlung bei häufig auftretenden Fehlern. 
  
Informationen zum Aktualisieren von den Azure Active Directory-Synchronisierungsdiensten auf Azure AD Connect finden Sie unter [Aktualisierungsanweisungen](https://go.microsoft.com/fwlink/p/?LinkId=733240).
  
## <a name="resolving-common-causes-of-problems-with-directory-synchronization-in-microsoft-365"></a>Beheben häufiger Ursachen von Problemen mit der Verzeichnissynchronisierung in Microsoft 365

### <a name="synchronized-objects-arent-appearing-or-updating-online-or-im-getting-synchronization-error-reports-from-the-service"></a>Synchronisierte Objekte werden nicht angezeigt oder nicht online aktualisiert, oder ich erhalte Synchronisierungsfehlerberichte vom Dienst.

- [Identitätssynchronisierung und Resilienz bei doppelten Attributen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

### <a name="i-have-an-alert-in-the-admin-center-or-am-receiving-automated-emails-that-there-hasnt-been-a-recent-synchronization-event"></a>Im Admin Center wird eine Benachrichtigung angezeigt, oder ich erhalte automatisierte E-Mails mit dem Hinweis, dass kürzlich kein Synchronisierungsereignis stattgefunden hat
- [Behandeln von Verbindungsproblemen mit Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)
- [Azure AD Connect-Konten und -Berechtigungen](https://go.microsoft.com/fwlink/p/?LinkId=820598)
- [Azure AD Connect-Synchronisierung: Verwalten des Azure AD-Dienstkontos](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-azureadaccount)
- [Die Verzeichnissynchronisierung mit Azure Active Directory wird beendet, oder Sie erhalten eine Warnung, die besagt, dass die Synchronisierung sich seit mehr als einem Tag nicht mehr registriert hat](https://support.microsoft.com/help/2882421/directory-synchronization-to-azure-active-directory-stops-or-you-re-warned-that-sync-hasn-t-registered-in-more-than-a-day)

### <a name="password-hashes-arent-synchronizing-or-im-seeing-an-alert-in-the-admin-center-that-there-hasnt-been-a-recent-password-hash-synchronization"></a>Kennworthashes werden nicht synchronisiert, oder im Admin Center wird eine Warnung angezeigt, die besagt, dass kürzlich keine Kennworthashsynchronisierung stattgefunden hat
- [Implementieren der Synchronisierung von Kennworthashes mit der Azure AD Connect-Synchronisierung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)

### <a name="im-seeing-an-alert-that-object-quota-exceeded"></a>Ich erhalte eine Warnung, dass das Objektkontingent überschritten ist
- Als Hilfe zum Schutz des Dienstes wurde ein Objektkontingent integriert. Falls Sie zu viele Objekte in Ihrem Verzeichnis haben, die mit Microsoft 365 synchronisiert werden müssen, [wenden Sie sich an den Support für Business-Produkte](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b), um Ihr Kontingent zu erhöhen.

### <a name="i-need-to-know-which-attributes-are-synchronized"></a>Ich möchte wissen, welche Attribute synchronisiert sind
- [Hier](https://go.microsoft.com/fwlink/p/?LinkId=396719) finden Sie eine Liste aller Attribute, die zwischen lokalen Verzeichnissen und der Cloud synchronisiert werden.

### <a name="i-cant-manage-or-remove-objects-that-were-synchronized-to-the-cloud"></a>Ich kann Objekte, die mit der Cloud synchronisiert wurden, nicht verwalten oder entfernen
- Sind Sie bereit, Objekte allein in der Cloud zu verwalten? Oder gibt es ein Objekt, das lokal gelöscht wurde und jetzt in der Cloud festhängt? Anleitung zum Beheben dieser Probleme finden Sie in diesem Artikel zur [Problembehandlung bei der Synchronisierung](https://go.microsoft.com/fwlink/p/?linkid=842044) und [Unterstützung](https://go.microsoft.com/fwlink/p/?LinkId=396720).

### <a name="i-got-an-error-message-that-my-company-has-exceeded-the-number-of-objects-that-can-be-synchronized"></a>Ich habe die Fehlermeldung bekommen, dass mein Unternehmen die Anzahl der synchronisierbaren Objekte überschritten hat
- Weitere Informationen zu diesem Problem finden Sie [hier](https://go.microsoft.com/fwlink/p/?LinkId=396721).
   
## <a name="other-resources"></a>Weitere Ressourcen

- [Skript zum Beheben von doppelten Benutzerprinzipalnamen](https://go.microsoft.com/fwlink/p/?LinkId=396725)
    
- [Vorbereiten einer nicht routingfähigen Domäne (z. B. ".lokale Domäne") für die Verzeichnissynchronisierung](prepare-a-non-routable-domain-for-directory-synchronization.md)
    
- [Skript zum Ermitteln der Anzahl aller synchronisierten Objekte](https://go.microsoft.com/fwlink/p/?LinkId=396726)
    
- [Behandeln von Problemen mit AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=396727)
    
- [Verwenden von PowerShell zum Korrigieren leerer "DisplayName"-Attribute für E-Mail-aktivierte Gruppen](https://go.microsoft.com/fwlink/p/?LinkId=396728)
    
- [Verwenden von PowerShell zum Korrigieren von doppelten UPNs](https://go.microsoft.com/fwlink/p/?LinkId=396730)
    
- [Verwenden von PowerShell zum Korrigieren von doppelten E-Mail-Adressen](https://go.microsoft.com/fwlink/p/?LinkId=396731)
    
