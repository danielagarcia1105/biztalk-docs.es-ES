---
title: Actualizar un artefacto | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40feab57-4286-4bdf-8f52-25d02b3fa60c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f32efa6195013d77ee368c0678a9ca67afb4e6e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980045"
---
# <a name="updating-an-artifact"></a>Actualizar un artefacto
Las dependencias entre artefactos en dos o más aplicaciones de BizTalk pueden tener un efecto significativo en la implementación de aplicaciones y el mantenimiento. Un artefacto es dependiente de otra cuando es necesario usar ese artefacto para funcionar correctamente, por ejemplo una orquestación que necesita usar una canalización específica para transmitir mensajes correctamente.  
  
 Para actualizar un artefacto en una aplicación, debe anular la implementación, junto con los artefactos que dependen de él. Cuando existen artefactos con dependencias en la misma aplicación, BizTalk Server controla de forma automática las tareas de anulación de la implementación y de nueva implementación para los artefactos actualizados y dependientes. Cuando los artefactos que tienen dependencias se encuentran en distintas aplicaciones, aunque este no sea el caso. Si desea actualizar un artefacto en una aplicación y un artefacto de otra aplicación tiene una dependencia en él, debe anular la implementación y volver a implementar el artefacto dependiente manualmente como sigue:  
  
1. Detenga, dé de baja y desenlace el artefacto dependiente.  
  
2. Actualice el artefacto del que depende.  
  
3. Enlace, dé de alta e iniciar el artefacto dependiente.  
  
   Para evitar la necesidad de realizar pasos manuales para actualizar un artefacto del que dependen otros artefactos, puede intentar mantener todos los artefactos con dependencias juntos en la misma aplicación. Esto no siempre es posible, sin embargo, porque la mayoría de los tipos de artefactos debe ser única en un grupo de BizTalk. No puede tener el mismo artefacto en dos aplicaciones distintas del mismo grupo, incluso cuando ambas aplicaciones contienen artefactos que dependen del mismo artefacto. Para obtener más información sobre el problema de artefactos únicos, vea [artefactos que deben ser únicos en una aplicación o grupo](http://go.microsoft.com/fwlink/?LinkId=155141) (<http://go.microsoft.com/fwlink/?LinkId=155141>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
   Puede agregar el artefacto necesario a una aplicación y, a continuación, agregue una referencia a esa aplicación desde otras aplicaciones que contienen artefactos que dependen de él. Si se agrega una referencia a una aplicación, los artefactos de la aplicación pueden usar los artefactos de la aplicación a la que hace referencia. Para obtener instrucciones sobre cómo agregar una referencia, consulte [cómo agregar una referencia a otra aplicación](http://go.microsoft.com/fwlink/?LinkID=155011) (<http://go.microsoft.com/fwlink/?LinkID=155011>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
   Para una lista de comprobación de tareas para actualizar artefactos en una aplicación de BizTalk, consulte [lista de comprobación: actualizar los artefactos de una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkId=155647) (<http://go.microsoft.com/fwlink/?LinkId=155647>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
## <a name="see-also"></a>Vea también  
 [Actualización de aplicaciones y artefactos](../technical-guides/updating-applications-and-artifacts.md)