---
title: Crear una A4SWIFT la ubicación de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
ms.assetid: 712cf42f-8d71-47e9-b2bf-3da158b74fe4
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11c77b7b28c65c4743998f7d4c54d9c7cd48437f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="creating-an-a4swift-receive-location"></a><span data-ttu-id="4b527-102">Crear una A4SWIFT la ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="4b527-102">Creating an A4SWIFT Receive Location</span></span>
<span data-ttu-id="4b527-103">Debe crear un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] ubicación de recepción para habilitar la recepción de mensajes de la red SWIFT mediante [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], tal y como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="4b527-103">You must create an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive location to enable message reception from the SWIFT network by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], as shown in the following figure.</span></span> <span data-ttu-id="4b527-104">La ubicación de recepción recibe mensajes de archivo sin formato desde una carpeta de archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="4b527-104">The receive location receives flat file messages from an inbound file folder.</span></span>  
  
 <span data-ttu-id="4b527-105">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-receive-location-configuration.gif "A4SWIFT_Receive_Location_Configuration")</span><span class="sxs-lookup"><span data-stu-id="4b527-105">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-receive-location-configuration.gif "A4SWIFT_Receive_Location_Configuration")</span></span>  
  
 <span data-ttu-id="4b527-106">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="4b527-106">**Summary**</span></span>  
  
 <span data-ttu-id="4b527-107">Crear y enlazar un puerto de recepción unidireccional y, a continuación, crear y habilitar una ubicación de recepción con las siguientes propiedades y los componentes:</span><span class="sxs-lookup"><span data-stu-id="4b527-107">Create and bind a one-way receive port, and then create and enable a receive location with the following properties and components:</span></span>  
  
|<span data-ttu-id="4b527-108">Propiedad/componentes</span><span class="sxs-lookup"><span data-stu-id="4b527-108">Property/Components</span></span>|<span data-ttu-id="4b527-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="4b527-109">Setting</span></span>|  
|--------------------------|-------------|  
|<span data-ttu-id="4b527-110">Puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="4b527-110">Receive port</span></span>|<span data-ttu-id="4b527-111">Puerto unidireccional</span><span class="sxs-lookup"><span data-stu-id="4b527-111">One-way port</span></span>|  
|<span data-ttu-id="4b527-112">Tipo de transporte</span><span class="sxs-lookup"><span data-stu-id="4b527-112">Transport type</span></span>|<span data-ttu-id="4b527-113">FILE</span><span class="sxs-lookup"><span data-stu-id="4b527-113">FILE</span></span>|  
|<span data-ttu-id="4b527-114">Dirección URI</span><span class="sxs-lookup"><span data-stu-id="4b527-114">Address URI</span></span>|<span data-ttu-id="4b527-115">Nombre de la carpeta que desea recibir el mensaje</span><span class="sxs-lookup"><span data-stu-id="4b527-115">Name of the folder that you want to receive the message</span></span>|  
|<span data-ttu-id="4b527-116">Máscara de archivo</span><span class="sxs-lookup"><span data-stu-id="4b527-116">File mask</span></span>|<span data-ttu-id="4b527-117">\*.  *\<extensión\>*, donde \< *extensión* \> es la extensión del entrante mensaje de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="4b527-117">\*.*\<extension\>*, where \<*extension*\> is the extension of the incoming flat file message</span></span>|  
|<span data-ttu-id="4b527-118">Controlador de recepción</span><span class="sxs-lookup"><span data-stu-id="4b527-118">Receive handler</span></span>|<span data-ttu-id="4b527-119">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="4b527-119">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="4b527-120">Canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="4b527-120">Receive pipeline</span></span>|<span data-ttu-id="4b527-121">El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de recepción que ha creado</span><span class="sxs-lookup"><span data-stu-id="4b527-121">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created</span></span>|  
  
### <a name="to-add-the-receive-port-and-location"></a><span data-ttu-id="4b527-122">Para agregar el puerto de recepción y ubicación</span><span class="sxs-lookup"><span data-stu-id="4b527-122">To add the receive port and location</span></span>  
  
