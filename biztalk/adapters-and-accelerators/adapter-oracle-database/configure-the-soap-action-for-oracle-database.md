---
title: Configurar la acción SOAP para la base de datos de Oracle en BizTalk | Microsoft Docs
description: Especifique una acción de SOAP en Visual Studio, o utilizar el adaptador WCF-Custom o WCF-OracleDB en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d21cca-3907-4f99-af76-c1e7286e1bcf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe8b1b2c1043551b692530dcff4b8fdf49a44b54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994677"
---
# <a name="configure-the-soap-action-for-oracle-database"></a>Configurar la acción SOAP para la base de datos de Oracle
Para completar cualquier operación en la base de datos de Oracle con el basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], los usuarios de adaptador deben especificar una acción de SOAP. La acción SOAP comunica al adaptador qué acción debe completarse. Puede especificar la acción de SOAP en tiempo de diseño o en tiempo de ejecución. Sin embargo, si especifica la acción de SOAP tanto en tiempo de diseño y tiempo de ejecución, se reemplaza la acción que escriba en tiempo de diseño.  
  
 Para obtener más información acerca de cómo especificar la acción SOAP, vea [especificar acciones SOAP para adaptadores de envío WCF](../../core/specifying-soap-actions-for-wcf-send-adapters.md).  
  
## <a name="enter-soap-action-from-visual-studio"></a>Especifique la acción SOAP desde Visual Studio  
 Desde Visual Studio, debe especificar la acción SOAP como parte de la orquestación mediante un **expresión** forma.  
  
1.  En la orquestación de BizTalk, incluya una **expresión** forma arrastrándolo desde la **orquestación de BizTalk** cuadro de herramientas.  
  
2.  Haga doble clic en el **expresión** forma para abrir el Editor de expresiones de BizTalk.  
  
3.  Especifica la acción en el Editor de expresiones de BizTalk. Por ejemplo:  
  
    ```
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
    ```  
  
     Para obtener más información acerca de **expresión** forma y el Editor de expresiones de BizTalk, consulte [cómo crear expresiones](../../core/how-to-create-expressions.md).  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a>Especifique la acción SOAP de administración de BizTalk Server  
 Desde la consola de administración de BizTalk Server, debe especificar la acción SOAP como parte de la configuración del puerto WCF-Custom o WCF-OracleDB. 

#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>Especifique una acción de SOAP para el puerto de WCF-Custom  
 
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
3. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
4. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.  
  
5. En el **acción** texto, especifique la acción SOAP para la operación. Puede especificar la acción de las maneras siguientes:  
  
   -   **Con el formato de acción única**. Utilice este formato si el WCF-Custom puerto envía y recibe mensajes de una sola operación. Por ejemplo:  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   **Con el formato de asignación de acción**. Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación. Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para insertar registros en la tabla EMP) y Op2 (para actualizar registros en la tabla EMP), se puede especificar la acción SOAP de la siguiente manera:  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        Este enfoque proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluir a través del mismo puerto.  
  
        El formato de la acción SOAP es diferente para cada operación. Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).  
  
#### <a name="enter-a-soap-action-for-the-wcf-oracledb-port"></a>Especifique una acción de SOAP para el puerto de WCF-OracleDB  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Agregar el adaptador de WCF-OracleDB a la consola de administración de BizTalk Server. Para obtener instrucciones, consulte [agregación del adaptador de base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).  
  
3. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
4. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el puerto de WCF-OracleDB que agregó anteriormente y, a continuación, haga clic en **configurar**.  
  
5. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.  
  
6. En el **acción** texto, especifique la acción SOAP para la operación. Puede especificar la acción de las maneras siguientes:  
  
   -   **Con el formato de acción única**. Utilice este formato si el WCF-OracleDB puerto envía y recibe mensajes de una sola operación. Por ejemplo:  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   **Con el formato de asignación de acción**. Utilice este formato si un único puerto de WCF-OracleDB envía y recibe mensajes de más de una operación. Por ejemplo, si un único puerto de WCF-OracleDB envía y recibe los mensajes de Op1 (para insertar registros en la tabla EMP) y Op2 (para actualizar registros en la tabla EMP), se puede especificar la acción SOAP de la siguiente manera:  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        Este enfoque proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluir a través del mismo puerto.  
  
        El formato de la acción SOAP es diferente para cada operación. Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)