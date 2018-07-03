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
# <a name="applicationmanager-biztalk-server-sample"></a><span data-ttu-id="b4f74-102">ApplicationManager (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b4f74-102">ApplicationManager (BizTalk Server Sample)</span></span>
<span data-ttu-id="b4f74-103">El ejemplo de ApplicationManager muestra cómo iniciar o detener una aplicación de BizTalk mediante los objetos de administración.</span><span class="sxs-lookup"><span data-stu-id="b4f74-103">The ApplicationManager sample demonstrates how to start or stop a  BizTalk application by using the administration objects.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="b4f74-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b4f74-104">Prerequisites</span></span>  

- <span data-ttu-id="b4f74-105">Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b4f74-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="b4f74-106">El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts.</span><span class="sxs-lookup"><span data-stu-id="b4f74-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="b4f74-107">Para obtener más información, consulte: [examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).</span><span class="sxs-lookup"><span data-stu-id="b4f74-107">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="b4f74-108">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4f74-108">What This Sample Does</span></span>  
 <span data-ttu-id="b4f74-109">Este ejemplo muestra cómo utilizar el **BtsCatalogExplorer** y **aplicación** clases a partir de la **Microsoft.BizTalk.ExplorerOM** espacio de nombres para iniciar y detener una implementada  Aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b4f74-109">This sample demonstrates using the **BtsCatalogExplorer** and **Application** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to start and stop a deployed  BizTalk application.</span></span> <span data-ttu-id="b4f74-110">El ejemplo está escrito en Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4f74-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="b4f74-111">En este tema también se incluye un script de ejemplo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4f74-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="b4f74-112">El ejemplo muestra las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="b4f74-112">The sample demonstrates the following operations:</span></span>  

-   <span data-ttu-id="b4f74-113">Conectarse a la base de datos de administración de BizTalk mediante el **BtsCatalogExplorer** clase.</span><span class="sxs-lookup"><span data-stu-id="b4f74-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  

-   <span data-ttu-id="b4f74-114">Buscar una instancia de aplicación de **BtsCatalogExplorer** según el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4f74-114">Finding an application instance from  **BtsCatalogExplorer** based on application name.</span></span>  

-   <span data-ttu-id="b4f74-115">Envío de un comando de inicio o detención para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4f74-115">Submitting a start or stop command for the application.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="b4f74-116">Dónde encontrar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4f74-116">Where To Find This Sample</span></span>  
 <span data-ttu-id="b4f74-117">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="b4f74-117">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="b4f74-118">\<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\ApplicationManager</span><span class="sxs-lookup"><span data-stu-id="b4f74-118">\<*Samples Path*\>\Admin\ExplorerOM\ApplicationManager</span></span>  

 <span data-ttu-id="b4f74-119">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="b4f74-119">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                 <span data-ttu-id="b4f74-120">Archivos</span><span class="sxs-lookup"><span data-stu-id="b4f74-120">File(s)</span></span>                                 |                                                 <span data-ttu-id="b4f74-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4f74-121">Description</span></span>                                                  |
|-------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                               <span data-ttu-id="b4f74-122">Program.cs</span><span class="sxs-lookup"><span data-stu-id="b4f74-122">Program.cs</span></span>                                | <span data-ttu-id="b4f74-123">Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b4f74-123">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="b4f74-124">ApplicationManager.sln,ApplicationManager.csproj,ApplicationManager.suo</span><span class="sxs-lookup"><span data-stu-id="b4f74-124">ApplicationManager.sln,ApplicationManager.csproj,ApplicationManager.suo</span></span> |                                  <span data-ttu-id="b4f74-125">Archivos de solución y proyecto para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b4f74-125">Solution and project files for the sample.</span></span>                                  |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="b4f74-126">Generación y ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4f74-126">Building and Running This Sample</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="b4f74-127">Procedimiento para generar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4f74-127">To build this sample</span></span>  

1. <span data-ttu-id="b4f74-128">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución ApplicationManager.sln.</span><span class="sxs-lookup"><span data-stu-id="b4f74-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file ApplicationManager.sln.</span></span>  

2. <span data-ttu-id="b4f74-129">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="b4f74-129">On the **Build** menu, click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="b4f74-130">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4f74-130">To run this sample</span></span>  

1. <span data-ttu-id="b4f74-131">Abra una ventana de comandos y desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="b4f74-131">Open a command window and navigate to the following folder:</span></span>  

    <span data-ttu-id="b4f74-132">\<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\ApplicationManager\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="b4f74-132">\<*Samples Path*\>\Admin\ExplorerOM\ApplicationManager\bin\Debug</span></span>  

2. <span data-ttu-id="b4f74-133">Ejecute el archivo ApplicationManager.exe y proporcione los dos siguientes argumentos de línea de comandos en el orden indicado:</span><span class="sxs-lookup"><span data-stu-id="b4f74-133">Run the file ApplicationManager.exe providing the following two ordered command-line arguments:</span></span>  

   - <span data-ttu-id="b4f74-134">**\<iniciar&#124;detener\>**  primer argumento es la operación que se realizará en la aplicación implementada.</span><span class="sxs-lookup"><span data-stu-id="b4f74-134">**\<start&#124;stop\>** First argument is the operation to be performed on the deployed application.</span></span>  

   - <span data-ttu-id="b4f74-135">**\<ApplicationName\>**  segundo argumento es el nombre de la aplicación implementada.</span><span class="sxs-lookup"><span data-stu-id="b4f74-135">**\<ApplicationName\>** Second argument is the name of the deployed application.</span></span>  

     <span data-ttu-id="b4f74-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b4f74-136">For example:</span></span>  

   ```  
   ApplicationManager.exe stop MyBizTalkApp  
   ```  

    <span data-ttu-id="b4f74-137">Si se ejecuta el ejemplo con parámetros de línea de comandos insuficientes, se muestra la sintaxis de uso.</span><span class="sxs-lookup"><span data-stu-id="b4f74-137">Running the sample with insufficient command-line parameters displays the usage syntax.</span></span> <span data-ttu-id="b4f74-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b4f74-138">For example:</span></span>  

   ```  
   Usage:  

   ApplicationManager <start|stop> <Application Name>  

    Where:  
     <Application Name> = The name of the application that needs to be changed  

   Example: ApplicationManager start Application1  
   ```  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="b4f74-139">Ejemplo de un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4f74-139">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="b4f74-140">El siguiente fragmento de script de Windows PowerShell se puede usar para mostrar las mismas características de la **ExplorerOM** clases:</span><span class="sxs-lookup"><span data-stu-id="b4f74-140">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  

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

 <span data-ttu-id="b4f74-141">El script espera los mismos argumentos de línea de comandos que el ejemplo [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4f74-141">The script expects the same command-line arguments as the [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] sample.</span></span> <span data-ttu-id="b4f74-142">Aquí se muestra un ejemplo de ejecución del script de Windows PowerShell para iniciar una aplicación BizTalk implementada:</span><span class="sxs-lookup"><span data-stu-id="b4f74-142">Here is an example of running the Windows PowerShell script to start a deployed BizTalk application:</span></span>  

```  
PS C:\> .\ApplicationManager.ps1 start MyBizTalkApp  

Issuing start command to MyBizTalkApp ...  
```  

## <a name="see-also"></a><span data-ttu-id="b4f74-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4f74-143">See Also</span></span>  
 [<span data-ttu-id="b4f74-144">Admin\ExplorerOM (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b4f74-144">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)