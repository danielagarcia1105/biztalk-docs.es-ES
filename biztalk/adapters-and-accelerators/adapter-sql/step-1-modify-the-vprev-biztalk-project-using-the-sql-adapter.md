---
title: 'Paso 1: Modificar el proyecto vPrev de BizTalk mediante el adaptador de SQL | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25ad959b-2818-47b8-9a09-3681abb75887
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2161520d1dba4ae070398668c53de2039e66e67d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979413"
---
# <a name="step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter"></a>Paso 1: Modificar el proyecto vPrev de BizTalk mediante el adaptador de SQL
![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, realice los siguientes cambios en el proyecto de BizTalk vPrev existente:  
  
- Generar metadatos para la operación de inserción en la tabla Customer usando basada en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
- Asignar el mensaje de solicitud para realizar una operación de inserción mediante el adaptador de SQL vPrev para un mensaje de solicitud para realizar una operación de inserción mediante basada en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
- Asignar el mensaje de respuesta recibido con el basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] al mensaje de respuesta recibido con el adaptador de SQL vPrev.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe tener un proyecto de BizTalk vPrev para realizar una operación de inserción en la tabla Customer en la base de datos de SQL Server.  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>Para modificar el proyecto vPrev de BizTalk  
  
1. Generar metadatos para la operación de inserción en la tabla Customer usando basada en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Puede usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar los metadatos.  
  
    Para obtener instrucciones sobre cómo generar los metadatos, vea [obtener metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md). Una vez generado el esquema, un archivo con el nombre similar a *TableOperation.dbo.Customer.xsd* se agrega al proyecto de BizTalk. Este archivo contiene el esquema para enviar un mensaje para realizar una operación de inserción en la tabla Customer en la base de datos de SQL Server con el basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
2. Generar los metadatos de la operación de inserción, también crea un archivo de enlace de puerto. En el paso siguiente, se usará este archivo de enlace para crear un puerto de envío WCF-Custom para enviar mensajes a la base de datos de SQL Server. También se establece la acción SOAP para la operación a la operación para el que genera los metadatos. Por ejemplo, si genera los metadatos de la operación de inserción, el nombre de la operación en la acción de SOAP en el puerto de envío será "Insert". Sin embargo, la operación de nombre en el puerto de envío lógico que cree como parte de la orquestación podría ser diferente, por ejemplo, "Operation_1". Como resultado, al enviar mensajes a la base de datos de SQL Server mediante el puerto de envío, obtendrá un error. Para evitarlo, asegúrese de que el nombre de la operación en la operación lógica puerto de envío en la orquestación está el mismo que el nombre de la operación para el que genera los metadatos.  
  
    Por lo tanto, en el caso de este tutorial, dado que generan los metadatos de la operación de inserción, cambie el nombre de la operación de puerto de envío lógico para "Insert".  
  
3. Para el mensaje de solicitud, asignar el esquema generado con el adaptador de base de datos SQL vPrev para el esquema generado con el basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
   1. Agregue a un asignador de BizTalk para el proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
       En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **RequestMap.btm**. Haga clic en **Agregar**.  
  
   2. En el panel Esquema de origen, haga clic en **Abrir esquema de origen**.  
  
   3. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y, a continuación, seleccione el esquema del mensaje de solicitud para el adaptador de SQL vPrev. Para este tutorial, seleccione *New_Migration.InsertCustomerService*y, a continuación, haga clic en **Aceptar**.  
  
   4. En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *insertar*y, a continuación, haga clic en **Aceptar**.  
  
   5. En el panel Esquema de destino, haga clic en **Abrir esquema de destino**.  
  
   6. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y, a continuación, seleccione el esquema del mensaje de solicitud basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para este tutorial, seleccione *New_Migration.TableOperation.dbo.Customer*y, a continuación, haga clic en **Aceptar**.  
  
   7. En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *insertar*y, a continuación, haga clic en **Aceptar**.  
  
   8. Asignar los elementos correspondientes en los esquemas como se muestra en la ilustración siguiente.  
  
       ![Asignar los esquemas de solicitud](../../adapters-and-accelerators/adapter-sql/media/850bbf52-fc3e-42c5-b879-51c6e39a502d.gif "850bbf52-fc3e-42c5-b879-51c6e39a502d")  
  
   9. Guarde el mapa.  
  
