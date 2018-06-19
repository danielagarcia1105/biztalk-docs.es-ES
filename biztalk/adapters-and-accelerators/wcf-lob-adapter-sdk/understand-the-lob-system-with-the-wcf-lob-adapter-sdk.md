---
title: Comprender el sistema LOB con el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0f97846-5ef2-4530-853a-fba5469156f7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d777022312c8511608519d155626c948da3efdb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225804"
---
# <a name="understand-the-lob-system-with-the-wcf-lob-adapter-sdk"></a>Comprender el sistema LOB con el SDK de adaptador LOB de WCF
Antes de desarrollar el adaptador mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], debe tener una descripción completa del sistema de línea de negocio de destino. Si no conoces la funcionalidad proporcionada por el sistema de línea de negocio, cómo se expone y el otro nivel de compatibilidad que proporcionan seguridad, transacciones y otras características, el adaptador no puede proporcionar las características requeridas por adaptador consumidores. Esta sección describen las áreas que debe comprender para diseñar el adaptador de forma eficaz.  
  
## <a name="the-path-to-understanding"></a>Para familiarizarse con la ruta de acceso  
 El propósito de un adaptador es exponer los datos y las operaciones de un sistema de línea de negocio de una manera coherente y accesible según las reglas impuestas por la especificación de adaptador o la API de adaptador. Para saber qué operaciones y los datos que se va a exponer, debe entender lo que hace el sistema y cómo expone sus datos y las operaciones. En concreto, debe pensar en los siguientes problemas de diseño:  
  
-   **Ciclo de vida de la conexión.** ¿Cómo se abren y se cierran de conexiones? ¿Cómo son las conexiones abiertas mantenidas? ¿Existen requisitos especiales para reutilizar una conexión? Para obtener más información acerca de las conexiones, consulte `Microsoft.ServiceModel.Channels.Common.IConnection`.  
  
-   **Los metadatos de operación y el tipo expuestos por el sistema.** ¿El sistema de línea de negocio permite búsqueda de operación y examinar y un acceso sencillo a los metadatos, o debe desarrollar código de soporte técnico para proporcionar esta funcionalidad? Por ejemplo, en SQL Server, las operaciones son objetos de procedimientos almacenados como. Tipo de metadatos acerca de las columnas, tablas y otros objetos son fáciles de recuperar. Sistemas heredados de línea de negocio pueden ser más difíciles trabajar con.  
  
-   **Cómo se exponen las operaciones y los datos por el sistema.** ¿Cómo se expone la API? ¿La compatibilidad con la API de bloqueo (sincrónico) y sin bloqueo llamadas (asincrónicas)? ¿Se admiten las devoluciones de llamada? ¿Conectará en el nivel de API o protocolo?  
  
-   **Compatibilidad con seguridad, transacciones y la mensajería de confianza.** Si la API es compatible con cualquiera de estas características, es posible que desee exponer en el consumidor de adaptador. Por ejemplo, SQL Server tiene seguridad y transacciones admiten aunque la mensajería de confianza no es práctico incluir (sería con MSMQ o algún otro sistema de puesta en cola).  
  
-   **¿Qué escenarios de uso y funcionalidad están importantes?** No limitar su comprensión para puramente técnicas; se tratan y capturar los requisitos empresariales con los usuarios con experiencia. ¿Existen restricciones únicas impuestas en algunas operaciones? ¿Son existen operaciones que todavía sean ilegibles útiles? ¿Algunas funciones rara vez se usa?  
  
 Para conocer esta información, debe consultar la documentación técnica y el usuario para el sistema de línea de negocio de destino. Si la documentación está ausente o dispersas, también puede obtener información sobre los aspectos técnicos del sistema, busque los foros de soporte técnico en línea, los grupos de noticias en línea, blogs, o mediante el examen de los archivos de instalación para obtener detalles de implementación. Si tiene acceso a la línea de negocio a los desarrolladores o los archivos de código, es posible que pueda detectar la información necesaria como semántica de conexión, compatibilidad con la seguridad y cómo se buscan e invocan las operaciones.  
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar el adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [Empezar a trabajar con el con el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md)   
 [Al seleccionar el marco de trabajo adecuado](https://msdn.microsoft.com/library/bb798089.aspx)