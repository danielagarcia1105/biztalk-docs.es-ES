---
title: Cómo actualizar una canalización mediante el control de versiones en paralelo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd884a76-71dd-4c90-b4ba-f1cd7f48eb04
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bf978b64876a91d06acfbe4c5d34278935cfa55
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970893"
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a>Cómo actualizar una canalización mediante el control de versiones en paralelo
Es una manera sencilla de usar una nueva canalización agregada por el control de versiones en paralelo seleccionar la versión de canalización recién implementado en el puerto de envío o ubicación de recepción. Esto reemplazará la canalización antigua con uno nuevo. Sin embargo, si necesita verdadera funcionalidad en paralelo para la compatibilidad con versiones anteriores, a continuación, debe crear nuevos puertos de envío y ubicaciones de recepción y enlazarlos a la nueva versión de canalización especificada.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a>Para agregar una nueva versión de un componente de canalización  
  
1. En Visual Studio, cree una nueva versión del componente de canalización y firmar el ensamblado.  
  
2. Agregar el componente de canalización en el **componentes de canalización** carpeta (\<*carpeta de instalación*\>\Pipeline Components).  
  
3. Agregue el componente de canalización a la canalización.  
  
4. Después de crear la canalización o implementar la solución, quite el componente de canalización desde el **componentes de canalización** carpeta.  
  
5. Agregue el componente de canalización a la caché de ensamblados global (GAC).  
  
   Después de haber completado estos pasos, hará referencia al ensamblado de canalización compilado a la versión correcta del componente de canalización y el dominio de aplicación que utiliza BizTalk Server encontrará la nueva versión del componente de canalización en la GAC, en lugar de Buscar anterior versión del componente de canalización en la carpeta de componentes de canalización.  
  
## <a name="see-also"></a>Vea también  
 [Actualización mediante el control de versiones en paralelo](../technical-guides/updating-using-side-by-side-versioning.md)