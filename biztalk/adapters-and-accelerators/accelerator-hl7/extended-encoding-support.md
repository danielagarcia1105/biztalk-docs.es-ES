---
title: "Compatibilidad con codificación extendidos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93a40fa6-d0da-416e-97fb-675ddde3f005
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e36c3baff4ac33f2878295791bb3f6615c1b25d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="extended-encoding-support"></a><span data-ttu-id="2c211-102">Soporte extendido de codificación</span><span class="sxs-lookup"><span data-stu-id="2c211-102">Extended Encoding Support</span></span>
<span data-ttu-id="2c211-103">De forma predeterminada, se reciben el HL7 canalización, BTAHL72X, solo admite la codificación ASCII.</span><span class="sxs-lookup"><span data-stu-id="2c211-103">By default, the HL7 receive pipeline, BTAHL72X, only supports ASCII encoding.</span></span> <span data-ttu-id="2c211-104">Esto significa que todos los caracteres de un mensaje de entrada con un valor equivalente mayor que 127 se reemplazan con "?".</span><span class="sxs-lookup"><span data-stu-id="2c211-104">This means that any characters in an input message with an equivalent value greater than 127 are replaced with "?".</span></span> <span data-ttu-id="2c211-105">Esto es porque no se representan caracteres con un valor equivalente superior a 127 en el juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="2c211-105">This is because characters with an equivalent value greater than 127 are not represented in the ASCII character set.</span></span>  
  
 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]<span data-ttu-id="2c211-106">proporciona compatibilidad para las dos codificaciones nueva:</span><span class="sxs-lookup"><span data-stu-id="2c211-106"> provides support for two new encodings:</span></span>  
  
-   <span data-ttu-id="2c211-107">Europeo occidental</span><span class="sxs-lookup"><span data-stu-id="2c211-107">Western European</span></span>  
  
-   <span data-ttu-id="2c211-108">UTF-8</span><span class="sxs-lookup"><span data-stu-id="2c211-108">UTF-8</span></span>  
  
 <span data-ttu-id="2c211-109">Crear y compilar un componente de canalización personalizado para implementar el soporte extendido de codificación.</span><span class="sxs-lookup"><span data-stu-id="2c211-109">You create and build a custom pipeline component to implement extended encoding support.</span></span> <span data-ttu-id="2c211-110">El componente de canalización personalizada utiliza el BTAHL7 2.X Desensamblador.</span><span class="sxs-lookup"><span data-stu-id="2c211-110">The custom pipeline component uses the BTAHL7 2.X Disassembler.</span></span> <span data-ttu-id="2c211-111">Crear una ubicación de recepción que usa la canalización personalizada para procesar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="2c211-111">You create a receive location that uses the custom pipeline to process messages.</span></span> <span data-ttu-id="2c211-112">Para probar la ubicación de recepción y una canalización personalizada, cree un puerto de envío que usa el 2.XSendPipeline BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="2c211-112">To test the receive location and custom pipeline, you create a send port that uses the BTAHL7 2.XSendPipeline.</span></span>  
  
### <a name="to-create-a-custom-pipeline"></a><span data-ttu-id="2c211-113">Para crear una canalización personalizada</span><span class="sxs-lookup"><span data-stu-id="2c211-113">To create a custom pipeline</span></span>  
  
1.  <span data-ttu-id="2c211-114">En [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], agregue un nuevo **proyecto vacío de servidor BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="2c211-114">In [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], add a new **Empty BizTalk Server Project**.</span></span>  
  
2.  <span data-ttu-id="2c211-115">En el Explorador de soluciones, haga clic en el nuevo proyecto, haga clic en **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2c211-115">In Solution Explorer, right-click the new project, click **Add**, and then click **New Item**.</span></span>  
  
3.  <span data-ttu-id="2c211-116">En el **Agregar nuevo elemento** diálogo cuadro, agregue un nuevo **canalización de recepción**.</span><span class="sxs-lookup"><span data-stu-id="2c211-116">In the **Add New Item** dialog box, add a new **Receive Pipeline**.</span></span>  
  
4.  <span data-ttu-id="2c211-117">En el cuadro de herramientas de canalización, arrastre el **BTAHL7 2.X Desensamblador** en el editor de canalizaciones y colóquela sobre la **desensamblar** fase **Coloque aquí** destino.</span><span class="sxs-lookup"><span data-stu-id="2c211-117">From the pipeline toolbox, drag the **BTAHL7 2.X Disassembler** to the pipeline editor and drop it onto the **Disassemble** stage **Drop Here** target.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c211-118">Si el Desensamblador de 2.7 BTAHL7 no está en el cuadro de herramientas, haga clic en el cuadro de herramientas y haga clic en **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="2c211-118">If the BTAHL7 2.7 Disassembler is not in the toolbox, right-click in the toolbox, and click **Choose Items**.</span></span> <span data-ttu-id="2c211-119">En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, en la **componente de canalización de BizTalk** ficha, seleccione la **BTAHL7 2.X Desensamblador** casilla de verificación y, a continuación, haga clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="2c211-119">In the **Choose Toolbox Items** dialog box, on the **BizTalk Pipeline Component** tab, select the **BTAHL7 2.X Disassembler** check box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="2c211-120">En el panel de propiedades para el **BTAHL7 2.X Desensamblador**, desde el **juego de caracteres de codificación** lista desplegable, seleccione **Europeo occidental** o **UTF8**codificación.</span><span class="sxs-lookup"><span data-stu-id="2c211-120">In the Properties pane for the **BTAHL7 2.X Disassembler**, from the **Encoding charset** drop-down list, select **Western European** or **UTF8** encoding.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c211-121">HL7 solo es compatible con ASCII (valor predeterminado), Europa occidental y codificación UTF8.</span><span class="sxs-lookup"><span data-stu-id="2c211-121">HL7 only supports ASCII (the default), Western European, and UTF8 encoding.</span></span> <span data-ttu-id="2c211-122">No seleccione las opciones de codificación porque no es compatible con HL7.</span><span class="sxs-lookup"><span data-stu-id="2c211-122">Do not select the other encoding options because HL7 does not support them.</span></span>  
  
