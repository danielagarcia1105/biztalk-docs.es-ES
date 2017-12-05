---
title: Colas de puesta en cola de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [MSMQ adapters], queue paths
- naming conventions, MSMQ adapters
- configuring [MSMQ adapters], naming conventions
- messages, queuing
- MSMQ adapters, troubleshooting
- MSMQ adapters, message queues
- configuring [MSMQ adapters], troubleshooting
- troubleshooting, queue paths [MSMQ adapters]
- naming conventions, queue paths [MSMQ adapters]
- configuring [MSMQ adapters], message queues
ms.assetid: b802348e-8543-4b06-a6e4-149b86139fb1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa8d2521a8cf434c7a0ea56f749f9df3f032551e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="message-queuing-queues"></a><span data-ttu-id="2b3b3-102">Colas de puesta en cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="2b3b3-102">Message Queuing Queues</span></span>
<span data-ttu-id="2b3b3-103">Esta sección describe cómo especificar colas de Microsoft Message Queue Server (a la que también se conoce como MSMQ) cuando utiliza el adaptador de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-103">This section describes how to specify Microsoft Message Queuing (also known as MSMQ) queues when you use the MSMQ adapter.</span></span> <span data-ttu-id="2b3b3-104">Describe las convenciones para especificar rutas y la función que los nombres de formato desempeñan cuando se traducen rutas a designaciones de cola.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-104">It describes the conventions for specifying paths and also describes the role that format names play in translating paths into queue designations.</span></span>  
  
## <a name="queue-path-naming-conventions"></a><span data-ttu-id="2b3b3-105">Convenciones de nomenclatura de ruta de cola</span><span class="sxs-lookup"><span data-stu-id="2b3b3-105">Queue Path Naming Conventions</span></span>  
 <span data-ttu-id="2b3b3-106">Si el nombre de la cola hace referencia a una ruta, utilice las convenciones de nomenclatura en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-106">If the queue name refers to a path, use the naming conventions in the following table.</span></span>  
  
|<span data-ttu-id="2b3b3-107">**Tipo de cola**</span><span class="sxs-lookup"><span data-stu-id="2b3b3-107">**Queue type**</span></span>|<span data-ttu-id="2b3b3-108">**Sintaxis de ruta de acceso**</span><span class="sxs-lookup"><span data-stu-id="2b3b3-108">**Syntax for path**</span></span>|  
|--------------------|-------------------------|  
|<span data-ttu-id="2b3b3-109">Cola pública</span><span class="sxs-lookup"><span data-stu-id="2b3b3-109">Public queue</span></span>|<span data-ttu-id="2b3b3-110">*NombreDeEquipo*\QueueName</span><span class="sxs-lookup"><span data-stu-id="2b3b3-110">*Computername*\QueueName</span></span>|  
|<span data-ttu-id="2b3b3-111">Cola privada</span><span class="sxs-lookup"><span data-stu-id="2b3b3-111">Private queue</span></span>|<span data-ttu-id="2b3b3-112">*NombreDeEquipo*\Private$\QueueName</span><span class="sxs-lookup"><span data-stu-id="2b3b3-112">*Computername*\Private$\QueueName</span></span>|  
|<span data-ttu-id="2b3b3-113">Cola de diario</span><span class="sxs-lookup"><span data-stu-id="2b3b3-113">Journal queue</span></span>|<span data-ttu-id="2b3b3-114">*NombreDeEquipo*\QueueName\Journal$</span><span class="sxs-lookup"><span data-stu-id="2b3b3-114">*Computername*\QueueName\Journal$</span></span>|  
|<span data-ttu-id="2b3b3-115">Cola de diario de equipo **Nota:** para cola de recepción solo.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-115">Computer journal queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="2b3b3-116">*NombreDeEquipo*\Journal$</span><span class="sxs-lookup"><span data-stu-id="2b3b3-116">*Computername*\Journal$</span></span>|  
|<span data-ttu-id="2b3b3-117">Cola de mensajes no enviados del equipo **Nota:** para cola de recepción solo.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-117">Computer dead-letter queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="2b3b3-118">*NombreDeEquipo*\Deadletter$</span><span class="sxs-lookup"><span data-stu-id="2b3b3-118">*Computername*\Deadletter$</span></span>|  
|<span data-ttu-id="2b3b3-119">Cola de mensajes no enviados de transacciones de equipo **Nota:** para cola de recepción solo.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-119">Computer transaction dead-letter queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="2b3b3-120">*NombreDeEquipo*\XactDeadletter$</span><span class="sxs-lookup"><span data-stu-id="2b3b3-120">*Computername*\XactDeadletter$</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="2b3b3-121">La ruta de la cola debe ser única.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-121">The path of the queue must be unique.</span></span>  
  
 <span data-ttu-id="2b3b3-122">Si el nombre de cola hace referencia a un nombre de formato, toma la forma de una cadena que indica si una cola es pública o privada seguida de un GUID generado para la cola y otros identificadores, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-122">If the queue name refers to a format name, it takes the form of a string that indicates whether a queue is public or private, followed by a generated GUID for the queue and other identifiers as needed.</span></span> <span data-ttu-id="2b3b3-123">Utilice las convenciones de nomenclatura de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-123">Use the naming conventions in the following table.</span></span>  
  
