---
title: 'Lección 2: Crear un ensamblado de BizTalk con nombre seguro para el proyecto SWIFTSchemas | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, creating strong-names
- strong-named assemblies
ms.assetid: 2aacbf38-8b1d-46ea-89ae-5207327bedc1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8e5b9ccc56b6b75ea574f956faac462e5b35dca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995525"
---
# <a name="lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project"></a>Lección 2: Crear un ensamblado de BizTalk con nombre seguro para el proyecto SWIFTSchemas
En esta lección, creará un nombre seguro en el que se compilan e implementan los ensamblados de BizTalk. Un ensamblado con nombre seguro ofrece varias ventajas de seguridad:  
  
- Un nombre seguro garantiza la exclusividad del ensamblado mediante la asignación de una firma digital y un único par de claves.  
  
- Un nombre seguro protege el linaje del ensamblado asegurándose de que nadie más puede generar una versión posterior del ensamblado.  
  
- Un nombre seguro proporciona una comprobación de integridad importante para garantizar que el contenido del ensamblado no ha cambiado desde la última compilación.  
  
  Puede generar un archivo de clave mediante la herramienta de nombre seguro (sn.exe) que viene con [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] o [!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)].  
  
### <a name="to-create-a-strong-named-biztalk-assembly"></a>Para crear un ensamblado de BizTalk con nombre seguro  
  
1. Inicie el símbolo del sistema de Visual Studio.  
  
2. En el símbolo del sistema de Visual Studio, vaya a la \< *unidad*\>: carpeta \labs.  
  
3. En el símbolo del sistema, escriba **sn – k swift.snk**, y, a continuación, presione ENTRAR. Asegúrese de que aparece un mensaje de éxito en la ventana de salida.  
  
   > [!NOTE]
   >  Si no aparece el mensaje correcto, use Visual Studio para solucionar problemas de su ensamblado.  
  
4. En el Explorador de soluciones, haga clic en el **SWIFTSchemas** del proyecto y, a continuación, haga clic en **propiedades**.  
  
5. Asegúrese de que en el cuadro de diálogo páginas de propiedades SWIFTSchemas **propiedades comunes** está expandido y, a continuación, seleccione **ensamblado**.  
  
6. Desplácese hacia abajo en las propiedades del ensamblado en el panel derecho y en el **nombre seguro** sección, haga clic en el cuadro a la derecha del **archivo clave de ensamblado**. Haga clic en el botón de puntos suspensivos.  
  
7. En el cuadro de diálogo de archivo de clave de ensamblado, vaya a  **\< *unidad*:\>\labs**.  
  
8. Seleccione el **swift.snk** de archivo como el archivo de clave y, a continuación, haga clic en **abierto**.  
  
9. En el cuadro de diálogo páginas de propiedades SWIFTSchemas, haga clic en **Aceptar**.  
  
10. En el **archivo** menú, haga clic en **guardar todo** para guardar los cambios.  
  
    Continúe con [lección 3: agregar esquemas de SWIFT a un proyecto](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md).