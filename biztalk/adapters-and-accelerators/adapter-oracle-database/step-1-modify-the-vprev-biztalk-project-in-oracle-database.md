---
title: 'Paso 1: Modificar el proyecto de BizTalk en la base de datos de Oracle vPrev | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e3e22ac-126b-46ec-a6dc-3421ad721392
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f8911a31eeec34a5508d29ff598a2f7624e5cd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-modify-the-vprev-biztalk-project-in-oracle-database"></a>Paso 1: Modificar el proyecto de BizTalk en la base de datos de Oracle vPrev
![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, realice los siguientes cambios en el proyecto de BizTalk vPrev existente:  
  
-   Generar metadatos para la operación de inserción en el SCOTT. Tabla CUSTOMER usando basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
-   Asignar el mensaje de solicitud para realizar una operación de inserción con el adaptador de base de datos de Oracle vPrev a un mensaje de solicitud para realizar una operación de inserción mediante basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
-   Asignar el mensaje de respuesta recibido con basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] al mensaje de respuesta para el adaptador de base de datos de Oracle vPrev.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener un proyecto de BizTalk vPrev para realizar una operación de inserción en el SCOTT. Tabla de clientes en la base de datos de Oracle.  
  
## <a name="modify-the-vprev-biztalk-project"></a>Modificar el proyecto de BizTalk vPrev  
  
1.  Generar metadatos para la operación de inserción en el SCOTT. Tabla CUSTOMER usando basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Puede usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar los metadatos.  
  
     Para obtener instrucciones sobre cómo generar los metadatos, consulte [obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md). Una vez generado el esquema, un archivo con el nombre similar al *OracleDBBindingSchema.xsd* se agrega al proyecto de BizTalk. Este archivo contiene el esquema para enviar un mensaje para realizar una operación de inserción en el SCOTT. Tabla de clientes en la base de datos de Oracle mediante basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
2.  Generar los metadatos de la operación de inserción, también crea un archivo de enlace de puerto. En el paso siguiente, este archivo de enlace se utilizará para crear un puerto de envío WCF-Custom para enviar mensajes a la base de datos de Oracle. La acción SOAP para la operación también se establece en la operación para el que generar metadatos. Por ejemplo, si genera metadatos para la operación de inserción, el nombre de la operación en la acción de SOAP en el puerto de envío será "Insertar". Sin embargo, la operación de nombre en el puerto de envío lógico que se crea como parte de la orquestación podría ser diferente, por ejemplo, "Operation_1". Como resultado, al enviar mensajes a la base de datos de Oracle mediante el puerto de envío, obtendrá un error. Para evitar esto, asegúrese de que el nombre de la operación en la operación lógica puerto en la orquestación es el mismo que el nombre de la operación para el que generar metadatos de envío.  
  
     Por lo tanto, en el caso de este tutorial, dado que generar metadatos para la operación de inserción, cambiar el nombre de la operación de puerto de envío lógico para "Insertar".  
  
3.  Para el mensaje de solicitud, asignar el esquema generado con el adaptador de base de datos de Oracle vPrev para el esquema generado mediante basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
    1.  Agregue a un asignador de BizTalk al proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y haga clic en **nuevo elemento**.  
  
         En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **RequestMap.btm**. Haga clic en **Agregar**.  
  
    2.  En el panel de esquema de origen, haga clic en **Abrir esquema de origen**.  
  
    3.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema del mensaje de solicitud para el adaptador de base de datos de Oracle vPrev. Para este tutorial, seleccione *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*. Haga clic en **Aceptar**.  
  
    4.  En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *insertar* y haga clic en **Aceptar**.  
  
    5.  En el panel de esquema de destino, haga clic en **Abrir esquema de destino**.  
  
    6.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema del mensaje de solicitud para basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para este tutorial, seleccione *Oracle_Migration.OracleDBBindingSchema*. Haga clic en **Aceptar**.  
  
    7.  En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *insertar* y haga clic en **Aceptar**.  
  
    8.  Asignar los elementos correspondientes en los esquemas de ambos tal y como se muestra en la ilustración siguiente.  
  
         ![Asignar la solicitud enviada a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/4cb59338-40d1-4eb1-bd89-b5a3183959e1.gif "4cb59338-40d1-4eb1-bd89-b5a3183959e1")  
  
    9. Guarde el mapa.  
  
4.  El mensaje de respuesta, asignar el esquema generado con el adaptador de base de datos de Oracle vPrev para el esquema generado mediante basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
    1.  Agregue a un asignador de BizTalk al proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y haga clic en **nuevo elemento**.  
  
         En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **ResponseMap.btm**. Haga clic en **Agregar**.  
  
    2.  En el panel de esquema de origen, haga clic en **Abrir esquema de origen**.  
  
    3.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para el mensaje de respuesta para basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para este tutorial, seleccione *Oracle_Migration.OracleDBBindingSchema*. Haga clic en **Aceptar**.  
  
    4.  En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *InsertResponse* y haga clic en **Aceptar**.  
  
    5.  En el panel de esquema de destino, haga clic en **Abrir esquema de destino**.  
  
    6.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para el mensaje de respuesta para el adaptador de base de datos de Oracle vPrev. Para este tutorial, seleccione *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*. Haga clic en **Aceptar**.  
  
    7.  En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *InsertResponse*y, a continuación, haga clic en **Aceptar**.  
  
    8.  Observará que el esquema para el mensaje de respuesta que se ajuste a las basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] contiene más *InsertResult* elemento. Debe quitar de los esquemas y la asignación del *InsertResponse* elemento en los esquemas de ambos.  
  
         Para ello, desde la **cuadro de herramientas**, arrastre el **recorte izquierdo de cadena** functoid y colóquela en la cuadrícula del asignador. Conectar el **InsertResponse** elemento en el esquema de origen hasta el functoid. De forma similar, conecte el **InsertResponse** elemento en el esquema de destino hasta el functoid. La ilustración siguiente muestra cómo se asignan los dos elementos mediante el functoid.  
  
         ![Asignar la respuesta recibida de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/7fe18f5b-100f-4fe2-ac92-c111629d7fe9.gif "7fe18f5b-100f-4fe2-ac92-c111629d7fe9")  
  
        > [!NOTE]
        >  Para obtener más información, consulte el **Functoid de recorte izquierdo de cadena** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)].
  
    9. Guarde el mapa.  
  
5.  Guarde y compile la solución de BizTalk. Haga clic en la solución y, a continuación, haga clic en **generar solución**.  
  
6.  Implementar la solución. Haga clic en la solución y, a continuación, haga clic en **implementar solución**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear un puerto de envío WCF-custom y configúrelo para utilizar las asignaciones creadas en este paso, como se describe en [paso 2: configurar la orquestación en la consola de administración de Biztalk Server con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Migrar proyectos de BizTalk](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)