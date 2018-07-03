---
title: Importar datos de Siebel mediante SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Management Studio, importing data by using
- how to, import data by using SQL Server Management Studio
ms.assetid: 67da7f7b-37ea-4a31-89ef-a9f6974ff976
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdcc6140bb50ebca299cd58f78063be8f108dea4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013181"
---
# <a name="import-siebel-data-using-sql-server-management-studio"></a>Importar datos de Siebel mediante SQL Server Management Studio
Esta sección proporciona información sobre cómo usar SQL Server Management Studio para importar datos desde un sistema Siebel en una base de datos de SQL Server. También proporciona instrucciones sobre cómo crear y ejecutar un paquete SSIS para importar estos datos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de realizar los procedimientos proporcionados en este tema, asegúrese de que:  
  
- El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] está instalado en el equipo.  
  
- SQL Server Business Intelligence Development Studio está instalado en el equipo.  
  
## <a name="importing-data-by-using-sql-server-management-studio"></a>Importar datos mediante SQL Server Management Studio  
 Realice los pasos siguientes para importar datos del sistema de Siebel con [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] con SQL Server Management Studio.  
  
#### <a name="to-import-data-by-using-sql-server-management-studio"></a>Para importar datos mediante SQL Server Management Studio  
  
1. Inicie SQL Server Management Studio.  
  
2. En el **conectar al servidor** diálogo cuadro, especifique los valores para conectarse a una base de datos de SQL Server y, a continuación, haga clic en **Connect**. Se abre Microsoft SQL Server Management Studio.  
  
3. En el Explorador de objetos, expanda el nombre de SQL Server, expanda **bases de datos**y haga clic en la base de datos en la que se van a exportar las tablas en el sistema Siebel. En el menú contextual, seleccione **tareas**y, a continuación, haga clic en **importar datos**. Esto inicia la importación de SQL Server y el Asistente para exportación.  
  
4. Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.  
  
5. En el **elegir un origen de datos** cuadro de diálogo desde el **origen de datos** lista desplegable, seleccione **.NET Framework Data Provider para aplicaciones Siebel eBusiness**. Especifique los valores de las propiedades de conexión diferentes para el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] cadena de conexión. Para obtener más información acerca de las propiedades de cadena de conexión, consulte [las propiedades de proveedor de datos de la cadena de conexión de Siebel](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).  
  
    Haga clic en **Siguiente**.  
  
6. En el **elegir un destino** cuadro de diálogo:  
  
   1.  Desde el **destino** lista desplegable, seleccione **SQL Native Client**.  
  
   2.  Desde el **nombre del servidor** lista desplegable, seleccione un nombre de SQL Server.  
  
   3.  Seleccione un modo de autenticación.  
  
   4.  Desde el **base de datos** lista desplegable, seleccione la base de datos a la que van a importar la tabla de Siebel.  
  
   5.  Haga clic en **Siguiente**.  
  
7. En el **especificar copia de tabla o consulta** diálogo cuadro, elija el **escribir una consulta para especificar los datos que se van a transferir** opción.  
  
8. En el **proporcionar una consulta de origen** diálogo cuadro, especifique una consulta SELECT para filtrar los datos que se importarán en el servidor SQL Server. Para obtener más información sobre la gramática de una instrucción SELECT de consulta para el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], consulte [sintaxis para una instrucción SELECT en Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).  
  
    Haga clic en el **analizar** botón para validar la consulta, haga clic en **Aceptar** en el cuadro de diálogo emergente y, a continuación, haga clic en **siguiente**.  
  
9. En el **seleccionar tablas de origen y las vistas** diálogo cuadro, active la casilla de verificación en las tablas de origen y destino. El origen es la consulta especificada para recuperar datos de Siebel. El destino es la tabla que se creará en la base de datos de SQL Server.  
  
