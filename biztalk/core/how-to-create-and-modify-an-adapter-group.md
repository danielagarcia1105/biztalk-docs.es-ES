---
title: "Cómo crear y modificar un grupo de adaptadores | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1eef051-2ed7-4e28-8cb9-0145d6c8ed76
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6865de8eb67d9fe1a6ca8d93b7d2e6527ae36364
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-and-modify-an-adapter-group"></a>Cómo crear y modificar un grupo de adaptadores
Una de las nuevas características del inicio de sesión único (SSO) es la capacidad para crear y modificar grupos de adaptadores. Como indica su nombre, un grupo de adaptadores es una colección de adaptadores. Puede utilizar grupos de adaptadores para organizar la configuración de seguridad y otras propiedades de los adaptadores.  
  
### <a name="to-create-and-modify-an-adapter-group"></a>Para crear y modificar un grupo de adaptadores  
  
1.  Cree el grupo de adaptadores con una llamada a la herramienta ssops.  
  
     En el archivo XML asociado, debe establecer la marca de grupo como un grupo de adaptadores.  
  
2.  Agregar uno o más adaptadores al grupo de adaptadores mediante `ISSOPSAdmin.AddAdapterToAdapterGroup`.  
  
     En este punto, el grupo de adaptadores está listo para trabajar como se desee. Si es necesario, puede ver la lista completa de los adaptadores asociados mediante `ISSOPSAdmin.GetAdaptersForAdapterGroup`.  
  
3.  Puede modificar la configuración de su grupo de adaptadores con `ISSOPSAdmin.SetAdapterProperties`.  
  
4.  Cuando haya terminado, puede quitar el adaptador de grupo de adaptadores con `ISSOPSAdmin.RemoveAdapterFromAdapterGroup`.  
  
5.  Por último, puede eliminar el grupo de adaptadores mediante `ISSOAdmin.DeleteApplication`.  
  
     Puede elegir en su lugar eliminar el grupo de adaptadores mediante el `-delete` comando de la herramienta ssops.  
  
## <a name="see-also"></a>Vea también  
 [Sincronización de contraseñas](../core/synchronizing-passwords.md)