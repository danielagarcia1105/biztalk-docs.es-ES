---
title: Cómo proteger canalizaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3a717f-acf8-4f08-a6fb-6d1d48b5b80a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 903e9faec81ce58aac243fb7a22bac6678a81a42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255188"
---
# <a name="how-to-secure-pipelines"></a>Cómo proteger las canalizaciones

## <a name="authentication-trusted"></a>Autenticación de confianza
Los hosts se pueden marcar en la consola de administración como **autenticación de confianza**. Un host con Autenticación de confianza supone que Microsoft BizTalk Server confiará en las propiedades de seguridad enviadas en el contexto del mensaje de un mensaje de este host. Las propiedades relacionadas con la seguridad en el contexto del mensaje son los **OriginatorPID**, que corresponde a la propiedad de contexto de mensaje BTS. Sourcepartyid de esta y el **OriginatorSID**, que corresponde a la propiedad de contexto de mensaje **BTS. WindowsUser**. Para obtener más información, consulte **propiedades de contexto de mensaje** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
 Un host que está marcado como **autenticación de confianza** tiene permiso para indicar que el host de confianza está agregando un mensaje a la cola de alguien que no es él como remitente del mensaje. En otras palabras, los hosts que no están marcados como **autenticación de confianza** no tiene permiso para agregar un mensaje a la cola de un remitente del mensaje que ellos mismos.  
  
> [!IMPORTANT]
>  El componente de canalización de descodificador de MIME/SMIME no comprueba la fecha de caducidad de los certificados de descifrado. Sin embargo, sí comprueba la fecha de caducidad de los certificados de firma.  
  
 Para obtener información acerca de la codificación y descodificación de mensajes enviados a través de SMTP o HTTP, vea [componente de canalización de codificador de MIME-SMIME](../core/mime-smime-encoder-pipeline-component.md). Consulte también [componente de canalización de descodificador de MIME-SMIME](../core/mime-smime-decoder-pipeline-component.md).  
  
 Para obtener información acerca de la comprobación de firma cuando se trabaja con terceros, vea [componente de canalización de resolución de entidad](../core/party-resolution-pipeline-component.md). Consulte también [cómo crear un acuerdo](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).  
  
## <a name="see-also"></a>Vea también  
 [Crear canalizaciones mediante el Diseñador de canalizaciones](../core/creating-pipelines-using-pipeline-designer.md)   
 [Desarrollar componentes de canalización personalizado](../core/developing-custom-pipeline-components.md)