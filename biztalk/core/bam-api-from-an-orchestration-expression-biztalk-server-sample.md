---
title: "API de BAM en el ejemplo de expresión de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5413940eaba97e6f68d5e068e26625f320e6e817
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a>API de BAM desde una expresión de orquestación (ejemplo de BizTalk Server)
En este ejemplo se demuestra cómo realizar lo siguiente:  
  
-   Usar la API de BAM en una expresión de orquestación de BizTalk Server.  
  
-   Realizar el seguimiento de elementos repetitivos en un mensaje como instancias de actividad individuales.  
  
-   Crear una relación entre los datos de BAM supervisados mediante un perfil de seguimiento y los datos de BAM supervisados mediante una API de BAM.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Puede encontrar este ejemplo en  *\<ruta de ejemplos\>*\BAM\BamFromExpression.  
  
 En la siguiente tabla se enumeran los archivos de este ejemplo y se describe el propósito de cada uno de ellos.  
  
|Archivo|Description|  
|----------|-----------------|  
|BamDefinition.xls|Hoja de estilo de definición de BAM.|  
|BamDefinition.xml|Definición de BAM.|  
|BamFromExpression.btproj|Seguimiento de archivo de proyecto de Visual Studio.|  
|BamFromExpression.sln|Solución de Visual Studio.|  
|Cleanup.bat|Archivo por lotes que se usa para anular la implementación del ejemplo.|  
|InputMessage.xml|Mensaje de entrada.|  
|Orchestration1.odx|Orquestación.|  
|PoSchema.xsd|Esquema del pedido de compra.|  
|PropertySchema.xsd|Esquema de propiedad.|  
|Setup.bat|Archivo por lotes para compilar e implementar el ejemplo.|  
|QueryBam.sql|Script de SQL.|  
  
## <a name="create-the-tracking-profile"></a>Crear el perfil de seguimiento  
  
1.  Abra un símbolo del sistema como administrador y ejecute  *\<ruta de ejemplos\>*\BAM\BAMFromExpression\Setup.bat. Setup.bat inicializa la infraestructura de BAM para este ejemplo e implementa la actividad de BAM.  
  
2.  Desde el **programas** > **Microsoft BizTalk Server**, haga clic en **Editor de perfiles de seguimiento**, y **ejecutar como administrador**.
  
3.  En el panel izquierdo de la **Editor de perfiles de seguimiento** ventana, haga clic en **haga clic aquí para seleccionar una definición de actividad de BAM**.  
  
4.  En el **nombre de definición de actividad de BAM** sección de la **Importar definición de actividad de BAM** cuadro de diálogo, seleccione **FromExpressionPo**y, a continuación, haga clic en **Aceptar**.  
  
5.  En el panel derecho de la **Editor de perfiles de seguimiento** ventana, haga clic en **haga clic aquí para seleccionar un origen de eventos**.  
  
6.  En el **nombre de ensamblado** sección de la **seleccionar ensamblado primario de origen de eventos** cuadro de diálogo, seleccione **Microsoft.Samples.BizTalk.BamFromExpression**y, a continuación, haga clic en  **Siguiente**.  
  
7.  En el **nombre de la orquestación** sección de la **Seleccionar orquestación** cuadro de diálogo, seleccione **BamFromExpression.Orchestration1**y, a continuación, haga clic en **Aceptar**.  
  
8.  Haga clic en el **Receive_1** forma y, a continuación, haga clic en **esquema de carga de mensaje**.  
  
9. Expanda  **\<esquema\>**, expanda **PurchaseOrder**, expanda **de**y, a continuación, arrastre **PoID** a la derecha panel para **ActivityID** en el panel izquierdo.  
  
10. Arrastre los elementos siguientes del panel derecho y suéltelos en los nodos con nombre del panel izquierdo:  
  
    |De|A|  
    |----------|--------|  
    |Nombre|De|  
    |State|State|  
    |City|City|  
    |Teléfono|Teléfono|  
    |Total|PoTotal|  
  
