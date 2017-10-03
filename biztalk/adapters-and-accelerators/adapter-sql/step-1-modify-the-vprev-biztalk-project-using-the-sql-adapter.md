---
title: 'Paso 1: Modificar el proyecto de BizTalk mediante el adaptador de SQL vPrev | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25ad959b-2818-47b8-9a09-3681abb75887
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f0eb02594251fa5ab1c209c1d2655056cf489df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter"></a>Paso 1: Modificar el proyecto de BizTalk mediante el adaptador de SQL vPrev
![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, realice los siguientes cambios en el proyecto de BizTalk vPrev existente:  
  
-   Generar metadatos para la operación de inserción en la tabla Customer usando basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
-   Asignar el mensaje de solicitud para realizar una operación de inserción con el adaptador de SQL vPrev a un mensaje de solicitud para realizar una operación de inserción mediante basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
-   Asignar el mensaje de respuesta recibido con basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] al mensaje de respuesta recibido con el adaptador de SQL vPrev.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe tener un proyecto de BizTalk vPrev para realizar una operación de inserción en la tabla de clientes en la base de datos de SQL Server.  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>Para modificar el proyecto de BizTalk vPrev  
  
1.  Generar metadatos para la operación de inserción en la tabla Customer usando basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Puede usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar los metadatos.  
  
     Para obtener instrucciones sobre cómo generar los metadatos, consulte [obtener metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md). Una vez generado el esquema, un archivo con el nombre similar al *TableOperation.dbo.Customer.xsd* se agrega al proyecto de BizTalk. Este archivo contiene el esquema para enviar un mensaje para realizar una operación de inserción en la tabla de clientes en la base de datos de SQL Server mediante basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
2.  Generar los metadatos de la operación de inserción, también crea un archivo de enlace de puerto. En el paso siguiente, este archivo de enlace se utilizará para crear un puerto de envío WCF-Custom para enviar mensajes a la base de datos de SQL Server. La acción SOAP para la operación también se establece en la operación para el que generar metadatos. Por ejemplo, si genera metadatos para la operación de inserción, el nombre de la operación en la acción de SOAP en el puerto de envío será "Insertar". Sin embargo, la operación de nombre en el puerto de envío lógico que se crea como parte de la orquestación podría ser diferente, por ejemplo, "Operation_1". Como resultado, al enviar mensajes a la base de datos de SQL Server mediante el puerto de envío, obtendrá un error. Para evitar esto, asegúrese de que el nombre de la operación en la operación lógica puerto en la orquestación es el mismo que el nombre de la operación para el que generar metadatos de envío.  
  
     Por lo tanto, en el caso de este tutorial, dado que generar metadatos para la operación de inserción, cambiar el nombre de la operación de puerto de envío lógico para "Insertar".  
  
3.  Para el mensaje de solicitud, asignar el esquema generado mediante vPrev adaptador de base de datos SQL para el esquema generado mediante basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
    1.  Agregue a un asignador de BizTalk al proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
         En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **RequestMap.btm**. Haga clic en **Agregar**.  
  
    2.  En el panel de esquema de origen, haga clic en **Abrir esquema de origen**.  
  
    3.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y, a continuación, seleccione el esquema del mensaje de solicitud para el adaptador SQL vPrev. Para este tutorial, seleccione *New_Migration.InsertCustomerService*y, a continuación, haga clic en **Aceptar**.  
  
    4.  En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *insertar*y, a continuación, haga clic en **Aceptar**.  
  
    5.  En el panel de esquema de destino, haga clic en **Abrir esquema de destino**.  
  
    6.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y, a continuación, seleccione el esquema del mensaje de solicitud para basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para este tutorial, seleccione *New_Migration.TableOperation.dbo.Customer*y, a continuación, haga clic en **Aceptar**.  
  
    7.  En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *insertar*y, a continuación, haga clic en **Aceptar**.  
  
    8.  Asignar los elementos correspondientes en los esquemas de ambos tal y como se muestra en la ilustración siguiente.  
  
         ![Asignar los esquemas de solicitud](../../adapters-and-accelerators/adapter-sql/media/850bbf52-fc3e-42c5-b879-51c6e39a502d.gif "850bbf52-fc3e-42c5-b879-51c6e39a502d")  
  
    9. Guarde el mapa.  
  
