---
title: Configurar propiedades de canalización de AS2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edir2.AS2.pipeline.properties
ms.assetid: 7faf6b05-710a-4d00-8c77-590ce9d9f962
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e41afd99e7af1441e2d3d8cc936c04cd9321779
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233324"
---
# <a name="configuring-as2-pipeline-properties"></a>Configurar propiedades de canalización de AS2
Las propiedades de canalización se usan en el proceso de mensajes AS2 entrantes y salientes cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha podido determinar el acuerdo que resuelve el intercambio de envío o recepción.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="as2-pipeline-properties"></a>Propiedades de canalización AS2  
 Se puede establecer la siguiente propiedad en las canalizaciones AS2:  
  
|Propiedad|Utilice|Valores|Canalización/Fase|  
|--------------|---------|------------|---------------------|  
|ContentTransferEncoding|Indica el método que se usará para representar los datos binarios en formato de texto ASCII.|8 bits (predeterminado)<br /><br /> 7 bits<br /><br /> 8 bits|AS2EdiSend/Encode<br /><br /> AS2Send/Encode|  
  
### <a name="to-set-a-pipeline-property"></a>Para establecer una propiedad de canalización  
  
1.  En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], haga clic con el botón secundario en la ubicación de recepción o puerto de envío mediante la canalización para la que desee establecer las propiedades. Haga clic en **Propiedades**.  
  
2.  Haga clic en el botón de elipsis (…) junto a la canalización para la que desee establecer las propiedades.  
  
3.  Escriba el valor de la propiedad y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md)