|<span data-ttu-id="2b3b3-124">**Tipo de formato**</span><span class="sxs-lookup"><span data-stu-id="2b3b3-124">**Format type**</span></span>|<span data-ttu-id="2b3b3-125">**Sintaxis de nombre de formato**</span><span class="sxs-lookup"><span data-stu-id="2b3b3-125">**Syntax for format name**</span></span>|  
|---------------------|--------------------------------|  
|<span data-ttu-id="2b3b3-126">Público</span><span class="sxs-lookup"><span data-stu-id="2b3b3-126">Public</span></span>|<span data-ttu-id="2b3b3-127">*FormatName*: Public = QueueGUID</span><span class="sxs-lookup"><span data-stu-id="2b3b3-127">*FormatName*:Public=QueueGUID</span></span>|  
|<span data-ttu-id="2b3b3-128">Directo</span><span class="sxs-lookup"><span data-stu-id="2b3b3-128">Direct</span></span>|<span data-ttu-id="2b3b3-129">*FormatName*: DIRECT = SPX:NetworkNumber:HostNumber\QueueName</span><span class="sxs-lookup"><span data-stu-id="2b3b3-129">*FormatName*:DIRECT=SPX:NetworkNumber:HostNumber\QueueName</span></span><br /><br /> <span data-ttu-id="2b3b3-130">*FormatName*: DIRECT = TCP:IPAddress\QueueName</span><span class="sxs-lookup"><span data-stu-id="2b3b3-130">*FormatName*: DIRECT=TCP:IPAddress\QueueName</span></span><br /><br /> <span data-ttu-id="2b3b3-131">*FormatName*: DIRECT = OS:ComputerName\QueueName</span><span class="sxs-lookup"><span data-stu-id="2b3b3-131">*FormatName*: DIRECT=OS:ComputerName\QueueName</span></span>|  
  
 <span data-ttu-id="2b3b3-132">Si la ruta de la cola del puerto de envío es una lista de distribución, la sintaxis de la ruta de la cola es:</span><span class="sxs-lookup"><span data-stu-id="2b3b3-132">If the send port queue path is a distribution list, then the queue path syntax is:</span></span>  
  
 <span data-ttu-id="2b3b3-133">DL=DistributionListGUID</span><span class="sxs-lookup"><span data-stu-id="2b3b3-133">DL=DistributionListGUID</span></span>  
  
 <span data-ttu-id="2b3b3-134">Si la ruta de la cola de envío o recepción es una URL HTTP o HTTPS, la sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="2b3b3-134">If the send or receive queue path is an HTTP or HTTPS URL, then the syntax is:</span></span>  
  
 <span data-ttu-id="2b3b3-135">FormatName:DIRECT = http: / /\<nombre de cliente\>/MSMQ /\<nombre de la cola\></span><span class="sxs-lookup"><span data-stu-id="2b3b3-135">FormatName:DIRECT=http://\<client name\>/msmq/\<queue name\></span></span>  
  
 <span data-ttu-id="2b3b3-136">FormatName:DIRECT = https: / /\<nombre de cliente\>/MSMQ /\<nombre de la cola\></span><span class="sxs-lookup"><span data-stu-id="2b3b3-136">FormatName:DIRECT=https://\<client name\>/msmq/\<queue name\></span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b3b3-137">"msmq" es la carpeta virtual creada por Message Queue Server en Servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="2b3b3-137">"msmq" is the virtual folder that Message Queuing creates in Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b3b3-138">Sólo puede utilizar HTTP para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-138">You can only use HTTP to send messages.</span></span> <span data-ttu-id="2b3b3-139">No es posible leer mensajes de una cola de un equipo remoto si aquélla se abre mediante un nombre de formato directo HTTP.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-139">You cannot read messages in a queue on a remote computer if the queue is opened using an HTTP direct format name.</span></span> <span data-ttu-id="2b3b3-140">No obstante, podrá seguir recibiendo mensajes (con formato) SOAP desde una cola remota mediante la ruta de cola pública o privada sin HTTP.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-140">However, you can still receive SOAP (formatted) messages from a remote queue by using the private or public queue path without HTTP.</span></span>  
  
 <span data-ttu-id="2b3b3-141">Si el nombre de cola hace referencia a una etiqueta de texto descriptivo que el administrador ha especificado para la cola, la sintaxis de la ruta de cola que hace referencia a esta etiqueta es:</span><span class="sxs-lookup"><span data-stu-id="2b3b3-141">If the queue name refers to a descriptive text label that the administrator specified for the queue, then the syntax of the queue path referring to this label is:</span></span>  
  
 <span data-ttu-id="2b3b3-142">LABEL:MyQueue</span><span class="sxs-lookup"><span data-stu-id="2b3b3-142">LABEL:MyQueue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b3b3-143">Las etiquetas no siempre son exclusivas.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-143">Labels are not always unique.</span></span> <span data-ttu-id="2b3b3-144">Por tanto, recibirá un mensaje de error si existe un conflicto de nombres cuando intenta conectarse a una cola específica mediante esta etiqueta.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-144">Therefore, you will receive an error if a name conflict exists when you try to connect to a specific queue by using its label.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b3b3-145">La etiqueta es un campo de transporte necesario para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-145">The label is a required transport field for the adapter.</span></span>  
  