6.  <span data-ttu-id="2c211-123">En el menú **Archivo** , haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="2c211-123">On the **File** menu, click **Save All**.</span></span>  
  
7.  <span data-ttu-id="2c211-124">Implemente el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2c211-124">Deploy the project.</span></span>  
  
     <span data-ttu-id="2c211-125">Crear una nueva ubicación de recepción para continuar.</span><span class="sxs-lookup"><span data-stu-id="2c211-125">Create a new receive location to continue.</span></span>  
  
### <a name="to-create-a-receive-location-that-uses-the-custom-pipeline"></a><span data-ttu-id="2c211-126">Para crear una ubicación de recepción que usa la canalización personalizada</span><span class="sxs-lookup"><span data-stu-id="2c211-126">To create a receive location that uses the custom pipeline</span></span>  
  
1.  <span data-ttu-id="2c211-127">En el **iniciar** menú, haga clic en **programas**, seleccione [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2c211-127">On the **Start** menu, click **Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2c211-128">En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda la aplicación designado para el ensamblado de canalización (de forma predeterminada, **BizTalk Application 1**), haga clic en **ubicaciones de recepción**, seleccione **nuevo**y, a continuación, haga clic en **Unidireccional ubicación de recepción**.</span><span class="sxs-lookup"><span data-stu-id="2c211-128">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand the application you designated for your pipeline assembly (by default, **BizTalk Application 1**), right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
3.  <span data-ttu-id="2c211-129">En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **canalización de recepción** lista de lista desplegable, seleccione el nombre de la opción de instalación de canalización que ha creado.</span><span class="sxs-lookup"><span data-stu-id="2c211-129">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, select the name of the custom pipeline you created.</span></span> <span data-ttu-id="2c211-130">(Este es el nombre del objeto de canalización personalizado, no el BTAHL7 de canalización de 2 X.)</span><span class="sxs-lookup"><span data-stu-id="2c211-130">(This is the name of the custom pipeline object, not the BTAHL7 2X pipeline.)</span></span>  
  
### <a name="to-create-a-send-port-to-test-the-receive-location-and-pipeline"></a><span data-ttu-id="2c211-131">Para crear un puerto de envío para probar la ubicación de recepción y una canalización</span><span class="sxs-lookup"><span data-stu-id="2c211-131">To create a send port to test the receive location and pipeline</span></span>  
  
1.  <span data-ttu-id="2c211-132">En el **iniciar** menú, haga clic en **programas**, seleccione [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2c211-132">On the **Start** menu, click **Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2c211-133">En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda la aplicación designado para el ensamblado de canalización (de forma predeterminada, **BizTalk Application 1**), haga clic en **puertos de envío**, seleccione **nuevo**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="2c211-133">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand the application you designated for your pipeline assembly (by default, **BizTalk Application 1**), right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="2c211-134">En el **propiedades de puerto de envío** cuadro de diálogo, en la **canalización de envío** lista desplegable, seleccione **BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="2c211-134">In the **Send Port Properties** dialog box, in the **Send pipeline** drop-down list, select **BTAHL72XSendPipeline**.</span></span>  
  
### <a name="to-test-the-receive-location-and-pipeline"></a><span data-ttu-id="2c211-135">Para probar la ubicación de recepción y una canalización</span><span class="sxs-lookup"><span data-stu-id="2c211-135">To test the receive location and pipeline</span></span>  
  
-   <span data-ttu-id="2c211-136">Coloque un archivo que contiene caracteres especiales y se guarda con la misma codificación que especificó en la canalización personalizada en la ubicación designada en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="2c211-136">Drop a file containing special characters and saved with the same encoding you specified in the custom pipeline into the location designated in the receive location.</span></span> <span data-ttu-id="2c211-137">El archivo en la ubicación de salida debe conservar los caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="2c211-137">The file at the output location should preserve the special characters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c211-138">Si intenta procesar un archivo que utiliza una codificación no admitidos (Recuerde que solo ASCII, Europeo occidental o UTF8 son compatibles), se registra un error en el Visor de eventos de aplicación con el Id. de error: 5633.</span><span class="sxs-lookup"><span data-stu-id="2c211-138">If you attempt to process a file that uses a non-supported encoding (remember that only ASCII, Western European, and UTF8 are supported), an error is logged in the Application Event Viewer with error ID: 5633.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c211-139">Si va a probar una canalización personalizada que se configura para la codificación UTF8, debe adjuntar caracteres de marca de orden de bytes (BOM) para el mensaje que se pasa.</span><span class="sxs-lookup"><span data-stu-id="2c211-139">If you are testing a custom pipeline configured for UTF8 encoding, you should attach Byte Order Mark (BOM) characters to the message you are passing.</span></span> <span data-ttu-id="2c211-140">Si va a probar una canalización personalizada que se configura para la codificación de Europa occidental, no conecte caracteres de la lista de materiales.</span><span class="sxs-lookup"><span data-stu-id="2c211-140">If you are testing a custom pipeline configured for Western European encoding, do not attach BOM characters.</span></span>