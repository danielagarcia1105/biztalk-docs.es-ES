---
title: "Información general sobre el modelo de servicio WCF con el adaptador de la base de datos de Oracle | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, overview
- invoking operations
- WCF service, creating and implementing
ms.assetid: 8ed765e5-b5e6-46bd-bcd6-282219caf75d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 100bacfeaf2e06d7ff491ec77f88e00980a96fa1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-database-adapter"></a>Información general sobre el modelo de servicio WCF con el adaptador de la base de datos de Oracle
Cuando se usan operaciones que el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] superficies, el código actúa como un cliente o un servicio para el adaptador. Para casi todas las operaciones que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies, el código es el cliente. Es decir, la aplicación invoca la operación en el adaptador; Por ejemplo insertar registros en una tabla de Oracle. La operación sola para los que el código actúa como un servicio en la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es para la operación de POLLINGSMT. En este caso, el adaptador envía los resultados de la operación de consulta de sondeo para la aplicación.  
  
 En el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el contrato de servicio que existe entre un cliente y un servicio se representa como una interfaz de .NET y las operaciones se representan como métodos en esta interfaz. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] y WCF ofrecen herramientas que permiten generar esta interfaz para las operaciones de destino de los metadatos que expone el adaptador. Estas herramientas también crean una clase de cliente WCF que puede usarse para invocar las operaciones que se exponen en la interfaz de servicio. Una aplicación cliente puede llamar a los métodos de la clase de cliente WCF para invocar operaciones en el adaptador. Para implementar un servicio para recibir la operación de POLLINGSTMT desde el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], implemente la interfaz generada para la operación de POLLINGSTMT.  
  
 Las siguientes secciones explican cómo utilizar el modelo de servicio WCF para crear código de cliente y el servicio para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
## <a name="creating-and-invoking-operations-on-a-wcf-client-by-using-the-oracle-database-adapter"></a>Cómo crear e invocar las operaciones en un cliente WCF mediante el adaptador de la base de datos de Oracle  
 Para usar el modelo de servicio WCF para invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], debe generar primero una clase de cliente WCF para las operaciones de destino. A continuación, puede crear una instancia de esta clase, un cliente de WCF y llamar a sus métodos para realizar operaciones en la base de datos de Oracle.  
  
#### <a name="to-invoke-operations-on-the-oracle-database-adapter"></a>Para invocar operaciones en el adaptador de la base de datos de Oracle  
  
1.  Generar un código de clase y la aplicación auxiliar de cliente WCF. Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos herramienta de utilidad ServiceModel (svcutil.exe) para generar una clase de cliente WCF destinada a los artefactos de base de datos de Oracle con el que desea trabajar. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio de WCF para artefactos de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).  
  
2.  Cree una instancia de cliente WCF mediante la especificación de un enlace del cliente. Especificación de un enlace de cliente implica especificar el enlace y la dirección del extremo que se va a usar el cliente de WCF. Puede hacerlo imperativamente en código o mediante declaración en configuración. Para obtener más información sobre cómo especificar un enlace del cliente, consulte [configurar un cliente de enlace de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md). El código siguiente crea a un cliente WCF que puede utilizarse para realizar operaciones de DML (lenguaje) de manipulación de datos en una tabla de base de datos de Oracle (/ SCOTT/ACCOUNTACTIVITY). También establece las credenciales de la base de datos de Oracle. El cliente de WCF se inicializa desde la configuración.  
  
    ```  
    SCOTTTableACCOUNTACTIVITYClient aaTableClient =   
        new SCOTTTableACCOUNTACTIVITYClient("OracleDBBinding_SCOTT.Table.ACCOUNTACTIVITY");  
  
    aaTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
    aaTableClient.ClientCredentials.UserName.Password = "TIGER";  
    ```  
  
3.  Abra al cliente de WCF.  
  
    ```  
    aaTableClient.Open();  
    ```  
  
4.  Invocar métodos en el cliente WCF que creó en el paso 2 para realizar operaciones en la base de datos de Oracle. El código siguiente, se invoca el **seleccione** método del cliente WCF para realizar la siguiente consulta SQL SELECT en la tabla ACCOUNTACTIVITY: `SELECT * FROM ACCOUNTACTIVITY`.  
  
    ```  
    // create a record set parameter to hold the SELECT query result set and invoke the Select operation;  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
    selectRecords = aaTableClient.Select("*", null);  
    ```  
  
5.  Cierre al cliente WCF.  
  
    ```  
    aaTableClient.Close();  
    ```  
  
 Para obtener más información sobre cómo realizar operaciones de DML en tablas y vistas, incluida la operación de selección usada anteriormente, consulte [realizar insertar básico, actualizaciones, eliminaciones y seleccionar operaciones mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md).  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-oracle-database-adapter"></a>Creación e implementación de un servicio WCF mediante el adaptador de la base de datos de Oracle  
 La [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] puede realizar el sondeo en una tabla de base de datos de Oracle o la vista. Esta funcionalidad le permite especificar una consulta SELECT de SQL que el adaptador debe ejecutar periódicamente en la base de datos de Oracle. Los resultados de esta consulta se devuelven a la aplicación a través de una operación especial, la operación de POLLINGSTMT. Para recibir los resultados de la consulta de sondeo, la aplicación debe implementar el servicio de contrato que la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone para que la operación de POLLINGSTMT.  
  
 Para implementar un servicio para recibir la operación POLLINGSTMT, primero debe generar la interfaz de .NET (también denominada el contrato de servicio WCF) que representa el contrato de servicio expuesto por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para la operación de POLLINGSTMT. Para obtener más información acerca de cómo hacerlo, consulte [generar un cliente de WCF o un contrato de servicio de WCF para artefactos de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).  
  
 A continuación, implementar un servicio WCF mediante la implementación de la interfaz generada. Esta clase contiene la lógica de negocios para procesar el mensaje POLLINGSTMT y devolver una respuesta al adaptador. A continuación, usar un host de servicio (**System.ServiceModel.ServiceHost**) para hospedar una instancia de este servicio. Para obtener más información, consulte [mensajes de datos cambiado basados en la recepción de sondeo mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md).  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)