---
title: Cómo asignar Values1 de propiedad de contexto de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e76c62-3110-482c-8083-84d411e6f475
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f9f5a42e208d81f8898ce85592402f675d1b361
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979745"
---
# <a name="how-to-assign-message-context-property-values"></a>Cómo asignar valores de propiedad de contexto de mensaje
Para administrar la sesión de conexión del adaptador de J.D. Edwards EnterpriseOne a partir de una orquestación de BizTalk, debe agregar la referencia a Microsoft.BizTalk.Adapters.JDEProperties.dll al proyecto. Este ensamblado se encuentra en %SystemDrive%\Archivos de programa\Archivos comunes\Microsoft BizTalk Adapters for Enterprise Applications\bin.  
  
 Tras hacer referencia a este esquema de propiedad, otras propiedades de contexto son accesibles para varias herramientas de desarrollo de BizTalk, por ejemplo, la forma Asignación de mensajes en el Diseñador de orquestaciones.  
  
 Para obtener acceso a una propiedad de contexto, especifique una de las disponibles en el espacio de nombres de J.D. Edwards EnterpriseOne. Para leer la propiedad de contexto de un mensaje recibido de un puerto enlazado con el adaptador de Microsoft BizTalk para J.D. Edwards EnterpriseOne, use la sintaxis Message(JDE.Property) en una expresión. Vea la administración de sesiones en el adaptador de J.D. Edwards EnterpriseOne para obtener una lista de propiedades.  
  
 En BizTalk, los mensajes son inmutables.  
  
### <a name="to-assign-context-property-value"></a>Para asignar valores de propiedad de contexto  
  
1. Crear un nuevo mensaje.  
  
2. Establecer el contenido del mensaje, por ejemplo mediante la asignación de un mensaje existente.  
  
3. Establecer las propiedades.  
  
   Para asignar propiedades de contexto a un mensaje destinado a un puerto de envío enlazado con el adaptador de Microsoft BizTalk para J.D. Edwards EnterpriseOne, use el operador de asignación de mensajes. Después, especifique una de las propiedades de contexto disponibles en el espacio de nombres de J.D. Edwards EnterpriseOne.  
  
   La sintaxis es: `Message(JDE.Property) = value;`  
  
## <a name="see-also"></a>Vea también  
 [Uso de propiedades de contexto de mensaje](../core/using-message-context-properties1.md)   
 [Administración de sesiones](../core/about-session-management2.md)   
 [Tutorial: Uso del adaptador de BizTalk para JD Edwards EnterpriseOne](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone.md)