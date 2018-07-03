---
title: ApplicationManager (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51ebe7a8-a0ca-4d2a-bf40-ec6421ba5a95
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b926f9e848ab86f5b168d46b3b0e84d85356f592
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010741"
---
# <a name="applicationmanager-biztalk-server-sample"></a>ApplicationManager (ejemplo de BizTalk Server)
El ejemplo de ApplicationManager muestra cómo iniciar o detener una aplicación de BizTalk mediante los objetos de administración.  

## <a name="prerequisites"></a>Requisitos previos  

- Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.  

- El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts. Para obtener más información, consulte: [examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).  

## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra cómo utilizar el **BtsCatalogExplorer** y **aplicación** clases a partir de la **Microsoft.BizTalk.ExplorerOM** espacio de nombres para iniciar y detener una implementada  Aplicación de BizTalk. El ejemplo está escrito en Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]. En este tema también se incluye un script de ejemplo de Windows PowerShell. El ejemplo muestra las siguientes operaciones:  

-   Conectarse a la base de datos de administración de BizTalk mediante el **BtsCatalogExplorer** clase.  

-   Buscar una instancia de aplicación de **BtsCatalogExplorer** según el nombre de la aplicación.  

-   Envío de un comando de inicio o detención para la aplicación.  

## <a name="where-to-find-this-sample"></a>Dónde encontrar este ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  

 \<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\ApplicationManager  

 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  


|                                 Archivos                                 |                                                 Descripción                                                  |
|-------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                               Program.cs                                | Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo. |
| ApplicationManager.sln,ApplicationManager.csproj,ApplicationManager.suo |                                  Archivos de solución y proyecto para el ejemplo.                                  |

## <a name="building-and-running-this-sample"></a>Generación y ejecución del ejemplo  

#### <a name="to-build-this-sample"></a>Procedimiento para generar este ejemplo  

1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución ApplicationManager.sln.  

2. En el menú **Compilar** , haga clic en **Compilar solución**.  

#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  

1. Abra una ventana de comandos y desplácese a la siguiente carpeta:  

    \<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\ApplicationManager\bin\Debug  

2. Ejecute el archivo ApplicationManager.exe y proporcione los dos siguientes argumentos de línea de comandos en el orden indicado:  

   - **\<iniciar&#124;detener\>**  primer argumento es la operación que se realizará en la aplicación implementada.  

   - **\<ApplicationName\>**  segundo argumento es el nombre de la aplicación implementada.  

     Por ejemplo:  

   ```  
   ApplicationManager.exe stop MyBizTalkApp  
   ```  

    Si se ejecuta el ejemplo con parámetros de línea de comandos insuficientes, se muestra la sintaxis de uso. Por ejemplo:  

   ```  
   Usage:  

   ApplicationManager <start|stop> <Application Name>  

    Where:  
     <Application Name> = The name of the application that needs to be changed  

   Example: ApplicationManager start Application1  
   ```  

## <a name="windows-powershell-script-example"></a>Ejemplo de un script de Windows PowerShell  
 El siguiente fragmento de script de Windows PowerShell se puede usar para mostrar las mismas características de la **ExplorerOM** clases:  

```  
#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

#=== Loop through applications in the catalog trying to find a name match ===#  

foreach($app in $Catalog.Applications)  
{  
    if ($($app.Name) -ieq $args[1])  
    {  

        #=== The first command-line argument should be "start" or "stop" ===#  

        if ($args[0] -ieq "start")  
        {  
            Write-Host `r`nIssuing start command to $app.Name...`r`n  
            $app.Start([Microsoft.BizTalk.ExplorerOM.ApplicationStartOption] "StartAll")  
            $Catalog.SaveChanges()  
        }  

        if ($args[0] -ieq "stop")  
        {  
            Write-Host `r`nIssuing stop command to $app.Name...`r`n  
            $app.Stop([Microsoft.BizTalk.ExplorerOM.ApplicationStopOption] "StopAll")  
            $Catalog.SaveChanges()  
        }  

    }  
}  
```  

 El script espera los mismos argumentos de línea de comandos que el ejemplo [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]. Aquí se muestra un ejemplo de ejecución del script de Windows PowerShell para iniciar una aplicación BizTalk implementada:  

```  
PS C:\> .\ApplicationManager.ps1 start MyBizTalkApp  

Issuing start command to MyBizTalkApp ...  
```  

## <a name="see-also"></a>Vea también  
 [Admin\ExplorerOM (carpeta de ejemplos de BizTalk Server)](../core/admin-explorerom-biztalk-server-samples-folder.md)