---
title: Simulierte Unternehmensstandardkonfiguration für Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Verwenden Sie diese Testumgebungsanleitung, um eine simulierte Unternehmenstestumgebung für Microsoft 365 enterprise zu erstellen.
ms.openlocfilehash: 8df63e1a580b57aa263c11dccaed947f46f2cbb9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926044"
---
# <a name="the-simulated-enterprise-base-configuration"></a>Die simulierte Unternehmensstandardkonfiguration

*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 als auch für Office 365 Enterprise verwendet werden.*

In diesem Artikel wird beschrieben, wie Sie eine vereinfachte Umgebung für Microsoft 365 Unternehmen erstellen, die:

- Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.
- Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus drei virtuellen Computern in einem virtuellen Azure-Netzwerk (DC1, APP1 und CLIENT1) besteht.
 
![Die simulierte Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

Das Erstellen einer vereinfachten Testumgebung umfasst zwei Phasen:
- [Phase 1: Erstellen eines simulierten Intranets](#phase-1-create-a-simulated-intranet)
- [Phase 2: Erstellen Ihres Abonnements für Microsoft 365 E5](#phase-2-create-your-microsoft-365-e5-subscription)

Sie können die resultierende Umgebung verwenden, um die Features und Funktionen von [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise) für Unternehmen mit zusätzlichen [Test lab Guides](m365-enterprise-test-lab-guides.md) oder allein zu testen.

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-create-a-simulated-intranet"></a>Phase 1: Erstellen eines simulierten Intranets

Erstellen Sie in dieser Phase ein simuliertes Intranet in Azure-Infrastrukturdiensten, das einen Active Directory Domain Services (AD DS)-Domänencontroller, einen Anwendungsserver und einen Clientcomputer enthält.

Sie verwenden diese Computer in zusätzlichen [Microsoft 365 test lab Guides](m365-enterprise-test-lab-guides.md) für Unternehmen, um hybride Identität und andere Funktionen zu konfigurieren und zu veranschaulichen.

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>Methode 1: Erstellen eines simulierten Intranets mit einer Azure Ressourcenmanager-Vorlage

In dieser Methode verwenden Sie eine Azure Resource Manager-Vorlage, um das simulierte Intranet zu erstellen. Azure Resource Manager-Vorlagen enthalten alle Anweisungen zum Erstellen der Azure-Netzwerkinfrastruktur, der virtuellen Computer und deren Konfiguration.

Lesen Sie vor der Bereitstellung der Vorlage die [ReadME-Seite der](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) Vorlage durch, und stellen Sie die folgenden Informationen bereit:

- Der öffentliche DNS-Domänenname Ihrer Testumgebung (testlab. \<*your public domain*> ). Sie geben diesen Namen im Feld **Domänenname** auf der Seite Benutzerdefinierte **Bereitstellung** ein.
- Ein DNS-Präfix für die URLs der öffentlichen IP-Adressen Ihrer virtueller Computer. Sie müssen diese Bezeichnung in das Feld **DNS-Präfix** der Seite **Benutzerdefinierte Bereitstellung** eingeben.

Nachdem Sie die Anweisungen gelesen haben, wählen Sie **Bereitstellen in Azure** auf der Vorlage [README-Seite](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) aus, um zu beginnen.

>[!Note]
>Das simulierte Intranet, das von der Azure Resource Manager-Vorlage erstellt wurde, erfordert ein kostenpflichtiges Azure-Abonnement.

Nachdem die Vorlage abgeschlossen ist, sieht Ihre Konfiguration wie die andere aus:

![Das simulierte Intranet in den Azure-Infrastrukturdiensten](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>Methode 2: Erstellen Ihres simulierten Intranets mit Azure PowerShell

Bei dieser Methode verwenden Sie Windows PowerShell und das Azure PowerShell-Modul zum Erstellen der Netzwerkinfrastruktur, der virtuellen Computer und ihrer Konfiguration.

Verwenden Sie diese Methode, wenn Sie Erfahrungen mit dem Erstellen von Elementen der Azure-Infrastruktur für jeden einzelnen Schritt mit PowerShell sammeln möchten. Sie können dann die PowerShell-Befehlsblöcke für eine eigene Bereitstellung von anderen virtuellen Computern in Azure anpassen.

#### <a name="step-1-create-dc1"></a>Phase 1: Erstellen von DC1

In diesem Schritt erstellen Sie ein virtuelles Azure-Netzwerk und fügen DC1 hinzu, einen virtuellen Computer, der ein Domänencontroller für eine AD DS-Domäne ist.

Starten Sie zunächst eine Windows PowerShell-Eingabeaufforderung auf dem lokalen Computer.
  
> [!NOTE]
> In den folgenden Befehlssätzen wird die aktuelle Version von Azure PowerShell verwendet. Informationen dazu finden Sie unter [Get started with Azure PowerShell cmdlets](/powershell/azureps-cmdlets-docs/). 
  
Melden Sie sich mit dem folgenden Befehl bei Ihrem Azure-Konto an.
  
```powershell
Connect-AzAccount
```

Rufen Sie den Namen Ihres Abonnements mithilfe des folgenden Befehls ab.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Tragen Sie Ihr Azure-Abonnement ein. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der eckigen Klammern ("<" und ">"), durch den richtigen Namen.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Im nächsten Schritt wird eine neue Ressourcengruppe für Ihr simuliertes Unternehmenstestlabor erstellt. Verwenden Sie zum Ermitteln eines eindeutigen Ressourcengruppennamens diesen Befehl, mit dem die vorhandenen Ressourcengruppen aufgeführt werden.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Erstellen Sie die neue Ressourcengruppe mit diesen Befehlen. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der eckigen Klammern, durch die richtigen Namen.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Erstellen Sie als Nächstes das virtuelle TestLab-Netzwerk, das das Unternehmensnetzwerksubnetz der simulierten Unternehmensumgebung hosten soll, und schützen Sie es mit einer Netzwerksicherheitsgruppe. Geben Sie den Namen Ihrer Ressourcengruppe ein, und führen Sie diese Befehle an der PowerShell-Eingabeaufforderung auf Dem lokalen Computer aus.
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Als Nächstes erstellen Sie den virtuellen Computer DC1 und konfigurieren ihn als Domänencontroller für **testlab.**\<your public domain> AD DS-Domäne und ein DNS-Server für die virtuellen Computer des virtuellen Netzwerks TestLab. Wenn der Name der öffentlichen Domäne **<span>contoso</span>.com** ist, ist die virtuelle Maschine DC1 ein Domänencontroller für die Domäne **<span>testlab</span>.contoso.com**.
  
Geben Sie zum Erstellen eines virtuellen Azure-Computers für DC1 den Namen Ihrer Ressourcengruppe ein, und führen Sie über die PowerShell-Eingabeaufforderung auf Ihrem lokalen Computer die nachfolgenden Befehle aus.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Sie werden nach einem Benutzernamen und Kennwort für das lokale Administratorkonto auf DC1 gefragt. Verwenden Sie ein sicheres Kennwort, und notieren Sie den Namen und das Kennwort an einem sicheren Ort.
  
Stellen Sie als Nächstes eine Verbindung mit dem virtuellen Computer DC1 herzustellen:
  
1. Wählen Sie [im Azure-Portal](https://portal.azure.com) **Ressourcengruppen** > <Namen Ihrer neuen **_Ressourcengruppe_*_> > _* DC1**  >  **Verbinden** aus.
    
2. Wählen Sie im bereich Öffnen die Option **RDP-Datei herunterladen aus.** Öffnen Sie die heruntergeladene DATEI DC1.rdp, und wählen Sie **dann Verbinden**.
    
3. Geben Sie den Namen des lokalen DC1-Administratorkontos an:
    
   - Für Windows 7:
    
     Wählen Sie **Windows-Sicherheit** dialogfeld Verwenden **eines anderen Kontos aus.** Geben **Sie unter Benutzername** den Namen des lokalen **\\ Administratorkontos DC1** < >.
    
   - Für Windows 8 oder Windows 10:
    
     Wählen Sie **Windows-Sicherheit** im Dialogfeld Weitere **Auswahlmöglichkeiten** aus, und wählen Sie **dann Verwenden eines anderen Kontos aus.** Geben **Sie unter Benutzername** den Namen des lokalen **\\ Administratorkontos DC1** < >.
    
4. Geben **Sie unter Kennwort** das Kennwort des lokalen Administratorkontos ein, und wählen Sie dann OK **aus.**
    
5. Wenn Sie dazu aufgefordert werden, wählen Sie **Ja aus.**
    
Im nächsten Schritt führen Sie diesen Befehl über eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten auf DC1 aus, um ein zusätzliches Datenlaufwerk als neues Volume mit dem Laufwerkbuchstaben „F:" hinzuzufügen.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Konfigurieren Sie als Nächstes DC1 als Domänencontroller und DNS-Server für **testlab.**\<*your public domain*> Domain vorgenommen. Geben Sie Ihren öffentlichen Domänennamen an, entfernen Sie die eckigen Klammern, und führen Sie diese Befehle dann auf Administratorebene Windows PowerShell dc1 aus.
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
Sie müssen ein Administratorkennwort für den abgesicherten Modus angeben. Bewahren Sie das Kennwort an einem sicheren Ort auf.
  
Beachten Sie, dass der Abschluss dieser Befehle ein paar Minuten in Anspruch nehmen kann.
  
Stellen Sie nach dem Neustart von DC1 wieder eine Verbindung zum virtuellen DC1-Computer her.
  
1. Wählen Sie [im Azure-Portal](https://portal.azure.com) **Ressourcengruppen** > <*Ressourcengruppennamen*> > **DC1**  >  **Verbinden** aus.
    
2. Führen Sie die heruntergeladene DATEI DC1.rdp aus, und wählen Sie **dann Verbinden**.
    
3. Wählen **Windows-Sicherheit** sie ein **anderes Konto verwenden aus.** Geben **Sie unter Benutzername** den Namen des lokalen **\\ Administratorkontos TESTLAB** < >.
    
4. Geben Sie **im Feld Kennwort** das Kennwort des lokalen Administratorkontos ein, und wählen Sie dann OK **aus.**
    
5. Wenn Sie dazu aufgefordert werden, wählen Sie **Ja aus.**
    
Erstellen Sie als Nächstes ein Benutzerkonto in Active Directory, das bei der Anmeldung bei TESTLAB-Domänenmitgliedscomputern verwendet wird. Führen Sie diesen Befehl an einer Eingabeaufforderung Windows PowerShell Administratorebene aus.
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

Beachten Sie, dass Sie mit diesem Befehl aufgefordert werden, das Benutzerkontokennwort "User1" einzugeben. Dieses Konto wird für Remotedesktopverbindungen für alle TESTLAB-Domänenmitgliedscomputer verwendet, wählen Sie daher ein starkes Kennwort aus. Zeichnen Sie das Kennwort des Benutzerkontos auf, und speichern Sie es an einem gesicherten Speicherort.
  
Konfigurieren Sie als Nächstes das neue Konto „Benutzer1“ als Domänen-, Unternehmens- und Schemaadministrator aus. Führen Sie diesen Befehl an der Windows PowerShell-Eingabeaufforderung auf Administratorebene aus.
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

Schließen Sie die Remotedesktopsitzung mit DC1, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ wieder eine Verbindung her.
  
Führen Sie als Nächstes den folgenden Befehl an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus, um Datenverkehr für das Tool Ping zuzulassen.
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

Ihre aktuelle Konfiguration sieht wie dies aus:
  
![Schritt 1 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a>Schritt 2: Konfigurieren von APP1

In diesem Schritt erstellen und konfigurieren Sie APP1, ein Anwendungsserver, der zunächst Web- und Dateifreigabedienste bereitstellt.

Geben Sie zum Erstellen eines virtuellen Azure-Computers für APP1 den Namen Ihrer Ressourcengruppe ein, und führen Sie über die Eingabeaufforderung auf Ihrem lokalen Computer die nachfolgenden Befehle aus.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Im nächsten Schritt stellen Sie eine Verbindung mit dem virtuellen Computer APP1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von APP1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung.
  
Wenn Sie die Namensauflösung und Netzwerkkommunikation zwischen APP1 und DC1 überprüfen möchten, führen Sie **ping dc1.testlab.**\<*your public domain name*> aus und überprüfen Sie, ob vier Antworten vorhanden sind.
  
Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung den virtuellen Computer APP1 mit der Domäne TESTLAB.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Beachten Sie, dass Sie nach dem Ausführen des Befehls **Add-Computer** die Anmeldeinformationen des TESTLAB \\ User1-Domänenkontos angeben müssen.
  
Stellen Sie nach dem Neustart von APP1 eine Verbindung über das Konto „TESLAB\\Benutzer1“ damit her, und öffnen Sie dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.
  
Im nächsten Schritt richten Sie APP1 mit dem folgenden Befehl in der Windows PowerShell-Eingabeaufforderung auf Administratorebene auf APP1 als Webserver ein.
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

Erstellen Sie als Nächstes einen freigegebenen Ordner und eine Textdatei innerhalb des Ordners auf APP1 mit diesen PowerShell-Befehlen.
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

Ihre aktuelle Konfiguration sieht wie dies aus:
  
![Schritt 2 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>Schritt 3: Konfigurieren von CLIENT1

In diesem Schritt wird CLIENT1 erstellt und konfiguriert, der als typischer Laptop, als Tablet oder als Desktopcomputer im Intranet fungiert.

> [!NOTE]  
> Der folgende Befehlssatz erstellt CLIENT1 unter Windows Server 2016 Datacenter. Er gilt für alle Arten von Azure-Abonnements. Wenn Sie über ein Visual Studio-basiertes Azure-Abonnement verfügen, können Sie CLIENT1 unter Windows 10 mit dem [Azure-Portal](https://portal.azure.com) erstellen.
  
Geben Sie zum Erstellen eines virtuellen Azure-Computers für CLIENT1 den Namen Ihrer Ressourcengruppe ein, und führen Sie diese Befehle an der Eingabeaufforderung auf Dem lokalen Computer aus.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Im nächsten Schritt stellen Sie eine Verbindung mit dem virtuellen Computer CLIENT1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von CLIENT1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.
  
Wenn Sie die Namensauflösung und Netzwerkkommunikation zwischen CLIENT1 und DC1 überprüfen möchten, führen Sie **ping dc1.testlab.**\<*your public domain name*> an einer Windows PowerShell Kommandozeile aus und stellen Sie sicher, dass vier Antworten vorhanden sind.
  
Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung den virtuellen Computer CLIENT1 mit der Domäne TESTLAB.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Beachten Sie, dass Sie nach der Ausführung des Befehls **Add-Computer** die Anmeldeinformationen für das Domänenkonto „TESTLAB\\Benutzer1“ eingeben müssen.
  
Stellen Sie nach dem Neustart von CLIENT1 eine Verbindung über den Kontonamen und das Kennwort von „TESTLAB\\Benutzer1“ damit her, und öffnen Sie dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.
  
Überprüfen Sie im nächsten Schritt, ob Sie von CLIENT1 aus auf Web- und Dateifreigaberessourcen auf APP1 zugreifen können.
  
1. Wählen Sie im Server-Manager im Strukturbereich lokale **Server aus.**
    
2. Wählen **Sie unter Eigenschaften für CLIENT1** neben IE Enhanced Security Configuration die Option **Ein** **aus.**
    
3. Wählen **Sie in Internet Explorer Enhanced Security Configuration** die Option **Aus** für **Administratoren** und **Benutzer** aus, und wählen Sie dann **OK aus.**
    
4. Wählen Sie auf dem Startbildschirm **Internet Explorer aus,** und wählen Sie dann **OK aus.**
    
5. Geben Sie in der Adressleiste **http <span>://</span>app1.testab.** \<*your public domain name*> **/** ein, und drücken Sie dann die **EINGABETASTE**. Nun sollte die standardmäßige Internetinformationsdienste-Webseite für APP1 angezeigt werden.
    
6. Wählen Sie auf der Desktop-Taskleiste das Symbol Datei-Explorer aus.
    
7. Geben Sie in der Adressleiste **\\ \\ app1 \\ Files ein,** und drücken Sie dann die **EINGABETASTE.** Es sollte ein Ordnerfenster mit dem Inhalt des freigegebenen Ordners Dateien angezeigt werden.
    
8. Doppelklicken Sie im Fenster des freigegebenen Ordners **Files** auf die Datei **Example.txt**. Nun sollte der Inhalt der Datei „Example.txt“ angezeigt werden.
    
9. Schließen Sie das Fenster **example.txt - Editor** und das Fenster des freigegebenen Ordners **Files**.
    
Ihre aktuelle Konfiguration sieht wie dies aus:
  
![Schritt 3 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a>Phase 2: Erstellen Ihres Abonnements für Microsoft 365 E5

In dieser Phase erstellen Sie ein neues Abonnement für Microsoft 365 E5, das einen neuen Azure AD-Mandanten verwendet, der von Ihrem Produktionsabonnement getrennt ist. Dies können Sie auf zwei Arten tun:

- Verwenden Sie ein Testabonnement von Microsoft 365 E5.

  Das Testabonnement von Microsoft 365 E5 gilt für 30 Tage, die problemlos auf 60 Tage verlängert werden können. Wenn das Testabonnement abläuft, müssen Sie entweder zu einem kostenpflichtigen Abonnement wechseln oder eine neue Testversion erstellen. Durch Erstellen neuer Testabonnements müssen Sie Ihre Konfiguration verlassen, was im Hintergrund zu komplexen Szenarien führen kann.  

- Verwenden Sie ein separates Produktionsabonnement von Microsoft 365 E5 mit einer kleinen Anzahl von Lizenzen.

  Dies ist eine zusätzliche Kosten, stellt jedoch sicher, dass Sie über eine Arbeitstestumgebung verfügen, die nicht abläuft. In diesem können Sie Features, Konfigurationen und Szenarien ausprobieren. Sie können die gleiche Testumgebung langfristig für Konzeptnachweise, Demonstrationen für Peers und Verwaltung sowie Anwendungsentwicklung und -tests verwenden. Diese Methode wird empfohlen.

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrieren für ein Office 365 E5-Testabonnement

Stellen Sie über das Azure-Portal eine Verbindung mit CLIENT1 mit dem KONTO CORP\User1 bereit.

Wenn Sie ein neues Office 365 E5-Testabonnement erstellen möchten, führen Sie die Anweisungen in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) der Testumgebungsanleitung zur einfachen Standardkonfiguration aus.

Wenn Sie Ihr neues Office 365 E5-Testabonnement konfigurieren möchten, führen Sie die Anweisungen in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) der Testumgebungsanleitung zur einfachen Standardkonfiguration aus.

#### <a name="using-an-office-365-e5-test-environment"></a>Verwenden einer Office 365 E5-Testumgebung

Wenn Sie nur eine Office 365 benötigen, müssen Sie den Rest dieses Artikels nicht lesen.

Weitere Testumgebungsanleitungen, die sowohl für Microsoft 365 als auch für Office 365 gelten, finden Sie unter [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).

### <a name="add-a-microsoft-365-e5-trial-subscription"></a>Hinzufügen eines Testabonnements für Microsoft 365 E5

Führen Sie die Anweisungen in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) der Testumgebungsanleitung für die einfache Basiskonfiguration aus, um ein Microsoft 365 E5-Testabonnement hinzuzufügen und Ihre Benutzerkonten mit Lizenzen zu konfigurieren.

  
## <a name="results"></a>Ergebnisse

Ihre Testumgebung verfügt nun über Folgendes:
  
- Ein Testabonnement für Microsoft 365 E5.
- Alle entsprechenden Benutzerkonten sind für die Verwendung von Microsoft 365 E5 aktiviert.
- Ein simuliertes und vereinfachtes Intranet.
    
Ihre endgültige Konfiguration sieht wie dies aus:
  
![Phase 2 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
Sie können nun mit zusätzlichen Features von Microsoft 365 [Enterprise experimentieren.](https://www.microsoft.com/microsoft-365/enterprise)
  
## <a name="next-steps"></a>Nächste Schritte

Sehen Sie sich diese zusätzlichen Testumgebungsanleitungen an:
  
- [Identität](m365-enterprise-test-lab-guides.md#identity)
- [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Schutz von Daten](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)