---
title: Cómo configurar el componente de canalización de resolución de entidades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authenticating, Partner Management
- Party Resolution [pipeline component], configuring
- Partner Management, authenticating
- pipeline components, Party Resolution
ms.assetid: 0ebd30f7-3a6b-4457-8e30-80bf81fbd28d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0c78792cd7c61ed1297954625fbd7da5aedfa04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248220"
---
# <a name="how-to-configure-the-party-resolution-pipeline-component"></a>Cómo configurar el componente de canalización Resolución de entidades
El componente de canalización de resolución de entidades se utiliza para asignar el Id. de seguridad de usuario y el sujeto del certificado para el cliente a una entidad de BizTalk Server. La asignación se utiliza para forzar la autenticación de las entidades que envían mensajes a BizTalk Server. Para obtener más información acerca de la administración de socios comerciales, vea[cómo crear un acuerdo](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).  
  
> [!NOTE]
>  Para permitir que el componente de canalización de resolución de entidades valide a un usuario de Windows, se debe agregar el alias WindowsUser a una entidad. Para obtener más información, consulte [componente de canalización de resolución de entidad](../core/party-resolution-pipeline-component.md).  
  
### <a name="to-configure-the-properties-for-the-party-resolution-pipeline-component"></a>Para configurar las propiedades del componente de canalización de resolución de entidades  
  
1.  Arrastre el componente de canalización de resolución de entidades hasta la fase ResolveParty de una canalización de recepción.  
  
2.  En la ventana Propiedades, en la **propiedades de componente de canalización** sección, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Resolver entidad mediante certificado**|Establecido en **True** si desea habilitar la resolución de entidades en función de la huella digital del certificado de firma de la entidad desde la cual se reciben los mensajes.<br /><br /> Valor predeterminado: **True**|  
    |**Resolver entidad mediante SID**|Establecido en **True** si desea habilitar la resolución de entidades basada en el identificador de seguridad (SID) de la cuenta del remitente.<br /><br /> Si ambas propiedades se establecen en **True**, **resolver entidad mediante certificado** propiedad tiene prioridad sobre la **resolver entidad mediante SID** propiedad, lo que significa que si el certificado como el SID están disponibles, se utiliza el sujeto del certificado. Si no se puede resolver la entidad utilizando el sujeto del certificado, el componente no regresa a la **resolver entidad mediante SID** propiedad y el valor predeterminado (s-1-5-7) se marca para **BTS. Sourcepartyid esta**.<br /><br /> Valor predeterminado: **True**|  
  
> [!NOTE]
>  Si usa el adaptador de BizTalk para Message Queue y desea resolver la entidad basan en nombre de usuario, establezca **resolver entidad mediante certificado** a **False** y **resolver entidad mediante SID** a **True**.  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de resolución de entidades](../core/party-resolution-pipeline-component.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [Resolución de entidades personalizadas (ejemplo de BizTalk Server)](../core/custom-party-resolution-biztalk-server-sample.md)