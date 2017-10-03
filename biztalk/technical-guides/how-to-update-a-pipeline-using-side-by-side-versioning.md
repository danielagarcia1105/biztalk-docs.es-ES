---
title: "Cómo actualizar una canalización mediante el control de versiones en paralelo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd884a76-71dd-4c90-b4ba-f1cd7f48eb04
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c4e8803128f2232905229de3b5de49994e039ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a>Cómo actualizar una canalización mediante el control de versiones en paralelo
El método sencillo para usar una nueva canalización agregada por el control de versiones en paralelo consiste en seleccionar la versión de canalización recién implementado en el puerto de envío o ubicación de recepción. Esto reemplazará la canalización antigua con uno nuevo. Sin embargo, si necesita verdadera funcionalidad en paralelo para la compatibilidad con versiones anteriores, a continuación, debe crear nuevos puertos de envío y ubicaciones de recepción y enlazarlos a la nueva versión de canalización especificada.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a>Para agregar una nueva versión de un componente de canalización  
  
1.  En Visual Studio, cree una nueva versión del componente de canalización y firmar el ensamblado.  
  
2.  Agregue el componente de canalización en el **componentes de canalización** carpeta (\<*carpeta de instalación*> \Pipeline Components).  
  
3.  Agregue el componente de canalización a la canalización.  
  
4.  Después de compilar la canalización o implementar la solución, quite el componente de canalización de la **componentes de canalización** carpeta.  
  
5.  Agregue el componente de canalización a la caché de ensamblados global (GAC).  
  
 Después de haber completado estos pasos, el ensamblado de canalización compilado hará referencia a la versión correcta del componente de canalización y AppDomain utilizado por [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] encontrará la nueva versión del componente de canalización en la GAC, en lugar de Buscar anterior versión del componente de canalización en la carpeta de componentes de canalización.  
  
## <a name="see-also"></a>Vea también  
 [Actualizar utilizando el control de versiones en paralelo](../technical-guides/updating-using-side-by-side-versioning.md)