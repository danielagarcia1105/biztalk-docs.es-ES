---
title: "Información general sobre el modelo de servicio WCF con el adaptador de Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, invoke operations on the Siebel system with a WCF client
- WCF service model, overview of
ms.assetid: 0e812473-0f50-4972-8b07-ec8edc2ef000
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c638255b103a9c588f22d6ddcb2a75b81619b73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-siebel-adapter"></a>Información general sobre el modelo de servicio WCF con el adaptador de Siebel
La [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] expone un sistema Siebel como un servicio WCF. Para llevar a cabo operaciones en los artefactos del sistema Siebel, por ejemplo, para invocar un método de un servicio de negocios de Siebel, se invoca una operación en el adaptador, que a su vez, realiza la operación en el sistema Siebel. Por lo tanto, el código actúa como un cliente al servicio de WCF presentado por el adaptador.  
  
 En el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el contrato de servicio que existe entre un cliente y un servicio se representa como una interfaz de .NET y las operaciones se representan como métodos en esta interfaz. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y WCF ofrecen herramientas que permiten generar esta interfaz para las operaciones de destino de los metadatos que expone el adaptador. Estas herramientas también crean una clase de cliente WCF que puede usarse para invocar las operaciones que se exponen en la interfaz de servicio. Una aplicación cliente puede llamar a los métodos de la clase de cliente WCF para invocar operaciones en el adaptador.  
  
 En la siguiente sección se explica cómo utilizar el modelo de servicio WCF para invocar las operaciones con un cliente de WCF.  
  
## <a name="invoking-operations-on-the-siebel-system-with-a-wcf-client"></a>Invocar operaciones en el sistema Siebel con un cliente de WCF  
 Para usar el modelo de servicio WCF para invocar operaciones en el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], debe generar primero una clase de cliente WCF para las operaciones de destino. A continuación, puede crear una instancia de esta clase, un cliente de WCF y llamar a sus métodos para realizar estas operaciones en el sistema Siebel.  
  
#### <a name="to-invoke-operations-on-the-siebel-adapter"></a>Para invocar operaciones en el adaptador de Siebel  
  
1.  Generar un código de clase y la aplicación auxiliar de cliente WCF. Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos herramienta de utilidad ServiceModel (svcutil.exe) para generar una clase de cliente WCF destinada a los artefactos del sistema Siebel con el que desea trabajar. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para los artefactos de la solución de Siebel](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).  
  
2.  Cree una instancia de cliente WCF y configurar al cliente WCF. Configurar al cliente de WCF implica especificar el enlace y dirección de punto de conexión (conexión URI) que el cliente va a usar. Puede hacerlo imperativamente en código o mediante declaración en configuración. Para obtener más información sobre cómo configurar el cliente de WCF, vea [configurar un cliente de WCF para un sistema Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md). El código siguiente crea a un cliente WCF que tiene como destino el servicio de negocios de Siebel TimeStamp. También establece las credenciales para el sistema Siebel. El cliente de WCF se inicializa desde la configuración.  
  
    ```  
    BusinessServices_TimeStamp_OperationClient client =  
        new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
    client.ClientCredentials.UserName.UserName = "YourUserName";  
    client.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  Abra al cliente de WCF.  
  
    ```  
    client.Open();  
    ```  
  
4.  Invocar métodos en el cliente WCF que creó en el paso 2 para realizar operaciones en el sistema Siebel. El código siguiente, se invoca el **Execute** método del cliente WCF para invocar la **Execute** método del servicio de negocio de marca de tiempo en el sistema Siebel.  
  
    ```  
    // Create a parameter to hold the results and then invoke the Execute method of the TimeStamp business service.  
    microsoft.lobservices.siebel._2007._03.BusinessServices.TimeStamp.ExecuteResponseRecord er;  
    er = client.Execute();  
    ```  
  
5.  Cierre al cliente WCF.  
  
    ```  
    client.Close();  
    ```  
  
 Para obtener más información sobre cómo invocar métodos de servicio de negocio de Siebel, consulte [invocar métodos de servicio empresarial con el adaptador de Siebel mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md) 
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Siebel mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)