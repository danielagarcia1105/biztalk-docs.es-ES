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
# <a name="support-for-queue-management"></a><span data-ttu-id="0a2dc-102">Compatibilidad de la administración de cola</span><span class="sxs-lookup"><span data-stu-id="0a2dc-102">Support for Queue Management</span></span>
<span data-ttu-id="0a2dc-103">Con el adaptador de MQSeries de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede crear y eliminar colas de forma remota en el administrador de cola MQSeries.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-103">With the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries adapter you can now create and delete queues remotely on the MQSeries Queue Manager.</span></span> <span data-ttu-id="0a2dc-104">Esto se admite porque [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza un objeto MQSAgent COM+ remoto que se comunica de forma directa con el administrador de cola MQSeries.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-104">This is supported because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses a remote MQSAgent COM+ object that communicates directly with the MQSeries Queue Manager.</span></span> <span data-ttu-id="0a2dc-105">Como norma general, MQSAgent se utiliza en tiempo de ejecución para leer mensajes en las colas remotas de MQSeries Server o bien, escribirlos allí.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-105">Typically this MQSAgent is used at run time to read and write messages to the remote MQSeries Server queues.</span></span> <span data-ttu-id="0a2dc-106">Más de un servidor BizTalk Server puede ser cliente de este servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-106">More than one BizTalk server can be a client of this remote service.</span></span> <span data-ttu-id="0a2dc-107">Además, MQSAgent proporciona las funciones de creación y eliminación de colas y es posible llamar de forma directa desde una orquestación o adaptador.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-107">Additionally, queue creation and deletion functions are provided by this MQSAgent and can be called directly from within an orchestration or adapter.</span></span> <span data-ttu-id="0a2dc-108">Esto se permite en escenarios muy dinámicos a través de los cuales la orquestación o el adaptador pueden crear una cola temporal y enviar, a continuación, un mensaje mediante ella, recibir una respuesta en otra cola y, por último, eliminar la cola temporal.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-108">This allows for highly dynamic scenarios whereby the orchestration or adapter can create a temporary queue and then send a message on it, receive a reply on another queue, and finally delete the temporary queue.</span></span>  
  
## <a name="createqueue-and-deletequeue-apis"></a><span data-ttu-id="0a2dc-109">API CreateQueue y DeleteQueue</span><span class="sxs-lookup"><span data-stu-id="0a2dc-109">CreateQueue and DeleteQueue APIs</span></span>  
 <span data-ttu-id="0a2dc-110">Las API CreateQueue y DeleteQueue se definen de la siguiente forma.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-110">The CreateQueue and DeleteQueue APIs are defined as follows.</span></span>  
  
### <a name="structure-definition"></a><span data-ttu-id="0a2dc-111">Definición de estructura</span><span class="sxs-lookup"><span data-stu-id="0a2dc-111">Structure Definition</span></span>  
  
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
  
### <a name="interface-definition"></a><span data-ttu-id="0a2dc-112">Definición de interfaz</span><span class="sxs-lookup"><span data-stu-id="0a2dc-112">Interface Definition</span></span>  
  
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
  
## <a name="examples"></a><span data-ttu-id="0a2dc-113">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0a2dc-113">Examples</span></span>  
 <span data-ttu-id="0a2dc-114">Siga los pasos del ejemplo 1 para crear una aplicación de consola de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] C# que pueda usarse para crear o eliminar colas de servidor MQSeries.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-114">Complete the steps in Example 1 to create a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] C# console application which can be used to create or delete MQSeries Server queues.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="0a2dc-115">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="0a2dc-115">Example 1</span></span>  
  
##### <a name="create-a-c-console-application-to-manage-mqseries-server-queues"></a><span data-ttu-id="0a2dc-116">Crear una aplicación de consola de C# para administrar colas de servidor MQSeries</span><span class="sxs-lookup"><span data-stu-id="0a2dc-116">Create a C# console application to manage MQSeries Server queues</span></span>  
  
1.  <span data-ttu-id="0a2dc-117">Crear una nueva aplicación Visual C# consola en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] con el nombre **MQSeriesQueues**.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-117">Create a new Visual C# Console Application in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] with the name **MQSeriesQueues**.</span></span>  
  
2.  <span data-ttu-id="0a2dc-118">Reemplace el código existente del archivo Program.cs que se genera con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a2dc-118">Replace any existing code in the Program.cs file that is generated with the code below:</span></span>  
  
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
  
3.  <span data-ttu-id="0a2dc-119">Agregue una referencia a este proyecto para el **MQSAgent 1.0 Type Library**.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-119">Add a reference to this project to the **MQSAgent 1.0 Type Library**.</span></span> <span data-ttu-id="0a2dc-120">El **MQSAgent 1.0 Type Library** está disponible en la **COM** pestaña de la **Agregar referencia** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-120">The **MQSAgent 1.0 Type Library** is available on the **COM** tab of the **Add reference** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a2dc-121">El componente MQSAgent COM+ debe estar instalado en el equipo en el que está ejecutando esta aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-121">The MQSAgent COM+ component must be installed on the computer that you are running this console application from.</span></span> <span data-ttu-id="0a2dc-122">Para obtener más información acerca de cómo instalar el componente MQSAgent COM + vea [mediante el Asistente de configuración de MQSAgent COM +](../core/using-the-mqsagent-com-configuration-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0a2dc-122">For more information about installing the MQSAgent COM+ component see [Using the MQSAgent COM+ Configuration Wizard](../core/using-the-mqsagent-com-configuration-wizard.md).</span></span>  
  
4.  <span data-ttu-id="0a2dc-123">Genere la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-123">Build the console application.</span></span>  
  
5.  <span data-ttu-id="0a2dc-124">Abra un símbolo del sistema en el mismo directorio en el que se encuentra la aplicación de consola compilada.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-124">Open a command prompt in the same directory as the compiled console application.</span></span>  
  
6.  <span data-ttu-id="0a2dc-125">Escriba el nombre de la aplicación de consola compilada con los argumentos adecuados y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="0a2dc-125">Type the name of the compiled console application with the appropriate arguments and press ENTER.</span></span> <span data-ttu-id="0a2dc-126">Por ejemplo, para eliminar la cola **testq** en el Administrador de cola **QM_Test** , debería escribir el texto siguiente en el símbolo del sistema y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="0a2dc-126">For example, to delete the queue **testq** for the Queue Manager **QM_Test** you would type the following text at the command prompt and press ENTER:</span></span>  
  
    ```  
    MQSeriesQueues d QM_Test testq  
    ```  
  
7.  <span data-ttu-id="0a2dc-127">Para crear la cola **testq** en el Administrador de cola **QM_Test** , debería escribir el texto siguiente en el símbolo del sistema y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="0a2dc-127">To create the queue **testq** for the Queue Manager **QM_Test** you would type the following text at the command prompt and press ENTER:</span></span>  
  
    ```  
    MQSeriesQueues c QM_Test testq  
    ```