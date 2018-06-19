---
title: 'Paso 18: Probar la nueva solución de enriquecimiento de mensajes | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, testing solution
ms.assetid: 233fbf79-0ab1-4064-b828-6bbbb56cbec2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 035925684617e74608246aed99fa98e16d0668a4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25960426"
---
# <a name="step-18-test-your-new-message-enrichment-solution"></a><span data-ttu-id="e8a64-102">Paso 18: Probar la nueva solución de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="e8a64-102">Step 18: Test Your New Message Enrichment Solution</span></span>
<span data-ttu-id="e8a64-103">En este paso, probará la solución mediante la aplicación WSClient para enviar un mensaje a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y ver si la aplicación MLLPReceive recibe un mensaje con formato HL7 según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="e8a64-103">In this step, you test your solution by using the WSClient application to send a message to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and seeing if the MLLPReceive application receives an HL7-formatted message as expected.</span></span>  
  
### <a name="to-test-your-solution"></a><span data-ttu-id="e8a64-104">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="e8a64-104">To test your solution</span></span>  
  
1.  <span data-ttu-id="e8a64-105">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e8a64-105">Open a command prompt.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8a64-106">Paso 2 requiere que se haya instalado la herramienta de prueba de MLLP mediante el procedimiento de instalación personalizada.</span><span class="sxs-lookup"><span data-stu-id="e8a64-106">Step 2 requires that you have installed the MLLP Test tool using the custom installation procedure.</span></span> <span data-ttu-id="e8a64-107">Si las utilidades \MLLP directorio que contiene MllpReceive.exe y MllpSend.exe no existe en el equipo, instálelos mediante la realización de una instalación personalizada.</span><span class="sxs-lookup"><span data-stu-id="e8a64-107">If the \MLLP Utilities directory containing MllpReceive.exe and MllpSend.exe does not exist on your computer, install them by performing a custom installation.</span></span> <span data-ttu-id="e8a64-108">Para obtener información, consulte [realizar una instalación personalizada](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span><span class="sxs-lookup"><span data-stu-id="e8a64-108">For information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
2.  <span data-ttu-id="e8a64-109">En el símbolo del sistema, escriba **cd \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP** () donde \< *unidad* \> es la letra de unidad de instalación) y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="e8a64-109">At the command prompt, type **cd \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities** (where \<*drive*\> is your installation drive letter), and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="e8a64-110">En el símbolo del sistema, escriba **mllpreceive /p 11000 /eb 11/SB 28 /cr 13**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="e8a64-110">At the command prompt, type **mllpreceive /p 11000 /eb 11 /sb 28 /cr 13**, and then press **Enter**.</span></span> <span data-ttu-id="e8a64-111">Esto ejecuta la aplicación de agente de escucha MLLP escuchando al puerto 11000 y especificar los caracteres EB, SB y CR predeterminado del mensaje MLLP y muestra cualquier mensaje recibido en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="e8a64-111">This runs the MLLP listener application listening to port 11000 and specifying the default EB, SB, and CR characters of the MLLP message, and displays any messages received to the screen.</span></span>  
  
4.  <span data-ttu-id="e8a64-112">Abra una segunda línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e8a64-112">Open a second command prompt.</span></span>  
  
5.  <span data-ttu-id="e8a64-113">En el símbolo del sistema, escriba **cd \< *unidad*\>: \Tutorial\WSClient\bin\Debug**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="e8a64-113">At the command prompt, type **cd \<*drive*\>:\Tutorial\WSClient\bin\Debug**, and then press **Enter**.</span></span>  
  
6.  <span data-ttu-id="e8a64-114">En el símbolo del sistema, escriba **smith henry de john wsclient 123456789**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="e8a64-114">At the command prompt, type **wsclient john henry smith 123456789**, and then press **Enter**.</span></span> <span data-ttu-id="e8a64-115">Esto envía un mensaje al servicio Web que contiene un mensaje de ejemplo con el nombre de un paciente de John Henry Smith y un número de seguridad social de ejemplo de 123456789.</span><span class="sxs-lookup"><span data-stu-id="e8a64-115">This sends a message to the Web service that contains a sample message with a patient name of John Henry Smith and a sample social security number of 123456789.</span></span>  
  
7.  <span data-ttu-id="e8a64-116">Tras una breve pausa, la aplicación MLLPReceive muestra el mensaje entrante de MLLP.</span><span class="sxs-lookup"><span data-stu-id="e8a64-116">After a short pause, the MLLPReceive application displays the incoming MLLP message.</span></span> <span data-ttu-id="e8a64-117">El mensaje debe ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8a64-117">The message should look similar to the following:</span></span>  
  
    ```  
    MSH|^~\&|TestTrailing^Delimiters|srcFac^srcFacUid|dstApp^dstAppUid|dstFac^dstFacUid|200307092343|sec|ADT^A04|msgid2134|P|2.2PID|||123456789||smith^john  
    ```  
  
     <span data-ttu-id="e8a64-118">Si no recibe una respuesta después de unos minutos, debe comprobar el registro de eventos de aplicación para los errores y empezar a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="e8a64-118">If you do not receive a response after a few minutes, you should check the Application event log for any errors and begin troubleshooting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a64-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8a64-119">See Also</span></span>  
 [<span data-ttu-id="e8a64-120">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="e8a64-120">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)