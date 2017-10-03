---
title: Arquitectura de BizTalk Adapter para PeopleSoft Enterprise | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, XML messages
- architecture
- XML, messages
- XML, validating
ms.assetid: f246e974-a082-430c-ad15-23a5e597738b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 377e49af3a20302b92a4214959b534c9d0949a93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-peoplesoft-enterprise"></a>Arquitectura del adaptador de BizTalk para PeopleSoft Enterprise
Durante el funcionamiento básico del adaptador de Microsoft BizTalk para PeopleSoft Enterprise, el adaptador recibe un mensaje XML de BizTalk Server. Incluye el mensaje XML en un sobre SOAP. El adaptador de BizTalk para PeopleSoft Enterprise reenvía las solicitudes SOAP al servidor. El adaptador se comunica con el sistema PeopleSoft mediante las clases psjoa de PeopleSoft, que conectan a este sistema mediante el protocolo de transacción Jolt. El sistema PeopleSoft recibe la solicitud y ejecuta la lógica empresarial. La respuesta se devuelve a través de un proceso similar.  
  
 ![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")  
Arquitectura del adaptador  
  
## <a name="peoplesoft-component-interface-methods"></a>Métodos de interfaces de componentes de PeopleSoft  
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
 [Planeamiento y arquitectura](../core/planning-and-architecture13.md)