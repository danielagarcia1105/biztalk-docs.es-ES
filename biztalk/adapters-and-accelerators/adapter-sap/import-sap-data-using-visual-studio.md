---
title: Importar datos SAP mediante Visual Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- importing SAP data, using Visual Studio
- Visual Studio, importing SAP data
ms.assetid: 70cce089-232d-4ab9-81bd-6b0d6f0097d7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1295f763815872bacedf2262f7c022d6813bd75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="import-sap-data-using-visual-studio"></a>Importar datos SAP mediante Visual Studio
Esta sección proporciona información sobre cómo usar Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para importar datos desde un sistema SAP en una base de datos de SQL Server. Esta sección proporciona instrucciones sobre cómo crear un paquete SSIS que se puede ejecutar para importar datos. En esta sección también proporciona información sobre cómo ejecutar el paquete SSIS.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de realizar los procedimientos proporcionados en este tema, asegúrese de que:  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]está instalado en el equipo.  
  
-   [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]está instalado en el equipo.  
  
### <a name="to-import-data-using-visual-studio"></a>Para importar datos con Visual Studio  
  
1.  Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y cree un proyecto de servicio de integración.  
  
2.  Desde el **proyecto** menú, seleccione **SSIS Import and Export Wizard**. Esto inicia el **SQL Server Import and Export Wizard**.  
  
3.  Lea la información de la pantalla de bienvenida y haga clic en **siguiente**.  
  
4.  En el **elegir un origen de datos** cuadro de diálogo, desde el **origen de datos** lista desplegable **.NET Framework Data Provider para mySAP Business Suite**. El cuadro de diálogo muestra los parámetros de conexión diferente para conectarse a un sistema SAP. Una cadena de conexión típica para conectarse a un sistema SAP mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requiere:  
  
    -   Los parámetros de conexión para un tipo de conexión. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] es compatible con los tipos de conexión A, B y D. Para conectarse a un sistema SAP debe proporcionar parámetros de conexión para cualquier *una* de estos tipos de conexión. Por ejemplo, para el tipo de conexión A, debe proporcionar el nombre del host de servidor de aplicación y el número del sistema.  
  
    -   La información de inicio de sesión para conectarse a un sistema SAP como nombre de usuario y la contraseña.  
  
     Para obtener más información acerca de la cadena de conexión para conectarse a un sistema SAP mediante la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [más información sobre el proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).  
  
     En el **elegir un origen de datos** diálogo cuadro, especifique:  
  
    -   Los parámetros de conexión para cualquier tipo de una conexión.  
  
    -   La información de inicio de sesión para conectarse a un sistema SAP.  
  
    -   Si desea habilitar la depuración de GUI de SAP.  
  
    -   Si desea utilizar el seguimiento de RFC SDK.  
  
     Haga clic en **Siguiente**.  
  
5.  En el **elegir un destino** cuadro de diálogo:  
  
    1.  Desde el **destino** lista desplegable, seleccione **SQL Native Client**.  
  
    2.  Desde el **nombre del servidor** lista desplegable, seleccione un nombre de SQL server.  
  
    3.  Seleccione un modo de autenticación.  
  
    4.  Desde el **base de datos** lista desplegable, seleccione la base de datos a la que van a importar la tabla SAP.  
  
    5.  Haga clic en **Siguiente**.  
  
6.  En el **especificar copia de tabla o consulta** diálogo cuadro, elija la **escribir una consulta para especificar los datos que se va a transferir** opción y haga clic en **siguiente**.  
  
7.  En el **proporcionar una consulta de origen** cuadro de diálogo, especifique una consulta SELECT para filtrar los datos que se importarán en el servidor SQL Server. Para obtener más información sobre la gramática de una instrucción SELECT de consulta para la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [sintaxis para una instrucción SELECT en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).  
  
     Haga clic en el **analizar** botón para validar la consulta y haga clic en **Aceptar** en el cuadro de diálogo emergente. Haga clic en **Siguiente**.  
  
8.  En el **seleccionar tablas de origen y vistas** cuadro de diálogo, seleccione la casilla de verificación en las tablas de origen y de destino. El origen es la consulta especificada para recuperar datos de SAP. El destino es la tabla que se creará en la base de datos de SQL Server.  
  
9. El asistente crea una asignación predeterminada entre el origen y el destino de campos de la tabla. Sin embargo, puede cambiar las asignaciones de acuerdo con sus necesidades. Para cambiar las asignaciones de campos, haga clic en **editar asignaciones**.  
  
     ![Asignaciones de columnas entre tablas SAP y SQL](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")  
  
10. En el **asignaciones de columnas** cuadro de diálogo, puede:  
  
    -   Cambiar los nombres de columnas en la tabla de destino.  
  
    -   Omitir ciertas columnas de la tabla de destino.  
  
    -   Cambiar el tipo de datos para los campos de tabla de destino.  
  
    -   Cambiar otros atributos de campo como que acepta valores NULL, el tamaño, la precisión y la escala.  
  
    -   Haga clic en **Aceptar**.  
  
11. En el **seleccionar tablas de origen y vistas** cuadro de diálogo, haga clic en **siguiente**.  
  
12. En el **Complete el asistente** diálogo cuadro, revise el resumen de las acciones que el asistente va a realizar y haga clic en **finalizar**.  
  
13. En el **operación en curso** cuadro de diálogo, el asistente inicia la ejecución de tareas para importar la información de SAP en una tabla de base de datos de SQL Server. El estado de cada tarea se muestra en el asistente.  
  
14. Después de que todas las tareas se ejecutan correctamente, haga clic en **cerrar**. Si se produce un error en una tarea, vea el correspondiente mensaje de error, corrija el problema y vuelva a ejecutar al asistente.  
  
15. El asistente agrega un paquete SSIS para el proyecto de servicio de integración. Guarde el proyecto de servicio de integración.  
  
## <a name="running-the-ssis-package"></a>Ejecutar el paquete SSIS  
 Una vez que el paquete se crea dentro de un proyecto de servicio de integración, puede ejecutarla para importar datos desde un sistema SAP en una base de datos de SQL Server. Realice los pasos siguientes para importar datos SAP mediante la ejecución del paquete.  
  
#### <a name="to-run-the-package-from-visual-studio"></a>Para ejecutar el paquete de Visual Studio  
  
1.  Navegue hasta el paquete SSIS en el Explorador de soluciones.  
  
2.  Haga clic en el nombre del paquete y seleccione **Ejecutar paquete**.  
  
 Para obtener más información sobre la ejecución de paquetes, consulte [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972). Para cualquier otra información relacionada con paquetes de SSIS, vea [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).  
  
## <a name="verifying-the-results"></a>Comprobar los resultados  
 Después de ejecutar el paquete, debe comprobar los resultados de inicio de sesión en el servidor SQL Server y yendo a la base de datos a la que se importan los datos SAP. Ejecutar el paquete debe haber creado una tabla de base de datos de destino y rellena con los valores de la tabla SAP.  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos para SAP con SSIS](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)