---
title: 'Paso 1: Modificar el proyecto vPrev de BizTalk en la base de datos de Oracle | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e3e22ac-126b-46ec-a6dc-3421ad721392
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5d55a5535d1f3f2234198d08393a314b1a304e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010573"
---
# <a name="step-1-modify-the-vprev-biztalk-project-in-oracle-database"></a>Paso 1: Modificar el proyecto vPrev de BizTalk en la base de datos de Oracle
![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, realice los siguientes cambios en el proyecto de BizTalk vPrev existente:  
  
- Generar metadatos para la operación de inserción en el SCOTT. Tabla CUSTOMER usando basada en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
- Asignar el mensaje de solicitud para realizar una operación de inserción mediante el adaptador de base de datos de Oracle vPrev para un mensaje de solicitud para realizar una operación de inserción mediante basada en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
- Asignar el mensaje de respuesta recibido con el basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] al mensaje de respuesta para el adaptador de base de datos de Oracle vPrev.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener un proyecto de BizTalk vPrev para realizar una operación de inserción en el SCOTT. Tabla de clientes en la base de datos de Oracle.  
  
## <a name="modify-the-vprev-biztalk-project"></a>Modificar el proyecto vPrev de BizTalk  
  
1. Generar metadatos para la operación de inserción en el SCOTT. Tabla CUSTOMER usando basada en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Puede usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar los metadatos.  
  
    Para obtener instrucciones sobre cómo generar los metadatos, vea [obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md). Una vez generado el esquema, un archivo con el nombre similar a *OracleDBBindingSchema.xsd* se agrega al proyecto de BizTalk. Este archivo contiene el esquema para enviar un mensaje para realizar una operación de inserción en el SCOTT. Tabla CUSTOMER de la base de datos de Oracle con el basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
2. Generar los metadatos de la operación de inserción, también crea un archivo de enlace de puerto. En el paso siguiente, se usará este archivo de enlace para crear un puerto de envío WCF-Custom para enviar mensajes a la base de datos de Oracle. También se establece la acción SOAP para la operación a la operación para el que genera los metadatos. Por ejemplo, si genera los metadatos de la operación de inserción, el nombre de la operación en la acción de SOAP en el puerto de envío será "Insert". Sin embargo, la operación de nombre en el puerto de envío lógico que cree como parte de la orquestación podría ser diferente, por ejemplo, "Operation_1". Como resultado, al enviar mensajes a la base de datos de Oracle mediante el puerto de envío, obtendrá un error. Para evitarlo, asegúrese de que el nombre de la operación en la operación lógica puerto de envío en la orquestación está el mismo que el nombre de la operación para el que genera los metadatos.  
  
    Por lo tanto, en el caso de este tutorial, dado que generan los metadatos de la operación de inserción, cambie el nombre de la operación de puerto de envío lógico para "Insert".  
  
3. Para el mensaje de solicitud, asignar el esquema generado con el adaptador de base de datos de Oracle vPrev para el esquema generado con el basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
   1. Agregue a un asignador de BizTalk para el proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y haga clic en **nuevo elemento**.  
  
       En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **RequestMap.btm**. Haga clic en **Agregar**.  
  
   2. En el panel Esquema de origen, haga clic en **Abrir esquema de origen**.  
  
   3. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema del mensaje de solicitud para el adaptador de base de datos de Oracle vPrev. Para este tutorial, seleccione *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*. Haga clic en **Aceptar**.  
  
   4. En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *insertar* y haga clic en **Aceptar**.  
  
   5. En el panel Esquema de destino, haga clic en **Abrir esquema de destino**.  
  
   6. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema del mensaje de solicitud basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para este tutorial, seleccione *Oracle_Migration.OracleDBBindingSchema*. Haga clic en **Aceptar**.  
  
   7. En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *insertar* y haga clic en **Aceptar**.  
  
   8. Asignar los elementos correspondientes en los esquemas como se muestra en la ilustración siguiente.  
  
       ![Asignar la solicitud enviada a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/4cb59338-40d1-4eb1-bd89-b5a3183959e1.gif "4cb59338-40d1-4eb1-bd89-b5a3183959e1")  
  
   9. Guarde el mapa.  
  
4. Para el mensaje de respuesta, asignar el esquema generado con el adaptador de base de datos de Oracle vPrev para el esquema generado con el basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
   1. Agregue a un asignador de BizTalk para el proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y haga clic en **nuevo elemento**.  
  
       En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **ResponseMap.btm**. Haga clic en **Agregar**.  
  
   2. En el panel Esquema de origen, haga clic en **Abrir esquema de origen**.  
  
   3. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para el mensaje de respuesta basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para este tutorial, seleccione *Oracle_Migration.OracleDBBindingSchema*. Haga clic en **Aceptar**.  
  
   4. En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *InsertResponse* y haga clic en **Aceptar**.  
  
   5. En el panel Esquema de destino, haga clic en **Abrir esquema de destino**.  
  
   6. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para el mensaje de respuesta para el adaptador de base de datos de Oracle vPrev. Para este tutorial, seleccione *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*. Haga clic en **Aceptar**.  
  
   7. En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *InsertResponse*y, a continuación, haga clic en **Aceptar**.  
  
   8. Observará que el esquema para el mensaje de respuesta que se ajuste a la basada en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] contiene más *InsertResult* elemento. Debe quitar esto desde el esquema y se asignan los *InsertResponse* elemento en los esquemas.  
  
       Para ello, en el **cuadro de herramientas**, arrastre el **recorte izquierdo de cadena** functoid y colóquela en la cuadrícula del asignador. Conectar el **InsertResponse** elemento del esquema de origen hasta el functoid. De forma similar, conecte el **InsertResponse** elemento del esquema de destino hasta el functoid. La ilustración siguiente muestra cómo se asignan los dos elementos mediante el functoid.  
  
       ![Asignar la respuesta recibida de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/7fe18f5b-100f-4fe2-ac92-c111629d7fe9.gif "7fe18f5b-100f-4fe2-ac92-c111629d7fe9")  
  
      > [!NOTE]
      >  Para obtener más información, consulte el **Functoid de recorte izquierdo de cadena** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)].
  
   9. Guarde el mapa.  
  
5. Guarde y compile la solución de BizTalk. Haga clic en la solución y, a continuación, haga clic en **compilar solución**.  
  
6. Implementar la solución. Haga clic en la solución y, a continuación, haga clic en **implementar solución**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear un puerto de envío WCF-custom y configurarlo para usar las asignaciones que creó en este paso, como se describe en [paso 2: configurar la orquestación en la consola de administración de Biztalk Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Migración de proyectos de BizTalk](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)