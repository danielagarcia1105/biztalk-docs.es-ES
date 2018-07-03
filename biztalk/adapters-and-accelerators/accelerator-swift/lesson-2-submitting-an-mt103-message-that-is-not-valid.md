---
title: 'Lección 2: Enviar un mensaje MT103 que no es válido | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, invalid messages
- submitting, invalid messages
- submitting, MT103 messages
- MT103 messages
- messages, MT103 messages
ms.assetid: 4b070ae1-c400-421a-b2f6-b7b1f22c0e41
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cb8f0539f3a832e3b54a6fa45b300558a8e39a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014885"
---
# <a name="lesson-2-submitting-an-mt103-message-that-is-not-valid"></a><span data-ttu-id="da3da-102">Lección 2: Enviar un mensaje MT103 que no es válido</span><span class="sxs-lookup"><span data-stu-id="da3da-102">Lesson 2: Submitting an MT103 Message That Is Not Valid</span></span>
<span data-ttu-id="da3da-103">En esta lección, envíe un mensaje MT103 que no es válido y, a continuación, solucionar el error resultante mediante las herramientas del sistema.</span><span class="sxs-lookup"><span data-stu-id="da3da-103">In this lesson, you submit an MT103 message that is not valid and then you troubleshoot the resulting error using your System Tools.</span></span>  
  
### <a name="to-submit-an-mt103-message-that-is-not-valid"></a><span data-ttu-id="da3da-104">Para enviar un mensaje MT103 que no es válido</span><span class="sxs-lookup"><span data-stu-id="da3da-104">To submit an MT103 message that is not valid</span></span>  
  
1. <span data-ttu-id="da3da-105">Copie el archivo MT103_Invalid_Sample.txt desde \< *unidad:*\>\Program Files\Microsoft Acelerador de BizTalk para SWIFT\SDK\Tutorial a \< *unidad* \>: Carpeta \Labs\Inbound\FlatFile.</span><span class="sxs-lookup"><span data-stu-id="da3da-105">Copy the file MT103_Invalid_Sample.txt from \<*drive:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial to \<*drive*\>:\Labs\Inbound\FlatFile folder.</span></span> <span data-ttu-id="da3da-106">Tenga en cuenta el tiempo que coloque el archivo en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="da3da-106">Note the time that you drop the file into the folder.</span></span>  
  
2. <span data-ttu-id="da3da-107">Abra \< *unidad:*\>\Labs\Outbound para comprobar que ningún archivo XML correspondiente a MT103_Invalid_Sample.txt está en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="da3da-107">Open \<*drive:*\>\Labs\Outbound to verify that no XML file corresponding to MT103_Invalid_Sample.txt is in the folder.</span></span> <span data-ttu-id="da3da-108">(El archivo XML correspondiente al mensaje MT103_Sample.txt válido debe ser todavía en esa carpeta.)</span><span class="sxs-lookup"><span data-stu-id="da3da-108">(The XML file corresponding to the valid MT103_Sample.txt message should still be in that folder.)</span></span>  
  
3. <span data-ttu-id="da3da-109">En el Bloc de notas, abra el archivo MT103_Invalid_Sample.txt en \< *unidad:*\>\Program Files\Microsoft Acelerador de BizTalk para SWIFT\SDK\Tutorial.</span><span class="sxs-lookup"><span data-stu-id="da3da-109">In Notepad, open the file MT103_Invalid_Sample.txt in \<*drive:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial.</span></span>  
  
4. <span data-ttu-id="da3da-110">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="da3da-110">Start **BizTalk Server Administration**.</span></span>  
  
5. <span data-ttu-id="da3da-111">En la consola de administración de BizTalk Server, expanda **Visor de eventos (Local)** y, a continuación, haga clic en **aplicación**.</span><span class="sxs-lookup"><span data-stu-id="da3da-111">In the BizTalk Server Administration Console, expand **Event Viewer (Local)**, and then click **Application**.</span></span>  
  
