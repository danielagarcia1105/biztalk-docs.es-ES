---
title: Cómo asignar Values2 de propiedad de contexto de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137f82ab-f301-465d-be78-a6e67971dd3b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afb08895ba841ce2e99399ea9590b05394102472
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006389"
---
# <a name="how-to-assign-message-context-property-values"></a>Cómo asignar valores de propiedad de contexto de mensaje
Para administrar la sesión de conexión de J.D. Edwards OneWorld a partir de una orquestación de BizTalk, debe agregar la referencia a Microsoft.BizTalk.Adapters.JDEProperties.dll al proyecto. Este ensamblado se encuentra en %SystemDrive%\Archivos de programa\Archivos comunes\Microsoft BizTalk Adapters for Enterprise Applications\bin.  
  
 Tras hacer referencia a este esquema de propiedad, otras propiedades de contexto son accesibles para varias herramientas de desarrollo de BizTalk, por ejemplo, la forma Asignación de mensajes en el Diseñador de orquestaciones.  
  
 Para obtener acceso a una propiedad de contexto, especifique una de las disponibles en el espacio de nombres de J.D. Edwards OneWorld. Para leer una propiedad de contexto de un mensaje recibido desde un puerto enlazado con el adaptador de Microsoft BizTalk para JD Edwards OneWorld, use la sintaxis, el mensaje (JDE. Propiedad), en una expresión. Para obtener una lista de propiedades, consulte Administración de sesiones de JD Edwards OneWorld.  
  
 En BizTalk, los mensajes son inmutables.  
  
### <a name="to-assign-a-message-context-property-value"></a>Procedimiento para asignar un valor de propiedad de contexto  
  
1. Crear un nuevo mensaje.  
  
2. Establecer el contenido del mensaje, por ejemplo mediante la asignación de un mensaje existente.  
  
3. Establecer las propiedades.  
  
   Para asignar propiedades de contexto a un mensaje destinado a un puerto de envío enlazado con el adaptador de Microsoft BizTalk para J.D. Edwards OneWorld, use el operador de asignación de mensajes. Después, especifique una de las propiedades de contexto disponibles en el espacio de nombres de J.D. Edwards OneWorld.  
  
   La sintaxis es: `Message(JDE.Property) = value;`  
  
## <a name="see-also"></a>Vea también  
 [Uso de propiedades de contexto de mensaje](../core/using-message-context-properties2.md)   
 [Administración de sesiones](../core/about-session-management1.md)   
 [Tutorial: Uso del adaptador de BizTalk para JD Edwards OneWorld](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)