## <a name="role-of-the-format-name"></a><span data-ttu-id="2b3b3-146">Función del nombre de formato</span><span class="sxs-lookup"><span data-stu-id="2b3b3-146">Role of the Format Name</span></span>  
 <span data-ttu-id="2b3b3-147">Message Queue Server utiliza el nombre de formato para identificar una cola y determinar cómo obtener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-147">Message Queuing uses the format name to identify a queue and to determine how to access it.</span></span> <span data-ttu-id="2b3b3-148">Message Queue Server asigna el nombre de formato a la cola.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-148">Message Queuing assigns the format name to the queue.</span></span>  
  
 <span data-ttu-id="2b3b3-149">Cuando especifica una cola mediante la sintaxis del nombre de la ruta, por ejemplo, myMachine\myQueue, Message Queue Server busca la ruta para encontrar el nombre de formato asociado.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-149">When you specify a queue using the path name syntax, for example myMachine\myQueue, Message Queuing looks up the path to find the associated format name.</span></span> <span data-ttu-id="2b3b3-150">Message Queue Server utiliza ese nombre de formato para obtener acceso a la cola.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-150">Message Queuing then uses that format name to access the queue.</span></span> <span data-ttu-id="2b3b3-151">Cuando especifica el nombre de formato, Message Queue Server utiliza el nombre de formato utilizado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-151">When you specify the format name, Message Queuing uses the format name you use.</span></span>  
  
 <span data-ttu-id="2b3b3-152">Para obtener más información acerca de nombres de formato, vea "Propiedad MessageQueue.FormatName" en la Ayuda de la biblioteca de clases de .Net Framework.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-152">For more information about format names, see "MessageQueue.FormatName Property" in .NET Framework Class Library Help.</span></span>  
  
## <a name="troubleshooting-queue-paths"></a><span data-ttu-id="2b3b3-153">Solucionar problemas de rutas de cola</span><span class="sxs-lookup"><span data-stu-id="2b3b3-153">Troubleshooting Queue Paths</span></span>  
  
-   <span data-ttu-id="2b3b3-154">Se produce una excepción si no coincide la sintaxis de la ruta de cola proporcionada con uno de los formatos descritos anteriormente en "Convenciones de nomenclatura de ruta de cola."</span><span class="sxs-lookup"><span data-stu-id="2b3b3-154">An exception occurs if the syntax of the provided queue path does not match one of the formats described earlier in "Queue Path Naming Conventions."</span></span>  
  
-   <span data-ttu-id="2b3b3-155">Los siguientes caracteres no son válidos como nombre de equipo en la ruta de cola:</span><span class="sxs-lookup"><span data-stu-id="2b3b3-155">The following are not valid characters for computer names in the queue path:</span></span>  
  
     <span data-ttu-id="2b3b3-156">\ ; , + "</span><span class="sxs-lookup"><span data-stu-id="2b3b3-156">\ ; , + "</span></span>  
  
     <span data-ttu-id="2b3b3-157">Se produce una excepción si el nombre de equipo es un número.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-157">An exception occurs if the computer name is a number.</span></span> <span data-ttu-id="2b3b3-158">Por ejemplo: 234\private$ \queue.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-158">For example: 234\private$\queue.</span></span>  
  
-   <span data-ttu-id="2b3b3-159">Para una cola de mensajes con problemas de entrega de equipo, una cola de diario de equipo y una cola de mensajes con problemas de entrega de transacción de equipos, se produce una excepción si el usuario especifica cualquiera de las colas de sistema como la cola de destino para envío.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-159">For a computer dead-letter queue, computer journal queue, and computer transaction dead-letter queue, an exception occurs if the user specifies any one of the system queues as the destination queue for send.</span></span>  
  
-   <span data-ttu-id="2b3b3-160">**System.Messaging.MessageQueue.Exists** no funciona para las colas remotas.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-160">**System.Messaging.MessageQueue.Exists** does not work for remote queues.</span></span> <span data-ttu-id="2b3b3-161">Para obtener más información, vea "Método MessageQueue.Exists" en la Ayuda de la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-161">For more information, see "MessageQueue.Exists Method" in .NET Framework Class Library Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b3b3-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b3b3-162">See Also</span></span>  
 [<span data-ttu-id="2b3b3-163">Configuración del adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="2b3b3-163">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)