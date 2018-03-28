---
title: 'Paso 10: Comprobar el escenario de extremo a extremo | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, verifying solution
ms.assetid: 24b74ba6-e303-4ab1-8a93-25a430e4894d
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d38f137625554bd689477964e3a969142eca0658
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="step-10-verify-the-end-to-end-scenario"></a><span data-ttu-id="6a183-102">Paso 10: Comprobar el escenario de extremo a extremo</span><span class="sxs-lookup"><span data-stu-id="6a183-102">Step 10: Verify the End-to-End Scenario</span></span>
<span data-ttu-id="6a183-103">En este paso, comprobará el escenario de extremo a extremo para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="6a183-103">In this step, you verify the end-to-end scenario for this tutorial.</span></span>  
  
### <a name="to-verify-the-end-to-end-tutorial-scenario"></a><span data-ttu-id="6a183-104">Para comprobar el escenario del tutorial-to-end</span><span class="sxs-lookup"><span data-stu-id="6a183-104">To verify the end-to-end tutorial scenario</span></span>  
  
1.  <span data-ttu-id="6a183-105">Haga clic en **iniciar**, seleccione **programas**, seleccione **Accesorios**y, a continuación, haga clic en **símbolo**.</span><span class="sxs-lookup"><span data-stu-id="6a183-105">Click **Start**, point to **Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="6a183-106">En la ventana de símbolo del sistema, vaya a  **\< *unidad*\>: \Program BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="6a183-106">In the Command Prompt window, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6a183-107">Si no se encuentra una carpeta de utilidades de MLLP bajo la carpeta del SDK, es podrán que no esté instaladas las herramientas de prueba MLLP.</span><span class="sxs-lookup"><span data-stu-id="6a183-107">If you cannot find an MLLP Utilities folder under the SDK folder, the MLLP test tools may not be installed.</span></span> <span data-ttu-id="6a183-108">Abra el Panel de Control y, a continuación, abra **agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="6a183-108">Open the Control Panel, and then open **Add or Remove Programs**.</span></span> <span data-ttu-id="6a183-109">Seleccione **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, seleccione **cambio**.</span><span class="sxs-lookup"><span data-stu-id="6a183-109">Select **Microsoft BizTalk \<version\> Accelerator for HL7**, and then select **Change**.</span></span> <span data-ttu-id="6a183-110">En el Asistente para la instalación de BTAHL7, seleccione **modificar**.</span><span class="sxs-lookup"><span data-stu-id="6a183-110">In the BTAHL7 setup wizard, select **Modify**.</span></span> <span data-ttu-id="6a183-111">Expanda el **adaptador** carpeta para ver si el **herramienta de prueba de MLLP** se ha instalado.</span><span class="sxs-lookup"><span data-stu-id="6a183-111">Expand the **Adapter** folder to see whether the **MLLP Test Tool** has been installed.</span></span> <span data-ttu-id="6a183-112">Si no es así, instalarlo.</span><span class="sxs-lookup"><span data-stu-id="6a183-112">If not, install it.</span></span>  
  
3.  <span data-ttu-id="6a183-113">En la ventana de símbolo del sistema, escriba **mllpreceive /p 14000**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="6a183-113">In the Command Prompt window, type **mllpreceive /p 14000**, and then press **Enter**.</span></span> <span data-ttu-id="6a183-114">Esto ejecuta la aplicación de agente de escucha MLLP escuchando al puerto 14000 y especificar los caracteres EB, SB y CR predeterminado del mensaje MLLP y muestra cualquier mensaje recibido en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="6a183-114">This runs the MLLP listener application listening to port 14000 and specifying the default EB, SB, and CR characters of the MLLP message, and displays any messages received to the screen.</span></span>  
  
4.  <span data-ttu-id="6a183-115">Inicie un símbolo del sistema adicional haciendo clic en **iniciar**, seleccione **programas**, seleccione **Accesorios**y, a continuación, haga clic en **símbolo**.</span><span class="sxs-lookup"><span data-stu-id="6a183-115">Start an additional command prompt by clicking **Start**, point to **Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
5.  <span data-ttu-id="6a183-116">En la segunda ventana de símbolo del sistema, vaya a  **\< *unidad*\>: \Program BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="6a183-116">In the second Command Prompt window, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6a183-117">El paso siguiente, envía el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6a183-117">The following step sends the message.</span></span>  
  
