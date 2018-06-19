---
title: 'Paso 5: Configurar un puerto de recepción y ubicación de recepción | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43fc8d12-5fde-4ddf-a7f0-770f078ba66b
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8ec436657aefaceb71207d37808936aa6eaa1a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277956"
---
# <a name="step-5-configure-a-receive-port-and-receive-location"></a><span data-ttu-id="f9340-102">Paso 5: Configurar un puerto de recepción y ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="f9340-102">Step 5: Configure a Receive Port and Receive Location</span></span>
<span data-ttu-id="f9340-103">![Paso 5 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span><span class="sxs-lookup"><span data-stu-id="f9340-103">![Step 5 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span></span>  
  
 <span data-ttu-id="f9340-104">En este paso, configurará un puerto de recepción y una ubicación de recepción para recibir el mensaje 850 en la carpeta configurada para la entidad Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="f9340-104">In this step you configure a receive port and receive location for receiving the 850 message in the folder set up for the Fabrikam party.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f9340-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f9340-105">Prerequisites</span></span>  
 <span data-ttu-id="f9340-106">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9340-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-receive-port-and-receive-location-for-receiving-the-850-message"></a><span data-ttu-id="f9340-107">Para configurar un puerto de recepción y una ubicación de recepción para recibir el mensaje 850</span><span class="sxs-lookup"><span data-stu-id="f9340-107">To configure a receive port and receive location for receiving the 850 message</span></span>  
  
1.  <span data-ttu-id="f9340-108">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**y, a continuación, **BizTalk Aplicación 1**.</span><span class="sxs-lookup"><span data-stu-id="f9340-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and then **BizTalk Application 1**.</span></span> <span data-ttu-id="f9340-109">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="f9340-109">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="f9340-110">En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba `ReceiveEDI_fromTHEM_A`.</span><span class="sxs-lookup"><span data-stu-id="f9340-110">In the Receive Port Properties dialog box, in the **Name** field, enter `ReceiveEDI_fromTHEM_A`.</span></span>  
  
3.  <span data-ttu-id="f9340-111">Haga clic en **ubicaciones de recepción** en el árbol de consola y, a continuación, haga clic en **New** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="f9340-111">Click **Receive Locations** in the console tree, and then click **New** in the right-hand pane.</span></span>  
  
4.  <span data-ttu-id="f9340-112">En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba `fromTHEM_4010_850`.</span><span class="sxs-lookup"><span data-stu-id="f9340-112">In the **Receive Location Properties** dialog box, in the **Name** field, enter `fromTHEM_4010_850`.</span></span>  
  
5.  <span data-ttu-id="f9340-113">Para **tipo**, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="f9340-113">For **Type**, select **FILE**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9340-114">El tipo de transporte de la ubicación de recepción es Archivo, ya que el mensaje de prueba es un archivo sin formato que va a enviarse a una carpeta.</span><span class="sxs-lookup"><span data-stu-id="f9340-114">The transport type of the receive location is FILE because the test message is a flat file delivered into a folder.</span></span>  
  
6.  <span data-ttu-id="f9340-115">En el **propiedades de transporte de archivo** cuadro de diálogo, haga clic en el **examinar** situado junto a la **carpeta recepción** campo.</span><span class="sxs-lookup"><span data-stu-id="f9340-115">In the **FILE Transport Properties** dialog box, click the **Browse** button next to the **Receive folder** field.</span></span> <span data-ttu-id="f9340-116">En el **Buscar carpeta** cuadro de diálogo, desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9340-116">In the **Browse for Folder** dialog box, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="f9340-117">En el **propiedades de transporte de archivo** cuadro de diálogo, cambie el **máscara de archivo** a  **\*.txt** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9340-117">In the **FILE Transport Properties** dialog box, change the **File mask** to **\*.txt** and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9340-118">La máscara de archivo está establecida como \*.txt, ya que el mensaje de prueba de entrada es un archivo de texto, SamplePO.txt.</span><span class="sxs-lookup"><span data-stu-id="f9340-118">The file mask is set to \*.txt because the input test message is a text file, SamplePO.txt.</span></span>  
  
8.  <span data-ttu-id="f9340-119">En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **canalización de recepción** campo, seleccione **EdiReceive**.</span><span class="sxs-lookup"><span data-stu-id="f9340-119">In the **Receive Location Properties** dialog box, in the **Receive Pipeline** field, select **EdiReceive**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9340-120">La canalización de recepción usada para recibir intercambios EDI, excepto para los entregados a través del transporte AS2, es la canalización EdiReceive.</span><span class="sxs-lookup"><span data-stu-id="f9340-120">The receive pipeline used to receive EDI interchanges, except for those delivered over the AS2 transport, is the EdiReceive pipeline.</span></span> <span data-ttu-id="f9340-121">(La canalización de recepción AS2EdiReceive se usa para recibir intercambios EDI entregados a través del transporte AS2).</span><span class="sxs-lookup"><span data-stu-id="f9340-121">(The AS2EdiReceive receive pipeline is used to receive EDI interchanges delivered over the AS2 transport.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9340-122">Si EdiReceive no se encuentra en la lista desplegable para la canalización de recepción, puede que su aplicación no tenga una referencia a la aplicación EDI de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f9340-122">If EdiReceive is not listed in the drop-down list for receive pipeline, your application may not have a reference to the BizTalk EDI Application.</span></span> <span data-ttu-id="f9340-123">Para agregar la referencia, vea [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span><span class="sxs-lookup"><span data-stu-id="f9340-123">To add the reference, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
9. <span data-ttu-id="f9340-124">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="f9340-124">Click **OK**, and then click **OK** again.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9340-125">La cuenta que tiene privilegios de inicio de sesión para el servicio de BizTalk deben tener también permisos de acceso completo para la carpeta de recepción asociada a la ubicación de recepción fromTHEM_4010_850 ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations\fromTHEM).</span><span class="sxs-lookup"><span data-stu-id="f9340-125">The account that has log-on privileges for the BizTalk service should also be granted full access permissions for the receive folder associated with the fromTHEM_4010_850 receive location ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations\fromTHEM).</span></span> <span data-ttu-id="f9340-126">En caso contrario, recibirá un error al intentar habilitar la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="f9340-126">If not, you will receive an error when attempting to enable the receive location.</span></span> <span data-ttu-id="f9340-127">Para cambiar los permisos de acceso para la carpeta de recepción, vaya a la ficha seguridad en el **propiedades** cuadro de diálogo de esa carpeta en el Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="f9340-127">To change the access permissions for the receive folder, go to the Security tab in the **Properties** dialog box for that folder in Windows Explorer.</span></span>  
  
10. <span data-ttu-id="f9340-128">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **ubicaciones de recepción**, haga clic en **fromTHEM_4010_850**y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="f9340-128">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **Receive Locations**, right-click **fromTHEM_4010_850**, and then click **Enable**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f9340-129">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f9340-129">Next Steps</span></span>  
 <span data-ttu-id="f9340-130">Configurar el puerto de envío (**toOrderSystem**) para enviar el mensaje 850 a OrderSystem, como se describe en [paso 6: configurar un puerto de envío para enviar datos a la organización](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="f9340-130">You configure the send port (**toOrderSystem**) to send the 850 message to OrderSystem, as described in [Step 6: Configure a Send Port to Send Data to Your Organization](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9340-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9340-131">See Also</span></span>  
 [<span data-ttu-id="f9340-132">Configurar un puerto para recibir mensajes y confirmaciones EDI</span><span class="sxs-lookup"><span data-stu-id="f9340-132">Configuring a Port to Receive EDI Messages and Acknowledgments</span></span>](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)