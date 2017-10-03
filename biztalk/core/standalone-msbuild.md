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
ms.openlocfilehash: 584d9d5fa8e0c0f6be64d3761fabe45cd08e5a26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="standalone-msbuild"></a>MSBUILD independiente
El **proyecto se compila** componente de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permite generar [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] soluciones sin [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Para instalar el **proyecto se compila** componente en el servidor, seleccione la **el componente de generación de proyecto** opción en el **categoría de Software adicionales** durante la instalación. Debe anular la selección de la **SDK y herramientas de programadores** tal y como se va a instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un equipo sin [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
 Para obtener más información acerca de MSBUILD, vea [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).  
  
## <a name="to-build-a-biztalk-project"></a>Para generar un proyecto de BizTalk  
  
1.  Haga clic en **Inicio**y, a continuación, en **Ejecutar**.  
  
2.  Tipo de **cmd**, y presione ENTRAR.  
  
3.  Cambie al directorio del proyecto y ejecute un comando MSBUILD para generar la solución de BizTalk.  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!TIP]
    >  Es podrán que deba configurar la variable de entorno PATH para que señale a la carpeta donde reside msbuild.exe (\<*directorio de instalación de windows*> \Microsoft.NET\Framework\v4).