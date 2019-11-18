---
title: Einrichten von Benutzern und Fällen in Office 365 Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Informationen zum Konfigurieren von Benutzerrollen, Erstellen von Fällen und Zuweisen von Benutzern zu Fällen in Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: e6fa3581fe15c089292e7585e7d053b817ae167b
ms.sourcegitcommit: 547bfc5f1fec7545cbe71b1919454425556c9227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2019
ms.locfileid: "38686143"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a>Einrichten von Benutzern und Fällen in Office 365 Advanced eDiscovery

In diesem Thema wird beschrieben, wie Sie Benutzer und Fälle für Office 365 Advanced eDiscovery einrichten.
  
> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="prerequisites"></a>Voraussetzungen

Vor dem Einrichten von Fällen und Benutzern in Advanced eDiscovery ist Folgendes erforderlich:
  
- Um die Daten eines Benutzers mithilfe von Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwalter der Daten) eine Office 365 E5-Lizenz zugewiesen werden. Alternativ können Benutzern mit einer Office 365 E1-oder E3-Lizenz eine erweiterte eDiscovery-eigenständige Lizenz zugewiesen werden. Administratoren und Compliance Officer, die Fällen zugeordnet sind, und Verwenden von Advanced eDiscovery zum Analysieren von Daten benötigen keine E5-Lizenz. 
    
- Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Office 365 Security &amp; Compliance Center sein, um einen eDiscovery-Fall zu erstellen und ihm Mitglieder hinzuzufügen. Um sich selbst der eDiscovery-Manager-Rollengruppe im &amp; Security Compliance Center hinzufügen zu können, müssen Sie ein globaler Administrator in Ihrer Office 365 Organisation sein. Wenn Sie kein globaler Administrator sind, müssen Sie einen globalen Administrator bitten, Sie zur eDiscovery-Manager-Rollengruppe hinzuzufügen. Weitere Informationen finden Sie unter:
    
  - [Berechtigungen im Microsoft 365 Security &amp; Compliance Center](~/security/office-365-security/protect-against-threats.md)
    
  - [Zuweisen von eDiscovery-Berechtigungen im Microsoft 365 &amp; Security Compliance Center](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>Schritt 1: Zuweisen von eDiscovery-Berechtigungen für Benutzer

Der erste Schritt besteht darin, Benutzern die Anforderungs Berechtigungen im Security &amp; Compliance Center zuzuweisen, damit Sie als Mitglied eines eDiscovery-Falls hinzugefügt werden können. Nachdem ein Benutzer als Mitglied eines Falls im Security &amp; Compliance Center hinzugefügt wurde, kann er auf den Fall in Advanced eDiscovery zugreifen.
  
Wenn Sie einem Benutzer die erforderlichen Berechtigungen zuweisen möchten, damit diese als Mitglied eines eDiscovery-Falls hinzugefügt werden können, lesen Sie Schritt 1 in [eDiscovery- &amp; Fällen im Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>Schritt 2: Erstellen eines eDiscovery-Falls und Hinzufügen von Mitgliedern

Der nächste Schritt ist das Erstellen eines neuen eDiscovery-Falls im Security &amp; Compliance Center und das Hinzufügen von Mitgliedern. Mitglieder der Anfrage können dann auf den Fall in Advanced eDiscovery zugreifen.
  
1. Informationen zum Erstellen eines neuen eDiscovery-Falls finden Sie unter Schritt 2 in [eDiscovery-Fällen im &amp; Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).
    
2. Informationen zum Hinzufügen von Mitgliedern zu einem eDiscovery-Fall finden Sie unter Schritt 3 in [eDiscovery- &amp; Fällen im Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>Schritt 3: Wechseln Sie zu einem Fall in Advanced eDiscovery

Nachdem Sie einen eDiscovery-Fall erstellt und Mitglieder hinzugefügt haben, können Sie (oder ein beliebiges Mitglied des Falles) auf den entsprechenden Fall in Advanced eDiscovery zugreifen. Informationen zum Zugriff auf einen Fall in Advanced eDiscovery finden Sie unter Schritt 8 in [eDiscovery-Fällen im &amp; Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).
  
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Vorbereiten der Daten](prepare-data-for-advanced-ediscovery.md)
 
