---
title: Compatibilidad con la administración de cola | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60d06ba-8cf3-46d6-af59-626f12fc572a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faeb3f141e114cf1f86157084f50d0a0d490833a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278700"
---
# <a name="support-for-queue-management"></a>Compatibilidad de la administración de cola
Con el adaptador de MQSeries de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede crear y eliminar colas de forma remota en el administrador de cola MQSeries. Esto se admite porque [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza un objeto MQSAgent COM+ remoto que se comunica de forma directa con el administrador de cola MQSeries. Como norma general, MQSAgent se utiliza en tiempo de ejecución para leer mensajes en las colas remotas de MQSeries Server o bien, escribirlos allí. Más de un servidor BizTalk Server puede ser cliente de este servicio remoto. Además, MQSAgent proporciona las funciones de creación y eliminación de colas y es posible llamar de forma directa desde una orquestación o adaptador. Esto se permite en escenarios muy dinámicos a través de los cuales la orquestación o el adaptador pueden crear una cola temporal y enviar, a continuación, un mensaje mediante ella, recibir una respuesta en otra cola y, por último, eliminar la cola temporal.  
  
## <a name="createqueue-and-deletequeue-apis"></a>API CreateQueue y DeleteQueue  
 Las API CreateQueue y DeleteQueue se definen de la siguiente forma.  
  
### <a name="structure-definition"></a>Definición de estructura  
  
```  
typedef enum QueueUsage {  
      Normal       = 0,  
      Transmission = 1  
} QueueUsage;  
  
typedef enum ResultCode {  
      QueueAlreadyExists                     = 0, //  no bits set  
      QueueCreated                           = 1, //  QueueCreated  
      QueueCreatedAndRemoteDefinitionUpdated = 5, //  QueueCreated | RemoteDefinitionUpdated  
      QueueAndRemoteDefinitionCreated        = 7, //  QueueCreated | RemoteDefinitionCreated | RemoteDefinitionUpdated  
      QueueDoesNotExist                      = 8, //  QueueDoesNotExist  
      QueueDeleted                           = 16 //  QueueDeleted  
} ResultCode;  
```  
  
### <a name="interface-definition"></a>Definición de interfaz  
  
```  
[  
            object,  
            uuid(E90AC1A6-657B-4680-AF6A-89F11113FB8B),  
            dual,  
            nonextensible,  
            helpstring("IMQSAdmin Interface"),  
            pointer_default(unique)  
]  
interface IMQSAdmin2 : IDispatch{  
  
HRESULT CreateQueue (  
[in]BSTR queueManager,  
[in]BSTR newQueueName,  
[in]QueueUsage usage,  
[in]BSTR remoteDefinition,  
[in]BSTR remoteQName,  
[in]BSTR remoteQMgrName,  
[in]BOOL updateExistingRemoteDefinition,  
[out, retval]ResultCode* resultCode);  
  
HRESULT DeleteQueue (  
[in]BSTR queueManager,  
[in]BSTR newQueueName,  
[out, retval]ResultCode* resultCode);  
};  
  
      [  
            uuid(412AF00D-7CA8-4d2a-AFF6-F61CE2E29A0D),  
            helpstring("MQSAdmin Class")  
      ]  
      coclass MQSAdmin  
      {  
            [default] interface IMQSAdmin2;  
      };  
  
```  
  
## <a name="examples"></a>Ejemplos  
 Siga los pasos del ejemplo 1 para crear una aplicación de consola de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] C# que pueda usarse para crear o eliminar colas de servidor MQSeries.  
  
### <a name="example-1"></a>Ejemplo 1  
  
##### <a name="create-a-c-console-application-to-manage-mqseries-server-queues"></a>Crear una aplicación de consola de C# para administrar colas de servidor MQSeries  
  
1.  Crear una nueva aplicación Visual C# consola en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] con el nombre **MQSeriesQueues**.  
  
2.  Reemplace el código existente del archivo Program.cs que se genera con el código siguiente:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using MQSAgentLib;  
  
    namespace MQSeriesQueues  
    {  
        class ManageQueues  
        {  
            public static void Main(string[] args)  
            {  
                // The first argument should be "c" (without quotes)  
                // to create a queue, anything else to delete a queue.  
                // The 2nd and 3rd arguments should be the name of   
                // the MQSeries Queue Manager and the name of   
                // the queue to be created or deleted for example  
                // the following usage will create the local   
                // queue testq for the Queue Manager QM_Test  
                // MQSeriesQueues c QM_Test testq  
                createordeleteQs(args[0], args[1], args[2]);  
            }  
  
            static void createordeleteQs(string Qswitch, string QMgr, string QName)  
            {   
            if ((Qswitch =="c" & (QMgr != null & QName != null)))  
                {  
                    CreateQueue(QMgr, QName);  
                }  
                else if(QMgr != null & QName != null)  
                {  
                    DeleteQueue(QMgr, QName);  
                }  
             }  
  
            static void CreateQueue(string Qmgr, string Qname)  
            {  
                MQSAdmin admin = new MQSAdmin();    
  
                ResultCode resultCode = admin.CreateQueue(Qmgr, Qname, 0, "", "", "", 0);  
  
                if ((resultCode & ResultCode.QueueCreated) == ResultCode.QueueCreated)  
                {  
                    Console.WriteLine("Queue Created.");  
                }  
                else if ((resultCode & ResultCode.QueueAlreadyExists) == ResultCode.QueueAlreadyExists)  
                {  
                    Console.WriteLine("Queue Already Exists.");  
                }  
            }  
  
            static void DeleteQueue(string Qmgr, string Qname)  
            {  
                MQSAdmin admin = new MQSAdmin();  
  
                ResultCode resultCode = admin.DeleteQueue(Qmgr, Qname);  
  
                if ((resultCode & ResultCode.QueueDeleted) == ResultCode.QueueDeleted)  
                {  
                    Console.WriteLine("Queue successfully deleted.");  
                }  
                if ((resultCode & ResultCode.QueueDoesNotExist) == ResultCode.QueueDoesNotExist)  
                {  
                    Console.WriteLine("Queue did not exist anyway!");  
                }  
            }  
  
        }  
    }  
    ```  
  
3.  Agregue una referencia a este proyecto para el **MQSAgent 1.0 Type Library**. El **MQSAgent 1.0 Type Library** está disponible en la **COM** pestaña de la **Agregar referencia** cuadro de diálogo.  
  
    > [!NOTE]
    >  El componente MQSAgent COM+ debe estar instalado en el equipo en el que está ejecutando esta aplicación de consola. Para obtener más información acerca de cómo instalar el componente MQSAgent COM + vea [mediante el Asistente de configuración de MQSAgent COM +](../core/using-the-mqsagent-com-configuration-wizard.md).  
  
4.  Genere la aplicación de consola.  
  
5.  Abra un símbolo del sistema en el mismo directorio en el que se encuentra la aplicación de consola compilada.  
  
6.  Escriba el nombre de la aplicación de consola compilada con los argumentos adecuados y presione ENTRAR. Por ejemplo, para eliminar la cola **testq** en el Administrador de cola **QM_Test** , debería escribir el texto siguiente en el símbolo del sistema y presione ENTRAR:  
  
    ```  
    MQSeriesQueues d QM_Test testq  
    ```  
  
7.  Para crear la cola **testq** en el Administrador de cola **QM_Test** , debería escribir el texto siguiente en el símbolo del sistema y presione ENTRAR:  
  
    ```  
    MQSeriesQueues c QM_Test testq  
    ```