10. El asistente crea una asignación predeterminada entre el origen y destino de los campos de tabla. Sin embargo, puede cambiar las asignaciones de acuerdo con sus necesidades. Para cambiar las asignaciones de campos, haga clic en **editar asignaciones**.  
  
     ![Asignaciones de columnas entre tablas Siebel y SQL](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")  
  
11. En el **asignaciones de columnas** cuadro de diálogo, puede:  
  
    -   Cambiar los nombres de columnas en la tabla de destino.  
  
    -   Omitir algunas columnas en la tabla de destino.  
  
    -   Cambiar el tipo de datos para los campos de tabla de destino.  
  
    -   Cambiar otros atributos de campo como que acepta valores NULL, tamaño, precisión y escala.  
  
         Cuando termine, haga clic en **Aceptar**.  
  
12. En el **seleccionar tablas de origen y las vistas** cuadro de diálogo, haga clic en **siguiente**.  
  
13. En el **guardar y ejecutar paquete** cuadro de diálogo:  
  
    - Seleccione el **ejecutar inmediatamente** casilla de verificación para ejecutar la consulta.  
  
    - Seleccione el **guardar el paquete SSIS** casilla de verificación para guardar la consulta como un paquete y ejecutarlo más tarde. Si decide guardar el paquete, también debe especificar si desea guardar el paquete en el servidor SQL Server o el sistema de archivos.  
  
    - Desde el **nivel de protección de paquetes** lista desplegable, seleccione una protección de nivel para el paquete y especifique las credenciales cuando sea necesario.  
  
    - Haga clic en **Siguiente**.  
  
      Si decide guardar el paquete, continúe con el paso siguiente. En caso contrario, vaya al paso 15.  
  
14. En el **guardar el paquete SSIS** diálogo cuadro, especifique lo siguiente:  
  
    -   El nombre del paquete  
  
    -   La descripción del paquete  
  
    -   Si decide guardar el paquete en un servidor SQL Server, seleccione un servidor SQL Server desde el **nombre del servidor** lista desplegable.  
  
    -   Si decide guardar el paquete en el sistema de archivos, especifique el nombre y la ubicación del archivo en el **nombre de archivo** cuadro de texto.  
  
         Cuando termine, haga clic en **Siguiente**.  
  
15. En el **Complete el asistente** diálogo cuadro, revise el resumen de las acciones que realizar el asistente y, a continuación, haga clic en **finalizar**.  
  
16. En el **realizar operaciones de** cuadro de diálogo, el asistente inicia la ejecución de tareas para importar la información de Siebel en una tabla de base de datos de SQL Server. El estado de cada tarea se muestra en el asistente.  
  
17. Después de que todas las tareas se ejecutan correctamente, haga clic en **cerrar**. Si se produce un error en una tarea, vea el correspondiente mensaje de error, corrija el problema y vuelva a ejecutar al asistente.  
  
## <a name="running-the-ssis-package"></a>Ejecutar el paquete SSIS  
 Si decide guardar el paquete SSIS, puede ejecutarla para recuperar la información más reciente en el sistema Siebel. Esta sección proporciona información sobre cómo ejecutar el paquete si se decide guardarlo en el sistema de archivos.  
  
#### <a name="to-run-the-package-from-windows-explorer"></a>Para ejecutar el paquete desde el Explorador de Windows  
  
1. Desde **Windows Explorer**, desplácese hasta la ubicación donde guardó el paquete y haga doble clic en el paquete.  
  
2. En el cuadro de diálogo **Utilidad de ejecución de paquetes** , haga clic en **Ejecutar**. El **progreso de ejecución del paquete** cuadro de diálogo muestra el progreso de las distintas tareas.  
  
3. Después de que todas las tareas se ejecutan correctamente, haga clic en **cerrar**.  
  
4. En el cuadro de diálogo **Utilidad de ejecución de paquetes** , haga clic en **Cerrar**.  
  
   Para obtener más información sobre la ejecución de paquetes, vea "Paquetes en ejecución" en [ http://go.microsoft.com/fwlink/?LinkId=94972 ](http://go.microsoft.com/fwlink/?LinkId=94972). Para cualquier otra información relacionada con los paquetes de SSIS, vea "paquete procedimientos temas (SSIS)" en [ http://go.microsoft.com/fwlink/?LinkId=94973 ](http://go.microsoft.com/fwlink/?LinkId=94973).  
  
## <a name="verifying-the-results"></a>Comprobar los resultados  
 Después de ejecutar el paquete, debe comprobar los resultados, vaya a la base de datos de SQL Server a la que se importan los datos de Siebel. Ejecutar el paquete debería haber creado una tabla en la base de datos de destino. Esta tabla debe rellenarse con los valores de la tabla de Siebel.  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos para Siebel con SSIS](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)