---
title: "Interfaces del motor de mensajería | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14241db3-edcf-4449-9ec8-2171a14496c0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a135505240e94fb42e5810a3e7ac71d4c99c34a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messaging-engine-interfaces"></a><span data-ttu-id="ce01c-102">Interfaces del motor de mensajería</span><span class="sxs-lookup"><span data-stu-id="ce01c-102">Messaging Engine Interfaces</span></span>
<span data-ttu-id="ce01c-103">Existen tres interfaces públicas que los adaptadores pueden usar para permitir la interacción con el motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="ce01c-103">There are three public interfaces that adapters can use to allow interaction with the Messaging Engine.</span></span> <span data-ttu-id="ce01c-104">Se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="ce01c-104">These are outlined in the following sections.</span></span>  
  
## <a name="ibttransportproxy"></a><span data-ttu-id="ce01c-105">IBTTransportProxy</span><span class="sxs-lookup"><span data-stu-id="ce01c-105">IBTTransportProxy</span></span>  
 <span data-ttu-id="ce01c-106">Los adaptadores siempre interactúan con el motor de mensajería mediante su propio proxy de transporte.</span><span class="sxs-lookup"><span data-stu-id="ce01c-106">Adapters always interact with the Messaging Engine by using their own transport proxy.</span></span> <span data-ttu-id="ce01c-107">El proxy de transporte se usa para operaciones tales como la creación de lotes, la obtención del generador de mensajes y el registro de receptores aislados en el motor.</span><span class="sxs-lookup"><span data-stu-id="ce01c-107">The transport proxy is used for operations such as creating batches, getting the message factory, and registering isolated receivers with the engine.</span></span>  
  
## <a name="ibttransportbatch"></a><span data-ttu-id="ce01c-108">IBTTransportBatch</span><span class="sxs-lookup"><span data-stu-id="ce01c-108">IBTTransportBatch</span></span>  
 <span data-ttu-id="ce01c-109">Esta interfaz la proporciona el motor de mensajería y define métodos que los adaptadores pueden usar para realizar operaciones en lotes de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ce01c-109">This interface is provided by the Messaging Engine, and defines methods that adapters can use to operate on batches of messages.</span></span> <span data-ttu-id="ce01c-110">El motor de mensajería procesa los lotes de manera asíncrona.</span><span class="sxs-lookup"><span data-stu-id="ce01c-110">The Messaging Engine processes batches asynchronously.</span></span>  
  
## <a name="ibtdtccommitconfirm"></a><span data-ttu-id="ce01c-111">IBTDTCCommitConfirm</span><span class="sxs-lookup"><span data-stu-id="ce01c-111">IBTDTCCommitConfirm</span></span>  
 <span data-ttu-id="ce01c-112">Los adaptadores que usan transacciones explícitas del Coordinador de transacciones distribuidas de Microsoft (MSDTC) con los lotes deben utilizar esta interfaz para notificar al motor cuál ha sido el resultado de la transacción mediante esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="ce01c-112">Adapters using explicit Microsoft Distributed Transaction Coordinator (MSDTC) transactions on batches must use this interface to notify the engine of the outcome of the transaction using this interface.</span></span>