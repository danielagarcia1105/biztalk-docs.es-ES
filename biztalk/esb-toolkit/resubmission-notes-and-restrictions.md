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
# <a name="resubmission-notes-and-restrictions"></a>Notas de reenvío y restricciones
Las siguientes notas y restricciones se aplican al proceso de reenvío:  
  
-   Puede volver a enviar mensajes XML a la ESB WCF en rampa, SOAP (ASMX) en rampa o ubicación de recepción cualquier HTTP.  
  
-   La dirección URL predeterminada para WCF rampa es http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc.  
  
-   El archivo Web.config portal define los detalles del extremo de la WCF rampa en el  **\<cliente\>**  nodo de la  **\<System.ServiceModel\>**  sección. Éste es el valor predeterminado.  
  
    ```  
    <endpoint  
      address="http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc"  
      binding="wsHttpBinding"  
      bindingConfiguration="WSHttpBinding_ITwoWayAsyncVoid"  
      contract="ProcessRequest"   
      name="WSHttpBinding_ITwoWayAsyncVoid">                  
    </endpoint>  
    ```  
  
-   Si WCF rampa reside en un servidor remoto, debe actualizar la dirección para que señale al servidor correcto.  
  
-   La dirección URL predeterminada para SOAP (ASMX) rampa es http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx.  
  
-   El archivo Web.config portal define la configuración de la SOAP (ASMX) rampa en el  **\<applicationSettings\>**  sección. Éste es el valor predeterminado.  
  
    ```  
    <setting   
      name="Microsoft_Practices_ESB_Portal_ProcessItinerary_Process"  
      serializeAs="String">  
      <value>  
        http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx  
      </value>  
    </setting>  
    ```  
  
-   Si la ASMX rampa reside en un servidor remoto, debe actualizar la dirección URL con la dirección de servidor correcto.  
  
-   Puede volver a enviar de archivo sin formato ubicación de recepción de mensajes con formato sólo para HTTP. No puede enviarlos a un WCF o SOAP en rampa. Debe asegurarse de que el HTTP ubicación de recepción tiene la canalización adecuada que se puede utilizar o analizar el archivo sin formato.  
  
-   El mensaje reenviado no contiene ninguna de las propiedades de contexto del mensaje original.  
  
-   Reenvío se aplica a solo el cuerpo del mensaje; no se aplica a todo el mensaje.  
  
-   El proceso de reenvío permite sólo los mensajes de una sola parte. No se puede utilizar el proceso de reenvío con mensajes de varias partes.  
  
-   No se puede volver a enviar mensajes en formato binario.