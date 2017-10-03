---
title: "Creación de esquemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20b88194-b400-4ebc-8882-d493fbf30e0f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac019276923467fe2d95f5a0a0b4a7b53513e9c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-schemas"></a>Creación de esquemas
Puede usar el Editor de BizTalk para crear dos tipos de esquemas: esquemas y esquemas de propiedades de mensaje.  
  
> [!NOTE]
>  Hay varios tipos de esquemas de mensaje, como esquemas de mensaje XML, esquema de mensaje de archivo sin formato y esquemas de sobres.  
  
 Los esquemas de mensaje definen la estructura y restringen el contenido de los mensajes que tiene previsto intercambiar con los socios comerciales o las aplicaciones. Esquemas de mensaje son los tipos más comunes de esquemas que se va a usar con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]puede crear esquemas de mensaje XML para los documentos empresariales y los sobres utilizados para contenerlos, y mediante el uso de la extensión de archivo sin formato en el Editor de BizTalk, se pueden crear esquemas de mensaje de archivo sin formato, incluyendo los esquemas para encabezados, cuerpos y finalizadores.  
  
 Los esquemas de propiedades son un tipo especial de esquema. Proporcionan una plantilla de validación para los datos de campos y registros que se promocionan desde un mensaje de instancia en lo que se conoce como el contexto del mensaje. La finalidad de los esquemas de propiedades es ofrecer una definición formal y segura de los tipos de datos que se van a promocionar en tiempo de ejecución.  
  
 Promoción de propiedades ofrece un mecanismo centralizado de extraer bloques principales de información, definidos por el usuario, desde dentro de un mensaje de instancia y hacerla más fácilmente accesible a los componentes de BizTalk Server manipulan el mensaje a medida que pasa a través de BizTalk Servidor. Un uso habitual de las propiedades promocionadas es hacer corresponder una instancia de mensaje con una suscripción, lo que permite enrutar adecuadamente el mensaje para procesarlo.  
  
 En esta sección se describen los modos que puede utilizar para crear distintos tipos de esquemas en BizTalk Server y se explican cuestiones relacionadas con varios tipos de esquemas.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Administrar esquemas en proyectos](../core/managing-schemas-within-projects.md)  
  
-   [Administrar los nodos de un esquema](../core/managing-the-nodes-within-a-schema.md)  
  
-   [Promoción de propiedades](../core/promoting-properties.md)