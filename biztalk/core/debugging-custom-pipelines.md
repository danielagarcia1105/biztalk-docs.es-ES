---
title: Depurar canalizaciones personalizadas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27e5445a-6415-4c52-a450-b74a71fc4aa2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a0f701518714aaf28d0ae07867c8c490c140fa0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="debugging-custom-pipelines"></a>Depurar canalizaciones personalizadas
Cuando se produce un error de procesamiento de mensaje en la canalización personalizada, puede usar la depuración del nivel de origen para identificar y corregir problemas. Esta depuración se realiza mediante la asociación del depurador de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] a BTSNTSVC.exe (si la canalización personalizada está implementada) o Pipeline.exe (si se usa la herramienta de canalización independiente).  
  
## <a name="procedures"></a>Procedimientos  
 Use los procedimientos siguientes para depurar las canalizaciones personalizadas.  
  
### <a name="how-to-debug-a-deployed-pipeline"></a>Cómo depurar una canalización implementada  
 Las consultas de seguimiento de la página Concentrador de grupo y los visualizadores de eventos proporcionan información útil acerca de los errores de procesamiento de mensajes que se han producido en los componentes implementados. Esta información puede usarse con frecuencia para encontrar el origen de un problema. Una vez que una canalización personalizada se ha implicado, la depuración de nivel de origen se puede usar para identificar cualquier código problemático.  
  
##### <a name="to-debug-a-deployed-custom-pipeline-using-visual-studio"></a>Para depurar una canalización personalizada implementada mediante Visual Studio  
  
1.  Cargue la solución de proyecto de canalización personalizada en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
2.  Cambiar la ruta de acceso de salida para la solución  *\<carpeta de instalación >*\Pipeline Components. En el Explorador de soluciones, haga clic en el proyecto, haga clic en la ficha generar y, a continuación, cambie la ruta de acceso de salida, haga clic en el **examinar** botón y seleccionando la  *\<carpeta de instalación >*\ Directorio de componentes de canalización.  
  
3.  Desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], implemente la solución haciendo clic **crear** &#124; **Implementar**.  
  
4.  Reinicie la instancia de host que ejecuta la canalización. Mediante la consola de administración de BizTalk Server, navegue a la instancia de host que ejecuta la canalización, haga clic en la instancia de host, a continuación, haga clic en **reiniciar**.  
  
5.  Adjuntar el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] depurador BTSNTSVC.exe. Puede hacerlo haciendo clic en **depurar** &#124; **Adjuntar al proceso**, haga clic en mostrar los procesos de todas las sesiones y, a continuación, haga doble clic en BTSNTSVC.exe.  
  
6.  Establecer puntos de interrupción.  
  
7.  Deposite un mensaje en la ubicación adecuada para iniciar el componente de canalización personalizada. El procesamiento debería detenerse en los puntos de interrupción establecidos.  
  
> [!NOTE]
>  Si el código inicia una excepción, BizTalk Server la detectará y, en última instancia, suspenderá el mensaje. Para evitar este comportamiento, debería interrumpir en las excepciones de primera probabilidad.  
  
### <a name="how-to-debug-using-pipelineexe"></a>Cómo depurar mediante Pipeline.exe  
 También puede probar las canalizaciones personalizadas mediante Pipeline.exe. Esto tiene la ventaja de que no es necesario implementar la canalización a costa de no funcione en condiciones similares a la producción.  
  
> [!NOTE]
>  Si la canalización personalizada usa el ensamblador/desensamblador de archivo sin formato, Pipeline.exe no se ejecutará correctamente. Esto se debe a que Pipeline.exe no tiene acceso a la base de datos de BizTalk. Una solución consiste en quitar el ensamblador / componentes de desensamblador y probarlos por separado con FFDasm.exe y FFAsm.exe. Vea [herramientas de canalización](../core/pipeline-tools.md) para obtener más información.  
  
##### <a name="to-debug-a-custom-pipeline-using-pipelineexe-and-visual-studio"></a>Para depurar una canalización personalizada mediante Pipeline.exe y Visual Studio  
  
1.  Cargue la solución de proyecto de canalización personalizada en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
2.  Cambiar la ruta de acceso de salida para la solución  *\<carpeta de instalación >*\Pipeline Components. En el Explorador de soluciones, haga clic en el proyecto, haga clic en la ficha generar y, a continuación, cambie la ruta de acceso de salida, haga clic en el **examinar** botón y seleccionando la  *\<carpeta de instalación >*\ Directorio de componentes de canalización.  
  
3.  Cambie la acción de inicio de la solución. En el Explorador de soluciones, haga clic en el proyecto, haga clic en la ficha Depurar, haga clic en programa externo de inicio y luego haga clic en **...** y vaya a  *\<carpeta de instalación >*\SDK\Utilities\PipelineTools y elija Pipeline.exe. En Opciones de inicio, escriba los argumentos de línea de comandos adecuados para su componente. Para obtener más información acerca de Pipeline.exe, vea [herramientas de canalización](../core/pipeline-tools.md). Una configuración típica especifica la canalización y un archivo de ejemplo:  
  
    ```  
    <Path>\YourPipeline.btp -d <Path>\YourTestFile.txt -c  
    ```  
  
4.  Establezca los puntos de interrupción.  
  
5.  Presione F5 para comenzar la depuración.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas de canalización](../core/pipeline-tools.md)