6. <span data-ttu-id="da3da-112">Busque una entrada de error que tiene un origen del Acelerador de BizTalk para SWIFT y una hora que corresponde a cuando se quita el mensaje no válido en el \< *unidad*\>: carpeta \Labs\Inbound\FlatFile.</span><span class="sxs-lookup"><span data-stu-id="da3da-112">Look for an error entry that has a source of BizTalk Accelerator for SWIFT and a time that corresponds to when you dropped the invalid message into the \<*drive*\>:\Labs\Inbound\FlatFile folder.</span></span> <span data-ttu-id="da3da-113">Haga doble clic en esa entrada de error.</span><span class="sxs-lookup"><span data-stu-id="da3da-113">Double-click that error entry.</span></span>  
  
7. <span data-ttu-id="da3da-114">En el cuadro de diálogo Propiedades de evento para el error, compruebe en el panel de descripción que se publicó el mensaje con errores en el cuadro de mensajes y que marca el Desensamblador de SWIFT **A4SWIFT_Failed** como **True**.</span><span class="sxs-lookup"><span data-stu-id="da3da-114">In the Event Properties dialog box for the error, verify in the Description pane that the failed message was published to the MessageBox and that the SWIFT Disassembler marked **A4SWIFT_Failed** as **True**.</span></span> <span data-ttu-id="da3da-115">Cierre el cuadro de diálogo Propiedades de evento.</span><span class="sxs-lookup"><span data-stu-id="da3da-115">Close the Event Properties dialog box.</span></span>  
  
8. <span data-ttu-id="da3da-116">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**y, a continuación, expanda **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="da3da-116">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, and then expand **BizTalk Group**.</span></span> <span data-ttu-id="da3da-117">En el **vista** menú, haga clic en **página concentrador de grupo**.</span><span class="sxs-lookup"><span data-stu-id="da3da-117">In the **View** menu, click **Group Hub Page**.</span></span>  
  
9. <span data-ttu-id="da3da-118">En el **información general del grupo** panel, en el **instancias de servicio suspendidas agrupadas** panel, haga clic en **agrupadas por aplicación**.</span><span class="sxs-lookup"><span data-stu-id="da3da-118">In the **Group Overview** pane, in the **Grouped Suspended Service Instances** pane, click **Grouped by Application**.</span></span>  
  
10. <span data-ttu-id="da3da-119">En el **vista previa del resultado de la consulta seleccionada** panel, haga doble clic en la entrada de **MT103_FlatFile_ReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="da3da-119">In the **Preview for the selected query result** pane, double-click the entry for **MT103_FlatFile_ReceivePort**.</span></span>  
  
11. <span data-ttu-id="da3da-120">En el cuadro de diálogo Detalles del servicio, haga clic en el **mensajes** ficha. Haga doble clic en la entrada para el que es el nombre del servicio **MT103_FlatFile_ReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="da3da-120">In the Service Details dialog box, click the **Messages** tab. Double-click the entry for which the Service Name is **MT103_FlatFile_ReceivePort**.</span></span>  
  
12. <span data-ttu-id="da3da-121">En el cuadro de diálogo Detalles del mensaje, haga clic en **cuerpo** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="da3da-121">In the Message Details dialog box, click **Body** in the left pane.</span></span>  
  
13. <span data-ttu-id="da3da-122">Compruebe que el mensaje que se muestra en el panel del cuerpo del cuadro de diálogo Detalles del mensaje se corresponde con MT103_Invalid_Sample.txt que abrió en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="da3da-122">Verify that the message displayed in the body pane of the Message Details dialog box corresponds to MT103_Invalid_Sample.txt that you opened in Notepad.</span></span>  
  
    <span data-ttu-id="da3da-123">Continúe con [lección 3: probar una instancia XML](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md).</span><span class="sxs-lookup"><span data-stu-id="da3da-123">Proceed to [Lesson 3: Testing an XML Instance](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md).</span></span>