4.  El mensaje de respuesta, asignar el esquema generado mediante vPrev adaptador de SQL para el esquema generado mediante basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
    1.  Agregue a un asignador de BizTalk al proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y haga clic en **nuevo elemento**.  
  
         En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **ResponseMap.btm**y, a continuación, haga clic en **agregar**.  
  
    2.  En el panel de esquema de origen, haga clic en **Abrir esquema de origen**.  
  
    3.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y, a continuación, seleccione el esquema para el mensaje de respuesta para basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para este tutorial, seleccione *New_Migration.TableOperation.dbo.Customer*y, a continuación, haga clic en **Aceptar**.  
  
    4.  En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *InsertResponse*y, a continuación, haga clic en **Aceptar**.  
  
    5.  En el panel de esquema de destino, haga clic en **Abrir esquema de destino**.  
  
    6.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y, a continuación, seleccione el esquema para el mensaje de respuesta para la vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para este tutorial, seleccione *New_Migration.InsertCustomerService*y, a continuación, haga clic en **Aceptar**.  
  
    7.  En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *InsertResponse*y, a continuación, haga clic en **Aceptar**.  
  
    8.  Observará algunas diferencias entre los esquemas de respuesta para generados por los dos adaptadores. Estas diferencias pueden explicarse como sigue:  
  
        -   Usar basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], si inserta un registro en una tabla que contiene una clave principal (y también es un campo de identidad) en la respuesta para la inserción de una operación devuelve el valor del campo de identidad para la fila insertada. Por lo tanto, el esquema para el mensaje de respuesta que se ajuste a las basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] contiene más *InsertResult* elemento. Este elemento contiene una matriz, que a su vez contiene los campos de identidad para las filas insertadas.  
  
        -   Mediante el vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], si se inserta un registro en una tabla, el adaptador devuelve solo un elemento vacío de "Correcto" como parte del mensaje de respuesta.  
  
         Por lo tanto, los esquemas se asignan de tal manera que la respuesta basada en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] que contiene el valor de los campos de identidad es "Copiar" como parte del elemento "Correcto", que forma parte del mensaje de respuesta de la vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Puede usar el functoid de copia masiva para copiar los elementos de un esquema a otro.  
  
         Para utilizar el functoid de copia masiva, de la **cuadro de herramientas**, arrastre el functoid de copia masiva y colóquela en la cuadrícula del asignador. Conectar el **InsertResult** elemento en el esquema de origen hasta el functoid. De forma similar, conecte el **correcto** elemento en el esquema de destino hasta el functoid. La ilustración siguiente muestra cómo se asignan los dos elementos mediante el functoid.  
  
         ![Asignar los esquemas de respuesta](../../adapters-and-accelerators/adapter-sql/media/c4a347ae-8d2d-4357-b18d-37f36bef17c7.gif "c4a347ae-8d2d-4357-b18d-37f36bef17c7")  
  
        > [!NOTE]
        >  Para obtener más información sobre el functoid de copia masiva, vea [http://go.microsoft.com/fwlink/?LinkId=119749](http://go.microsoft.com/fwlink/?LinkId=119749).  
  
    9. Guarde el mapa.  
  
5.  Guarde y compile la solución de BizTalk. Haga clic en la solución y, a continuación, haga clic en **generar solución**.  
  
6.  Implementar la solución. Haga clic en la solución y, a continuación, haga clic en **implementar solución**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear un puerto de envío WCF-custom y configúrelo para utilizar las asignaciones creadas en este paso, como se describe en [paso 2: configurar la orquestación en la consola de administración de BizTalk Server con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Migrar proyectos de BizTalk para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)