6.  <span data-ttu-id="6a183-118">En la ventana de símbolo del sistema, escriba **mllpsend/SB 11 /EB 28 /CR 13/f "\<*unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\SDK\ To-End Tutorial\ADT ^ A03.txt "**, donde \< *unidad* \> es la letra de unidad de instalación.</span><span class="sxs-lookup"><span data-stu-id="6a183-118">In the Command Prompt window, type **mllpsend /SB 11 /EB 28 /CR 13 /f "\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\ADT^A03.txt"**, where \<*drive*\> is your installation drive letter.</span></span> <span data-ttu-id="6a183-119">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="6a183-119">Press **Enter**.</span></span>  
  
7.  <span data-ttu-id="6a183-120">Compruebe que dispone de los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="6a183-120">Verify that you have the following results:</span></span>  
  
    -   <span data-ttu-id="6a183-121">La aplicación de agente de escucha MLLP debe mostrar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="6a183-121">The MLLP listener application should display a message.</span></span> <span data-ttu-id="6a183-122">La primera línea del mensaje debe tener los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="6a183-122">The first line of the message should have the following values:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7^IE^UUID|MCM|HI^System^GUID||199601121005||ADT^A04|000001|P|2.4|||SU|NE  
        ```  
  
    -   <span data-ttu-id="6a183-123">Aparece un mensaje en \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para Tutorial\Tutorial_sendMsg_RX HL7\SDK\End-to-End.</span><span class="sxs-lookup"><span data-stu-id="6a183-123">A message appears in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendMsg_RX.</span></span> <span data-ttu-id="6a183-124">Este mensaje debe ser el mismo que el mensaje que se muestra en la aplicación de agente de escucha MLLP.</span><span class="sxs-lookup"><span data-stu-id="6a183-124">This message should be the same as the message shown by the MLLP listener application.</span></span> <span data-ttu-id="6a183-125">Compruebe que la primera línea del mensaje tiene los mismos valores de mensaje como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="6a183-125">Verify that the first line of the message has the same message values as follows.</span></span> <span data-ttu-id="6a183-126">Tenga en cuenta que los valores de MSH3 un nd MSH5 en el código siguiente coinciden con los valores especificados para el Tutorial_RXSystem:</span><span class="sxs-lookup"><span data-stu-id="6a183-126">Note that the values for MSH3 a nd MSH5 in the following code match the values you specified for the Tutorial_RXSystem:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7|MCM|Tutorial_RXSystem||199601121005||ADT^A03|000001|P|2.3.1  
        ```  
  
    -   <span data-ttu-id="6a183-127">Aparecen dos mensajes en \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para Tutorial\Tutorial_sendAck_ADT HL7\SDK\End-to-End.</span><span class="sxs-lookup"><span data-stu-id="6a183-127">Two messages appear in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT.</span></span> <span data-ttu-id="6a183-128">Uno de estos mensajes es una confirmación de la aplicación; el otro es una confirmación de confirmación.</span><span class="sxs-lookup"><span data-stu-id="6a183-128">One of these messages is an application acknowledgment; the other is a commit acknowledgment.</span></span> <span data-ttu-id="6a183-129">La confirmación de la aplicación debe tener el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="6a183-129">The application acknowledgment should have the following content:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|000001|P|2.3.1|||AL  
        MSA|AA|000001  
        ```  
  
    -   <span data-ttu-id="6a183-130">La confirmación de confirmación debe tener el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="6a183-130">The commit acknowledgment should have the following content:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|100000|P|2.3.1  
        MSA|CA|000001  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="6a183-131">Si los mensajes no aparecen correctamente, utilice la herramienta de mantenimiento y seguimiento de actividad (HAT) para solucionar el error.</span><span class="sxs-lookup"><span data-stu-id="6a183-131">If the messages do not appear correctly, use the Health and Activity Tracking (HAT) tool to troubleshoot the error.</span></span>  
  
 <span data-ttu-id="6a183-132">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="6a183-132">Congratulations!</span></span> <span data-ttu-id="6a183-133">Ha completado correctamente el Tutorial de BTAHL7-to-End.</span><span class="sxs-lookup"><span data-stu-id="6a183-133">You have successfully completed the BTAHL7 End-to-End Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a183-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a183-134">See Also</span></span>  
 [<span data-ttu-id="6a183-135">Tutorial integral</span><span class="sxs-lookup"><span data-stu-id="6a183-135">End-to-End Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)