11. Haga clic en el icono de carpeta con la flecha (![botón con carpeta y seguridad &#45; flecha](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) para mostrar la orquestación.  
  
12. Arrastre el **Receive_1** forma en el panel derecho a **recibidos** en el panel izquierdo.  
  
13. Arrastre el **Send_1** forma en el panel derecho a **enviar** en el panel izquierdo.  
  
14. Guarde el perfil de seguimiento para  *\<ruta de ejemplos\>*\BAM\BamFromExpression\ BamFromExpression.btt.  
  
15. En el **herramientas** menú, haga clic en **aplicar perfil de seguimiento**.  
  
## <a name="build-and-initialize-this-sample"></a>Crear e inicializar este ejemplo  
  
Implemente el perfil de seguimiento BamFromExpression.btt. Vea [utilidad de administración de perfiles de cómo implementar perfiles de seguimiento con el seguimiento](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md).  
  
## <a name="run-this-sample"></a>Ejecutar este ejemplo  
  
Copie el archivo  *\<ruta de ejemplos\>*\BamFromExpression\InputMessage.xml a  *\<ruta de ejemplos\>*\BamFromExpression\Input.  
  
En unos 10 segundos, aparecerá el mensaje de salida en  *\<ruta de ejemplos\>*\BamFromExpression\Output.  
  
## <a name="view-the-bam-data"></a>Ver los datos de BAM  
  
1.  Abra SQL Server Management Studio.  
  
2.  En SQL Server Management Studio, expanda el servidor, expanda **bases de datos**, expanda **BAMPrimaryImport**y, a continuación, expanda **tablas**.  
  
3.  Haga clic en **dbo.bam_FromExpressionPo_Completed**y, a continuación, haga clic en **Abrir tabla**. Si está utilizando SQL Server, haga clic en **seleccionar las primeras 1000 filas**.  
  
     El contenido de la tabla bam_FromExpressionPo_Completed se muestra en el panel derecho. La fila con el identificador de actividad 123 representa el pedido de 345 USD incluido en el mensaje de entrada.  
  
4.  Haga clic en **dbo.bam_FromExpressionPoItem_Completed**y, a continuación, haga clic en **Abrir tabla**. Si está utilizando SQL Server, haga clic en **seleccionar las primeras 1000 filas**.  
  
     El contenido de la tabla bam_FromExpressionPoItem_Completed se muestra en el panel derecho. Las dos filas, que tienen actividad identificadores 123_0 y 123_1, representan los elementos del pedido de compra: MC Flash y descodificador de infrarrojos.  
  
5.  Haga clic en **dbo.bam_FromExpressionPoItem_CompletedRelationships**y, a continuación, haga clic en **Abrir tabla**. Si está utilizando SQL Server, haga clic en **seleccionar las primeras 1000 filas**.  
  
     El contenido de la tabla bam_FromExpressionPoItem_CompletedRelationships se muestra en el panel derecho. Cada fila de la tabla representa una relación entre una actividad FromExpressionPoItem y una actividad FromExpressionPo. El valor de la **ActivityID** columna hace referencia al identificador de la actividad FromExpressionPoItem. El valor de la **ReferenceData** columna hace referencia al identificador de la actividad FromExpressionPo. En este caso, ambos registros indican que los artículos MC Flash y descodificador de infrarrojos están asociados con el pedido de 345 USD.  
  
## <a name="re-run-the-sample"></a>Vuelva a ejecutar el ejemplo  
  
1.  Abra un símbolo del sistema como administrador y ejecute  *\<ruta de ejemplos\>*\BAM\BamFromExpression\Cleanup.bat para quitar el perfil de seguimiento y otras infraestructuras BAM. 
  
2.  Ejecutar  *\<ruta de ejemplos\>*\BAM\BamFromExpression\Setup.bat para compilar el ejemplo e implementarlo.  
  
## <a name="see-also"></a>Vea también  
 [(Carpeta de ejemplos de BizTalk Server) de supervisión de la actividad de negocio](../core/business-activity-monitoring-biztalk-server-samples-folder.md)   
 [Relaciones de actividades](../core/activity-relationships.md)