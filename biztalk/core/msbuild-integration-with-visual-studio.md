---
title: "Integración de MSBUILD con Visual Studio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aedcabf7-b2cf-482a-9ade-7311e104bff9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4a639945881625dd697798080c913ec0e5e3a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="msbuild-integration-with-visual-studio"></a><span data-ttu-id="9fccf-102">Integración de MSBUILD con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9fccf-102">MSBUILD Integration with Visual Studio</span></span>
<span data-ttu-id="9fccf-103">Visual Studio usa el formato de archivo de proyecto MSBUILD para almacenar información de generación sobre proyectos administrados, incluidos los proyectos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9fccf-103">Visual Studio uses the MSBUILD project file format to store build information about managed projects including BizTalk projects.</span></span> <span data-ttu-id="9fccf-104">La configuración del proyecto que se ha agregado y cambiado con Visual Studio se refleja en el archivo .btproj que se genera para cada proyecto.</span><span class="sxs-lookup"><span data-stu-id="9fccf-104">Project settings added and changed through Visual Studio are reflected in the .btproj file that is generated for each project.</span></span> <span data-ttu-id="9fccf-105">Visual Studio usa una instancia alojada de MSBUILD para crear proyectos de BizTalk, lo que significa que un proyecto de BizTalk se puede crear en Visual Studio o en la línea de comandos, con resultados idénticos.</span><span class="sxs-lookup"><span data-stu-id="9fccf-105">Visual Studio uses a hosted instance of MSBUILD to build BizTalk projects, meaning that a BizTalk project can be built in Visual Studio or from the command line, with identical results.</span></span>  
  
 <span data-ttu-id="9fccf-106">Para obtener más información acerca de MSBUILD, vea [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span><span class="sxs-lookup"><span data-stu-id="9fccf-106">For more information on MSBUILD, see [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
 <span data-ttu-id="9fccf-107">El siguiente procedimiento muestra cómo usar MSBUILD para crear un proyecto de BizTalk de ejemplo desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="9fccf-107">The following procedure shows you how to use MSBUILD to build a sample BizTalk project from command line.</span></span>  
  
## <a name="to-build-a-biztalk-project-from-a-command-line"></a><span data-ttu-id="9fccf-108">Procedimiento para crear un proyecto de BizTalk desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="9fccf-108">To build a BizTalk project from a command line</span></span>  
  
1.  <span data-ttu-id="9fccf-109">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="9fccf-109">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="9fccf-110">Cambie al directorio del proyecto y ejecute un comando MSBUILD para generar la solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9fccf-110">Switch to the project directory, and run a MSBUILD command to build the BizTalk solution.</span></span>  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="9fccf-111">La solución puede contener proyectos de BizTalk y no de BizTalk, por ejemplo, la biblioteca de clases C#.</span><span class="sxs-lookup"><span data-stu-id="9fccf-111">The solution may contain BizTalk and non-BizTalk projects, such as a C# class library.</span></span>