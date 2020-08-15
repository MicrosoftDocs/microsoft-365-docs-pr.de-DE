---
title: Microsoft 365-Identitäts Modelle und Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 06/09/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: In diesem Artikel erfahren Sie, wie Sie den Azure AD-Benutzer Identitätsdienst in Microsoft 365 mit reinen cloudbasierten oder hybriden Identitäts Modellen verwalten.
ms.openlocfilehash: d91e14f678e487365805b024e4025e9a39db0c2c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690866"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365-Identitäts Modelle und Azure Active Directory

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365 verwendet Azure Active Directory (Azure AD), eine Cloud-basierte Benutzeridentität und einen Authentifizierungsdienst, der in Ihrem Microsoft 365-Abonnement enthalten ist, um Identitäten und Authentifizierung für Microsoft 365 zu verwalten. Die ordnungsgemäße Konfiguration Ihrer Identitätsinfrastruktur ist für die Verwaltung von Microsoft 365-Benutzer Zugriff und-Berechtigungen für Ihre Organisation unerlässlich.

Bevor Sie beginnen, schauen Sie sich dieses Video an, um eine Übersicht über die Identitätsmodelle und Authentifizierung für Microsoft 365 zu erhalten.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Bei der ersten Planungs Wahl handelt es sich um das Microsoft 365-Identitätsmodell.

## <a name="microsoft-365-identity-models"></a>Microsoft 365-Identitäts Modelle

Um Benutzerkonten zu planen, müssen Sie zunächst die beiden Identitätsmodelle in Microsoft 365 verstehen. Sie können die Identitäten Ihrer Organisation nur in der Cloud verwalten, oder Sie können Ihre lokalen AD DS-Identitäten (Active Directory Domain Services) verwalten und diese zur Authentifizierung verwenden, wenn Benutzer auf Microsoft 365-Clouddienste zugreifen.  

Nachfolgend finden Sie die beiden Identitätstypen sowie deren beste Anwendungsfälle und Vorteile.

| Attribut | Reine Cloudidentität | Hybrididentität |
|:-------|:-----|:-----|
| **Definition** | Das Benutzerkonto ist nur im Azure AD Mandanten für Ihr Microsoft 365-Abonnement vorhanden. | Ein Benutzerkonto ist in AD DS vorhanden, und eine Kopie befindet sich auch im Azure AD-Mandanten für Ihr Microsoft 365-Abonnement. Das Benutzerkonto in Azure AD kann auch eine gehashte Version des bereits gehashten AD DS Benutzerkontokennworts enthalten. |
| **Authentifizierung von Benutzeranmeldeinformationen durch Microsoft 365** | Der Azure AD-Mandant für Ihr Microsoft 365-Abonnement führt die Authentifizierung mit dem Cloudidentitätskonto durch. | Der Azure AD-Mandant für Ihr Microsoft 365-Abonnement behandelt verarbeitet entweder den Authentifizierungsprozess oder leitet den Benutzer an einen anderen Identitätsanbieter weiter. |
| **Ideal für** | Organisationen, die keinen lokalen AD DS besitzen oder benötigen. | Organisationen, die AD DS oder einen anderen Identitätsanbieter verwenden. |
| **Größter Vorteil** | Einfach zu verwenden. Es sind keine zusätzlichen Verzeichnistools oder Server erforderlich. | Benutzer können dieselben Anmeldeinformationen verwenden, wenn sie auf lokale oder cloudbasierte Ressourcen zugreifen. |
||||

## <a name="cloud-only-identity"></a>Reine Cloudidentität

Bei der reinen Cloudidentität werden Benutzerkonten verwendet, die nur in Azure AD vorhanden sind. Cloudidentitäten werden in der Regel von kleinen Organisationen verwendet, die keine lokalen Server haben oder AD DS nicht zum Verwalten lokaler Identitäten verwenden. 

Hier sind die grundlegenden Komponenten der reinen Cloudidentität.
 