1.  <span data-ttu-id="4b527-123">Iniciar **administración de BizTalk Server** consola.</span><span class="sxs-lookup"><span data-stu-id="4b527-123">Start **BizTalk Server Administration** console.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b527-124">La consola de administración de BizTalk Server también puede abrir desde dentro de Visual Studio, haga clic en **administración de BizTalk Server** en el **herramientas** menú.</span><span class="sxs-lookup"><span data-stu-id="4b527-124">The BizTalk Server Administration Console can also be opened from within Visual Studio by clicking **BizTalk Server Administration** in the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="4b527-125">En la consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **BizTalk Aplicación 1**.</span><span class="sxs-lookup"><span data-stu-id="4b527-125">In Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="4b527-126">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="4b527-126">Right-click **Receive Ports**, point to **New**, and then click **One-Way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="4b527-127">En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba un nombre para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="4b527-127">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port.</span></span>  
  
5.  <span data-ttu-id="4b527-128">Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b527-128">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="4b527-129">Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="4b527-129">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="4b527-130">En el, seleccione un cuadro de diálogo de puerto de recepción, haga clic en el puerto de recepción recién creado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b527-130">In the Select a Receive Port dialog box, click the receive port that you just created, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="4b527-131">En el cuadro de diálogo Propiedades de la ubicación de recepción, en el **nombre** , escriba un nombre para la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="4b527-131">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location.</span></span>  
  
9. <span data-ttu-id="4b527-132">En el **transporte** sección, para la **tipo** cuadro de texto, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="4b527-132">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
10. <span data-ttu-id="4b527-133">Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.</span><span class="sxs-lookup"><span data-stu-id="4b527-133">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
11. <span data-ttu-id="4b527-134">En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="4b527-134">In the FILE Transport Properties dialog box, click **Browse**.</span></span> <span data-ttu-id="4b527-135">Desplácese a la carpeta que desea recibir el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4b527-135">Move to the folder that you want to receive the message.</span></span> <span data-ttu-id="4b527-136">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b527-136">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b527-137">Si esta carpeta no existe, puede crearlo mediante el **crear nueva carpeta** comando.</span><span class="sxs-lookup"><span data-stu-id="4b527-137">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  
  
12. <span data-ttu-id="4b527-138">En el cuadro de diálogo Propiedades de transporte de archivo, en la **máscara de archivo** cuadro, escriba  **\*.\< *extensión*\>**, donde \< *extensión* \> es la extensión del entrante mensaje de archivo sin formato, como **.txt**.</span><span class="sxs-lookup"><span data-stu-id="4b527-138">In the FILE Transport Properties dialog box, in the **File Mask** box, enter **\*.\<*extension*\>**, where \<*extension*\> is the extension of the incoming flat file message, such as **.txt**.</span></span> <span data-ttu-id="4b527-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b527-139">Click **OK**.</span></span>  
  
13. <span data-ttu-id="4b527-140">En el cuadro de diálogo Propiedades de la ubicación de recepción, asegúrese de que **BizTalkServerApplication** se haya especificado para la **controlador de recepción** cuadro.</span><span class="sxs-lookup"><span data-stu-id="4b527-140">In the Receive Location Properties dialog box, ensure that **BizTalkServerApplication** is entered for the **Receive handler** box.</span></span>  
  
14. <span data-ttu-id="4b527-141">Para el **canalización de recepción** , seleccione la canalización de recepción personalizada de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4b527-141">For the **Receive Pipeline** box, select your custom receive pipeline from the drop-down list.</span></span>  
  
15. <span data-ttu-id="4b527-142">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b527-142">Click **Apply**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="4b527-143">En la consola de administración de BizTalk Server, haga clic en **ubicaciones de recepción**, haga clic en la ubicación de recepción recién creado y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="4b527-143">In the BizTalk Server Administration Console, click **Receive Locations**, right-click the receive location that you just created, and then click **Enable**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b527-144">Después de habilitar la ubicación de recepción, BizTalk sondea activamente la carpeta de archivos.</span><span class="sxs-lookup"><span data-stu-id="4b527-144">After you enable the receive location, BizTalk actively polls your file folder.</span></span>