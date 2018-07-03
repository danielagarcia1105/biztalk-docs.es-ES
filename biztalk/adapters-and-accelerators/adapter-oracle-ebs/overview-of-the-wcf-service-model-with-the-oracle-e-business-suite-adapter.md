---
title: Información general sobre el modelo de servicio WCF con el adaptador de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aeeac8a4-a4bc-4963-951c-0c806e232f1e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a591c06b89464f640ea4992b927a68a62e69307
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994629"
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter"></a>Información general sobre el modelo de servicio WCF con el adaptador de Oracle E-Business Suite
La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone un sistema Oracle E-Business Suite como un servicio WCF. Para llevar a cabo operaciones en los artefactos de Oracle E-Business Suite, por ejemplo, para invocar un procedimiento almacenado, invoca una operación en el adaptador, que, a su vez, realiza la operación en Oracle E-Business Suite. El código actúa como un cliente al servicio de WCF presentado por el adaptador.  
  
 En el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el contrato de servicio que existe entre un cliente y un servicio se representa como una interfaz de .NET y las operaciones se representan como métodos en esta interfaz. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] y WCF proporcionan herramientas que permiten generar esta interfaz para las operaciones de destino de los metadatos que expone el adaptador. Estas herramientas también crean una clase de cliente WCF que puede usarse para invocar las operaciones expuestas en la interfaz de servicio. Una aplicación cliente puede llamar a los métodos de la clase de cliente WCF para invocar operaciones en el adaptador.  
  
 La siguiente sección explica cómo usar el modelo de servicio WCF para invocar operaciones con un cliente de WCF.  
  
## <a name="invoking-operations-on-the-oracle-e-business-suite-with-a-wcf-client"></a>Invocar operaciones en Oracle E-Business Suite con un cliente de WCF  
 Para usar el modelo de servicio WCF para invocar operaciones en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], primero debe generar una clase de cliente WCF para las operaciones de destino. A continuación, puede crear una instancia de esta clase, un cliente de WCF y llamar a sus métodos para llevar a cabo estas operaciones en Oracle E-Business Suite.  
  
#### <a name="to-invoke-operations-on-the-oracle-e-business-adapter"></a>Para invocar operaciones en el adaptador de Oracle E-Business  
  
1. Generar un código de clase y la aplicación auxiliar de cliente WCF. Use el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutil.exe) para generar una clase de cliente WCF dirigida a los artefactos de Oracle E-Business Suite con la que desea trabajar. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
2. Crear una instancia de cliente WCF y configurar al cliente de WCF. Configurar al cliente de WCF implica especificar el enlace y dirección de punto de conexión (conexión de URI) que utilizará el cliente. Puede hacerlo imperativamente en código o mediante declaración en configuración. El código siguiente crea un cliente WCF que tiene como destino el **interfaz cliente** programa simultáneo en la **cuentas por cobrar** aplicación en Oracle E-Business Suite. También establece las credenciales para Oracle E-Business Suite. El cliente de WCF se inicializa a partir de la configuración.  
  
   ```  
   ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR"); //picking the binding and address from app.config  
  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
   > [!NOTE]
   >  Puede especificar la dirección de enlace y el punto de conexión de cliente en el código o declárelo en el archivo de configuración app.config. El fragmento de código anterior usa el último. Para obtener más información sobre cómo usar ambos enfoques, consulte [configurar un enlace de cliente de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).  
  
3. Abra al cliente de WCF.  
  
   ```  
   client.Open();  
   ```  
  
4. Invocar métodos en el cliente de WCF que creó en el paso 2 para realizar operaciones en Oracle E-Business Suite. El código siguiente invoca el **interfaz cliente** programa simultáneo en la **cuentas por cobrar** aplicación en Oracle E-Business Suite.  
  
   ```  
   string Result = client.RACUST(null, null, null, description, null, recipro_cust, org_id);  
   ```  
  
    **RACUST** es el nombre real del programa interfaz de cliente simultáneo. **Interfaz cliente** es el nombre descriptivo del programa simultáneo.  
  
5. Cierre al cliente WCF.  
  
   ```  
   client.Close();  
   ```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)