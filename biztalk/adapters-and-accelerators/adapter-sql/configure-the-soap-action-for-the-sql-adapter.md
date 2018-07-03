---
title: Configurar la acción SOAP para el adaptador de SQL en BizTalk | Microsoft Docs
description: Especifique una acción de SOAP en Visual Studio, o utilizar el adaptador WCF-Custom o WCF-SQL en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acd7f60b-c27f-4988-a67c-e56ef8d38f66
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a927740ba04a0fd1b080e73ef60892ffdc9bf385
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980525"
---
# <a name="configure-the-soap-action-for-the-sql-adapter"></a>Configurar la acción SOAP para el adaptador de SQL
Para realizar cualquier operación en SQL Server con el basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], debe especificar una acción de SOAP. La acción SOAP comunica al adaptador qué acción debe realizarse. Puede especificar la acción SOAP desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Sin embargo, si especifica la acción de SOAP en ambas ubicaciones, la acción que ha especificado desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] serán reemplazadas.  
  
 Para obtener más información acerca de cómo especificar la acción SOAP, vea [especificar acciones SOAP para adaptadores de envío WCF](../../core/specifying-soap-actions-for-wcf-send-adapters.md).
  
## <a name="enter-the-soap-action-in-visual-studio"></a>Especifique la acción SOAP en Visual Studio  
 Desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], debe especificar la acción SOAP como parte de la orquestación mediante un **expresión** forma.  
  
1.  En la orquestación de BizTalk, incluya una **expresión** forma arrastrándolo desde la **orquestación de BizTalk** cuadro de herramientas.  
  
2.  Haga doble clic en el **expresión** forma para abrir el Editor de expresiones de BizTalk.  
  
3.  Especifica la acción en el Editor de expresiones de BizTalk. Por ejemplo:  
  
    ```  
    OutboundMessage(WCF.Action)="TableOp/Insert/dbo/Employee"  
    ```  
  
     Para obtener más información sobre la **expresión** forma y el Editor de expresiones de BizTalk, consulte [cómo crear expresiones](../../core/how-to-create-expressions.md).
  
## <a name="enter-the-soap-action-from-the-biztalk-server-administration-console"></a>Especifique la acción SOAP desde la consola de administración de BizTalk Server  
 Desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, puede especificar la acción SOAP como parte de la configuración del puerto WCF-Custom o WCF-SQL.  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>Especifique una acción de SOAP para el puerto de WCF-Custom  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
3. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
4. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.  
  
5. En el **acción** texto, especifique la acción SOAP para la operación. Puede especificar la acción de las maneras siguientes:  
  
   -   **Con el formato de acción única**. Utilice este formato si el WCF-Custom puerto envía y recibe mensajes de una sola operación. Por ejemplo:  
  
       ```  
       TableOp/Insert/dbo/Employee  
       ```  
  
   -   **Con el formato de asignación de acción**. Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación. Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para insertar registros en la tabla de empleados) y Op2 (para actualizar registros en la tabla de empleados), se puede especificar la acción SOAP de la siguiente manera:  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
         <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
       </BtsActionMapping>  
       ```  
  
        El enfoque de asignación de acción proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluya a través del mismo puerto.  
  
        El formato de la acción SOAP es diferente para cada operación. Para obtener más información sobre el formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).
  
### <a name="enter-a-soap-action-for-the-wcf-sql-port"></a>Especifique una acción de SOAP para el puerto de WCF-SQL  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Agregar el adaptador de WCF-SQL para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregación del adaptador de SQL a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).  
  
3. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
4. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el adaptador de WCF-SQL que agregó anteriormente y, a continuación, haga clic en **configurar**.  
  
5. En el cuadro de diálogo Propiedades de transporte, haga clic en el **General** ficha.  
  
6. En el **acción** texto, especifique la acción SOAP para la operación. Puede especificar la acción de las maneras siguientes:  
  
   -   **Con el formato de acción única**. Utilice este formato si el WCF-SQL puerto envía y recibe mensajes de una sola operación. Por ejemplo:  
  
       ```  
       TableOp/Insert/dbo/Employee  
       ```  
  
   -   **Con el formato de asignación de acción**. Utilice este formato si un único puerto de WCF-SQL envía y recibe mensajes de más de una operación. Por ejemplo, si un único puerto de WCF-SQL envía y recibe los mensajes de Op1 (para insertar registros en la tabla de empleados) y Op2 (para actualizar registros en la tabla de empleados), se puede especificar la acción SOAP de la siguiente manera:  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
         <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
       </BtsActionMapping>  
       ```  
  
        El enfoque de asignación de acción proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluya a través del mismo puerto.  
  
        El formato de la acción SOAP es diferente para cada operación. Para obtener más información sobre el formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)