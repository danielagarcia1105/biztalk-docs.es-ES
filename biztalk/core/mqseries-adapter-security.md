---
title: Seguridad del adaptador de MQSeries | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, MQSeries adapters
- MQSeries adapters, security
ms.assetid: 0bd82c21-6b77-4a66-a4e9-4a91ba4a56c4
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08d5228dab8463c2ad5dc7f9d9347899d4c41a67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-with-the-mqseries-adapter"></a><span data-ttu-id="80d2c-102">Seguridad con el adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="80d2c-102">Security with the MQSeries adapter</span></span>

<span data-ttu-id="80d2c-103">La seguridad del adaptador de MQSeries comienza con la protección de los servidores MQSeries y BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="80d2c-103">MQSeries adapter security begins with securing your BizTalk and MQSeries servers.</span></span> <span data-ttu-id="80d2c-104">Para obtener información acerca de cómo proteger el servidor BizTalk Server, vea [seguro y proteger los datos](secure-and-protect-your-biztalk-messages.md).</span><span class="sxs-lookup"><span data-stu-id="80d2c-104">For information about securing BizTalk Server, see [Secure and protect your data](secure-and-protect-your-biztalk-messages.md).</span></span> <span data-ttu-id="80d2c-105">Para obtener información acerca de la seguridad del servidor MQSeries, vea la documentación del servidor MQSeries de IBM.</span><span class="sxs-lookup"><span data-stu-id="80d2c-105">For information about MQSeries Server security, see the IBM MQSeries Server documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80d2c-106">El adaptador utiliza automáticamente privacidad de paquete para el envío y la recepción de mensajes entre el servidor BizTalk Server y el servidor MQSeries.</span><span class="sxs-lookup"><span data-stu-id="80d2c-106">The adapter automatically uses packet privacy for sending and receiving messages between BizTalk Server and MQSeries Server.</span></span>  

## <a name="adapter-security"></a><span data-ttu-id="80d2c-107">Seguridad del adaptador</span><span class="sxs-lookup"><span data-stu-id="80d2c-107">Adapter security</span></span>  
 <span data-ttu-id="80d2c-108">Para utilizar el adaptador mismo de forma segura, es preciso prestar atención a cuatro áreas:</span><span class="sxs-lookup"><span data-stu-id="80d2c-108">Using the adapter itself securely requires attention to four areas:</span></span>  
  
-   <span data-ttu-id="80d2c-109">La selección de la identidad de la aplicación y los miembros para MQSAgent</span><span class="sxs-lookup"><span data-stu-id="80d2c-109">Choosing the application identity and members for MQSAgent</span></span>  
  
-   <span data-ttu-id="80d2c-110">El control de las cuentas de BizTalk Server que utilizan el adaptador</span><span class="sxs-lookup"><span data-stu-id="80d2c-110">Controlling the BizTalk Server accounts using the adapter</span></span>  
  
-   <span data-ttu-id="80d2c-111">La protección de las secuencias de comandos de creación de cola</span><span class="sxs-lookup"><span data-stu-id="80d2c-111">Securing the queue creation scripts</span></span>  
  
-   <span data-ttu-id="80d2c-112">Uso apropiado de la **aplicación afiliada de SSO** propiedad</span><span class="sxs-lookup"><span data-stu-id="80d2c-112">Making appropriate use of the **SSO Affiliate Application** property</span></span>  
  
 <span data-ttu-id="80d2c-113">La cuenta asignada a la identidad de la aplicación durante la configuración no debería ser una cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="80d2c-113">The account assigned to the application identity during configuration should not be an administrator account.</span></span> <span data-ttu-id="80d2c-114">En su lugar, la cuenta debe tener los privilegios mínimos requeridos: acceso de lectura y escritura a las colas de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="80d2c-114">Rather, the account should have the minimum required privileges—read and write access to the MQSeries queues.</span></span>  
  
 <span data-ttu-id="80d2c-115">Asegúrese de asignar únicamente cuentas de BizTalk Server que utilizan el adaptador a la función MQSAgent.</span><span class="sxs-lookup"><span data-stu-id="80d2c-115">Make sure that you assign only BizTalk Server accounts using the adapter to the MQSAgent role.</span></span>  
  
 <span data-ttu-id="80d2c-116">Al utilizar secuencias de comandos exportadas, creadas durante el proceso de definición de cola, mantenga las secuencias de comandos en un área segura.</span><span class="sxs-lookup"><span data-stu-id="80d2c-116">When using exported scripts created during the queue definition process, keep the scripts in a secure area.</span></span> <span data-ttu-id="80d2c-117">Sólo deberían tener acceso los administradores que utilicen las secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="80d2c-117">Only administrators using the scripts should have access.</span></span>  
  
 <span data-ttu-id="80d2c-118">Si la aplicación utiliza propiedades de encabezado MQCIH y MQIIH para colocar las credenciales de usuario en los mensajes salientes, use la **aplicación afiliada de SSO** propiedad en el **propiedades de transporte** página.</span><span class="sxs-lookup"><span data-stu-id="80d2c-118">If your application uses MQCIH and MQIIH header properties to put user credentials in outbound messages, use the **SSO Affiliate Application** property on the **Transport Properties** page.</span></span> <span data-ttu-id="80d2c-119">Para obtener más información acerca de esta propiedad, vea [cómo configurar ubicaciones de recepción de MQSeries adaptador y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).</span><span class="sxs-lookup"><span data-stu-id="80d2c-119">For more information about this property, see [How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d2c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="80d2c-120">See Also</span></span>  
 <span data-ttu-id="80d2c-121">[Estructura del adaptador de MQSeries](../core/structure-of-the-mqseries-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="80d2c-121">[Structure of the MQSeries Adapter](../core/structure-of-the-mqseries-adapter.md) </span></span>  
 [<span data-ttu-id="80d2c-122">¿Qué es el adaptador de MQSeries?</span><span class="sxs-lookup"><span data-stu-id="80d2c-122">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)