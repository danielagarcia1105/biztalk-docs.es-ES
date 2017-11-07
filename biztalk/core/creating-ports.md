---
title: "Creación de puertos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, creating
- receive ports
- creating, send ports
- creating, ports
- Configuration database [BizTalk Server], connecting
- receive ports, creating
- send ports
- send ports, creating
ms.assetid: 4f99f884-5b84-4f9f-8cec-dd5da259ba7f
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d109e102ada04e673fa5eddc3010201b266a150
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="creating-ports"></a><span data-ttu-id="b4c34-102">Crear puertos</span><span class="sxs-lookup"><span data-stu-id="b4c34-102">Creating Ports</span></span>
<span data-ttu-id="b4c34-103">Use los siguientes procedimientos para crear puertos de envío y recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="b4c34-103">Use the following procedures to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports for Single Sign-on.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="b4c34-104">Crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="b4c34-104">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="b4c34-105">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="b4c34-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="b4c34-106">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4c34-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="b4c34-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="b4c34-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="b4c34-108">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4c34-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="b4c34-109">Escriba un nombre para el puerto de envío, por ejemplo, `SSOSendToPeopleSoft`.</span><span class="sxs-lookup"><span data-stu-id="b4c34-109">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="b4c34-110">Desde el **tipo** lista desplegable, seleccione **PeopleSoft**.</span><span class="sxs-lookup"><span data-stu-id="b4c34-110">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="b4c34-111">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="b4c34-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="b4c34-112">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="b4c34-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="b4c34-113">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="b4c34-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="b4c34-114">Haga clic en **configurar** para configurar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="b4c34-114">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="b4c34-115">En el **propiedades de transporte de PeopleSoft** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4c34-115">In the **PeopleSoft Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="b4c34-116">Expanda **propiedades de adaptador necesarias**y escriba **ruta de acceso de servidor de aplicación**, **JAVA_HOME**, **nombre de usuario**,  **contraseña**y el archivo Jar para la conexión en el sistema Peoplesoft.</span><span class="sxs-lookup"><span data-stu-id="b4c34-116">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="b4c34-117">No tiene que establecer la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="b4c34-117">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="b4c34-118">En la lista, seleccione la aplicación afiliada de SSO que ha creado para representar el sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="b4c34-118">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="b4c34-119">Para **usar SSO**, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b4c34-119">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="b4c34-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b4c34-120">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="b4c34-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b4c34-121">Click **OK**.</span></span>  
  
## <a name="creating-a-receive-port"></a><span data-ttu-id="b4c34-122">Crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="b4c34-122">Creating a Receive Port</span></span>  
  
#### <a name="to-create-a-receive-port"></a><span data-ttu-id="b4c34-123">Para crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="b4c34-123">To create a receive port</span></span>  
  
1.  <span data-ttu-id="b4c34-124">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4c34-124">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="b4c34-125">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puertos de recepción unidireccionales**.</span><span class="sxs-lookup"><span data-stu-id="b4c34-125">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="b4c34-126">En el **propiedades de puerto de recepción** ventana, en la **General** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4c34-126">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="b4c34-127">En el **nombre** , escriba `ReceiveFromTIBCOEMS`.</span><span class="sxs-lookup"><span data-stu-id="b4c34-127">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="b4c34-128">En el **autenticación** cuadro del grupo, especifique cómo se administran los mensajes al utilizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="b4c34-128">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="b4c34-129">Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="b4c34-129">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="b4c34-130">En el **ubicaciones de recepción** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4c34-130">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="b4c34-131">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="b4c34-131">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="b4c34-132">En el **ubicaciones de recepción** ventana, en la **General** página, escriba el **nombre** de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="b4c34-132">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="b4c34-133">Desde el **tipo** lista desplegable, seleccione el tipo de transporte y desde el **controlador de recepción** lista desplegable, seleccione la dirección de transporte.</span><span class="sxs-lookup"><span data-stu-id="b4c34-133">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="b4c34-134">Desde el **canalización de recepción** lista desplegable, seleccione la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="b4c34-134">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="b4c34-135">En el **programación** página, seleccione la **fecha de inicio** y **fecha de finalización** para restringir la recepción de documentos.</span><span class="sxs-lookup"><span data-stu-id="b4c34-135">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="b4c34-136">Seleccione el **habilitar ventana de servicio** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="b4c34-136">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="b4c34-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b4c34-137">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="b4c34-138">En el **asignaciones de entrada** , seleccione las asignaciones de entrada para transformar documentos en el puerto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b4c34-138">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="b4c34-139">En el **seguimiento** página, seleccione el seguimiento de cuerpos de mensaje y el seguimiento de propiedades de mensaje deseado.</span><span class="sxs-lookup"><span data-stu-id="b4c34-139">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="b4c34-140">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b4c34-140">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c34-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4c34-141">See Also</span></span>  
 [<span data-ttu-id="b4c34-142">Proteger el adaptador</span><span class="sxs-lookup"><span data-stu-id="b4c34-142">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)