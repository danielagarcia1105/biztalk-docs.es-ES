---
title: Tipos de errores de mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transformation stage
- assembly stage
- errors, disassembly stage
- errors, assembly stage
- routing, errors
- errors, transformation stage
- errors, messages [HAT]
- errors, routing
- disassembly stage, errors
- messages, errors [HAT]
ms.assetid: 3a8e1c58-4b53-4439-837d-aaa233eb9158
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 466c7c21fd1a00e192307dd82384dc613b6697a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286756"
---
# <a name="types-of-message-failures"></a><span data-ttu-id="44b7e-102">Tipos de errores de mensaje</span><span class="sxs-lookup"><span data-stu-id="44b7e-102">Types of Message Failures</span></span>
<span data-ttu-id="44b7e-103">En este tema se enumeran los distintos puntos en los que puede producirse un error de mensaje.</span><span class="sxs-lookup"><span data-stu-id="44b7e-103">This topic lists different points where a message failure may occur.</span></span>  
  
 <span data-ttu-id="44b7e-104">**Errores en la fase de desensamblado**</span><span class="sxs-lookup"><span data-stu-id="44b7e-104">**Failures in the disassembly phase**</span></span>  
  
 <span data-ttu-id="44b7e-105">Puede producirse un error de procesamiento en la fase de desensamblado, es decir, en uno de los componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="44b7e-105">Processing might also fail during the disassembly phase; that is, failure in one of the pipeline components.</span></span> <span data-ttu-id="44b7e-106">Por ejemplo, se puede producir un error de descifrado debido a la ausencia del certificado de descifrado en el servidor de procesamiento, o bien un error de análisis a causa de problemas en el esquema o en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="44b7e-106">For example, decryption failed due to absence of decryption cert on the processing server, or parsing failure due to problem either in the schema or in the message.</span></span>  
  
 <span data-ttu-id="44b7e-107">**Errores de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="44b7e-107">**Failures in routing**</span></span>  
  
 <span data-ttu-id="44b7e-108">Cuando un mensaje se ha desensamblado correctamente, el siguiente punto posible de error es el enrutamiento; por ejemplo, si los usuarios habilitan la ubicación de recepción apropiada en una orquestación pero olvidan dar de alta dicha orquestación.</span><span class="sxs-lookup"><span data-stu-id="44b7e-108">After a message disassembles successfully, the next potential failure point is routing; for example, users enable a corresponding receive location of an orchestration and forget to enlist the orchestration.</span></span> <span data-ttu-id="44b7e-109">En este caso, se produce un error de enrutamiento del mensaje recogido desde la ubicación de recepción, y la base de datos de cuadro de mensajes genera un informe Error de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="44b7e-109">In this case, the message picked up from the receive location fails routing and the MessageBox database generates a Routing Failure report.</span></span>  
  
 <span data-ttu-id="44b7e-110">Los informes Error de enrutamiento se muestran en la consola de administración de BizTalk Server como mensajes suspendidos no reanudables.</span><span class="sxs-lookup"><span data-stu-id="44b7e-110">Routing Failure reports are listed in the BizTalk Server Administration Console as non-resumable suspended messages.</span></span> <span data-ttu-id="44b7e-111">Cada informe Error de enrutamiento contiene una instantánea de la propiedad de mensaje, tomada en el momento en que se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="44b7e-111">Each Routing Failure report contains a message property snap shot taken when the routing failure occurred.</span></span> <span data-ttu-id="44b7e-112">Puede utilizar la información de cada informe para determinar por qué se ha producido un error de enrutamiento en el mensaje asociado.</span><span class="sxs-lookup"><span data-stu-id="44b7e-112">You can use the information in each report to determine why routing failed for its associated message.</span></span> <span data-ttu-id="44b7e-113">Si el mensaje asociado es reanudable, puede corregir el problema de enrutamiento, y seguidamente reanudar el mensaje para continuar con su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="44b7e-113">If the associated message is resumable, you can correct the routing problem and resume the message so that processing continues.</span></span> <span data-ttu-id="44b7e-114">Los informes Error de enrutamiento se enumeran en la lista de resultados, con el nombre de servicio y tipo de servicio en blanco.</span><span class="sxs-lookup"><span data-stu-id="44b7e-114">Routing Failure reports are listed in the results list with a blank service name and service type.</span></span> <span data-ttu-id="44b7e-115">Cuando se finaliza una instancia suspendida, el informe Error de enrutamiento asociado a la instancia suspendida es eliminado automáticamente por el trabajo Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb, que se ejecuta cada minuto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="44b7e-115">When you terminate a suspended instance, the Routing Failure report associated with the suspended instance is automatically deleted by the Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job that runs every minute by default.</span></span> <span data-ttu-id="44b7e-116">Para obtener más información acerca del trabajo Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb, consulte [estructura de base de datos y trabajos](../core/database-structure-and-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="44b7e-116">For more information about the Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job, see [Database Structure and Jobs](../core/database-structure-and-jobs.md).</span></span>  
  
 <span data-ttu-id="44b7e-117">**Errores durante la fase de transformación**</span><span class="sxs-lookup"><span data-stu-id="44b7e-117">**Failures during the transformation phase**</span></span>  
  
-   <span data-ttu-id="44b7e-118">**Mensajes recibidos**.</span><span class="sxs-lookup"><span data-stu-id="44b7e-118">**Received Messages**.</span></span> <span data-ttu-id="44b7e-119">Cuando se recibe un mensaje procedente de una ubicación de recepción, se efectúa el desensamblado del mensaje (por ejemplo, se descifra y se analiza) y, de forma opcional, puede transformarse a un formato distinto mediante una asignación de entrada especificada en un puerto de envío, además de publicarse en el cuadro de mensajes para su enrutamiento a una orquestación o a un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="44b7e-119">When a message is received from Receive Location, the message is disassembled (for example, decrypted and parsed), the message might optionally be transformed to a different format via an Inbound Map specified on a receive Port, and published to the MessageBox for routing to an orchestration or a Send Port.</span></span> <span data-ttu-id="44b7e-120">En este caso, puede producirse un error de procesamiento durante la fase de transformación debido a una asignación de entrada incorrecta, o a problemas en el esquema o en el mensaje recibido.</span><span class="sxs-lookup"><span data-stu-id="44b7e-120">In this case, processing may fail during transformation phase due to incorrect Inbound Map, or problems in the schema or in the message received.</span></span>  
  
-   <span data-ttu-id="44b7e-121">**Los mensajes enviados**.</span><span class="sxs-lookup"><span data-stu-id="44b7e-121">**Sent Messages**.</span></span> <span data-ttu-id="44b7e-122">Cuando un mensaje debe enviarse a una ubicación de envío, una asignación de entrada configurada en el puerto de envío puede, de forma opcional, transformar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="44b7e-122">When a message is to be sent to a Send Location, an Outbound Map configured on Send Port might optionally transform the message.</span></span> <span data-ttu-id="44b7e-123">A continuación, el mensaje transformado se ensambla y se entrega al adaptador para su transmisión definitiva a la ubicación de envío.</span><span class="sxs-lookup"><span data-stu-id="44b7e-123">Then the transformed message is assembled and handed to the adapter for final transmission to the Send Location.</span></span> <span data-ttu-id="44b7e-124">En este caso, puede producirse un error de procesamiento en la fase de transformación debido a una asignación de salida incorrecta, o a problemas en el esquema o en el mensaje de origen.</span><span class="sxs-lookup"><span data-stu-id="44b7e-124">In this case, processing may fail during transformation phase due to incorrect Outbound Map or problem in schema or source message.</span></span>  
  
 <span data-ttu-id="44b7e-125">**Errores en la fase de ensamblado de mensaje**</span><span class="sxs-lookup"><span data-stu-id="44b7e-125">**Failures in the message assembly phase**</span></span>  
  
 <span data-ttu-id="44b7e-126">También puede producirse un error de procesamiento durante la fase de ensamblado del mensaje, es decir, en el componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="44b7e-126">Processing can also fail during message assembly phase – in other words, failing in pipeline component.</span></span> <span data-ttu-id="44b7e-127">Cuando el mensaje se ha ensamblado correctamente, el siguiente punto posible de error es la transmisión a la ubicación de envío; por ejemplo, cuando la ubicación de envío (que pertenece a un socio comercial) no funciona o no existe.</span><span class="sxs-lookup"><span data-stu-id="44b7e-127">After a message successfully assembles, the next potential failure point becomes transmission to Send Location; for example, the Send Location (which belongs to the partner) might be down or not exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44b7e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="44b7e-128">See Also</span></span>  
 [<span data-ttu-id="44b7e-129">Investigación de orquestación, puerto y errores de mensaje</span><span class="sxs-lookup"><span data-stu-id="44b7e-129">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)