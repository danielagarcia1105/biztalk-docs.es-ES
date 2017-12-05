---
title: "Instalar el ejemplo de resolución dinámica con los Scripts de instalación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 644b6403-9883-4256-80d5-37881a87ed0e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 872bb73b9060e25986876c1c2da71afae84b5c52
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="install-the-dynamic-resolution-sample-using-the-install-scripts"></a><span data-ttu-id="92ea1-102">Instalar el ejemplo de resolución dinámica con los Scripts de instalación</span><span class="sxs-lookup"><span data-stu-id="92ea1-102">Install the Dynamic Resolution Sample Using the Install Scripts</span></span>
<span data-ttu-id="92ea1-103">En esta sección se describe cómo puede instalar el ejemplo de resolución dinámica de las secuencias de comandos de instalación proporcionadas con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92ea1-103">This section describes how you can install the Dynamic Resolution sample from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="92ea1-104">**Para instalar el ejemplo de resolución dinámica de las secuencias de comandos de instalación**</span><span class="sxs-lookup"><span data-stu-id="92ea1-104">**To install the Dynamic Resolution sample from the install scripts**</span></span>  
  
1.  <span data-ttu-id="92ea1-105">Si desea ejecutar los ejemplos de mensajes unidireccionales que utilicen FTP, cree el siguiente sitio FTP:</span><span class="sxs-lookup"><span data-stu-id="92ea1-105">If you want to execute one-way messaging examples that use FTP, create the following FTP site:</span></span>  
  
    -   <span data-ttu-id="92ea1-106">Nombre del directorio Virtual FTP: Out</span><span class="sxs-lookup"><span data-stu-id="92ea1-106">FTP Virtual Directory name: Out</span></span>  
  
    -   <span data-ttu-id="92ea1-107">Ubicación: \Source\Samples\DynamicResolution\Test\FTP\Out</span><span class="sxs-lookup"><span data-stu-id="92ea1-107">Location: \Source\Samples\DynamicResolution\Test\FTP\Out</span></span>  
  
    -   <span data-ttu-id="92ea1-108">Permisos: Lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="92ea1-108">Permissions: Read and Write</span></span>  
  
    -   <span data-ttu-id="92ea1-109">Asegúrese de que el grupo de usuarios de la aplicación de BizTalk tiene permiso de acceso completo para esta ubicación</span><span class="sxs-lookup"><span data-stu-id="92ea1-109">Ensure the BizTalk Application Users group has full access permission for this location</span></span>  
  
2.  <span data-ttu-id="92ea1-110">Si desea ejecutar los ejemplos de mensajes bidireccionales que usan MQSeries, utilice el Explorador de WebSphere para crear lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="92ea1-110">If you want to execute two-way messaging examples that use MQSeries, use WebSphere Explorer to create the following:</span></span>  
  
    -   <span data-ttu-id="92ea1-111">Un administrador de cola con el nombre ESB. USO DE DEP. Sample.QueueManager</span><span class="sxs-lookup"><span data-stu-id="92ea1-111">A queue manager with the name ESB.DEP.Sample.QueueManager</span></span>  
  
    -   <span data-ttu-id="92ea1-112">Una cola denominada TEST. OUT dentro de ESB. USO DE DEP. Sample.QueueManager</span><span class="sxs-lookup"><span data-stu-id="92ea1-112">A queue named TEST.OUT within the ESB.DEP.Sample.QueueManager</span></span>  
  
3.  <span data-ttu-id="92ea1-113">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="92ea1-113">On the **Start** menu, click **Run**.</span></span>  
  
4.  <span data-ttu-id="92ea1-114">En el **ejecutar** cuadro de diálogo, escriba **cmd**, y, a continuación, presione ENTRAR para abrir el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="92ea1-114">In the **Run** dialog box, type **cmd**, and then press ENTER to open the command prompt.</span></span>  
  
5.  <span data-ttu-id="92ea1-115">Ejecute el comando siguiente, reemplazando el \<ruta de acceso\> parámetro con la ruta de acceso completa al archivo .cmd que desea instalar (la ruta predeterminada en esta versión es \Source\Samples\DynamicResolution\Install\Scripts\\):</span><span class="sxs-lookup"><span data-stu-id="92ea1-115">Run the following command, replacing the \<path\> parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\DynamicResolution\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```