---
title: "Información general sobre el modelo de servicio WCF con el adaptador de SQL | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7641bcc7-3845-4914-9b1b-cb86b998ea6d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3afbf1822945f0a47b09a93b3ac3cc2f8ac8653d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-sql-adapter"></a>Información general sobre el modelo de servicio WCF con el adaptador de SQL
La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone una operación de SQL Server como un servicio WCF. Para llevar a cabo operaciones en artefactos de SQL Server, por ejemplo, para invocar un procedimiento almacenado, se invoca una operación en el adaptador, que a su vez, realiza la operación en el servidor SQL Server. Por lo tanto, el código actúa como un cliente al servicio de WCF presentado por el adaptador.  
  
 En el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el contrato de servicio que existe entre un cliente y un servicio se representa como una interfaz de .NET y las operaciones se representan como métodos en esta interfaz. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y WCF ofrecen herramientas que permiten generar esta interfaz para las operaciones de destino de los metadatos que expone el adaptador. Estas herramientas también crean una clase de cliente WCF que puede usarse para invocar las operaciones que se exponen en la interfaz de servicio. Una aplicación cliente puede llamar a los métodos de la clase de cliente WCF para invocar operaciones en el adaptador. Para implementar un servicio para recibir operaciones entrantes desde el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], implemente la interfaz generada para las operaciones de entrada.  
  
 En la siguiente sección se explica cómo utilizar el modelo de servicio WCF para invocar las operaciones con un cliente de WCF.  
  
## <a name="invoking-operations-on-the-sql-server-with-a-wcf-client"></a>Invocar operaciones en el servidor SQL Server con un cliente de WCF  
 Para usar el modelo de servicio WCF para invocar operaciones en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], debe generar primero una clase de cliente WCF para las operaciones de destino. A continuación, puede crear una instancia de esta clase, un cliente de WCF y llamar a sus métodos para realizar estas operaciones en el sistema de SQL Server. En esta sección se proporciona un esquema de una aplicación de cliente de adaptador .NET típica aspecto. Se proporcionan explicaciones detalladas sobre cómo realizar diferentes operaciones en la base de datos de SQL Server mediante el adaptador en temas específicos.  
  
#### <a name="to-invoke-operations-on-the-sql-adapter"></a>Para invocar operaciones en el adaptador de SQL  
  
1.  Generar un código de clase y la aplicación auxiliar de cliente WCF. Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]generar una clase de cliente WCF destinada a los artefactos de base de datos de SQL Server con el que desea trabajar. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
2.  Cree una instancia de cliente WCF y configurar al cliente WCF. Configurar al cliente de WCF implica especificar el enlace y dirección de punto de conexión (conexión URI) que el cliente va a usar. Puede hacerlo imperativamente en código o mediante declaración en configuración. El código siguiente crea un cliente WCF que tiene como destino el **seleccione** operación en el **empleado** tabla en una base de datos de SQL Server. También establece las credenciales de la base de datos de SQL Server. El cliente de WCF se inicializa desde la configuración.  
  
    ```  
    TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee"); //picking the binding and address from the app.config  
  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!NOTE]
    >  Puede especificar la dirección de enlace y el punto de conexión de cliente en el código o declarar en el archivo de configuración app.config. El fragmento de código anterior usa el último. Para obtener más información sobre cómo usar ambos métodos, consulte [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).  
  
3.  Abra al cliente de WCF.  
  
    ```  
    client.Open();  
    ```  
  
4.  Invocar métodos en el cliente WCF que creó en el paso anterior para realizar una operación Select en la base de datos SQL server. El código siguiente, invoca el método de selección del cliente WCF para invocar la instrucción SELECT en una tabla de base de datos de SQL Server.  
  
    ```  
    client.Select("*", "where [Name] = ‘John Smith’");  
    ```  
  
5.  Cierre al cliente WCF.  
  
    ```  
    client.Close();  
    ```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SQL con el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)