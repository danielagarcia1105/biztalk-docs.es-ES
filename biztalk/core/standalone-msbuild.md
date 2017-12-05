---
title: MSBUILD independiente | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21aa3693-3788-4874-b506-6f4584fb4fd5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcee1d06bf57eb2ea98c214501c2499f0ce83d95
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="standalone-msbuild"></a><span data-ttu-id="6563a-102">MSBUILD independiente</span><span class="sxs-lookup"><span data-stu-id="6563a-102">Standalone MSBUILD</span></span>
<span data-ttu-id="6563a-103">El **proyecto se compila** componente de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permite generar soluciones de BizTalk Server sin [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6563a-103">The **Project Build** component of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] allows you to build BizTalk Server solutions without [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="6563a-104">Para instalar el **proyecto se compila** componente en el servidor, seleccione la **el componente de generación de proyecto** opción en el **categoría de Software adicionales** durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="6563a-104">To install the **Project Build** component on your server, select the **Project Build Component** option in the **Additional Software category** during installation.</span></span> <span data-ttu-id="6563a-105">Debe anular la selección de la **SDK y herramientas de programadores** tal y como se va a instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un equipo sin [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6563a-105">You should unselect the **Developer Tools and SDK** as you are installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a computer without [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6563a-106">Para obtener más información acerca de MSBUILD, vea [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span><span class="sxs-lookup"><span data-stu-id="6563a-106">For more information on MSBUILD, see [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
## <a name="to-build-a-biztalk-project"></a><span data-ttu-id="6563a-107">Para generar un proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6563a-107">To build a BizTalk project</span></span>  
  
1.  <span data-ttu-id="6563a-108">Haga clic en **Inicio**y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6563a-108">Click **Start**, and click **Run**.</span></span>  
  
2.  <span data-ttu-id="6563a-109">Tipo de **cmd**, y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="6563a-109">Type **cmd**, and press ENTER.</span></span>  
  
3.  <span data-ttu-id="6563a-110">Cambie al directorio del proyecto y ejecute un comando MSBUILD para generar la solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="6563a-110">Switch to the project directory, and run a MSBUILD command to build the BizTalk solution.</span></span>  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="6563a-111">Es podrán que deba configurar la variable de entorno PATH para que señale a la carpeta donde reside msbuild.exe (\<*directorio de instalación de windows*\>\Microsoft.NET\Framework\v4).</span><span class="sxs-lookup"><span data-stu-id="6563a-111">You may need set the PATH environment variable to point to the folder in which msbuild.exe resides (\<*windows installation directory*\>\Microsoft.NET\Framework\v4).</span></span>