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
# <a name="msbuild-integration-with-visual-studio"></a>Integración de MSBUILD con Visual Studio
Visual Studio usa el formato de archivo de proyecto MSBUILD para almacenar información de generación sobre proyectos administrados, incluidos los proyectos de BizTalk. La configuración del proyecto que se ha agregado y cambiado con Visual Studio se refleja en el archivo .btproj que se genera para cada proyecto. Visual Studio usa una instancia alojada de MSBUILD para crear proyectos de BizTalk, lo que significa que un proyecto de BizTalk se puede crear en Visual Studio o en la línea de comandos, con resultados idénticos.  
  
 Para obtener más información acerca de MSBUILD, vea [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).  
  
 El siguiente procedimiento muestra cómo usar MSBUILD para crear un proyecto de BizTalk de ejemplo desde la línea de comandos.  
  
## <a name="to-build-a-biztalk-project-from-a-command-line"></a>Procedimiento para crear un proyecto de BizTalk desde la línea de comandos  
  
1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
2.  Cambie al directorio del proyecto y ejecute un comando MSBUILD para generar la solución de BizTalk.  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!NOTE]
    >  La solución puede contener proyectos de BizTalk y no de BizTalk, por ejemplo, la biblioteca de clases C#.