---
title: Verwalten von Microsoft 365-Gruppen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Erfahren Sie mehr über das Verwalten Microsoft 365 Gruppen.
ms.openlocfilehash: 529bdb874661329497b103a1207b90625ad33a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911007"
---
# <a name="manage-microsoft-365-groups"></a>Verwalten von Microsoft 365-Gruppen

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können die Microsoft 365 je nach Konfiguration auf verschiedene Weise verwalten. Sie können Benutzerkonten im [Microsoft 365 Admin Center](../admin/add-users/index.yml), PowerShell, in Active Directory Domain Services (AD DS) oder im Azure Active Directory [(Azure AD) Admin Center verwalten.](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>Planen, wo und wie Sie Ihre Gruppen verwalten

Wo und wie Sie Ihre Benutzerkonten verwalten können, hängt vom Identitätsmodell ab, das Sie für Ihre Microsoft 365. Die beiden Gesamtmodelle sind nur cloudbasierte und hybride Modelle.
  
### <a name="cloud-only"></a>Rein cloudbasiert

Sie erstellen und verwalten Gruppen mit:

- [Das Microsoft 365 Admin Center](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD Admin Center](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>Hybrid

AD DS-Gruppen werden mit Microsoft 365 von AD DS synchronisiert, daher müssen Sie lokale AD DS-Tools verwenden, um diese Gruppen zu verwalten.

Sie können auch Azure AD-Gruppen erstellen und verwalten, die von AD DS-Gruppen getrennt sind, aber Benutzer und Gruppen aus AD DS enthalten können. In diesem Fall können Sie:

- [Das Microsoft 365 Admin Center](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD Admin Center](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer

Azure AD ermöglicht Gruppen, die von Gruppenbesitzern anstelle von IT-Administratoren verwaltet werden können. Diese Funktion, bekannt als *Self-Service-Gruppenverwaltung*, ermöglicht es Gruppenbesitzern, denen keine Administratorrolle zugewiesen ist, Sicherheitsgruppen zu erstellen und zu verwalten. 

Benutzer können die Mitgliedschaft in einer Sicherheitsgruppe anfordern, und die Anforderung wird an den Gruppenbesitzer gesendet, statt an den IT-Administrator. So kann die tägliche Kontrolle über Gruppenmitgliedschaften an die Team-, Projekt- oder Unternehmensbesitzer delegiert werden, die die geschäftliche Verwendung für die Gruppe verstehen und die Mitgliedschaften verwalten können.

>[!Note]
>Self-Service-Gruppenverwaltung ist nur für Azure AD-Sicherheitsgruppen und Microsoft 365-Gruppen aktiviert. Sie ist nicht für E-Mail-aktivierte Gruppen, Verteilerlisten oder gruppen, die von AD DS synchronisiert wurden, verfügbar.
>

Weitere Informationen finden Sie in den [Anweisungen zum Konfigurieren einer Azure AD-Gruppe für Self-Service-Verwaltung](/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

## <a name="set-up-dynamic-group-membership"></a>Einrichten der dynamischen Gruppenmitgliedschaft

Azure AD unterstützt das Konfigurieren einer Reihe von Regeln, die Benutzerkonten automatisch als Mitglieder einer Azure AD-Gruppe hinzufügen oder entfernen. Dies ist als *dynamische Gruppenmitgliedschaft* bekannt. Die Regeln basieren auf Benutzerkontoattributen, wie Abteilung oder Land.

Die Regeln werden wie folgt angewendet:

- Wenn ein neues Benutzerkonto allen Regeln für die Gruppe entspricht, wird es ein Mitglied.
- Wenn ein Benutzerkonto kein Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es allen Regeln für die Gruppe entspricht, wird es ein Mitglied dieser Gruppe.
- Wenn ein Benutzerkonto nicht allen Regeln für die Gruppe entspricht, wird es nicht zur Gruppe hinzugefügt.
- Wenn ein Benutzerkonto Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es nicht mehr allen Regeln für die Gruppe entspricht, wird es als Mitglied der Gruppe entfernt.

Um die dynamische Mitgliedschaft zu verwenden, müssen Sie zuerst die Sätze von Gruppen mit einem gemeinsamen Satz von Benutzerkonto-Attributen bestimmen. Beispielsweise sollten alle Mitglieder der Vertriebsabteilung Teil der Azure AD-Gruppe „Vertrieb“ sein, basierend auf dem Benutzerkonto-Attribut „Abteilung“ = „Vertrieb“.

Lesen Sie die [Anweisungen, um die Regeln für eine dynamische Azure AD-Gruppe zu erstellen und zu konfigurieren](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

## <a name="set-up-automatic-licensing"></a>Einrichten der automatischen Lizenzierung

Sie können Sicherheitsgruppen in Azure AD konfigurieren, um allen Mitgliedern der Gruppe automatisch Lizenzen aus einer Reihe von Abonnements zuzuordnen. Dies wird als *gruppenbasierte Lizenzierung* bezeichnet. Wenn ein Benutzerkonto der Gruppe hinzugefügt oder aus ihr entfernt wird, werden die Lizenzen für die Gruppenabonnements dem Benutzerkonto automatisch zugewiesen, bzw. die Zuweisung wird entfernt.

Für Microsoft 365 Enterprise konfigurieren Sie Azure AD-Sicherheitsgruppen, um die passenden Microsoft 365 Enterprise-Lizenzen zuzuweisen.

Stellen Sie sicher, dass Sie genug Lizenzen für alle Gruppenmitglieder haben. Wenn keine Lizenzen mehr vorhanden sind, werden neuen Benutzern keine Lizenzen zugewiesen, bis Lizenzen verfügbar werden.

>[!Note]
>Sie sollten  nicht die gruppenbasierte Lizenzierung für Gruppen konfigurieren, die Azure Business to Business (B2B)-Konten enthalten.
>

Weitere Informationen finden Sie unter [Group-based licensing basics in Azure AD](/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Weitere Informationen [finden Sie in den Anweisungen zum Konfigurieren der gruppenbasierten Lizenzierung für eine Azure-Sicherheitsgruppe.](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)