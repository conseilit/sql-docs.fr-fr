---
title: "À l’aide de l’accès URL dans une Application Windows | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- Windows applications [Reporting Services]
- Web Browser controls [Reporting Services]
- Windows Forms [Reporting Services]
- browser controls [Reporting Services]
- URL access [Reporting Services], Windows applications
ms.assetid: a4b222e5-0cbd-409c-92c4-046a674db8ac
caps.latest.revision: 48
author: sabotta
ms.author: carlasab
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 6174bfd45317faf9b6c8c7131dd1c5026d3a4d51
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---
# <a name="integrating-reporting-services-using-url-access---windows-application"></a>Intégration de Reporting Services à l’aide de l’accès URL - Application Windows
  Même si l'accès URL à un serveur de rapports est optimisé pour un environnement Web, vous pouvez également utiliser l'accès URL pour incorporer des rapports [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans une application [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows. Toutefois, l'accès URL qui nécessite des Windows Forms requiert toujours l'utilisation de la technologie du navigateur Web. Vous pouvez utiliser les scénarios d'intégration suivants avec l'accès URL et les Windows Forms :  
  
-   Afficher un rapport dans une application Windows Form en démarrant un navigateur Web par programme.  
  
-   Utiliser le contrôle <xref:System.Windows.Forms.WebBrowser> sur un Windows Form pour afficher un rapport.  
  
## <a name="starting-internet-explorer-from-a-windows-form"></a>Démarrage d'Internet Explorer à partir d'un Windows Form  
 Vous pouvez utiliser la classe <xref:System.Diagnostics.Process> pour accéder à un processus qui s'exécute sur un ordinateur. Le <xref:System.Diagnostics.Process> classe est un utile [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] construction pour démarrer, arrêter, contrôler et surveiller des applications. Pour afficher un rapport spécifique dans votre base de données du serveur de rapports, vous pouvez démarrer le **IExplore** processus, passant dans l’URL au rapport. L'exemple de code suivant peut être utilisé pour démarrer [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer et passer une URL de rapport spécifique lorsque l'utilisateur clique sur un bouton dans un Windows Form.  
  
```vb  
Private Sub viewReportButton_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles viewReportButton.Click  
   ' Build the URL access string based on values supplied by a user  
   Dim url As String = serverUrlTextBox.Text + "?" & reportPathTextBox.Text & _  
   "&rs:Command=Render" & "&rs:Format=HTML4.0"  
  
   ' If the user does not select the toolbar check box,  
   ' turn the toolbar off in the HTML Viewer  
   If toolbarCheckBox.Checked = False Then  
      url += "&rc:Toolbar=False"  
   End If  
   ' load report in the Web browser  
   Try  
      System.Diagnostics.Process.Start("IExplore", url)  
   Catch  
      MessageBox.Show("The system could not start the specified report using Internet Explorer.", _  
      "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error)  
   End Try  
End Sub 'viewReportButton_Click  
```  
  
```csharp  
// Sample click event for a Button control on a Windows Form  
private void viewReportButton_Click(object sender, System.EventArgs e)  
{  
   // Build the URL access string based on values supplied by a user  
   string url = serverUrlTextBox.Text + "?" + reportPathTextBox.Text +  
      "&rs:Command=Render" + "&rs:Format=HTML4.0";  
  
   // If the user does not check the toolbar check box,  
   // turn the toolbar off in the HTML Viewer  
   if (toolbarCheckBox.Checked == false)  
      url += "&rc:Toolbar=False";  
  
   // load report in the Web browser  
   try  
   {  
      System.Diagnostics.Process.Start("IExplore", url);  
   }  
  
   catch (Exception)  
   {  
      MessageBox.Show(  
         "The system could not open the specified report using Internet Explorer.",   
         "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error);  
   }  
}  
```  
  
## <a name="embedding-a-browser-control-on-a-windows-form"></a>Incorporation d'un contrôle de navigateur Web sur un Windows Form  
 Si vous ne souhaitez pas consulter votre rapport dans un navigateur Web externe, vous pouvez incorporer de façon transparente un navigateur Web dans le cadre de votre Windows Form à l'aide du contrôle <xref:System.Windows.Forms.WebBrowser>.  
  
###### <a name="to-add-the-webbrowser-control-to-your-windows-form"></a>Pour ajouter le contrôle WebBrowser à votre Windows Form  
  
1.  Créez une application Windows, que ce soit [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] ou [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].  
  
2.  Recherchez le <xref:System.Windows.Forms.WebBrowser> contrôler dans le **boîte à outils** boîte de dialogue.  
  
     Si le **boîte à outils** est n’est pas visible vous pouvez y accéder en cliquant sur le **vue** élément de menu et en sélectionnant **boîte à outils**.  
  
3.  Faites glisser le <xref:System.Windows.Forms.WebBrowser>contrôle sur l’aire de conception de votre Windows Form.  
  
     Le <xref:System.Windows.Forms.WebBrowser>contrôle nommé webBrowser1 est ajouté au formulaire  
  
 Dirigez le <xref:System.Windows.Forms.WebBrowser> contrôle vers une URL en appelant son **naviguer** (méthode). Vous pouvez assigner une chaîne d'accès URL spécifique à votre contrôle <xref:System.Windows.Forms.WebBrowser> au moment de l'exécution comme l'illustre l'exemple suivant.  
  
```vb  
Dim url As String = "http://localhost/reportserver?/" & _  
                    "AdventureWorks2012 Sample Reports/" & _  
                    "Company Sales&rs:Command=Render"  
WebBrowser1.Navigate(url)  
```  
  
```csharp  
string url = "http://localhost/reportserver?/" +  
             "AdventureWorks2012 Sample Reports/" +  
             "Company Sales&rs:Command=Render";  
webBrowser1.Navigate(url);  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Intégration de Reporting Services dans des Applications](../../reporting-services/application-integration/integrating-reporting-services-into-applications.md)   
 [Intégration de Reporting Services à l’aide de l’accès URL](../../reporting-services/application-integration/integrating-reporting-services-using-url-access.md)   
 [Intégration de Reporting Services à l’aide de SOAP](../../reporting-services/application-integration/integrating-reporting-services-using-soap.md)   
 [Intégration de Reporting Services à l’aide de contrôles ReportViewer](../../reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls.md)   
 [Accès URL &#40; SSRS &#41;](../../reporting-services/url-access-ssrs.md)  
  
  