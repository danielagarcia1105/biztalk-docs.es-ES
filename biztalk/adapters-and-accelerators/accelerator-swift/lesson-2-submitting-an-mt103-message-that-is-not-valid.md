---
title: 'Lección 2: Enviar un mensaje de MT103 que no es válido | Documentos de Microsoft'
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
ms.openlocfilehash: d064c06aec2698da1be3824ec709dac1702f8e40
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961298"
---
# <a name="lesson-2-submitting-an-mt103-message-that-is-not-valid"></a><span data-ttu-id="11548-102">Lección 2: Enviar un mensaje de MT103 que no es válido</span><span class="sxs-lookup"><span data-stu-id="11548-102">Lesson 2: Submitting an MT103 Message That Is Not Valid</span></span>
<span data-ttu-id="11548-103">En esta lección, se envía un mensaje de MT103 que no es válido y, a continuación, solucionar el error resultante mediante sus herramientas de sistema.</span><span class="sxs-lookup"><span data-stu-id="11548-103">In this lesson, you submit an MT103 message that is not valid and then you troubleshoot the resulting error using your System Tools.</span></span>  
  
### <a name="to-submit-an-mt103-message-that-is-not-valid"></a><span data-ttu-id="11548-104">Para enviar un mensaje de MT103 que no es válido</span><span class="sxs-lookup"><span data-stu-id="11548-104">To submit an MT103 message that is not valid</span></span>  
  
1.  <span data-ttu-id="11548-105">Copie el archivo MT103_Invalid_Sample.txt de \< *unidad:*\>\Program Acelerador de BizTalk para SWIFT\SDK\Tutorial a \< *unidad* \>: \Labs\Inbound\FlatFile carpeta.</span><span class="sxs-lookup"><span data-stu-id="11548-105">Copy the file MT103_Invalid_Sample.txt from \<*drive:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial to \<*drive*\>:\Labs\Inbound\FlatFile folder.</span></span> <span data-ttu-id="11548-106">Tenga en cuenta el tiempo que coloque el archivo en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="11548-106">Note the time that you drop the file into the folder.</span></span>  
  
2.  <span data-ttu-id="11548-107">Abra \< *unidad:*\>\Labs\Outbound para comprobar que ningún archivo XML correspondiente a MT103_Invalid_Sample.txt está en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="11548-107">Open \<*drive:*\>\Labs\Outbound to verify that no XML file corresponding to MT103_Invalid_Sample.txt is in the folder.</span></span> <span data-ttu-id="11548-108">(El archivo XML correspondiente al mensaje MT103_Sample.txt válido todavía debería en esa carpeta.)</span><span class="sxs-lookup"><span data-stu-id="11548-108">(The XML file corresponding to the valid MT103_Sample.txt message should still be in that folder.)</span></span>  
  
3.  <span data-ttu-id="11548-109">En el Bloc de notas, abra el archivo MT103_Invalid_Sample.txt en \< *unidad:*\>\Program Acelerador de BizTalk para SWIFT\SDK\Tutorial.</span><span class="sxs-lookup"><span data-stu-id="11548-109">In Notepad, open the file MT103_Invalid_Sample.txt in \<*drive:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial.</span></span>  
  
4.  <span data-ttu-id="11548-110">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="11548-110">Start **BizTalk Server Administration**.</span></span>  
  
5.  <span data-ttu-id="11548-111">En la consola de administración de BizTalk Server, expanda **Visor de eventos (Local)** y, a continuación, haga clic en **aplicación**.</span><span class="sxs-lookup"><span data-stu-id="11548-111">In the BizTalk Server Administration Console, expand **Event Viewer (Local)**, and then click **Application**.</span></span>  
  
6.  <span data-ttu-id="11548-112">Busque una entrada de error que tenga un origen de Acelerador de BizTalk para SWIFT y una hora que corresponde a cuando se quita el mensaje no válido en el \< *unidad*\>: \Labs\Inbound\FlatFile carpeta.</span><span class="sxs-lookup"><span data-stu-id="11548-112">Look for an error entry that has a source of BizTalk Accelerator for SWIFT and a time that corresponds to when you dropped the invalid message into the \<*drive*\>:\Labs\Inbound\FlatFile folder.</span></span> <span data-ttu-id="11548-113">Haga doble clic en esa entrada de error.</span><span class="sxs-lookup"><span data-stu-id="11548-113">Double-click that error entry.</span></span>  
  
7.  <span data-ttu-id="11548-114">En el cuadro de diálogo Propiedades de evento para el error, compruebe en el panel de descripción que se publicó el mensaje con errores en el cuadro de mensajes y que marca el Desensamblador de SWIFT **A4SWIFT_Failed** como **True**.</span><span class="sxs-lookup"><span data-stu-id="11548-114">In the Event Properties dialog box for the error, verify in the Description pane that the failed message was published to the MessageBox and that the SWIFT Disassembler marked **A4SWIFT_Failed** as **True**.</span></span> <span data-ttu-id="11548-115">Cierre el cuadro de diálogo de propiedades de evento.</span><span class="sxs-lookup"><span data-stu-id="11548-115">Close the Event Properties dialog box.</span></span>  
  
8.  <span data-ttu-id="11548-116">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**y, a continuación, expanda **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="11548-116">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, and then expand **BizTalk Group**.</span></span> <span data-ttu-id="11548-117">En el **vista** menú, haga clic en **página concentrador de grupo**.</span><span class="sxs-lookup"><span data-stu-id="11548-117">In the **View** menu, click **Group Hub Page**.</span></span>  
  
9. <span data-ttu-id="11548-118">En el **información general del grupo** panel, en la **instancias de servicio suspendidas agrupadas** panel, haga clic en **agrupados por la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="11548-118">In the **Group Overview** pane, in the **Grouped Suspended Service Instances** pane, click **Grouped by Application**.</span></span>  
  
10. <span data-ttu-id="11548-119">En el **vista previa del resultado de la consulta seleccionada** panel, haga doble clic en la entrada de **MT103_FlatFile_ReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="11548-119">In the **Preview for the selected query result** pane, double-click the entry for **MT103_FlatFile_ReceivePort**.</span></span>  
  
11. <span data-ttu-id="11548-120">En el cuadro de diálogo Detalles del servicio, haga clic en el **mensajes** ficha. Haga doble clic en la entrada para los que es el nombre del servicio **MT103_FlatFile_ReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="11548-120">In the Service Details dialog box, click the **Messages** tab. Double-click the entry for which the Service Name is **MT103_FlatFile_ReceivePort**.</span></span>  
  
12. <span data-ttu-id="11548-121">En el cuadro de diálogo Detalles del mensaje, haga clic en **cuerpo** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="11548-121">In the Message Details dialog box, click **Body** in the left pane.</span></span>  
  
13. <span data-ttu-id="11548-122">Compruebe que el mensaje mostrado en el panel de cuerpo del cuadro de diálogo Detalles del mensaje se corresponde con MT103_Invalid_Sample.txt que abrió en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="11548-122">Verify that the message displayed in the body pane of the Message Details dialog box corresponds to MT103_Invalid_Sample.txt that you opened in Notepad.</span></span>  
  
 <span data-ttu-id="11548-123">Continúe con [lección 3: probar una instancia XML](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md).</span><span class="sxs-lookup"><span data-stu-id="11548-123">Proceed to [Lesson 3: Testing an XML Instance](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md).</span></span>