---
title: Enviar IDOC desde un sistema SAP para usar el adaptador de mySAP en BizTalk | Documentos de Microsoft
description: ''
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aea8a5e9-d775-4d52-a434-c2908b53cd2d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63f7d1ccdaa8cb6a4ee12ad1cc4263c487a164c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215596"
---
# <a name="sending-idocs-from-an-sap-system"></a><span data-ttu-id="f0f2d-102">Enviar IDOC desde un sistema SAP</span><span class="sxs-lookup"><span data-stu-id="f0f2d-102">Sending IDOCs from an SAP System</span></span>
<span data-ttu-id="f0f2d-103">Tareas de alto nivel que se complete en el sistema SAP para enviar un IDOC desde el sistema SAP a una aplicación externa.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-103">High-level tasks to complete on the SAP system to send an IDOC from the SAP system to an external application.</span></span> <span data-ttu-id="f0f2d-104">Póngase en contacto con el Administrador de SAP para llevar a cabo estas tareas o consulte las instrucciones de SAP.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-104">Contact your SAP administrator for performing these tasks or see the SAP guidance.</span></span>  
  
## <a name="send-an-idoc-from-sap"></a><span data-ttu-id="f0f2d-105">Enviar un IDOC desde SAP</span><span class="sxs-lookup"><span data-stu-id="f0f2d-105">Send an IDOC from SAP</span></span>  
  
1.  <span data-ttu-id="f0f2d-106">Inicie la GUI de SAP.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-106">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="f0f2d-107">Crear un sistema lógico con la transacción de BD54.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-107">Create a logical system using BD54 transaction.</span></span>  
  
3.  <span data-ttu-id="f0f2d-108">Crear un destino RFC en conexiones de TCP/IP con la transacción SM59.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-108">Create an RFC destination in TCP/IP connections using SM59 transaction.</span></span>  
  
4.  <span data-ttu-id="f0f2d-109">Crear un puerto mediante transacciones WE21 y adjuntarlo al destino RFC creado en el último paso.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-109">Create a port using WE21 transaction and attach it to the RFC destination created in the last step.</span></span>  
  
5.  <span data-ttu-id="f0f2d-110">Crear un perfil de socio comercial mediante transacciones de WE20 con el tipo de mensaje necesario y el tipo IDOC y, a continuación, adjuntarlo al puerto creado en el último paso.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-110">Create a partner profile using WE20 transaction with the required message type and IDOC type, and then attach it to the port created in the last step.</span></span>  
  
6.  <span data-ttu-id="f0f2d-111">Mantener un modelo distribuido mediante la conexión del tipo de mensaje en el puerto utilizando la transacción de venta.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-111">Maintain a distributed model by connecting the message type to the port using the SALE transaction.</span></span>  
  
7.  <span data-ttu-id="f0f2d-112">Generar un IDOC de SAP.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-112">Generate an IDOC within SAP.</span></span> <span data-ttu-id="f0f2d-113">Por ejemplo, usar transacciones BD10 para desencadenar un IDOC MATMAS.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-113">For example, use BD10 transaction to trigger a MATMAS IDOC.</span></span> <span data-ttu-id="f0f2d-114">Para obtener información acerca de otras transacciones para desencadenar el IDOC específico, póngase en contacto con el Administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-114">Contact your SAP administrator for information about other transactions to trigger specific IDOCs.</span></span>  

## <a name="view-transaction-ids-in-sap"></a><span data-ttu-id="f0f2d-115">Id. de transacción de vista en SAP</span><span class="sxs-lookup"><span data-stu-id="f0f2d-115">View Transaction IDs in SAP</span></span>
<span data-ttu-id="f0f2d-116">Cuando el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] invoca un tRFC o envía un IDOC a un sistema SAP, los registros de sistema SAP una transacción TID (Id.) en respuesta.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-116">When the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] invokes a tRFC or sends an IDOC to an SAP system, the SAP system registers a transaction ID (TID) in response.</span></span> <span data-ttu-id="f0f2d-117">En algunos casos, tendrá que conocer el TID que está registrado con el sistema SAP en respuesta a una llamada desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0f2d-117">In some scenarios, you might need to know the TID that is registered with the SAP system in response to a call from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="f0f2d-118">Por ejemplo, puede identificar la unidad lógica de trabajo (LUW) en el sistema SAP para solucionar un problema.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-118">For example, you might want to identify the logical unit of work (LUW) on the SAP system to troubleshoot an issue.</span></span>  
  
 <span data-ttu-id="f0f2d-119">Para ver el TID en un sistema SAP, debe usar la transacción SM58.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-119">To view the TIDs in an SAP system, you must use transaction SM58.</span></span> <span data-ttu-id="f0f2d-120">Póngase en contacto con el Administrador de SAP o consulte la Guía de SAP para obtener más información acerca de esta transacción.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-120">Contact your SAP administrator or refer to the SAP guidance for more information about this transaction.</span></span> 

## <a name="view-details-about-idocs-sent-and-received-from-sap"></a><span data-ttu-id="f0f2d-121">Ver detalles acerca de IDOC enviados y recibidos desde SAP</span><span class="sxs-lookup"><span data-stu-id="f0f2d-121">View details about IDOCs sent and received from SAP</span></span>
<span data-ttu-id="f0f2d-122">Mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], puede enviar un IDOC a un sistema SAP o recibir un IDOC desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-122">Using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you can send an IDOC to an SAP system or receive an IDOC from an SAP system.</span></span> <span data-ttu-id="f0f2d-123">Para realizar un seguimiento del estado y ver los datos de un IDOC envían o reciben por un sistema SAP, puede usar la transacción WE02.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-123">To track the status and view the data of an IDOC sent or received by an SAP system, you can use transaction WE02.</span></span> <span data-ttu-id="f0f2d-124">Póngase en contacto con el Administrador de SAP o consulte la Guía de SAP para obtener más información acerca de esta transacción.</span><span class="sxs-lookup"><span data-stu-id="f0f2d-124">Contact your SAP administrator, or refer to the SAP guidance for more information about this transaction.</span></span>  

  
## <a name="see-also"></a><span data-ttu-id="f0f2d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0f2d-125">See Also</span></span>  
 [<span data-ttu-id="f0f2d-126">Realizar tareas mediante la GUI de SAP para escenarios de adaptadores SAP específicos</span><span class="sxs-lookup"><span data-stu-id="f0f2d-126">Performing Tasks Using the SAP GUI for Specific SAP Adapter Scenarios</span></span>](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)