---
title: ApplicationAdapter | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f9b876b-cd37-4e24-a476-186adc155ac0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b7a754b044fb12bf7cec9fed0e5455e6192c072
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974933"
---
# <a name="applicationadapter"></a><span data-ttu-id="60f35-102">ApplicationAdapter</span><span class="sxs-lookup"><span data-stu-id="60f35-102">ApplicationAdapter</span></span>
<span data-ttu-id="60f35-103">El ejemplo ApplicationAdapter muestra cómo enviar notificaciones desde los procesos públicos y privados (servicio de respuesta o iniciador) cuando reciba un mensaje.</span><span class="sxs-lookup"><span data-stu-id="60f35-103">The ApplicationAdapter sample demonstrates how to send notifications from the public and private processes (responder or initiator) when you receive a message.</span></span> <span data-ttu-id="60f35-104">Puede personalizar el ejemplo con cualquier funcionalidad adicional que desee.</span><span class="sxs-lookup"><span data-stu-id="60f35-104">You can customize the sample with whatever additional functionality you want.</span></span>  
  
 <span data-ttu-id="60f35-105">El ejemplo ApplicationAdapter muestra cómo implementar la `IApplicationAdapter` interfaz a la `ApplicationAdapter1` clase.</span><span class="sxs-lookup"><span data-stu-id="60f35-105">The ApplicationAdapter sample demonstrates how to implement the `IApplicationAdapter` interface to the `ApplicationAdapter1` class.</span></span> <span data-ttu-id="60f35-106">Esta clase incluye dos métodos, `BeginNotify` y `Notify`.</span><span class="sxs-lookup"><span data-stu-id="60f35-106">This class includes two methods, `BeginNotify` and `Notify`.</span></span> <span data-ttu-id="60f35-107">Los parámetros para cada clase de la categoría de mensaje, nombre de la entidad de origen, nombre de la entidad de destino, código de proceso de interfaz de socio (PIP), Id. de instancia PIP y versión de PIP.</span><span class="sxs-lookup"><span data-stu-id="60f35-107">The parameters for each class are the message category, source party name, destination party name, Partner Interface Process (PIP) code, PIP instance ID, and PIP version.</span></span>  
  
 <span data-ttu-id="60f35-108">Establecer el ApplicationAdapter para un acuerdo, escriba el nombre del ensamblado y el nombre de clase en el **General** ficha del acuerdo en el Microsoft® [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span><span class="sxs-lookup"><span data-stu-id="60f35-108">You set the ApplicationAdapter for an agreement by entering the assembly name and class name on the **General** tab of the agreement in the Microsoft® [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span></span> <span data-ttu-id="60f35-109">El archivo .dll de adaptador de aplicación se ejecuta bajo las mismas credenciales que el servicio de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="60f35-109">The application adapter .dll file runs under the same credentials as the BizTalk host service.</span></span>  
  
 <span data-ttu-id="60f35-110">Si cambia el ejemplo ApplicationAdapter o cualquier variable de entorno externo que depende el ejemplo ApplicationAdapter, reinicie el servicio de host de BizTalk que hospeda el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] proceso público.</span><span class="sxs-lookup"><span data-stu-id="60f35-110">If you change the ApplicationAdapter sample or any external environment variable that the ApplicationAdapter sample depends on, restart the BizTalk host service that hosts the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public process.</span></span>  
  
 <span data-ttu-id="60f35-111">Se encuentra en el código de ejemplo ApplicationAdapter \< *unidad*\>: \Program Files\ BizTalk \<versión\> Acelerador para RosettaNet\SDK\ApplicationAdapter\\.</span><span class="sxs-lookup"><span data-stu-id="60f35-111">The ApplicationAdapter sample code is located at \<*drive*\>:\Program Files\ BizTalk \<version\> Accelerator for RosettaNet\SDK\ApplicationAdapter\\.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="60f35-112">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="60f35-112">Demonstrates</span></span>  
 <span data-ttu-id="60f35-113">El ejemplo de ApplicationAdapter muestra cómo notificar a los procesos Respondedor privado que el proceso público ha recibido un mensaje.</span><span class="sxs-lookup"><span data-stu-id="60f35-113">The ApplicationAdapter sample demonstrates how to notify the responder private process that the public process has received a message.</span></span> <span data-ttu-id="60f35-114">La notificación indica la categoría del mensaje, el nombre de la entidad de origen, el nombre de la entidad de destino, el código PIP, la versión PIP y el identificador de instancia PIP.</span><span class="sxs-lookup"><span data-stu-id="60f35-114">The notification indicates the message category, the source party name, the destination party name, the PIP code, the PIP version, and the PIP instance ID.</span></span> <span data-ttu-id="60f35-115">Puede enviar esta notificación para una acción o un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="60f35-115">You can send this notification for either an action or a response message.</span></span>  
  
 <span data-ttu-id="60f35-116">El `BeginNotify` y `Notify` métodos funcionan como sigue:</span><span class="sxs-lookup"><span data-stu-id="60f35-116">The `BeginNotify` and `Notify` methods work as follows:</span></span>  
  
1.  <span data-ttu-id="60f35-117">El proceso público del Respondedor recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="60f35-117">The responder public process receives a message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="60f35-118">Los siguientes pasos también son aplicables para el escenario en el que el iniciador público recibe un mensaje de respuesta desde el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="60f35-118">The following steps are also applicable for the scenario in which the public initiator receives a response message from the responder.</span></span>  
  
2.  <span data-ttu-id="60f35-119">Si la validación por la canalización de recepción y el proceso público y el adaptador de validación, si procede, se realizó correctamente, el público del Respondedor procesa llamadas la `BeginNotify` método en el `ApplicationAdapter` clase.</span><span class="sxs-lookup"><span data-stu-id="60f35-119">If validation by the receive pipeline and public process, and validation adapter, if applicable, was successful, the responder public process calls the `BeginNotify` method in the `ApplicationAdapter` class.</span></span> <span data-ttu-id="60f35-120">Este método notifica el proceso privado del servicio de respuesta que el proceso público ha recibido el mensaje nuevo y guarda el mensaje en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="60f35-120">This method notifies the responder private process that the public process has received the new message and saved the message in the MessageBox database.</span></span>  
  
3.  <span data-ttu-id="60f35-121">El proceso público del Respondedor envía un mensaje de señal al iniciador.</span><span class="sxs-lookup"><span data-stu-id="60f35-121">The responder public process sends a signal message back to the initiator.</span></span>  
  
4.  <span data-ttu-id="60f35-122">El proceso público del Respondedor envía el contenido del servicio de mensaje para el proceso privado del Respondedor.</span><span class="sxs-lookup"><span data-stu-id="60f35-122">The responder public process sends the message service content to the responder private process.</span></span>  
  
5.  <span data-ttu-id="60f35-123">El proceso privado del Respondedor coloca el mensaje en la tabla MessagesToLOB de la base de datos BTARNDATA.</span><span class="sxs-lookup"><span data-stu-id="60f35-123">The responder private process puts the message in the MessagesToLOB table of the BTARNDATA database.</span></span>  
  
6.  <span data-ttu-id="60f35-124">Las llamadas de proceso privado del Respondedor del `Notify` método en el `ApplicationAdapter` clase para enviar el mensaje final notificar hasta el proceso público del Respondedor.</span><span class="sxs-lookup"><span data-stu-id="60f35-124">The responder private process calls the `Notify` method in the `ApplicationAdapter` class to send the End Notify message back to the responder public process.</span></span> <span data-ttu-id="60f35-125">El proceso público del Respondedor debe recibir el mensaje de notificar al final para el proceso se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="60f35-125">The responder public process must receive the End Notify message for the process to be successfully completed.</span></span> <span data-ttu-id="60f35-126">En caso contrario, el mensaje se suspende.</span><span class="sxs-lookup"><span data-stu-id="60f35-126">Otherwise, the message is suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60f35-127">Puede usar el `Notify` mensaje para indicar que la aplicación de línea de negocio (LOB) que está esperando el mensaje en la tabla MessagesToLOB.</span><span class="sxs-lookup"><span data-stu-id="60f35-127">You can use the `Notify` message to signal the line-of-business (LOB) application that the message is waiting in the MessagesToLOB table.</span></span> <span data-ttu-id="60f35-128">Como pronto el sistema de alertas de la aplicación de LOB, la aplicación de LOB puede recuperar el mensaje de esa tabla.</span><span class="sxs-lookup"><span data-stu-id="60f35-128">As soon the system alerts the LOB application, the LOB application can retrieve the message from that table.</span></span>  
  
## <a name="to-implement-this-sample"></a><span data-ttu-id="60f35-129">Para implementar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="60f35-129">To Implement this Sample</span></span>  
 <span data-ttu-id="60f35-130">Para implementar el ejemplo ApplicationAdapter, debe agregar el adaptador de aplicación para el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="60f35-130">To implement the ApplicationAdapter sample, you must add the application adapter to the agreement.</span></span>  
  
#### <a name="to-add-the-application-adapter-to-an-agreement"></a><span data-ttu-id="60f35-131">Para agregar el adaptador de aplicación a un acuerdo</span><span class="sxs-lookup"><span data-stu-id="60f35-131">To add the application adapter to an agreement</span></span>  
  
1. <span data-ttu-id="60f35-132">Haga clic en **iniciar**, apunte a **todos los programas**, señale Microsoft **BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Consola de administración**.</span><span class="sxs-lookup"><span data-stu-id="60f35-132">Click **Start**, point to **All Programs**, point to Microsoft **BizTalk \<version\> Accelerator for RosettaNet**, and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="60f35-133">En el [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y haga clic en **acuerdos**.</span><span class="sxs-lookup"><span data-stu-id="60f35-133">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and click **Agreements**.</span></span>  
  
3. <span data-ttu-id="60f35-134">Haga doble clic en el acuerdo al que desea agregar el adaptador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="60f35-134">Double-click the agreement to which you want to add the application adapter.</span></span>  
  
4. <span data-ttu-id="60f35-135">En el **aplicación adaptador** cuadro, haga clic en el botón de puntos suspensivos (**...** ) situado a la derecha de **nombre del ensamblado**, desplazarse a la ubicación que contiene el ensamblado de adaptador de aplicación, seleccione el archivo .dll adecuado y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="60f35-135">In the **Application Adapter** box, click the ellipsis button (**...**) button to the right of **Assembly name**, move to the location that contains the application adapter assembly, select the appropriate .dll file, and then click **Open**.</span></span>  
  
5. <span data-ttu-id="60f35-136">Haga clic en la flecha hacia abajo para **nombre de la clase**, seleccione la clase de adaptador de aplicación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="60f35-136">Click the down arrow for **Class Name**, select the application adapter class, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f35-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="60f35-137">See Also</span></span>  
 [<span data-ttu-id="60f35-138">Ejemplos de adaptadores</span><span class="sxs-lookup"><span data-stu-id="60f35-138">Adapter Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)