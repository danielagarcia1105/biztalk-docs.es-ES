---
title: Los contratos de cómo tratar con tipos erróneos en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- typed fault contracts [orchestrations]
- WCF services, orchestrations
- orchestrations, typed fault contracts
- orchestrations, WCF services
ms.assetid: 5a1a7d22-b0ff-4d09-bebf-4995229784b0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a7643c4a39785018368572d721eed3ef6545c6b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "25970770"
---
# <a name="how-to-handle-typed-fault-contracts-in-orchestrations"></a><span data-ttu-id="fd3f5-102">Cómo controlar los contratos con tipos erróneos en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="fd3f5-102">How to Handle Typed Fault Contracts in Orchestrations</span></span>
<span data-ttu-id="fd3f5-103">En este tema se explica cómo controlar los contratos con tipos erróneos al consumir servicios WCF desde las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-103">This topic describes how to handle typed fault contracts when consuming WCF services from within orchestrations.</span></span> <span data-ttu-id="fd3f5-104">Para controlar las excepciones de tipo erróneo en orquestaciones, los servicios WCF que va a consumir deben tener la **FaultContractAttribute** aplica a las operaciones de servicio; por lo tanto, los errores se pueden iniciar mediante el uso de  **FaultException**\<T\> donde T puede ser cualquier contrato de datos válido o un tipo serializable de los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-104">To handle typed fault exceptions in orchestrations, the WCF services that you are consuming must have the **FaultContractAttribute** applied to the service operations; therefore, the faults can be thrown by using **FaultException**\<T\> where T can be any valid data contract or serializable type from the WCF services.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="fd3f5-105">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fd3f5-105">Procedures</span></span>  
  
#### <a name="to-handle-typed-fault-contracts-in-orchestrations"></a><span data-ttu-id="fd3f5-106">Para controlar los contratos con tipo erróneo en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="fd3f5-106">To handle typed fault contracts in orchestrations</span></span>  
  
1.  <span data-ttu-id="fd3f5-107">En la Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, en el Explorador de soluciones, haga clic en el proyecto, haga clic en **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-107">In your Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, in Solution Explorer, right-click your project, click **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="fd3f5-108">En el **agregar elementos generados - \< ***nombre del proyecto*** \>**  cuadro de diálogo, en la **plantillas** sección, seleccione **consumir WCF Servicio**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-108">In the **Add Generated Items - \<***Project name***\>** dialog box, in the **Templates** section, select **Consume WCF Service**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="fd3f5-109">En el **éste es el Asistente para consumición de servicio de BizTalk WCF** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-109">On the **Welcome to the BizTalk WCF Service Consuming Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="fd3f5-110">En el **origen de metadatos** página, seleccione **punto de conexión de intercambio de metadatos (MEX)** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-110">On the **Metadata source** page, select **Metadata Exchange (MEX) endpoint**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="fd3f5-111">En el **extremo de metadatos** página, especifique la dirección URL para el servicio en ejecución que proporciona metadatos para su descarga mediante WS-Metadata Exchange o Http-Get — por ejemplo, http://localhost: 8005.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-111">On the **Metadata Endpoint** page, specify the URL for the running service that provides metadata for download through WS-Metadata Exchange or Http-Get—for example, http://localhost:8005.</span></span> <span data-ttu-id="fd3f5-112">Para obtener el documento de metadatos de la dirección URL, haga clic en **obtener**.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-112">To get the metadata document from the URL, click **Get**.</span></span> <span data-ttu-id="fd3f5-113">Si el servicio en ejecución requiere una credencial de usuario con el esquema de autenticación básica, haga clic en **editar** para abrir el **Asistente de consumición de servicio WCF de BizTalk** cuadro de diálogo en el que puede proporcionar el nombre de usuario y contraseña que se utilizará al obtener acceso a lo servicio en ejecución.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-113">If the running service requires a user credential with the basic authentication scheme, click **Edit** to open the **BizTalk WCF Service Consuming Wizard** dialog box in which you can supply the user name and password to use when accessing the running service.</span></span> <span data-ttu-id="fd3f5-114">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-114">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="fd3f5-115">En el **Importar resumen de metadatos de servicio de WCF** página, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-115">On the **Import WCF Service Metadata Summary** page, review your settings.</span></span> <span data-ttu-id="fd3f5-116">Puede hacer clic en **volver** realizar ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-116">You can click **Back** to make any changes.</span></span> <span data-ttu-id="fd3f5-117">A continuación, haga clic en **importación** para crear los artefactos de BizTalk y los tipos que se usará para utilizar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-117">Then click **Import** to create the BizTalk artifacts and types to be used for consuming the WCF service.</span></span>  
  
