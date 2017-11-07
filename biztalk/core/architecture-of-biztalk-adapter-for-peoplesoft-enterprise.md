---
title: Arquitectura de BizTalk Adapter para PeopleSoft Enterprise | Documentos de Microsoft
description: "Describe cómo se reciben los mensajes, cómo los mensajes se valida y proporciona información acerca de los métodos de interfaz de componente cuando se usa el adaptador de PeopleSoft con BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f246e974-a082-430c-ad15-23a5e597738b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb0f43dacdbd6036ef59fa3fe16102d4fe12379
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="peoplesoft-enterprise-adapter-architecture"></a>Arquitectura del adaptador de PeopleSoft Enterprise
Durante el funcionamiento básico del adaptador de Microsoft BizTalk para PeopleSoft Enterprise, el adaptador recibe un mensaje XML de BizTalk Server. Incluye el mensaje XML en un sobre SOAP. El adaptador de BizTalk para PeopleSoft Enterprise reenvía las solicitudes SOAP al servidor. El adaptador se comunica con el sistema PeopleSoft mediante las clases psjoa de PeopleSoft, que conectan a este sistema mediante el protocolo de transacción Jolt. El sistema PeopleSoft recibe la solicitud y ejecuta la lógica empresarial. La respuesta se devuelve a través de un proceso similar.  
  
 ![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")  

  
## <a name="component-interface-methods"></a>Métodos de las interfaces de componentes  
 Las API básicas proporcionadas por la interfaz de componente de PeopleSoft son de una naturaleza de bajo nivel. El cliente requiere múltiples invocaciones de estos API. Por ejemplo, para obtener la propiedad de una instancia de un componente de interfaz, el cliente necesita una o dos llamadas para establecer los valores clave, seguidas de una llamada del método Get de nivel inferior. A continuación, debe enviar varias llamadas para obtener las propiedades. Con el adaptador de BizTalk para PeopleSoft Enterprise, se proporciona un nuevo conjunto de métodos estándar (Get, Create, Find y Update), de modo que el cliente solo debe realizar una única llamada para obtener el mismo resultado. Para ello, se deja que el adaptador de BizTalk para PeopleSoft Enterprise realice varias llamadas de parte del cliente. Para obtener más información acerca de los métodos, vea [métodos de interfaz de componente de apéndice A:](../core/appendix-a-component-interface-methods.md).  
  
 Para crear un esquema para PeopleSoft, el adaptador de BizTalk para PeopleSoft Enterprise recupera las definiciones o metadatos de la interfaz del componente PeopleSoft.  
  
 El adaptador de BizTalk para PeopleSoft Enterprise se basa en interfaces de componente para la funcionalidad de envío y no requiere PeopleSoft Integration Broker. Las interfaces de componente se exponen como servicios Web, a los que se puede tener acceso desde BizTalk Server.  
  
### <a name="validation"></a>Validación  
 Cuando el adaptador de BizTalk para PeopleSoft Enterprise recibe un mensaje XML de BizTalk Server, se llevan a cabo dos niveles de validación:  
  
-   El mensaje XML debe ser válido con respecto a la especificación XML.  
  
-   El mensaje XML debe coincidir con lo que el servicio Web específico requiere (por ejemplo, coincidencia de interfaz como los tipos de datos).  
  
> [!NOTE]
>  No hay ninguna validación en relación con la lógica empresarial, que es el dominio de sistema PeopleSoft y es transparente para el adaptador de BizTalk para PeopleSoft Enterprise.  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   