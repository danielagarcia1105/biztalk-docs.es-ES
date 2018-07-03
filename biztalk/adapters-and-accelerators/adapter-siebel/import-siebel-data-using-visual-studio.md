---
title: Importar datos de Siebel con Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33701361-eca2-4795-a5e0-78162a98e9ba
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d631c461c876ef4066e497d7d72d2e5fe13d022
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978037"
---
# <a name="import-siebel-data-using-visual-studio"></a>Importar datos de Siebel con Visual Studio
Esta sección proporciona información sobre cómo usar Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para importar datos desde un sistema Siebel en una base de datos de SQL Server. También proporciona instrucciones sobre cómo crear y ejecutar un paquete SSIS para importar estos datos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de realizar los procedimientos proporcionados en este tema, asegúrese de que:  
  
- El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] está instalado en el equipo.  
  
- Microsoft Visual Studio está instalado en el equipo.  
  
## <a name="import-in-visual-studio"></a>Importación en Visual Studio  
 
1. Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y crear un proyecto de servicio de integración.  
  
2. Desde el **proyecto** menú, seleccione **SSIS Import and Export Wizard**. Esto inicia la importación de SQL Server y el Asistente para exportación.  
  
3. Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.  
  
4. En el **elegir un origen de datos** cuadro de diálogo desde el **origen de datos** lista desplegable **.NET Framework Data Provider para aplicaciones Siebel eBusiness**. Especifique los valores de las propiedades de conexión diferentes para el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] cadena de conexión. Para obtener más información acerca de las propiedades de cadena de conexión, consulte [las propiedades de proveedor de datos de la cadena de conexión de Siebel](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).  
  
    Haga clic en **Siguiente**.  
  
5. En el **elegir un destino** cuadro de diálogo:  
  
   1.  Desde el **destino** lista desplegable, seleccione **SQL Native Client**.  
  
   2.  Desde el **nombre del servidor** lista desplegable, seleccione un nombre de SQL Server.  
  
   3.  Seleccione un modo de autenticación.  
  
   4.  Desde el **base de datos** lista desplegable, seleccione la base de datos a la que van a importar la tabla de Siebel.  
  
   5.  Haga clic en **Siguiente**.  
  
6. En el **especificar copia de tabla o consulta** diálogo cuadro, elija el **escribir una consulta para especificar los datos que se van a transferir** opción.  
  
7. En el **proporcionar una consulta de origen** diálogo cuadro, especifique una consulta SELECT para filtrar los datos que se importarán en el servidor SQL Server. Para obtener más información sobre la gramática de una instrucción SELECT de consulta para el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], consulte [sintaxis para una instrucción SELECT en Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).  
  
8. Para validar la consulta, haga clic en el **analizar** botón, haga clic en **Aceptar** en el cuadro de diálogo emergente y, a continuación, haga clic en **siguiente**.  
  
9. En el **seleccionar tablas de origen y las vistas** diálogo cuadro, active la casilla de verificación en las tablas de origen y destino. El origen es la consulta especificada para recuperar datos de Siebel. El destino será la tabla que se creará en la base de datos de SQL Server.  
  
10. El asistente crea una asignación predeterminada entre el origen y destino de los campos de tabla. Sin embargo, puede cambiar las asignaciones de acuerdo con sus necesidades. Para cambiar las asignaciones de campos, haga clic en **editar asignaciones**.  
  
11. En el **asignaciones de columnas** cuadro de diálogo, puede:  
  
    - Cambiar los nombres de columnas en la tabla de destino.  
  
    - Omitir algunas columnas en la tabla de destino.  
  
    - Cambiar el tipo de datos para los campos de tabla de destino.  
  
    - Cambiar otros atributos de campo como que acepta valores NULL, tamaño, precisión y escala.  
  
    - Haga clic en **Aceptar**.  
  
      ![Asignaciones de columnas entre tablas Siebel y SQL](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")  
  
12. En el **seleccionar tablas de origen y las vistas** cuadro de diálogo, haga clic en **siguiente**.  
  
13. En el **Complete el asistente** diálogo cuadro, revise el resumen de las acciones que realizar el asistente y, a continuación, haga clic en **finalizar**.  
  
14. En el **realizar operaciones de** cuadro de diálogo, el asistente inicia la ejecución de tareas para importar la información de Siebel en una tabla de base de datos de SQL Server. El estado de cada tarea se muestra en el asistente.  
  
15. Después de que todas las tareas se ejecutan correctamente, haga clic en **cerrar**. Si se produce un error en una tarea, vea el correspondiente mensaje de error, corrija el problema y vuelva a ejecutar al asistente.  
  
16. El asistente agrega un paquete SSIS para el proyecto de servicio de integración. Guarde el proyecto de servicio de integración.  
  
## <a name="run-the-ssis-package"></a>Ejecutar el paquete SSIS  
 Una vez creado el paquete dentro de un proyecto de servicio de integración, puede ejecutarla para importar datos desde un sistema Siebel en una base de datos de SQL Server. Realice los pasos siguientes para importar datos de Siebel mediante la ejecución del paquete.  
  
1.  Navegue hasta el paquete SSIS en el Explorador de soluciones.  
  
2.  Haga clic en el nombre del paquete y, a continuación, seleccione **Ejecutar paquete**.  
  
[Ejecutar paquetes de Integration Services (SSIS)](https://docs.microsoft.com/sql/integration-services/packages/run-integration-services-ssis-packages) proporciona más información. 
  
## <a name="verify-the-results"></a>Comprobar los resultados  
 Después de ejecutar el paquete, debe comprobar los resultados, iniciar sesión en el servidor SQL Server y vaya a la base de datos a la que se importan los datos de Siebel. Ejecutar el paquete debería haber creado una tabla en la base de datos de destino. Esta tabla debe rellenarse con los valores de la tabla de Siebel.  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos para Siebel con SSIS](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)