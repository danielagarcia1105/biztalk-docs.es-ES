---
title: Uso de puertos en orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, receiving
- ports, configuring manually
- send ports, messages
- ports, creating
- ports, messages
- creating, ports
- send ports, sending
- ports, operations
- configuring, ports
- ports, deleting
- deleting, ports
- orchestrations, ports
- Port Configuration Wizard [Orchestration Designer]
- ports
- ports, about ports
- ports, configuring
ms.assetid: 968b2d1b-e233-4eb0-8254-9ec6b7642cdf
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7f48c1c070e3a3a3e7ebe7e86618a4fd9ebc90d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-ports-in-orchestrations"></a><span data-ttu-id="6bf62-102">Utilizar puertos en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="6bf62-102">Using Ports in Orchestrations</span></span>
<span data-ttu-id="6bf62-103">Los puertos especifican cómo la orquestación enviará los mensajes a otros procesos empresariales y cómo los recibirá de ellos.</span><span class="sxs-lookup"><span data-stu-id="6bf62-103">Ports specify how your orchestration will send messages to and receive messages from other business processes.</span></span> <span data-ttu-id="6bf62-104">Cada puerto tiene un tipo, una dirección y un enlace, que en combinación determinan la dirección de la comunicación, el patrón de comunicación, la ubicación de destino a la que se envía el mensaje, la ubicación de origen desde la que se recibe el mensaje y cómo tiene lugar la comunicación.</span><span class="sxs-lookup"><span data-stu-id="6bf62-104">Each port has a type, a direction, and a binding, which together determine the direction of communication, the pattern of communication, the location to or from which the message is sent or received, and how the communication takes place.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bf62-105">Existe una diferencia entre un puerto y un tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="6bf62-105">There is a distinction between a port and a port type.</span></span> <span data-ttu-id="6bf62-106">Un puerto es una instancia de un tipo de puerto; varios puertos diferentes pueden tener el mismo tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="6bf62-106">A port is an instance of a port type; several different ports may have the same port type.</span></span>  
  
 <span data-ttu-id="6bf62-107">En función de estos factores, un puerto puede tener asociado un URI (una ubicación física), un transporte (ARCHIVO, HTTP, SOAP, SMTP o Message Queue Server de BizTalk), una canalización de envío para preparar un mensaje para el envío (por ejemplo, ensamblado, cifrado, compresión o cualquier otro tipo de acción en él) y una canalización de recepción para preparar un mensaje recibido para el procesamiento (por ejemplo, desensamblado, descifrado o descompresión).</span><span class="sxs-lookup"><span data-stu-id="6bf62-107">Depending on these factors, a port may have associated with it a URI (a physical location), a transport (either FILE, HTTP, SOAP, SMTP or BizTalk Message Queuing), a send pipeline to prepare a message for sending (for example, by assembling, encrypting, compressing, or performing some other action on it), and a receive pipeline to prepare a received message for processing (for example, by disassembling, decrypting, or decompressing it).</span></span>  
  
 <span data-ttu-id="6bf62-108">Los puertos se agregan a una orquestación de forma muy similar a como se agregan controles a un formulario Web Forms o Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6bf62-108">You add ports to an orchestration in much the same way that you add controls to a Web Form or Windows Form.</span></span> <span data-ttu-id="6bf62-109">También se pueden agregar puertos mediante la ventana Vista orquestación.</span><span class="sxs-lookup"><span data-stu-id="6bf62-109">You can also add ports by using the Orchestration View window.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6bf62-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6bf62-110">In This Section</span></span>  
  
-   [<span data-ttu-id="6bf62-111">Patrón de comunicación</span><span class="sxs-lookup"><span data-stu-id="6bf62-111">Communication Pattern</span></span>](../core/communication-pattern.md)  
  
-   [<span data-ttu-id="6bf62-112">Dirección de comunicación</span><span class="sxs-lookup"><span data-stu-id="6bf62-112">Communication Direction</span></span>](../core/communication-direction.md)  
  
-   [<span data-ttu-id="6bf62-113">Enlaces de puertos</span><span class="sxs-lookup"><span data-stu-id="6bf62-113">Port Bindings</span></span>](../core/port-bindings.md)  
  
-   [<span data-ttu-id="6bf62-114">Cómo usar puertos en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="6bf62-114">How to Use Ports in Orchestrations</span></span>](../core/how-to-use-ports-in-orchestrations.md)  
  
-   [<span data-ttu-id="6bf62-115">Cómo trabajar con tipos de puerto</span><span class="sxs-lookup"><span data-stu-id="6bf62-115">How to Work with Port Types</span></span>](../core/how-to-work-with-port-types.md)  
  
-   [<span data-ttu-id="6bf62-116">Cómo ejecutar al Asistente para configuración de puertos</span><span class="sxs-lookup"><span data-stu-id="6bf62-116">How to Run the Port Configuration Wizard</span></span>](../core/how-to-run-the-port-configuration-wizard.md)  
  
-   [<span data-ttu-id="6bf62-117">Trabajar con puertos de enlace directo en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="6bf62-117">Working with Direct Bound Ports in Orchestrations</span></span>](../core/working-with-direct-bound-ports-in-orchestrations.md)  
  
## <a name="see-also"></a><span data-ttu-id="6bf62-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bf62-118">See Also</span></span>  
 <span data-ttu-id="6bf62-119">[Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="6bf62-119">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="6bf62-120">Usar vínculos de rol en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="6bf62-120">Using Role Links in Orchestrations</span></span>](../core/using-role-links-in-orchestrations.md)