![Grundlegende Komponenten der reinen Cloud-Identität](../media/about-microsoft-365-identity/cloud-only-identity.png)

Sowohl lokale als auch Remotebenutzer (Online) verwenden Ihre Azure AD Benutzerkonten und Kennwörter für den Zugriff auf Microsoft 365 Cloud Services. Azure AD authentifiziert Benutzeranmeldeinformationen basierend auf den gespeicherten Benutzerkonten und Kennwörtern.

### <a name="administration"></a>Verwaltung
Da Benutzerkonten nur in Azure AD gespeichert werden, verwalten Sie Cloud-Identitäten mit Tools wie dem [Microsoft 365 Admin Center](https://admin.microsoft.com) und [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md). 

## <a name="hybrid-identity"></a>Hybrididentität

Die Hybrididentität verwendet Konten, die von einem lokalen AD DS stammen und eine Kopie im Azure AD-Mandanten eines Microsoft 365-Abonnements aufweisen. Die meisten Änderungen fließen jedoch nur in eine Richtung. Änderungen, die Sie an AD DS-Benutzerkonten vornehmen, werden mit Ihrer Kopie in Azure AD synchronisiert. Änderungen, die in cloudbasierten Konten in Azure AD vorgenommen wurden, wie z. B. neue Benutzerkonten, werden jedoch nicht mit AD DS synchronisiert.

Azure AD Connect bietet die laufende Kontosynchronisierung. Es wird auf einem lokalen Server ausgeführt, überprüft auf Änderungen in AD DS und leitet diese Änderungen an Azure AD weiter. Azure AD Connect bietet die Möglichkeit zu filtern, welche Konten synchronisiert werden, und ob eine Hashversion der Benutzerkennwörter synchronisiert werden soll; dies wird als „Kennworthashsynchronisierung“ (Password hash synchronization, PHS) bezeichnet.

Wenn Sie die Hybrididentität implementieren, ist Ihr lokales AD DS die autorisierende Quelle für Kontoinformationen. Dies bedeutet, dass Sie Verwaltungsaufgaben hauptsächlich lokal durchführen, die dann mit Azure AD synchronisiert werden. 

Nachfolgend finden Sie die Komponenten der Hybrididentität.

![Komponenten der Hybrid Identität](../media/about-microsoft-365-identity/hybrid-identity.png)

Der Azure AD-Mandant hat eine Kopie der AD DS-Konten. In dieser Konfiguration authentifizieren sich sowohl lokale als auch Remotebenutzer beim Zugriff auf Microsoft 365-Clouddienste bei Azure AD.

>[!Note]
>Sie müssen immer Azure AD Connect verwenden, um Benutzerkonten für die Hybrididentität zu synchronisieren. Sie benötigen die synchronisierten Benutzerkonten in Azure AD, um die Lizenzzuweisung und Gruppenverwaltung durchzuführen, um Berechtigungen zu konfigurieren und um andere Verwaltungsaufgaben auszuführen, die Benutzerkonten umfassen.
>

### <a name="administration"></a>Verwaltung

Da die ursprünglichen und autorisierenden Benutzerkonten im lokalen AD DS gespeichert sind, verwalten Sie Ihre Identitäten mit den gleichen Tools wie AD DS, z. B. mit dem Tool „Active Directory-Benutzer und -Computer“. 

Sie verwenden nicht das Microsoft 365 Admin Center oder PowerShell für Microsoft 365, um synchronisierte Benutzerkonten in Azure AD zu verwalten.

## <a name="next-step"></a>Nächster Schritt

Wenn Sie das Cloud-only-Identitätsmodell benötigen, lesen Sie die Informationen unter [Cloud-only Identity](cloud-only-identities.md).

Wenn Sie das hybride Identitätsmodell benötigen, finden Sie unter [Hybrid Identity](plan-for-directory-synchronization.md).


## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