7.  <span data-ttu-id="fd3f5-118">En el **completar el Asistente para consumición de servicio de BizTalk WCF** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-118">On the **Completing the BizTalk WCF Service Consuming Wizard** page, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="fd3f5-119">Supongamos que el Servicio WCF que va a consumir inicia la siguiente excepción de error:</span><span class="sxs-lookup"><span data-stu-id="fd3f5-119">Suppose that the WCF service that you are consuming throws the following fault exception:</span></span>  
  
    ```  
    throw new FaultException<MyOperationException>(divideException);  
    ```  
  
     <span data-ttu-id="fd3f5-120">La operación errónea en el puerto de envío espera un mensaje de tipo **MyOperationException**, pero el mensaje de respuesta WCF contiene el cuerpo de error completo.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-120">The fault operation on the send port expects a message of type **MyOperationException**, but the WCF response message contains the whole fault body.</span></span> <span data-ttu-id="fd3f5-121">Por lo tanto, debe extraer el **MyOperationException** parte del mensaje mediante la configuración de la **cuerpo del mensaje entrante de BizTalk** opción en el cuadro de diálogo de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-121">Therefore, you need to extract the **MyOperationException** part from the message by configuring the **Inbound BizTalk message body** option in the transport properties dialog box.</span></span> <span data-ttu-id="fd3f5-122">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="fd3f5-122">For example,</span></span>  
  
    -   <span data-ttu-id="fd3f5-123">Seleccione **ruta--contenido ubicado por la ruta de cuerpo**.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-123">Select **Path -- content located by body path**.</span></span>  
  
    -   <span data-ttu-id="fd3f5-124">Establezca la expresión de ruta del cuerpo a continuación:</span><span class="sxs-lookup"><span data-stu-id="fd3f5-124">Set the Body path expression to the following:</span></span>  
  
        ```  
        /*[local-name()='Fault']/*[local-name()='Detail']/* | /*[local-name()='DivideResponse']  
        ```  
  
    -   <span data-ttu-id="fd3f5-125">Seleccione **Xml** desde el **codificación de nodo** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-125">Select **Xml** from the **Node encoding** drop-down list.</span></span>  
  
9. <span data-ttu-id="fd3f5-126">En la orquestación, será necesario agregar un ámbito y dos controladores de excepción.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-126">In the orchestration, you will need to add a scope and two exception handlers.</span></span> <span data-ttu-id="fd3f5-127">Es un controlador de excepción para la operación de error similar al **MyOperationException** se muestra en el ejemplo anterior; el otro controlador de excepciones es para capturar genérico **SOAPExceptions**.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-127">One exception handler is for the Fault operation, similar to **MyOperationException** shown in the preceding example; the other exception handler is for catching generic **SOAPExceptions**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd3f5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd3f5-128">See Also</span></span>  
 <span data-ttu-id="fd3f5-129">[Cómo iniciar excepciones erróneas desde orquestaciones publicadas como servicios WCF](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="fd3f5-129">[How to Throw Fault Exceptions from Orchestrations Published as WCF Services](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md) </span></span>  
 [<span data-ttu-id="fd3f5-130">Cómo usar el servicio de WCF de BizTalk consumiendo Asistente para consumir un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="fd3f5-130">How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service</span></span>](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)