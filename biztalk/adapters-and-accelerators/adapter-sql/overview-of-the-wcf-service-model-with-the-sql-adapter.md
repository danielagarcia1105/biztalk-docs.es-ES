---
title: Información general sobre el modelo de servicio WCF con el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7641bcc7-3845-4914-9b1b-cb86b998ea6d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 121b425abe1c7c34ba75e535799770031b931525
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997333"
---
# <a name="overview-of-the-wcf-service-model-with-the-sql-adapter"></a>Información general sobre el modelo de servicio WCF con el adaptador de SQL
La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone una operación de SQL Server como un servicio WCF. Para llevar a cabo operaciones en los artefactos de SQL Server, por ejemplo, para invocar un procedimiento almacenado, invoca una operación en el adaptador, que, a su vez, realiza la operación en el servidor SQL Server. Por lo tanto, el código actúa como un cliente al servicio de WCF presentado por el adaptador.  
  
 En el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el contrato de servicio que existe entre un cliente y un servicio se representa como una interfaz de .NET y las operaciones se representan como métodos en esta interfaz. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y WCF proporcionan herramientas que permiten generar esta interfaz para las operaciones de destino de los metadatos que expone el adaptador. Estas herramientas también crean una clase de cliente WCF que puede usarse para invocar las operaciones expuestas en la interfaz de servicio. Una aplicación cliente puede llamar a los métodos de la clase de cliente WCF para invocar operaciones en el adaptador. Para implementar un servicio para recibir operaciones de entrada desde el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], implemente la interfaz generada para las operaciones de entrada.  
  
 La siguiente sección explica cómo usar el modelo de servicio WCF para invocar operaciones con un cliente de WCF.  
  
## <a name="invoking-operations-on-the-sql-server-with-a-wcf-client"></a>Invocar operaciones en el servidor SQL Server con un cliente de WCF  
 Para usar el modelo de servicio WCF para invocar operaciones en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], primero debe generar una clase de cliente WCF para las operaciones de destino. A continuación, puede crear una instancia de esta clase, un cliente de WCF y llamar a sus métodos para llevar a cabo estas operaciones en el sistema de SQL Server. Esta sección proporciona un esquema de una aplicación de cliente de .NET adaptador típica aspecto. Una explicación detallada sobre cómo realizar distintas operaciones en la base de datos de SQL Server mediante el adaptador se proporciona en temas específicos.  
  
#### <a name="to-invoke-operations-on-the-sql-adapter"></a>Para invocar operaciones en el adaptador de SQL  
  
1. Generar un código de clase y la aplicación auxiliar de cliente WCF. Use el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]generar una clase de cliente WCF dirigido a los artefactos de la base de datos de SQL Server con la que desea trabajar. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
2. Crear una instancia de cliente WCF y configurar al cliente de WCF. Configurar al cliente de WCF implica especificar el enlace y dirección de punto de conexión (conexión de URI) que utilizará el cliente. Puede hacerlo imperativamente en código o mediante declaración en configuración. El código siguiente crea un cliente WCF que tiene como destino el **seleccione** operación en el **empleado** tabla en una base de datos de SQL Server. También establece las credenciales de la base de datos de SQL Server. El cliente de WCF se inicializa a partir de la configuración.  
  
   ```  
   TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee"); //picking the binding and address from the app.config  
  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
   > [!NOTE]
   >  Puede especificar la dirección de enlace y el punto de conexión de cliente en el código o declárelo en el archivo de configuración app.config. El fragmento de código anterior usa el último. Para obtener más información sobre cómo usar ambos enfoques, consulte [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).  
  
3. Abra al cliente de WCF.  
  
   ```  
   client.Open();  
   ```  
  
4. Invocar métodos en el cliente de WCF que creó en el paso anterior para realizar una operación Select en la base de datos SQL server. El código siguiente invoca el método Select del cliente WCF para invocar la instrucción SELECT en una tabla de base de datos de SQL Server.  
  
   ```  
   client.Select("*", "where [Name] = ‘John Smith’");  
   ```  
  
5. Cierre al cliente WCF.  
  
   ```  
   client.Close();  
   ```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SQL con el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)