---
title: "Restricciones y notas de reenvío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 391064a9-1d61-4b10-97ab-d93b37d1ae23
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d03c969dc056e251d8109ce5bc0a29c16f8ffeda
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="resubmission-notes-and-restrictions"></a><span data-ttu-id="943b7-102">Notas de reenvío y restricciones</span><span class="sxs-lookup"><span data-stu-id="943b7-102">Resubmission Notes and Restrictions</span></span>
<span data-ttu-id="943b7-103">Las siguientes notas y restricciones se aplican al proceso de reenvío:</span><span class="sxs-lookup"><span data-stu-id="943b7-103">The following notes and restrictions apply to the resubmission process:</span></span>  
  
-   <span data-ttu-id="943b7-104">Puede volver a enviar mensajes XML a la ESB WCF en rampa, SOAP (ASMX) en rampa o ubicación de recepción cualquier HTTP.</span><span class="sxs-lookup"><span data-stu-id="943b7-104">You can resubmit XML messages to the ESB WCF on-ramp, SOAP (ASMX) on-ramp, or any HTTP receive location.</span></span>  
  
-   <span data-ttu-id="943b7-105">La dirección URL predeterminada para WCF rampa es http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc.</span><span class="sxs-lookup"><span data-stu-id="943b7-105">The default URL for the WCF on-ramp is http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc.</span></span>  
  
-   <span data-ttu-id="943b7-106">El archivo Web.config portal define los detalles del extremo de la WCF rampa en el  **\<cliente\>**  nodo de la  **\<System.ServiceModel\>**  sección.</span><span class="sxs-lookup"><span data-stu-id="943b7-106">The portal Web.config file defines the endpoint details for the WCF on-ramp in the **\<Client\>** node of the **\<System.ServiceModel\>** section.</span></span> <span data-ttu-id="943b7-107">Éste es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="943b7-107">The following is the default value.</span></span>  
  
    ```  
    <endpoint  
      address="http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc"  
      binding="wsHttpBinding"  
      bindingConfiguration="WSHttpBinding_ITwoWayAsyncVoid"  
      contract="ProcessRequest"   
      name="WSHttpBinding_ITwoWayAsyncVoid">                  
    </endpoint>  
    ```  
  
-   <span data-ttu-id="943b7-108">Si WCF rampa reside en un servidor remoto, debe actualizar la dirección para que señale al servidor correcto.</span><span class="sxs-lookup"><span data-stu-id="943b7-108">If the WCF on-ramp resides on a remote server, you must update the address to point to the correct server.</span></span>  
  
-   <span data-ttu-id="943b7-109">La dirección URL predeterminada para SOAP (ASMX) rampa es http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx.</span><span class="sxs-lookup"><span data-stu-id="943b7-109">The default URL for the SOAP (ASMX) on-ramp is http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx.</span></span>  
  
-   <span data-ttu-id="943b7-110">El archivo Web.config portal define la configuración de la SOAP (ASMX) rampa en el  **\<applicationSettings\>**  sección.</span><span class="sxs-lookup"><span data-stu-id="943b7-110">The portal Web.config file defines the configuration for the SOAP (ASMX) on-ramp in the **\<applicationSettings\>** section.</span></span> <span data-ttu-id="943b7-111">Éste es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="943b7-111">The following is the default value.</span></span>  
  
    ```  
    <setting   
      name="Microsoft_Practices_ESB_Portal_ProcessItinerary_Process"  
      serializeAs="String">  
      <value>  
        http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx  
      </value>  
    </setting>  
    ```  
  
-   <span data-ttu-id="943b7-112">Si la ASMX rampa reside en un servidor remoto, debe actualizar la dirección URL con la dirección de servidor correcto.</span><span class="sxs-lookup"><span data-stu-id="943b7-112">If the ASMX on-ramp resides on a remote server, you need to update the URL with the correct server address.</span></span>  
  
-   <span data-ttu-id="943b7-113">Puede volver a enviar de archivo sin formato ubicación de recepción de mensajes con formato sólo para HTTP.</span><span class="sxs-lookup"><span data-stu-id="943b7-113">You can resubmit flat file formatted messages only to an HTTP receive location.</span></span> <span data-ttu-id="943b7-114">No puede enviarlos a un WCF o SOAP en rampa.</span><span class="sxs-lookup"><span data-stu-id="943b7-114">You cannot submit them to a WCF or SOAP on-ramp.</span></span> <span data-ttu-id="943b7-115">Debe asegurarse de que el HTTP ubicación de recepción tiene la canalización adecuada que se puede utilizar o analizar el archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="943b7-115">You must ensure that the HTTP receive location has the appropriate pipeline that can consume and/or parse the flat file.</span></span>  
  
-   <span data-ttu-id="943b7-116">El mensaje reenviado no contiene ninguna de las propiedades de contexto del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="943b7-116">The resubmitted message does not contain any of the context properties of the original message.</span></span>  
  
-   <span data-ttu-id="943b7-117">Reenvío se aplica a solo el cuerpo del mensaje; no se aplica a todo el mensaje.</span><span class="sxs-lookup"><span data-stu-id="943b7-117">Resubmission applies to only the message body; it does not apply to the entire message.</span></span>  
  
-   <span data-ttu-id="943b7-118">El proceso de reenvío permite sólo los mensajes de una sola parte.</span><span class="sxs-lookup"><span data-stu-id="943b7-118">The resubmission process supports only single-part messages.</span></span> <span data-ttu-id="943b7-119">No se puede utilizar el proceso de reenvío con mensajes de varias partes.</span><span class="sxs-lookup"><span data-stu-id="943b7-119">You cannot use the resubmission process with multi-part messages.</span></span>  
  
-   <span data-ttu-id="943b7-120">No se puede volver a enviar mensajes en formato binario.</span><span class="sxs-lookup"><span data-stu-id="943b7-120">You cannot resubmit binary-formatted messages.</span></span>