4. Para el mensaje de respuesta, asignar el esquema generado con el adaptador de SQL vPrev para el esquema generado con el basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
   1. Agregue a un asignador de BizTalk para el proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y haga clic en **nuevo elemento**.  
  
       En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **ResponseMap.btm**y, a continuación, haga clic en **agregar**.  
  
   2. En el panel Esquema de origen, haga clic en **Abrir esquema de origen**.  
  
   3. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y, a continuación, seleccione el esquema para el mensaje de respuesta basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para este tutorial, seleccione *New_Migration.TableOperation.dbo.Customer*y, a continuación, haga clic en **Aceptar**.  
  
   4. En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *InsertResponse*y, a continuación, haga clic en **Aceptar**.  
  
   5. En el panel Esquema de destino, haga clic en **Abrir esquema de destino**.  
  
   6. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y, a continuación, seleccione el esquema para el mensaje de respuesta para la vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para este tutorial, seleccione *New_Migration.InsertCustomerService*y, a continuación, haga clic en **Aceptar**.  
  
   7. En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *InsertResponse*y, a continuación, haga clic en **Aceptar**.  
  
   8. Observará algunas diferencias entre los esquemas de respuesta para generados por los dos adaptadores. Estas diferencias pueden explicarse como sigue:  
  
      - Con el basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], si inserta un registro en una tabla que contiene una clave principal (y también es un campo de identidad) en la respuesta para la inserción de una operación devuelve el valor del campo de identidad para la fila insertada. Por lo tanto, el esquema para el mensaje de respuesta que se ajuste a la basada en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] contiene más *InsertResult* elemento. Este elemento contiene una matriz, que a su vez contiene los campos de identidad para las filas insertadas.  
  
      - Mediante el vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], si inserta un registro en una tabla, el adaptador devuelve solo un elemento "¡Success" vacío como parte del mensaje de respuesta.  
  
        Por lo tanto, los esquemas se asignan de manera que la respuesta basada en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] que contiene el valor de los campos de identidad es "Copiar" como parte del elemento "Correcto", que forma parte del mensaje de respuesta de la vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Puede usar el functoid de copia masiva para copiar los elementos de un esquema a otro.  
  
        Para usar el functoid de copia masiva, desde el **cuadro de herramientas**, arrastre el functoid de copia masiva y colóquela en la cuadrícula del asignador. Conectar el **InsertResult** elemento del esquema de origen hasta el functoid. Conectarse de forma similar, el **éxito** elemento del esquema de destino hasta el functoid. La ilustración siguiente muestra cómo se asignan los dos elementos mediante el functoid.  
  
        ![Asignar los esquemas de respuesta](../../adapters-and-accelerators/adapter-sql/media/c4a347ae-8d2d-4357-b18d-37f36bef17c7.gif "c4a347ae-8d2d-4357-b18d-37f36bef17c7")  
  
      > [!NOTE]
      >  Para obtener más información sobre el functoid de copia masiva, vea [ http://go.microsoft.com/fwlink/?LinkId=119749 ](http://go.microsoft.com/fwlink/?LinkId=119749).  
  
   9. Guarde el mapa.  
  
5. Guarde y compile la solución de BizTalk. Haga clic en la solución y, a continuación, haga clic en **compilar solución**.  
  
6. Implementar la solución. Haga clic en la solución y, a continuación, haga clic en **implementar solución**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear un puerto de envío WCF-custom y configurarlo para usar las asignaciones que creó en este paso, como se describe en [paso 2: configurar la orquestación en la consola de administración de BizTalk Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Migrar proyectos de BizTalk para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)