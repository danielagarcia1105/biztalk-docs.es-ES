---
title: "Componente de canalización de resolución de entidad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ad728ff-4d7c-4ab3-af0e-76006576dce5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6649016dbfc225c4c2f557c73ff37dfc010a1588
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="party-resolution-pipeline-component"></a>Componente de canalización de resolución de entidades

## <a name="overview"></a>Información general
La misión del componente de canalización de resolución de entidades es asignar el certificado de remitente o el identificador de seguridad de remitente (SSID) a la correspondiente entidad de BizTalk server configurada.  
  
 Cuando el componente de resolución de entidades lee el mensaje entrante, que acepta dos propiedades de contexto de mensaje como entrada: **WindowsUser** y **SignatureCertificate**. El **WindowsUser** propiedad se rellena por el adaptador, o por un componente de canalización personalizado, con el nombre de usuario del remitente cuando forma confiable puede derivar la información del remitente. El **SignatureCertificate** está formado por el adaptador o el componente de canalización de descodificador de MIME/SMIME con la huella digital del certificado de autenticación del cliente.  
  
 Si el mensaje está firmado, la huella digital del certificado utilizado para validar la firma del mensaje entrante se utiliza entonces para mirar en el Repositorio de configuración con objeto de determinar qué entidad lleva asociada. Si se encuentra una entidad, el SourcePartyID de esta entidad se coloca en el contexto del mensaje como originador del mensaje.   
  
 Para permitir que el componente de canalización de resolución de entidades valide a un usuario de Windows, se debe agregar el alias "WindowsUser" a una entidad. Escriba "WindowsUser" en los campos nombre y calificador y establezca el valor en un nombre de usuario en formato de \<ombre de usuario > (por ejemplo, undominio\unusuario). En un escenario independiente, el valor WindowsUser utilizado para configurar la entidad debe coincidir con el valor establecido por el adaptador de recepción.  
  
 Si el mensaje llega al componente de resolución de entidades con dos de las propiedades de marcado, el componente de resolución de entidades en primer lugar intenta resolver la entidad mediante el certificado (suponiendo que el **resolver entidad mediante certificado** propiedad es establecido en **True**). Si se resuelve la entidad, el sourcepartyid de esta para esa entidad se coloca en el contexto del mensaje como el OriginatorPID del mensaje si el proceso de host que ejecuta la canalización está marcado como **autenticación de confianza** por la canalización. Si no se puede completar la resolución de la entidad mediante el certificado, el valor OriginatorPID del mensaje se marca con "s-1-5-7", que es el SID de un usuario anónimo. Para obtener más información acerca de la propiedad OriginatorPID, consulte [cómo proteger canalizaciones](../core/how-to-secure-pipelines.md).  

## <a name="resolve-the-party"></a>Resolver la entidad  
 En la siguiente tabla se muestra cómo la entidad intenta resolver el componente Resolución de entidades.  
  
|Mediante SID|Mediante certificado|WindowsUser|SignatureCertificate|Resultado|  
|------------|--------------------|-----------------|--------------------------|------------|  
|True|False|Disponible|Disponible o no disponible|Se resuelve la entidad.|  
|True|False|No disponible|Disponible o no disponible|No se resuelve la entidad y se marca como anónimo.|  
|False|True|Disponible o no disponible|Disponible o no disponible|No se resuelve la entidad y se marca como anónimo.|  
|True|True|Disponible|Disponible|Se resuelve la entidad.|  
|True|True|No disponible|Disponible o no disponible|No se resuelve la entidad y se marca como anónimo.|  
|False|False|Disponible o no disponible|Disponible o no disponible|No se resuelve la entidad y se marca como anónimo.|  
  
 Para obtener información acerca de cómo configurar el componente de canalización de resolución de entidades, vea [cómo configurar el componente de canalización de resolución de entidad](../core/how-to-configure-the-party-resolution-pipeline-component.md).  
  
## <a name="see-also"></a>Vea también  
-  **Propiedades de contexto del mensaje**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
-  [Componentes de canalización](../core/pipeline-components.md)   
-  [Resolución de entidades personalizadas (ejemplo de BizTalk Server)](../core/custom-party-resolution-biztalk-server-sample.md)   
-  [Autenticación de mensajes entre procesos](../core/authentication-of-messages-between-processes.md)